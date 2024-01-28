```op.yml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  name: node-exporter
  namespace: default
  labels:
    app: exporter
    role: monitoring
spec:
  selector:
    matchLabels:
      app: exporter
      role: monitoring
  template:
    metadata:
      labels:
        app: exporter
        role: monitoring
    spec:
      tolerations:
      - key: "node.kubernetes.io/unschedulable"
        operator: "Exists"
        effect: "NoSchedule"
      containers:
      - name: node-exporter
        image: alpine:latest
        ports:
        - containerPort: 3000
        env:
        - name: MY_INT_VARIABLE
          value: "5"
        - name: MY_STRING_VARIABLE
          value: "Hello"
        - name: MY_BOOLEAN_VARIABLE
          value: "true"
        resources:
          requests:
            cpu: 100m
            memory: 100Mi
          limits:
            cpu: 200m
            memory: 120Mi
        livenessProbe:
          httpGet:
            path: /api/healthy
            port: 3000
          initialDelaySeconds: 10
          timeoutSeconds: 5
          periodSeconds: 15
          failureThreshold: 6
        readinessProbe:
          httpGet:
            path: /api/ready
            port: 3000
          initialDelaySeconds: 20
          timeoutSeconds: 15
          periodSeconds: 30
          failureThreshold: 3
  revisionHistoryLimit: 2

```

```requirements 
create a DaemonSet manifest which should be deployed to every node in a cluster pods deployed as content if this deamonset are meant to collect data from the nodes and should be deployed to a node even when it tainted with noschedule taint deamonset(ds) 
requirements 
1. 'app/v1' as ds apiVersion 
2. ds name 'node-exporter' 
3. ds namespace as default 'kubectl apply -f daemonset.yaml' 
4. ds revision history limit should be set to 2 
5. ds should tolerate 'NoSchedule' taint 
6. ds should have 2 labels and matching labels assigned 'app=exporter' and 'role=monitoring' 
7. ds should define 1 container with properties 
7a container name 'node-exporter' 
7b container image 'alpine:latest' 
7c expose port '3000' 
7d container 2 labels assigned 'app=exporter' and 'role=monitoring' 
7e container should have liveness and readiness probes: 
7e1 liveness probe -> (exec http get path '/api/healthy' on the port exposed by container with an initial delay '10sec' timeout '5sec' assigned to probe , should occure in every '15 sec' and it should fail after '6' tries 
7e2 readiness probe > (exec http get path '/api/ready' on the port exposed by container with an initial delay '20sec' timeout '15sec' assigned to probe , should occure in every '30 sec' and it should fail after '3' tries 
7f container should request 100m CPU and 100 Mi of memory with limit 200m CPU and 120 Mi of memory 
7g container shoulf gave the following envt variable defined (in this exact order)- 
7g1 MY_INT_VARIABLE: 5 
7g2 MY_STRING_VARIABLE: Hello 
7g3 MY_BOOLEAN_VARIABLE: true 
```