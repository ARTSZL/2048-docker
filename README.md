# Dockerized 2048 Game Deployment on AWS Elastic Beanstalk

This project create the popular 2048 game using Docker and deploys it to AWS Elastic Beanstalk. The 2048 game source code is available at [https://github.com/gabrielecirulli/2048](https://github.com/gabrielecirulli/2048). Thanks to [N4si](https://github.com/N4si) for the step by step walkthrough.

## Prerequisites

Before getting started, ensure you have the following prerequisites:

- An AWS account with appropriate IAM permissions.
- [Docker](https://www.docker.com/) installed on your local machine.
- [AWS Elastic Beanstalk Command Line Interface (EB CLI)](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3.html) installed on your local machine.

## Getting Started

Follow the steps below to deploy the 2048 game on AWS Elastic Beanstalk.

1. Create the Dockerfile.

2. Build the Docker image. Replace 2048-docker with your desired image name.

   ```bash
   docker build -t 2048-docker .

4. Run the Docker container to test the game locally.

   ```bash
   docker run -d -p 80:80 2048-docker

5. The game should now be accessible in your web browser at http://localhost:80.

6. Stop the Docker container once you have tested the game.

   ```bash
   docker stop $(docker ps -a -q)

7. Create an AWS Elastic Beanstalk application using the EB CLI. Replace my-2048-game with your desired application name.

   ```bash
   eb init -p docker my-2048-game

8. Create an environment and deploy the game to AWS Elastic Beanstalk.

   ```bash
   eb create my-2048-environment

9. Access your deployed game through the provided Elastic Beanstalk URL.

## Cleanup

To terminate the AWS resources and Docker containers created for this project, follow these steps:

1. Terminate the Elastic Beanstalk environment.

   ```bash
   eb terminate my-2048-environment

2. Remove the AWS Elastic Beanstalk application.

   ```bash
   eb terminate my-2048-game

3. Remove the Docker image and container.

   ```bash
   docker stop $(docker ps -a -q)
   docker rmi docker-2048

## License

This project is licensed under the MIT License - see the [LICENSE](https://github.com/ARTSZL/2048-docker/blob/main/LICENSE) file for details.

## Acknowledgments

[2048 Game by gabrielecirulli](https://github.com/gabrielecirulli/2048)
[Docker](https://www.docker.com/)
[AWS Elastic Beanstalk](https://docs.aws.amazon.com/elasticbeanstalk)

Feel free to contribute to this project and make improvements. If you encounter any issues, please open a GitHub issue.
