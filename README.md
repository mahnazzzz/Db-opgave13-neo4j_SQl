# Db-opgave13-neo4j_SQl


you can find the assignment [her](https://github.com/datsoftlyngby/soft2019spring-databases/blob/master/assignments/assignment13.md)

## Loading data into th Neo4j 
. docker run \ -d --name neo4j \ --rm \ --publish=7474:7474 \ --publish=7687:7687 \ --env NEO4J_AUTH=neo4j/123 \ neo4j
. docker cp social_network_nodes.csv neo4j:/var/lib/neo4j/import.
. docker cp social_network_edges.csv neo4j:/var/lib/neo4j/import.
. using periodic commit load csv from 'file:///social_network_nodes.csv' as userInfo create (:User { id: line[0], name: line[1], job: line[2], birthday:line[3]})

## loading data into the sql 
 
 Create table User_information ( node_id int, name varchar(100), job varchar(100), birthday varchar(100) );



. mysql -u root -p --local-infile socialNetwork
. load data local infile '/social_network_nodes.csv' INTO TABLE social_network_nodes fields terminated by',' ENCLOSED BY '"' lines terminated by '\n' ignore  1 rows;
. 





