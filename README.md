# utl-ratio-of-integers-to-estimate-pi-ie_22-divided-by_7-optmization
Ratio of integers to estimate pi ie 22 divided by 7 optmization
    StackOverflow: Ratio of integers to estimate pi ie 22 divided by 7 optmization                                      
                                                                                                                        
    github                                                                                                              
    https://tinyurl.com/y364tz27                                                                                        
    https://github.com/rogerjdeangelis/utl-ratio-of-integers-to-estimate-pi-ie_22-divided-by_7-optmization              
                                                                                                                        
    StackOverflow;                                                                                                      
    https://tinyurl.com/y3vudpt2                                                                                        
    https://stackoverflow.com/questions/57939328/finding-the-fraction-which-is-minimal-to-pi-in-r                       
                                                                                                                        
    John Coleman                                                                                                        
    https://stackoverflow.com/users/4996248/john-coleman                                                                
                                                                                                                        
                                                                                                                        
    *_                   _                                                                                              
    (_)_ __  _ __  _   _| |_                                                                                            
    | | '_ \| '_ \| | | | __|                                                                                           
    | | | | | |_) | |_| | |_                                                                                            
    |_|_| |_| .__/ \__,_|\__|                                                                                           
            |_|                                                                                                         
    ;                                                                                                                   
                                                                                                                        
    %let min_integer = 2;                                                                                               
    %let max_integer = 10000000;                                                                                        
                                                                                                                        
    *            _               _                                                                                      
      ___  _   _| |_ _ __  _   _| |_                                                                                    
     / _ \| | | | __| '_ \| | | | __|                                                                                   
    | (_) | |_| | |_| |_) | |_| | |_                                                                                    
     \___/ \__,_|\__| .__/ \__,_|\__|                                                                                   
                    |_|                                                                                                 
    ;                                                                                                                   
                                                                                                                        
    SAS macro variable frac                                                                                             
                                                                                                                        
    %put &=frac;                                                                                                        
                                                                                                                        
    FRAC=5419351 / 1725033                                                                                              
                                                                                                                        
    %put %sysevalf(&frac.);                                                                                             
                                                                                                                        
    3.14159265358981                                                                                                    
                                                                                                                        
    %put %sysevalf(&frac.);                                                                                             
    %put %sysfunc(constant(PI));                                                                                        
                                                                                                                        
    Comparison                                                                                                          
                                                                                                                        
    Estimate from R 3.141592653589 81                                                                                   
    SAS Value       3.141592653589 79                                                                                   
                                                                                                                        
    *                                                                                                                   
     _ __  _ __ ___   ___ ___  ___ ___                                                                                  
    | '_ \| '__/ _ \ / __/ _ \/ __/ __|                                                                                 
    | |_) | | | (_) | (_|  __/\__ \__ \                                                                                 
    | .__/|_|  \___/ \___\___||___/___/                                                                                 
    |_|                                                                                                                 
    ;                                                                                                                   
                                                                                                                        
    * input;                                                                                                            
    %symdel                                                                                                             
        min_integer                                                                                                     
        max_integer                                                                                                     
        frac / nowarn;                                                                                                  
                                                                                                                        
    %let min_integer =2;                                                                                                
    %let max_integer=10000000;                                                                                          
                                                                                                                        
    * solution;                                                                                                         
                                                                                                                        
    %utl_submit_r64("                                                                                                   
    findBestApprox <- function(minD, maxD) {                                                                            
      lowers <- floor(pi*(minD:maxD))/(minD:maxD);                                                                      
      i <- which.min(abs(pi - lowers));                                                                                 
      best.lower <- lowers[i];                                                                                          
      uppers <- ceiling(pi*(minD:maxD))/(minD:maxD);                                                                    
      j <- which.min(abs(pi - uppers));                                                                                 
      best.upper <- uppers[j];                                                                                          
      if(abs(pi - best.lower) < abs(pi - best.upper)) {                                                                 
        d <- minD + i - 1;                                                                                              
        n <- floor(pi*d);                                                                                               
      } else {                                                                                                          
        d <- minD + j - 1;                                                                                              
        n <- ceiling(pi*d);                                                                                             
      };                                                                                                                
      c(n,d)                                                                                                            
    };                                                                                                                  
    frac<-findBestApprox(&min_integer,&max_integer);                                                                    
    frac<-paste(frac[1],'/',frac[2]);                                                                                   
    frac;                                                                                                               
    writeClipboard(frac);                                                                                               
    ",returnvar=frac);                                                                                                  
                                                                                                                        
    %put &=frac;                                                                                                        
                                                                                                                        
    FRAC  =  5419351 / 1725033                                                                                          
                                                                                                                        
    %put %sysevalf(&frac.);                                                                                             
                                                                                                                        
    3.14159265358981                                                                                                    
                                                                                                                        
    %put %sysevalf(&frac.);                                                                                             
    %put %sysfunc(constant(PI));                                                                                        
                                                                                                                        
    3.14159292035398                                                                                                    
    3.14159265358979                                                                                                    
                                                                                                                        
                                                                                                                        
