# Frac-seq-in-BECs-Code

# When employing SAS to perform differential expression:

ods output lsmeans=ftot_lsmean_status;
ods output modelanova=ftot_model_status;
 
proc glm data=finaltotal order=internal outstat=ftot_glm_results  ;
               class  status ;
               model pct = status / ss3 ;
              
               lsmeans status  / out=ftot_pct_means;
               by transcript;
run; quit;
 
ods output close;
