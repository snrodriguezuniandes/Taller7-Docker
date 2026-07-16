FROM python:3.12-slim

<<<<<<< HEAD
# Crear usuario que ejecuta el dash
RUN adduser --disabled-password --gecos '' dash-user
=======
# Crear usuario que ejecuta la app
RUN adduser --disabled-password --gecos '' api-user
>>>>>>> 4702406e86564fac98930ec36671ef7fa36b7821

# Instalar compiladores C/C++ y build tools
RUN apt-get update && apt-get install -y --no-install-recommends \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

# Definir directorio de trabajo 
<<<<<<< HEAD
WORKDIR /opt/app

# Instalar dependencias
ADD ./app /opt/app/
RUN pip install --upgrade pip
RUN pip install -r /opt/app/requirements.txt

# Hacer el directorio de trabajo ejecutable 
RUN chmod +x /opt/app/run.sh
# Cambiar propiedad de la carpeta a dash-user 
RUN chown -R dash-user:dash-user ./

USER dash-user
# Puerto a exponer para el tablero
EXPOSE 8050
=======
WORKDIR /opt/bankchurn-api

# Instalar dependencias
ADD ./bankchurn-api /opt/bankchurn-api/
RUN pip install --upgrade pip
RUN pip install -r /opt/bankchurn-api/requirements.txt

# Hacer el directorio de trabajo ejecutable 
RUN chmod +x /opt/bankchurn-api/run.sh
# Cambiar propiedad de la carpeta a api-user 
RUN chown -R api-user:api-user ./

USER api-user
# Puerto a exponer para la api 
EXPOSE 8001
>>>>>>> 4702406e86564fac98930ec36671ef7fa36b7821

# Comandos a ejecutar al correr el contenedor 
CMD ["bash", "./run.sh"]
