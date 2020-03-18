---
title: Verwenden von dotnet-svcutil.xmlserializer
description: Erfahren Sie, wie Sie das NuGet-Paket `dotnet-svcutil.xmlserializer` zum Vorabgenerieren einer Serialisierungsassembly für .NET Core-Projekte verwenden können.
author: huanwu
ms.date: 11/27/2018
ms.openlocfilehash: 4811647c294118cb160d25805e7d3ada97f071f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75344898"
---
# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="b1fc6-103">Verwendung von „dotnet-svcutil.xmlserializer“ in .NET Core</span><span class="sxs-lookup"><span data-stu-id="b1fc6-103">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

<span data-ttu-id="b1fc6-104">Mit dem NuGet-Paket `dotnet-svcutil.xmlserializer` kann eine Serialisierungsassembly für .NET Core-Projekte vorab generiert werden.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-104">The `dotnet-svcutil.xmlserializer` NuGet package can pre-generate a serialization assembly for .NET Core projects.</span></span> <span data-ttu-id="b1fc6-105">Es generiert vorab C#-Serialisierungscode für die Typen in der Clientanwendung, die vom WCF-Dienstvertrag verwendet werden und über XmlSerializer serialisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-105">It pre-generates C# serialization code for the types in the client application that are used by the WCF Service Contract and that can be serialized by the XmlSerializer.</span></span> <span data-ttu-id="b1fc6-106">Dies verbessert die Startleistung der XML-Serialisierung beim Serialisieren oder Deserialisieren von Objekten dieser Typen.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-106">This improves the startup performance of XML serialization when serializing or deserializing objects of those types.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b1fc6-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b1fc6-107">Prerequisites</span></span>

* <span data-ttu-id="b1fc6-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) oder höher</span><span class="sxs-lookup"><span data-stu-id="b1fc6-108">[.NET Core 2.1 SDK](https://dotnet.microsoft.com/download) or later</span></span>
* <span data-ttu-id="b1fc6-109">Ihr bevorzugter Code-Editor</span><span class="sxs-lookup"><span data-stu-id="b1fc6-109">Your favorite code editor</span></span>

<span data-ttu-id="b1fc6-110">Sie können mit dem Befehl `dotnet --info` überprüfen, welche Versionen von .NET Core SDK und Runtime Sie bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-110">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

## <a name="getting-started"></a><span data-ttu-id="b1fc6-111">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="b1fc6-111">Getting started</span></span>

<span data-ttu-id="b1fc6-112">So verwenden Sie `dotnet-svcutil.xmlserializer` in einer .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="b1fc6-112">To use `dotnet-svcutil.xmlserializer` in a .NET Core console application:</span></span>

1. <span data-ttu-id="b1fc6-113">Erstellen Sie einen WCF-Dienst mit dem Namen „MyWCFService“ unter Verwendung der Standardvorlage „WCF Service Application“ unter .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-113">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span> <span data-ttu-id="b1fc6-114">Fügen Sie das `[XmlSerializerFormat]`-Attribut auf folgende Weise der Dienstmethode hinzu:</span><span class="sxs-lookup"><span data-stu-id="b1fc6-114">Add `[XmlSerializerFormat]` attribute on the service method like the following:</span></span>

   ```csharp
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```

2. <span data-ttu-id="b1fc6-115">Erstellen Sie eine .NET Core-Konsolenanwendung als WCF-Clientanwendung für .NET Core 2.1 oder höhere Versionen.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-115">Create a .NET Core console application as WCF client application that targets at .NET Core 2.1 or later versions.</span></span> <span data-ttu-id="b1fc6-116">Erstellen Sie beispielsweise mit dem folgenden Befehl eine App mit dem Namen „MyWCFClient“:</span><span class="sxs-lookup"><span data-stu-id="b1fc6-116">For example, create an app named 'MyWCFClient' with the following command:</span></span>

    ```dotnetcli
    dotnet new console --name MyWCFClient
    ```

    <span data-ttu-id="b1fc6-117">Um sicherzustellen, dass Ihr Projekt .NET Core 2.1 oder höher als Ziel verwendet, überprüfen Sie das XML-Element `TargetFramework` in Ihrer Projektdatei:</span><span class="sxs-lookup"><span data-stu-id="b1fc6-117">To ensure your project is targeting .NET Core 2.1 or later, inspect the `TargetFramework` XML element in your project file:</span></span>

    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```

3. <span data-ttu-id="b1fc6-118">Fügen Sie einen Paketverweis auf `System.ServiceModel.Http` mithilfe des folgenden Befehls hinzu:</span><span class="sxs-lookup"><span data-stu-id="b1fc6-118">Add a package reference to `System.ServiceModel.Http` by running the following command:</span></span>

    ```dotnetcli
    dotnet add package System.ServiceModel.Http
    ```

4. <span data-ttu-id="b1fc6-119">Fügen Sie den WCF Client-Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="b1fc6-119">Add the WCF Client code:</span></span>

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

5. <span data-ttu-id="b1fc6-120">Fügen Sie einen Verweis auf das `dotnet-svcutil.xmlserializer`-Paket mithilfe des folgenden Befehls hinzu:</span><span class="sxs-lookup"><span data-stu-id="b1fc6-120">Add a reference to the `dotnet-svcutil.xmlserializer` package by running the following command:</span></span>
  
    ```dotnetcli
    dotnet add package dotnet-svcutil.xmlserializer
    ```

    <span data-ttu-id="b1fc6-121">Durch Ausführen des Befehls sollte ein Eintrag zu Ihrer Projektdatei hinzugefügt werden, die Folgendem ähnelt:</span><span class="sxs-lookup"><span data-stu-id="b1fc6-121">Running the command should add an entry to your project file similar to this:</span></span>
  
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="b1fc6-122">Erstellen Sie die Anwendung durch Ausführen von `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-122">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="b1fc6-123">Wenn alle Vorgänge erfolgreich ausgeführt werden, wird eine Assembly mit dem Namen *MyWCFClient.XmlSerializers.dll* im Ausgabeordner generiert.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-123">If everything succeeds, an assembly named *MyWCFClient.XmlSerializers.dll* is generated in the output folder.</span></span> <span data-ttu-id="b1fc6-124">Wenn das Tool die Assembly nicht generieren kann, werden Warnungen in der Buildausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-124">If the tool failed to generate the assembly, you'll see warnings in the build output.</span></span>

7. <span data-ttu-id="b1fc6-125">Starten Sie den WCF-Dienst, indem Sie z.B. `http://localhost:2561/Service1.svc` im Browser ausführen.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-125">Start the WCF service by, for example, running `http://localhost:2561/Service1.svc` in the browser.</span></span> <span data-ttu-id="b1fc6-126">Starten Sie dann die Client-Anwendung; sie wird automatisch geladen und verwendet die zuvor generierten Serialisierungsmodule zur Runtime.</span><span class="sxs-lookup"><span data-stu-id="b1fc6-126">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
