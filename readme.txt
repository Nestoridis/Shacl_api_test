cd shacl-1.3.2/bin/

bash shaclinfer.sh -datafile simple-rule.shapes.ttl

# output #
@prefix rdf:   <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix owl:   <http://www.w3.org/2002/07/owl#> .
@prefix xsd:   <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> 
# end of output #


cd apache-jena-4.1.0/bin/
bash infer --rdfs=../../simple-rule.shapes.ttl ../../simple-rule.shapes.ttl > ../../simple-rule.shapes_infer.ttl
#it will create a new file : simple-rule.shapes_infer.ttl in 

cd ../../
bash shaclinfer.sh -datafile simple-rule.shapes_infer.ttl

# output #
@prefix rdf:   <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix owl:   <http://www.w3.org/2002/07/owl#> .
@prefix xsd:   <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs:  <http://www.w3.org/2000/01/rdf-schema#> .

<http://intelligence.csd.auth.gr/simple-rule#george>
        <http://intelligence.csd.auth.gr/simple-rule#knows>
                <http://intelligence.csd.auth.gr/simple-rule#nick> .
# end of output#
