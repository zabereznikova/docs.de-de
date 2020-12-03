---
title: 'Übersicht: Generieren von selbstsignierten Zertifikaten'
description: Eine Übersicht über das Microsoft dotnet dev-certs-Tool, das Funktionen für .NET Core- und ASP.NET Core-Projekte sowie weitere Optionen für die Verwendung selbstsignierter Zertifikate umfasst.
author: angee
ms.date: 11/19/2020
ms.openlocfilehash: b5bf4b719495c2d6ec248e8592367ac452be91c1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032176"
---
# <a name="generate-self-signed-certificates-with-the-net-cli"></a>Generieren von selbstsignierten Zertifikaten mit der .NET-CLI

Wenn Sie selbstsignierte Zertifikate verwenden, gibt es verschiedene Möglichkeiten, um sie zu erstellen und für die Bereitstellung sowie für Testszenarios zu verwenden.  In diesem Leitfaden erhalten Sie Informationen zur Verwendung von selbstsignierten Zertifikaten mit `dotnet dev-certs` und anderen Optionen wie `PowerShell` und `OpenSSL`.

Sie können dann mithilfe eines Beispiels überprüfen, ob das Zertifikat geladen wird, z. B. mit einer [ASP.NET Core-App](https://github.com/dotnet/dotnet-docker/blob/master/samples/run-aspnetcore-https-development.md), die in einem Container gehostet wird.

## <a name="prerequisites"></a>Voraussetzungen

Im Beispiel können Sie entweder .NET Core 3.1 oder .NET 5 verwenden.

Stellen Sie für `dotnet dev-certs` sicher, dass Sie die richtige Version von .NET installiert haben:

* [Installieren von .NET unter Windows](../install/windows.md)
* [Installieren von .NET unter Linux](../install/linux.md)
* [Installieren von .NET unter macOS](../install/macos.md)

Für dieses Beispiel benötigen Sie den [Docker-Client](https://www.docker.com/products/docker) [Docker 17.06](https://docs.docker.com/release-notes/docker-ce) oder höher.

## <a name="prepare-sample-app"></a>Vorbereiten der Beispiel-App

Sie müssen die Beispiel-App je nach Runtime vorbereiten, die Sie zum Testen verwenden möchten, entweder [.NET Core 3.1](#net-core-31-sample-app) oder [.NET 5](#net-5-sample-app).

Verwenden Sie für diese Anleitung eine [Beispiel-App](https://hub.docker.com/_/microsoft-dotnet-samples), und nehmen Sie wenn nötig Anpassungen vor.

### <a name="net-core-31-sample-app"></a>Beispiel-App für .NET Core 3.1

Abrufen der Beispiel-App

```console
git clone https://github.com/dotnet/dotnet-docker/
```

Navigieren Sie auf lokaler Ebene zum Repository, und öffnen Sie den Arbeitsbereich in einem Editor.

> [!NOTE]
> Wenn Sie dotnet publish-Parameter zum *Trimmen* der Bereitstellung verwenden möchten, sollten Sie sicherstellen, dass die entsprechenden Abhängigkeiten zur Unterstützung von SSL-Zertifikaten hinzugefügt werden.
Aktualisieren Sie die Datei [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj), um sicherzustellen, dass die richtigen Assemblys zum Container hinzugefügt werden. Informieren Sie sich in diesem Zusammenhang darüber, wie Sie die CSPROJ-Datei so aktualisieren können, dass [SSL-Zertifikate unterstützt](../deploying/trim-self-contained.md#support-for-ssl-certificates) werden, wenn Sie Trimming für eigenständige Bereitstellungen einsetzen.

Stellen Sie sicher, dass die Datei `aspnetapp.csproj` ein passendes Zielframework enthält:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>.netcoreapp3.1</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

Ändern Sie das Dockerfile, um sicherzustellen, dass die Runtime auf .NET Core 3.1 verweist:

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet-core
FROM mcr.microsoft.com/dotnet/core/sdk:3.1 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app --no-restore

# final stage/image
FROM mcr.microsoft.com/dotnet/core/aspnet:3.1
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["dotnet", "aspnetapp.dll"]
```

Stellen Sie sicher, dass Sie auf die Beispiel-App verweisen.

```console
cd .\dotnet-docker\samples\aspnetapp
```

Erstellen Sie den Container zum Testen auf lokaler Ebene.

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

### <a name="net-5-sample-app"></a>.NET 5-Beispiel-App

Überprüfen Sie für diese Anleitung das Beispiel [aspnetapp](https://hub.docker.com/_/microsoft-dotnet-samples) auf .NET 5.

Überprüfen Sie, ob das [Dockerfile](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile) für die Beispiel-App .NET 5 verwendet.

Je nach Hostbetriebssystem muss die ASP.NET-Runtime gegebenenfalls aktualisiert werden. Wenn Sie im Dockerfile beispielsweise von `mcr.microsoft.com/dotnet/aspnet:5.0-nanoservercore-2009 AS runtime` zu `mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime` wechseln, können Sie besser eine passende Windows-Runtime als Ziel festlegen.

Dies hilft beispielsweise beim Testen der Zertifikate unter Windows:

```Dockerfile
# https://hub.docker.com/_/microsoft-dotnet
FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build
WORKDIR /source

# copy csproj and restore as distinct layers
COPY *.sln .
COPY aspnetapp/*.csproj ./aspnetapp/
RUN dotnet restore -r win-x64

# copy everything else and build app
COPY aspnetapp/. ./aspnetapp/
WORKDIR /source/aspnetapp
RUN dotnet publish -c release -o /app -r win-x64 --self-contained false --no-restore

# final stage/image
# Uses the 2009 release; 2004, 1909, and 1809 are other choices
FROM mcr.microsoft.com/dotnet/aspnet:5.0-windowsservercore-ltsc2019 AS runtime
WORKDIR /app
COPY --from=build /app ./
ENTRYPOINT ["aspnetapp"]

```

Wenn wir die Zertifikate unter Linux testen, können Sie das vorhandene Dockerfile verwenden.

Stellen Sie sicher, dass die Datei `aspnetapp.csproj` ein passendes Zielframework enthält:

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
    <!--Other Properties-->
  </PropertyGroup>

</Project>
```

> [!NOTE]
> Wenn Sie `dotnet publish`-Parameter zum *Trimmen* der Bereitstellung verwenden möchten, sollten Sie sicherstellen, dass die passenden Abhängigkeiten zur Unterstützung von SSL-Zertifikaten hinzugefügt werden.
Aktualisieren Sie die Datei [dotnet-docker\samples\aspnetapp\aspnetapp.csproj](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/aspnetapp/aspnetapp.csproj), um sicherzustellen, dass die richtigen Assemblys zum Container hinzugefügt werden. Informieren Sie sich in diesem Zusammenhang darüber, wie Sie die CSPROJ-Datei so aktualisieren können, dass [SSL-Zertifikate unterstützt](../deploying/trim-self-contained.md#support-for-ssl-certificates) werden, wenn Sie Trimming für eigenständige Bereitstellungen einsetzen.

Stellen Sie sicher, dass Sie auf die Beispiel-App verweisen.

```console
cd .\dotnet-docker\samples\aspnetapp
```

Erstellen Sie den Container zum Testen auf lokaler Ebene.

```console
docker build -t aspnetapp:my-sample -f Dockerfile .
```

## <a name="create-a-self-signed-certificate"></a>Erstellen eines selbstsignierten Zertifikats

Sie können mithilfe der folgenden Tools ein selbstsigniertes Zertifikat erstellen:

- [Mit dotnet dev-certs](#with-dotnet-dev-certs)
- [Mit PowerShell](#with-powershell)
- [Mit OpenSSL](#with-openssl)

### <a name="with-dotnet-dev-certs"></a>Mit dotnet dev-certs

Sie können `dotnet dev-certs` verwenden, um mit selbstsignierten Zertifikaten zu arbeiten. In diesem Beispiel wird eine PowerShell-Konsole verwendet.

```console
dotnet dev-certs https -ep $env:USERPROFILE\.aspnet\https\aspnetapp.pfx -p crypticpassword
dotnet dev-certs https --trust
```

> [!NOTE]
> Der Zertifikatsname, in diesem Fall *aspnettapp*.pfx, muss mit dem Projektassemblynamen identisch sein. `crypticpassword` wird als Ersatz für ein Kennwort Ihrer Wahl verwendet. Wenn die Konsole die Meldung "A valid HTTPS certificate is already present" (Es gibt bereit ein gültiges HTTPS-Zertifikat) zurückgibt, gibt es bereits ein vertrauenswürdiges Zertifikat in Ihrem Speicher. Dieses können Sie mithilfe der MMC-Konsole exportieren.

Konfigurieren Sie die Anwendungsgeheimnisse für das Zertifikat:

```console
dotnet user-secrets -p aspnetapp\aspnetapp.csproj set "Kestrel:Certificates:Development:Password" "crypticpassword"
```

> [!NOTE]
> Hinweis: Das Kennwort muss dem Kennwort entsprechen, das für das Zertifikat verwendet wird.

Führen Sie das Containerimage mit einer für HTTPS konfigurierten ASP.NET Core-Instanz aus:

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -v $env:APPDATA\microsoft\UserSecrets\:C:\Users\ContainerUser\AppData\Roaming\microsoft\UserSecrets -v $env:USERPROFILE\.aspnet\https:C:\Users\ContainerUser\AppData\Roaming\ASP.NET\Https mcr.microsoft.com/dotnet/samples:aspnetapp
```

Sobald die Anwendung gestartet wurde, navigieren Sie in Ihrem Webbrowser zu `https://localhost:8001`.

#### <a name="clean-up"></a>Bereinigung

Wenn die Geheimnisse und Zertifikate nicht verwendet werden, sollten Sie diese löschen.

```console
dotnet user-secrets remove "Kestrel:Certificates:Development:Password" -p aspnetapp\aspnetapp.csproj
dotnet dev-certs https --clean
```

### <a name="with-powershell"></a>Mit PowerShell

Sie können PowerShell verwenden, um selbstsignierte Zertifikate zu generieren. Dabei hilft Ihnen der [PKI-Client](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps&preserver-view=true).

```powershell
$cert = New-SelfSignedCertificate -DnsName @("contoso.com", "www.contoso.com") -CertStoreLocation "cert:\LocalMachine\My"
```

Wenn das Zertifikat generiert wird, sollte es in einem Zertifikatspeicher gespeichert werden, um Tests im Browser durchzuführen.

```powershell
$certKeyPath = "c:\certs\contoso.com.pfx"
$password = ConvertTo-SecureString 'password' -AsPlainText -Force
$cert | Export-PfxCertificate -FilePath $certKeyPath -Password $password
$rootCert = $(Import-PfxCertificate -FilePath $certKeyPath -CertStoreLocation 'Cert:\LocalMachine\Root' -Password $password)
```

An dieser Stellen sollten die Zertifikate über ein [MMC-Snap-In](../../framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md) abrufbar sein.

Sie können den Beispielcontainer im Windows-Subsystem für Linux (WSL) ausführen:

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> Mit der Volumebereitstellung kann der Dateipfad je nach Host anders aufgebaut sein.  Beispielsweise können Sie in WSL */c/certs* durch */mnt/c/certs* ersetzen.

Wenn Sie den Container verwenden, der zuvor für Windows erstellt wurde, sieht der Ausführungsbefehl wie folgt aus:

```console
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

Navigieren Sie in einem Browser zu „contoso.com:8001“, sobald die Anwendung ausgeführt wird.

Stellen Sie sicher, dass die Hosteinträge aktualisiert werden, damit `contoso.com` auf einer passenden IP-Adresse (z. B. 127.0.0.1) antwortet. Wenn das Zertifikat nicht erkannt wird, sollten Sie sich vergewissern, dass das Zertifikat, das mit dem Container geladen wird, ebenfalls vom Host als vertrauenswürdig eingestuft wird, und dass es passende SAN-/DNS-Einträge für `contoso.com` gibt.

#### <a name="clean-up"></a>Bereinigung

```powershell
$cert | Remove-Item
Get-ChildItem $certFilePath | Remove-Item
$rootCert | Remove-item
```

### <a name="with-openssl"></a>Mit OpenSSL

Sie können [OpenSSL](https://www.openssl.org/) verwenden, um selbstsignierte Zertifikate zu erstellen. In diesem Beispiel werden WSL/Ubuntu und eine Bash-Shell mit `OpenSSL` verwendet.

Hierdurch werden eine CRT- und eine KEY-Datei generiert.

```bash
PARENT="contoso.com"
openssl req \
-x509 \
-newkey rsa:4096 \
-sha256 \
-days 365 \
-nodes \
-keyout $PARENT.key \
-out $PARENT.crt \
-subj "/CN=${PARENT}" \
-extensions v3_ca \
-extensions v3_req \
-config <( \
  echo '[req]'; \
  echo 'default_bits= 4096'; \
  echo 'distinguished_name=req'; \
  echo 'x509_extension = v3_ca'; \
  echo 'req_extensions = v3_req'; \
  echo '[v3_req]'; \
  echo 'basicConstraints = CA:FALSE'; \
  echo 'keyUsage = nonRepudiation, digitalSignature, keyEncipherment'; \
  echo 'subjectAltName = @alt_names'; \
  echo '[ alt_names ]'; \
  echo "DNS.1 = www.${PARENT}"; \
  echo "DNS.2 = ${PARENT}"; \
  echo '[ v3_ca ]'; \
  echo 'subjectKeyIdentifier=hash'; \
  echo 'authorityKeyIdentifier=keyid:always,issuer'; \
  echo 'basicConstraints = critical, CA:TRUE, pathlen:0'; \
  echo 'keyUsage = critical, cRLSign, keyCertSign'; \
  echo 'extendedKeyUsage = serverAuth, clientAuth')

openssl x509 -noout -text -in $PARENT.crt
```

Wenn Sie eine PFX-Datei erstellen möchten, verwenden Sie den folgenden Befehl:

```bash
openssl pkcs12 -export -out $PARENT.pfx -inkey $PARENT.key -in $PARENT.crt
```

> [!NOTE]
> Das Beispiel „.aspnetcore 3.1“ verwendet `.pfx` und ein Kennwort. Ab der Runtime `.net 5` kann Kestrel ebenfalls `.crt`-Dateien und PEM-codierte `.key`-Dateien verwenden.

Je nach Hostbetriebssystem muss das Zertifikat als vertrauenswürdig eingestuft werden. Auf einem Linux-Host werden Zertifikate auf andere Weise und in Abhängigkeit mit der Distribution als vertrauenswürdig eingestuft.

Für diesen Leitfaden stellen wir das folgende Beispiel für Windows unter Verwendung von PowerShell bereit:

```powershell
Import-Certificate -FilePath $certFilePath -CertStoreLocation 'Cert:\LocalMachine\Root'
```

Führen Sie für .NET Core 3.1 den folgenden Befehl in WSL aus:

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.pfx -v /c/path/to/certs/:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

Ab .NET 5 kann Kestrel `.crt`-Dateien und PEM-codierte `.key`-Dateien verwenden. Sie können das Beispiel mithilfe des folgenden Befehls für .NET 5 ausführen:

```bash
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=/https/contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=/https/contoso.com.key -v /c/path/to/certs:/https/ mcr.microsoft.com/dotnet/samples:aspnetapp
```

> [!NOTE]
> In WSL kann der Pfad der Volumebereitstellung je nach Konfiguration abweichen.

Führen Sie für .NET Core 3.1 unter Windows den folgenden Befehl in `Powershell` aus:

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Password="password" -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.pfx -v c:\certs:C:\https aspnetapp:my-sample
```

Führen Sie für .NET 5 unter Windows den folgenden Befehl in PowerShell aus:

```powershell
docker run --rm -it -p 8000:80 -p 8001:443 -e ASPNETCORE_URLS="https://+;http://+" -e ASPNETCORE_HTTPS_PORT=8001 -e ASPNETCORE_ENVIRONMENT=Development -e ASPNETCORE_Kestrel__Certificates__Default__Path=c:\https\contoso.com.crt -e ASPNETCORE_Kestrel__Certificates__Default__KeyPath=c:\https\contoso.com.key -v c:\certs:C:\https aspnetapp:my-sample
```

Navigieren Sie in einem Browser zu „contoso.com:8001“, sobald die Anwendung ausgeführt wird.

Stellen Sie sicher, dass die Hosteinträge aktualisiert werden, damit `contoso.com` auf einer passenden IP-Adresse (z. B. 127.0.0.1) antwortet. Wenn das Zertifikat nicht erkannt wird, sollten Sie sich vergewissern, dass das Zertifikat, das mit dem Container geladen wird, ebenfalls vom Host als vertrauenswürdig eingestuft wird, und dass es passende SAN-/DNS-Einträge für `contoso.com` gibt.

#### <a name="clean-up"></a>Bereinigung

Stellen Sie sicher, dass Sie die selbstsignierten Zertifikate nach Abschluss der Tests löschen.

```powershell
Get-ChildItem $certFilePath | Remove-Item
```
