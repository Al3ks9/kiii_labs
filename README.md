# Jenkins Docker Compose Stack (Jenkins + Blue Ocean)

## Quick start

1. Open a terminal in this folder.
2. Build and start:

   docker compose up -d --build

## Required verification steps

1. Build and start the stack:

   docker compose up -d --build

2. Verify both services are running (must show docker and jenkins-blueocean):

   docker compose ps

3. Get logs and copy the initial admin password from output:

   docker compose logs jenkins-blueocean

   Optional filtered view:

   docker compose logs jenkins-blueocean | sed -n '/Please use the following password to proceed to installation:/,+1p'

4. Jenkins URL to use in browser and in setup notes:

   http://localhost:8080

5. Final confirmation both services are still running:

   docker compose ps

## Optional direct password command

If logs are noisy, read it directly from inside the Jenkins container:

docker compose exec jenkins-blueocean cat /var/jenkins_home/secrets/initialAdminPassword
