# <a name="using-dotnet-svcutilxmlserializer-on-net-core"></a>Verwendung von „dotnet-svcutil.xmlserializer“ in .NET Core

## <a name="prerequisites"></a>Erforderliche Komponenten

Folgendes ist erforderlich, damit „dotnet-svcutil.xmlserializer“ funktioniert. 

* [.NET Core 2.1 SDK oder höher](https://www.microsoft.com/net/download/dotnet-core/sdk-2.1.300)
* [.NET Core Runtime 2.1 oder höher](https://www.microsoft.com/net/download/dotnet-core/runtime-2.1.0)

Sie können mit dem Befehl `dotnet --info` überprüfen, welche Versionen von .NET Core SDK und Runtime Sie bereits installiert haben.

So verwenden Sie „dotnet-svcutil.xmlserializer“ in einer .NET Core-Konsolenanwendung:

1. Erstellen Sie einen WCF-Dienst mit dem Namen „MyWCFService“ unter Verwendung der Standardvorlage „WCF Service Application“ unter .NET Framework.  Fügen Sie das ```[XmlSerializerFormat]```-Attribut wie im Folgenden beschrieben der Dienstmethode hinzu.
    ```c#
    [ServiceContract]
    public interface IService1
    {
        [XmlSerializerFormat]
        [OperationContract(Action = "http://tempuri.org/IService1/GetData", ReplyAction = "http://tempuri.org/IService1/GetDataResponse")]
        string GetData(int value);
    }
    ```
2. Erstellen Sie eine .NET Core-Konsolenanwendung als WCF-Clientanwendung für netcoreapp 2.1, erstellen Sie mit dem Befehl z.B. eine App mit dem Namen „MyWCFClient“.
    ```
    dotnet new console --name MyWCFClient
    ```
    Stellen Sie sicher, dass Ihre CSPROJ-Datei für eine netcoreapp 2.1 bestimmt ist. Verwenden Sie hierzu das folgende XML-Element in der CSPROJ-Datei.
    ```xml
    <TargetFramework>netcoreapp2.1</TargetFramework>
    ```
3. Fügen Sie einen Paketverweis auf System.ServiceModel.Http mithilfe des folgenden Befehls hinzu:
   
   ```dotnet add package System.ServiceModel.Http -v 4.5.0```

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
5. Bearbeiten Sie die CSPROJ-Datei, und fügen Sie einen Verweis auf das dotnet-svcutil.xmlserializer-Paket hinzu. Beispiel:

    i. Führen Sie den Befehl aus: `dotnet add package dotnet-svcutil.xmlserializer -v 1.0.0`

    ii. Fügen Sie die folgenden Zeilen in „MyWCFClient.csproj“ hinzu.
    ```xml
    <ItemGroup>
      <DotNetCliToolReference Include="dotnet-svcutil.xmlserializer" Version="1.0.0" />
    </ItemGroup>
    ```

6. Erstellen Sie die Anwendung durch Ausführen von `dotnet build`. Wenn alle Vorgänge erfolgreich ausgeführt werden, wird eine Assembly mit dem Namen MyApp.XmlSerializers.dll im Ausgabeordner generiert. Wenn das Tool die Assembly nicht generieren kann, werden Warnungen in der Buildausgabe angezeigt.

7. Starten Sie den WCF-Dienst z.B. durch Ausführen von http://localhost:2561/Service1.svc im Browser. Starten Sie dann die Client-Anwendung; sie wird automatisch geladen und verwendet die zuvor generierten Serialisierungsmodule zur Runtime.
