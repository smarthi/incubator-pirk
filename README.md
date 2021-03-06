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

<img alt="Apache Pirk" class="img-responsive" src="contrib/ApachePirk.png" width="350"/>
--

--

[![Build Status](https://api.travis-ci.org/apache/incubator-pirk.svg?branch=master)](https://travis-ci.org/apache/incubator-pirk?branch=master)
[![Coverage Status](https://coveralls.io/repos/github/apache/incubator-pirk/badge.svg?branch=master)](https://coveralls.io/github/apache/incubator-pirk?branch=master)
[![Documentation Status](https://img.shields.io/:docs-latest-green.svg)](http://pirk.incubator.apache.org/for_users)
[![GitHub license](https://img.shields.io/badge/license-Apache%202-blue.svg)](https://raw.githubusercontent.com/apache/incubator-pirk/master/LICENSE)
[![Twitter Follow](https://img.shields.io/twitter/follow/ApachePirk.svg?style=social)](https://twitter.com/ApachePirk)

[Apache Pirk (incubating)](http://pirk.incubator.apache.org/) is a framework for scalable Private Information Retrieval (PIR). The goal of Pirk is to provide a landing place for robust, scalable, and practical implementations of PIR algorithms.

## Documentation

Please see the [Apache Pirk](http://pirk.incubator.apache.org/) website for documentation.    

## Getting Started

Pirk is written in Java and currently uses a Maven build system with a single level pom.xml. As such, Pirk may be built via ‘mvn package’.

For convenience, the following POM files are included:

* pom.xml — Pirk pom file for Hadoop/YARN, Storm and Spark platforms
* pom-with-benchmarks.xml — Pirk pom file for running Paillier benchmarking testing

Pirk may be built with a specific pom file via ‘mvn package -f ’

Dependencies can be found in the pom.xml file and include [Apache Hadoop](http://hadoop.apache.org/), [Apache Spark](http://spark.apache.org/), [Apache Storm](http://storm.apache.org) and [Elasticsearch](https://github.com/elastic/elasticsearch). Currently, Pirk may be utilized in a distributed Hadoop/MapReduce, Storm or Spark framework as well as in standalone mode.

If you are a User, please check out the [For Users](http://pirk.incubator.apache.org/for_users) section of the Pirk website.

If you are a Developer, please check out the [For Developers](http://pirk.incubator.apache.org/for_developers) section of the Pirk website.

## Pirk Basics 

[Private Information Retrieval](https://en.wikipedia.org/wiki/Private_information_retrieval) (PIR) enables a user/entity to privately and securely obtain information from a dataset, to which they have been granted access, without revealing, to the dataset owner or to an observer, any information regarding the questions asked or the results obtained. Employing homomorphic encryption techniques, PIR enables datasets to remain resident in their native locations while giving the ability to query the datasets with sensitive terms.

There are two parties in a PIR transaction - the Querier, the party asking encrypted questions, and the Responder, the party holding the target data and answering encrypted questions (performing encrypted queries).  

Pirk is centered around the [Querier](http://pirk.incubator.apache.org/for_users#querier) and the [Responder](http://pirk.incubator.apache.org/for_users#responder).

In Pirk, the Querier is responsible for the following:

* Generating the encrypted query vectors (representing encrypted questions)
* Generating the necessary decryption items for each query vector
* Decrypting encrypted query results obtained from the Responder

Once the Querier generates an encrypted query, it must be sent to the Responder. 

In Pirk, the Responder is responsible for the following:

* Performing encrypted queries over their target datasets (using encrypted query vectors)
* Forming the encrypted query results 

The encrypted query results must be sent from the Responder back to the Querier for decryption.

Pirk employs generic [data and query schemas](http://pirk.incubator.apache.org/for_users#data-and-query-schemas), specified via XML files, that are shared between the Querier and Responder to enable flexible and varied data and query types.

## License 

	   Licensed under the Apache License, Version 2.0 (the "License");
	   you may not use this file except in compliance with the License.
	   You may obtain a copy of the License at
   
	    (http://www.apache.org/licenses/LICENSE-2.0)
	    
	    Unless required by applicable law or agreed to in writing, software
	    distributed under the License is distributed on an "AS IS" BASIS,
	    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
	    See the License for the specific language governing permissions and
	    limitations under the License. See accompanying LICENSE file.

## Export Control

This distribution includes cryptographic software. The country in which you 
currently reside may have restrictions on the import, possession, use, and/or
re-export to another country, of encryption software. BEFORE using any 
encryption software, please check your country's laws, regulations and 
policies concerning the import, possession, or use, and re-export of encryption
software, to see if this is permitted. See <http://www.wassenaar.org/> for more
information.

The U.S. Government Department of Commerce, Bureau of Industry and Security 
(BIS), has classified this software as Export Commodity Control Number (ECCN) 
5D002.C.1, which includes information security software using or performing 
cryptographic functions with asymmetric algorithms. The form and manner of this
Apache Software Foundation distribution makes it eligible for export under the 
License Exception ENC Technology Software Unrestricted (TSU) exception (see the
BIS Export Administration Regulations, Section 740.13) for both object code and
source code.

The following provides more details on the included cryptographic software: 

Apache Pirk implements cryptographic software and is designed for use with the
Java Cryptography Architecture (JCA).

See
http://www.oracle.com/us/products/export/eccn-matrix-345817.html

## Apache Software Foundation Incubation

Apache Pirk is an effort undergoing incubation at The Apache Software Foundation (ASF), sponsored by the name of Apache TLP sponsor. Incubation is required of all newly accepted projects until a further review indicates that the infrastructure, communications, and decision making process have stabilized in a manner consistent with other successful ASF projects. While incubation status is not necessarily a reflection of the completeness or stability of the code, it does indicate that the project has yet to be fully endorsed by the ASF.

