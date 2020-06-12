---
title: Verwenden von dotnet-svcutil.xmlserializer
description: Erfahren Sie, wie Sie das NuGet-Paket `dotnet-svcutil.xmlserializer` zum Vorabgenerieren einer Serialisierungsassembly für .NET Core-Projekte verwenden können.
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 14bb2e8a85ec35f08b0a83b9734a64d751074f1b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84284324"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>Verwendung von „dotnet-svcutil.xmlserializer“ in .NET Core

Mit dem NuGet-Paket `dotnet-svcutil.xmlserializer` kann eine Serialisierungsassembly für .NET Core-Projekte vorab generiert werden. Es generiert vorab C#-Serialisierungscode für die Typen in der Clientanwendung, die vom WCF-Dienstvertrag verwendet werden und über XmlSerializer serialisiert werden können. Dies verbessert die Startleistung der XML-Serialisierung beim Serialisieren oder Deserialisieren von Objekten dieser Typen.

## <a name="prerequisites"></a>Voraussetzungen

* [.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höher
* Ihr bevorzugter Code-Editor

Sie können mit dem Befehl `dotnet --info` überprüfen, welche Versionen von .NET Core SDK und Runtime Sie bereits installiert haben.

## <a name="getting-started"></a>Erste Schritte

So verwenden Sie `dotnet-svcutil.xmlserializer` in einer .NET Core-Konsolenanwendung:

1. Erstellen Sie einen WCF-Dienst mit dem Namen „MyWCFService“ unter Verwendung der Standardvorlage „WCF Service Application“ unter .NET Framework. Fügen Sie das `[XmlSerializerFormat]`-Attribut auf folgende Weise der Dienstmethode hinzu:

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. Erstellen Sie eine .NET Core-Konsolenanwendung als WCF-Clientanwendung für .NET Core 2.1 oder höhere Versionen. Erstellen Sie beispielsweise mit dem folgenden Befehl eine App mit dem Namen „MyWCFClient“:

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    Um sicherzustellen, dass Ihr Projekt .NET Core 2.1 oder höher als Ziel verwendet, überprüfen Sie das XML-Element `TargetFramework` in Ihrer Projektdatei:

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. Fügen Sie einen Paketverweis auf `System.ServiceModel.Http` mithilfe des folgenden Befehls hinzu:

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

4. Fügen Sie den WCF Client-Code hinzu:

    ```csharp
    using System.ServiceModel;

        class Program
        {
            static void Main(string[] args)
            {
                var myBinding = new BasicHttpBinding();
                var myEndpoint = new EndpointAddress("http://localhost:2561/Service1.svc"); //Fill your service url here
                var myChannelFactory = new ChannelFactory<IService1>(myBinding, myEndpoint);
                IService1 client = myChannelFactory.CreateChannel();
                string s = client.GetData(1);
                ((ICommunicationObject)client).Close();
            }
        }

    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

5. Fügen Sie einen Verweis auf das `dotnet-svcutil.xmlserializer`-Paket mithilfe des folgenden Befehls hinzu:
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    Durch Ausführen des Befehls sollte ein Eintrag zu Ihrer Projektdatei hinzugefügt werden, die Folgendem ähnelt:
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. Erstellen Sie die Anwendung durch Ausführen von `dotnet build`. Wenn alle Vorgänge erfolgreich ausgeführt werden, wird eine Assembly mit dem Namen *MyWCFClient.XmlSerializers.dll* im Ausgabeordner generiert. Wenn das Tool die Assembly nicht generieren kann, werden Warnungen in der Buildausgabe angezeigt.

7. Starten Sie den WCF-Dienst, indem Sie z.B. `http://localhost:2561/Service1.svc` im Browser ausführen. Starten Sie dann die Client-Anwendung; sie wird automatisch geladen und verwendet die zuvor generierten Serialisierungsmodule zur Laufzeit.
