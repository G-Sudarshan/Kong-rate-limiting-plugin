# Kong Rate Limiting Plugin

Kong plugin implemented using Kong gateway and docker. Limits http requests not to exceed rate of 5 requests per minute to specified service.

> This plugin limits http request made on service named gists which in running on localhost:8000/gists 
> 
> The gists service simply communicate with GitHub API 

----
## Step 1: Implement plugin in Kong.yml file. 
#### Specify the service and no. of hits in Kong.yml

![code](https://github.com/G-Sudarshan/Kong-rate-limiting-plugin/blob/main/docs/images/code.png)

## Step 2: Spin up the docker container
#### Use following docker compose command to run the container
````bash
docker-compose up
````

![docker-compose](https://github.com/G-Sudarshan/Kong-rate-limiting-plugin/blob/main/docs/images/docker%20compose%20up.png)

## Step 3 : Hit gists service 
##### send http get request to `localhost:8000/gists` If you see following output means the API call is working fine and you are all set to test the working of the plugin.
![gists-service](https://github.com/G-Sudarshan/Kong-rate-limiting-plugin/blob/main/docs/images/gists.png)

## Step 4: Test plugin
#### send more than 5 requests within one minute ( in other words within 60 seconds ) and if you get this error then plugin is working fine. Hurray! 
#### you will get this output on your 6th request itself.
![plugin-outpu](https://github.com/G-Sudarshan/Kong-rate-limiting-plugin/blob/main/docs/images/rate-limiting-request.png)
