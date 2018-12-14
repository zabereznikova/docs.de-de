# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a><span data-ttu-id="64531-101">Verwendung von „dotnet-svcutil.xmlserializer“ in .NET Core</span><span class="sxs-lookup"><span data-stu-id="64531-101">Using dotnet-svcutil.xmlserializer on .NET Core</span></span>

## <a name="prerequisites"></a><span data-ttu-id="64531-102">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="64531-102">Prerequisites</span></span>

<span data-ttu-id="64531-103">Folgendes ist erforderlich, damit „dotnet-svcutil.xmlserializer“ funktioniert.</span><span class="sxs-lookup"><span data-stu-id="64531-103">The following is required for dotnet-svcutil.xmlserializer to work.</span></span> 

* [<span data-ttu-id="64531-104">.NET Core 2.1 SDK oder höher</span><span class="sxs-lookup"><span data-stu-id="64531-104">.NET Core 2.1 SDK or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [<span data-ttu-id="64531-105">.NET Core Runtime 2.1 oder höher</span><span class="sxs-lookup"><span data-stu-id="64531-105">.NET Core Runtime 2.1 or later</span></span>](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)

<span data-ttu-id="64531-106">Sie können mit dem Befehl `dotnet --info` überprüfen, welche Versionen von .NET Core SDK und Runtime Sie bereits installiert haben.</span><span class="sxs-lookup"><span data-stu-id="64531-106">You can use the command `dotnet --info` to check which versions of .NET Core SDK and runtime you already have installed.</span></span>

<span data-ttu-id="64531-107">So verwenden Sie „dotnet-svcutil.xmlserializer“ in einer .NET Core-Konsolenanwendung:</span><span class="sxs-lookup"><span data-stu-id="64531-107">To use dotnet-svcutil.xmlserializer in a .NET Core console application:</span></span>

1. <span data-ttu-id="64531-108">Erstellen Sie einen WCF-Dienst mit dem Namen „MyWCFService“ unter Verwendung der Standardvorlage „WCF Service Application“ unter .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64531-108">Create a WCF Service named 'MyWCFService' using the default template 'WCF Service Application' in .NET Framework.</span></span>  <span data-ttu-id="64531-109">Fügen Sie das ```[XmlSerializerFormat]```-Attribut wie im Folgenden beschrieben der Dienstmethode hinzu.</span><span class="sxs-lookup"><span data-stu-id="64531-109">Add ```[XmlSerializerFormat]``` attribute on the service method like the following</span></span>
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. <span data-ttu-id="64531-110">Erstellen Sie eine .NET Core-Konsolenanwendung als WCF-Clientanwendung für netcoreapp 2.1, erstellen Sie mit dem Befehl z.B. eine App mit dem Namen „MyWCFClient“.</span><span class="sxs-lookup"><span data-stu-id="64531-110">Create a .NET Core console application as WCF client application that targets at netcoreapp 2.1, e.g. create an app named 'MyWCFClient' with the command,</span></span>
    ```
    dotnet new console --name MyWCFClient
    ```
    <span data-ttu-id="64531-111">Stellen Sie sicher, dass Ihre CSPROJ-Datei für eine netcoreapp 2.1 bestimmt ist.</span><span class="sxs-lookup"><span data-stu-id="64531-111">Make sure your csproj targets a netcoreapp 2.1.</span></span> <span data-ttu-id="64531-112">Verwenden Sie hierzu das folgende XML-Element in der CSPROJ-Datei.</span><span class="sxs-lookup"><span data-stu-id="64531-112">This is done using the following XML element in your .csproj file</span></span>
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. <span data-ttu-id="64531-113">Fügen Sie einen Paketverweis auf System.ServiceModel.Http mithilfe des folgenden Befehls hinzu:</span><span class="sxs-lookup"><span data-stu-id="64531-113">Add a package reference to System.ServiceModel.Http by running the following command:</span></span>
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

4. <span data-ttu-id="64531-114">Fügen Sie den WCF Client-Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="64531-114">Add the WCF Client code:</span></span>
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
5. <span data-ttu-id="64531-115">Bearbeiten Sie die CSPROJ-Datei, und fügen Sie einen Verweis auf das dotnet-svcutil.xmlserializer-Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="64531-115">Edit the .csproj file and add a reference to the dotnet-svcutil.xmlserializer package.</span></span> <span data-ttu-id="64531-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="64531-116">For example:</span></span>

    <span data-ttu-id="64531-117">i.</span><span class="sxs-lookup"><span data-stu-id="64531-117">i.</span></span> <span data-ttu-id="64531-118">Führen Sie den Befehl aus: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span><span class="sxs-lookup"><span data-stu-id="64531-118">Run command: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`</span></span>

    <span data-ttu-id="64531-119">ii.</span><span class="sxs-lookup"><span data-stu-id="64531-119">ii.</span></span> <span data-ttu-id="64531-120">Fügen Sie die folgenden Zeilen in „MyWCFClient.csproj“ hinzu.</span><span class="sxs-lookup"><span data-stu-id="64531-120">Add the following lines in MyWCFClient.csproj,</span></span>
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. <span data-ttu-id="64531-121">Erstellen Sie die Anwendung durch Ausführen von `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="64531-121">Build the application by running `dotnet build`.</span></span> <span data-ttu-id="64531-122">Wenn alle Vorgänge erfolgreich ausgeführt werden, wird eine Assembly mit dem Namen MyApp.XmlSerializers.dll im Ausgabeordner generiert.</span><span class="sxs-lookup"><span data-stu-id="64531-122">If everything succeeds, an assembly named MyWCFClient.XmlSerializers.dll will be generated in the output folder.</span></span> <span data-ttu-id="64531-123">Wenn das Tool die Assembly nicht generieren kann, werden Warnungen in der Buildausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64531-123">You will see warnings in the build output if the tool failed to generate the assembly.</span></span>

7. <span data-ttu-id="64531-124">Starten Sie den WCF-Dienst z.B. durch Ausführen von http://localhost:2561/Service1.svc im Browser.</span><span class="sxs-lookup"><span data-stu-id="64531-124">Start the WCF service e.g. by running http://localhost:2561/Service1.svc in the browser.</span></span> <span data-ttu-id="64531-125">Starten Sie dann die Client-Anwendung; sie wird automatisch geladen und verwendet die zuvor generierten Serialisierungsmodule zur Runtime.</span><span class="sxs-lookup"><span data-stu-id="64531-125">Then start the client application, and it will automatically load and use the pre-generated serializers at runtime.</span></span>
