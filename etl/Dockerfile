FROM python

# Add our python app code to the image
RUN mkdir -p /etl
ADD . /etl
WORKDIR /etl

# Install Python modules
RUN cd /etl; pip3 install -r requirements.txt

# Run db migrations
CMD ["alembic", "upgrade", "head"]

# Set the default command to execute
#CMD ["python", "etl.py"]

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
