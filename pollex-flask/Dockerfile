# Dcokerfile - Docker build script for Pollex
#
#    Copyright (c) 2019 - Open Source Competencer Center ICMC-USP
#
#    This file is part of Pollex.
#
#    Pollex is free software: you can redistribute it and/or modify
#    it under the terms of the GNU General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    Pollex is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU General Public License for more details.
#
#    You should have received a copy of the GNU General Public License
#    along with this program.  If not, see <https://www.gnu.org/licenses/>.

# Application is currently based on Ubuntu and Python

FROM ubuntu:19.10
FROM python:3.7

# Application home directory

RUN mkdir /home/pollex

WORKDIR /home/pollex

# We need Flask framework (there's currently no official Docker image)

RUN pip install flask

# Copy application files into the image

COPY index.py .
# COPY templates/* templates/
# COPY static/* static/

# By default, the container will listen to port 5000 internally

EXPOSE 5000

# Start WSGI application

ENV FLASK_APP=index.py
ENV FLASK_ENV=development

ENTRYPOINT ["python"]
CMD ["index.py"]

