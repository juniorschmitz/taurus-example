sudo usermod -aG docker jenkins


docker container run -u root --name jenkins-blueocean --rm --detach ^
  --network jenkins --env DOCKER_HOST=tcp://docker:2376 ^
  --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1 ^
  --volume jenkins-data:/var/jenkins_home ^
  --volume jenkins-docker-certs:/certs/client:ro ^
  --publish 8080:8080 --publish 50000:50000 jenkinsci/blueocean


docker run --rm -v /var/jenkins_home/workspace/TestTaurus:/bzt-configs -v /var/jenkins_home/workspace/TestTaurus/reports:/tmp/artifacts blazemeter/taurus example.yml


reporting:
- module: final-stats
  summary: true
  percentiles: true
  summary-labels: false
  failed-labels: false
  test-duration: true
  dump-xml: report.xml
  dump-csv: report.csv