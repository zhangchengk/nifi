<!--
  Licensed to the Apache Software Foundation (ASF) under one or more
  contributor license agreements.  See the NOTICE file distributed with
  this work for additional information regarding copyright ownership.
  The ASF licenses this file to You under the Apache License, Version 2.0
  (the "License"); you may not use this file except in compliance with
  the License.  You may obtain a copy of the License at
      http://www.apache.org/licenses/LICENSE-2.0
  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
-->
# Apache NiFi MiNiFi Command and Control (C2) Server

## How to execute minifi-c2-integration-tests

### Build required modules
mvn -pl minifi/minifi-assembly -am install -T1C -DskipTests
mvn -pl minifi/minifi-docker -am install -T1C -DskipTests -P docker
mvn -pl minifi/minifi-c2/minifi-c2-assembly -am install -T1C -DskipTests
mvn -pl minifi/minifi-c2/minifi-c2-docker -am install -T1C -DskipTests -P docker
mvn -pl nifi-toolkit/nifi-toolkit-assembly -am install -T1C -DskipTests

### Execute integration tests
mvn verify -Pdocker -f minifi/minifi-c2/minifi-c2-integration-tests/pom.xml