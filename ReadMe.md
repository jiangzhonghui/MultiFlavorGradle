# Understanding studio folder structure and maintain seperate builds:
====================================================================

1. build-config: Adding common files here.
 
 		
		    |
		    --assets
		       |
		       --system.properties

		    --res
			|
			--values
		       		|
  		      		--environment.xml

2. Add configuration values in 'build-config' under 'app' folder.

 In this sample:

		 app
		 |
  			--build.config
			  |
     			--dev.properties
        	 		|
         			-- base.url=www.devlab.com

    		 	--qa.properties
         			|
         			-- base.url=www.qalab.com


3. Build script is copy these resources bases on the flavors such as QA,DEV in 'app/src' folder


	  	app
		  |
		  --build.gradle (written code for replace the content of build-config)


Finally Directory structure would be in the following structure:


		 app
		 |
  			--src
    			|
    			--main
        			|
        			--res
    			--dev
        			|
        			--res (environment.xml with build-config dev base url)
    			--qa
        			|
        			--res (environment.xml with build config qa base url)


Enjoy!














