# Docker + Ollama + OpenWebUI

This is a simple Docker setup using docker compose to get Ollama with Open WebUI up and running in seconds. The stack is configured to use all locally available GPU's.

Tested on Ubuntu and it works.
Update the .env file to adjust the directory paths for model and data storage to your own setup.

*Endpoints*
- http://localhost:11343 - Ollama API
- http://localhost:1080 - Open WebUI

To start the stack simply run:
~~~
docker compose up
~~~

## Ollama operations
You can interact with ollama in docker by running
~~~
docker compose ollama ollama 
~~~

But to make it more convininent add the following to ~/.bashrc:
~~~
echo "alias ollama='docker exec -it ollama ollama'" > ~/.bashrc
source ~/.bashrc
~~~

Now you can interact with ollama like it was installed locally:
~~~
ollama ps
ollama ls
ollama run deepseek-r1:7b
~~~

## Docker operations

Pull latest images
~~~
docker compose pull
~~~

Start up
~~~
docker compose up -d
~~~

Logs
~~~
docker compose logs -f
~~~

Shutdown
~~~
docker compose down
~~~
