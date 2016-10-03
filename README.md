# haproxyconfigatron
HAProxy configuration using DNS to store cluster information (SRV/TXT records)  

Requires: Net::DNS

Reads the TXT record for haproxy-cfg.haproxy-cfg.$svcroot to get all  
tuples it needs to write an haproxy.cfg file to a webroot  
where other servers can consume it via a publish/subscribe model  
Services for configuration are also stored $servicename.$servicename.$svcroot  
as SRV records. The weight of the SRV will be used to determine maxconns  
for haproxy loadbalancing.  

