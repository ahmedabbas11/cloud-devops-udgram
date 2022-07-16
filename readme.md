# build project 2
project 2 is formed of 2 templates 
- infra 
- web

infra is for network resources such as vpc, subnet, internet gateways , natgateway,...
while web is for creating web servers and load balancers,...

## to execute infra template
```./create.sh project2-infra network-infra.yml network-infra-parameters.json```

## to execute web template
```./create.sh project2-web webservers.yml webservers-prod-parameters.json```

### local profile
webservers-prod-parameters.json vs webservers-local-parameters.json
>you can use local parameters file called "webservers-local-parameters.json" during development to save extra cost.


## Project url
to get project url please run the following command and replace the stack name used to crate.
```
aws cloudformation describe-stacks --stack-name project2-web --query "Stacks[0].Outputs[?OutputKey=='loadBalancerUrl'].OutputValue" --output text
```




## to delete infra stack
 ```aws cloudformation delete-stack --stack-name project2-infra```

## to delete web stack
```aws cloudformation delete-stack --stack-name project2-web ```



> you may use create.sh provided in the support material. or use aws cloudformation create-stack ...