# spring security configuration

![](../.gitbook/assets/image%20%28171%29.png)

![](../.gitbook/assets/image%20%28181%29.png)

* **authorizeRequests\(\)** : restrict access based on the httpservletreqest 
* **anyrequest\(\)**.authenticated\(\) : any request to the app must be authenticated\(logged in\)
* **formLogin\(\):** customizing the form login process
* **loginPage\(\)**: show our custom form at the request mapping
* **loginProcessingUrl\(\):** login form should post data to this URL for processing
* **permitAll\(\):** we want everyone to see login page, no need to log in.



### Login Controller

![](../.gitbook/assets/image%20%28170%29.png)

### front-end form post

![](../.gitbook/assets/image%20%28176%29.png)

### contextPath

![](../.gitbook/assets/image%20%28169%29.png)

### antMatchers

![](../.gitbook/assets/image%20%28173%29.png)

