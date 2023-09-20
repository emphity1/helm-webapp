# Testing with helm previuosly made webapp
<ol>
  <li>I will use <ul>
      <li>Self made helm chart for webapp(springboot)</li>
      <li>Chart for elastic</li>
      <li>Chart for RabbitMQ</li>

  </ul></li>














  1. Watch all cluster members come up.
  $ kubectl get pods --namespace=default -l app=elasticsearch-master -w
2. Retrieve elastic user's password.
  $ kubectl get secrets --namespace=default elasticsearch-master-credentials -ojsonpath='{.data.password}' | base64 -d
3. Test cluster health using Helm test.
  $ helm --namespace=default test elasticsearch
