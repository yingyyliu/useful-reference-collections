# AWS Developer

1. **Web environment**
2. **Worker environment** background worker

## Deployment

1. **Elastic Beanstalk** handles deployment, from capacity provisioning, load balancing, auto-scaling to application health monitoring
2. It costs nothing to use Elastic Beanstalk (only the resources it provisions, eg. RDS, ELB, EC2...)
3. Recommended for test or development apps. Not recommended for production use. However, for small business, it's ok to use Elastic Beanstalk.
4. You can use the following preconfigured platform: Java,.NET, PHP,Node.js, Python, Ruby, Go and Docker.
5. You can run containers on EB either in Single-container or Multi-container, these containers are running on ECS instead of EC2
6. Able to launch either a **Web Environment** or a **Worker Environment**
   - **Web Environment** come in two types:
     - **Single-Instance Env:** Launches a single EC2, an EIP (Elastic IP Addr) is assigned to the EC2
     - **Load Balanced Env:** Launches EC2s behind an ELB (Elastic Load Balancer) behind an ASG (Auto Scaling Group)
   - **Worker Environment:** Creates a SQS (Simple Queue Service), install SQS daemon on the EC2 instance, and has ASG scaling policy which will add or remove instances based on queue size
7. EB has following **deployment policies**:
   - **All at once:** takes all servers out-of-service, applies changes, put servers back-in-service, fast, has downtime
   - **Rolling:** updates servers in batches, reduced capacity based on batch size
   - **Rolling with additional batch:** add new servers in batches to replace old, never reduce capacity
   - **Immutable:** creates the same amount of servers, and switches all at once to new server, remove old servers
8. Rolling deployment policies require an ELB so cannot be used with Single-Instance web environments
9. In-Place deployment is when deployment occurs within the environment, all deployment policies are in-place
10. Blue/Green is when deployment swaps environments (outside an environment), when you have external resources such as RDS which cannot be destroyed, its suited for Blue/Green
11. **.ebextensions** is a folder which contains all configuration files
12. With EB you can provide a **custom image** which can improve provisioning times
13. If you let Elastic Beanstalk create the RDS instance, that means when you delete your environment it will delete the database.
    This setup intended for development and test environments
14. **Dockerrun.aws.json** is similar to a ECS Task Definition files and defines multi container configuration

## Security

## Development With AWS Services

## Refactoring

## Monitoring and Troubleshooting

# Reference

1. https://www.youtube.com/watch?v=RrKRN9zRBWs
2. https://aws.amazon.com/whitepapers/
3. https://docs.aws.amazon.com/
