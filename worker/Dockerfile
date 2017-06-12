FROM microsoft/dotnet:1.1.1-sdk

WORKDIR /code

ARG PROXY
ENV http_proxy $PROXY 

ADD src/Worker /code/src/Worker

RUN dotnet restore -v minimal src/Worker \
    && dotnet publish -c Release -o "./" "src/Worker/" 

CMD dotnet src/Worker/Worker.dll
