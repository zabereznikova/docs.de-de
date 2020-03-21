---
title: 'Vorgehensweise: Erstellen eines WCF-Diensts, der über WebSockets kommuniziert'
ms.date: 03/30/2017
ms.assetid: bafbbd89-eab8-4e9a-b4c3-b7b0178e12d8
ms.openlocfilehash: d420ac8fcb98ddec195093be8ae25be37443da4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184976"
---
# <a name="how-to-create-a-wcf-service-that-communicates-over-websockets"></a><span data-ttu-id="8421b-102">Vorgehensweise: Erstellen eines WCF-Diensts, der über WebSockets kommuniziert</span><span class="sxs-lookup"><span data-stu-id="8421b-102">How to: Create a WCF Service that Communicates over WebSockets</span></span>
<span data-ttu-id="8421b-103">WCF-Dienste und -Clients können die <xref:System.ServiceModel.NetHttpBinding>-Bindung verwenden, um über WebSockets zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="8421b-103">WCF services and clients can use the <xref:System.ServiceModel.NetHttpBinding> binding to communicate over WebSockets.</span></span>  <span data-ttu-id="8421b-104">WebSockets werden verwendet, wenn die <xref:System.ServiceModel.NetHttpBinding> bestimmt, dass der Dienstvertrag einen Rückrufvertrag definiert.</span><span class="sxs-lookup"><span data-stu-id="8421b-104">WebSockets will be used when the <xref:System.ServiceModel.NetHttpBinding> determines the service contract defines a callback contract.</span></span> <span data-ttu-id="8421b-105">In diesem Thema wird das Implementieren eines WCF-Diensts und -Clients beschrieben, die mithilfe der <xref:System.ServiceModel.NetHttpBinding> über WebSockets kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="8421b-105">This topic describes how to implement a WCF service and client that uses the <xref:System.ServiceModel.NetHttpBinding> to communicate over WebSockets.</span></span>  
  
### <a name="define-the-service"></a><span data-ttu-id="8421b-106">Definieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="8421b-106">Define the Service</span></span>  
  
1. <span data-ttu-id="8421b-107">Definieren Sie einen Rückrufvertrag.</span><span class="sxs-lookup"><span data-stu-id="8421b-107">Define a callback contract</span></span>  
  
    ```csharp  
    [ServiceContract]  
        public interface IStockQuoteCallback  
        {  
            [OperationContract(IsOneWay = true)]  
            Task SendQuote(string code, double value);  
        }  
    ```  
  
     <span data-ttu-id="8421b-108">Dieser Vertrag wird von der Clientanwendung implementiert, damit der Dienst Nachrichten zurück an den Client senden kann.</span><span class="sxs-lookup"><span data-stu-id="8421b-108">This contract will be implemented by the client application to allow the service to send messages back to the client.</span></span>  
  
2. <span data-ttu-id="8421b-109">Definieren Sie den Dienstvertrag, und geben Sie die `IStockQuoteCallback`-Schnittstelle als Rückrufvertrag an.</span><span class="sxs-lookup"><span data-stu-id="8421b-109">Define the service contract and specify the `IStockQuoteCallback` interface as the callback contract.</span></span>  
  
    ```csharp  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
        public interface IStockQuoteService  
        {  
            [OperationContract(IsOneWay = true)]  
            Task StartSendingQuotes();  
        }  
    ```  
  
3. <span data-ttu-id="8421b-110">Implementieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="8421b-110">Implement the service contract.</span></span>  
  
    ```csharp
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  

            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="8421b-111">Der Dienstvorgang `StartSendingQuotes` wird als asynchroner Aufruf implementiert.</span><span class="sxs-lookup"><span data-stu-id="8421b-111">The service operation `StartSendingQuotes` is implemented as an asynchronous call.</span></span> <span data-ttu-id="8421b-112">Der Rückrufkanal wird mithilfe des `OperationContext` abgerufen, und wenn der Kanal geöffnet ist, wird ein asynchroner Aufruf des Rückrufkanals ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8421b-112">We retrieve the callback channel using the `OperationContext` and if the channel is open, we make an async call on the callback channel.</span></span>  
  
4. <span data-ttu-id="8421b-113">Konfigurieren des Diensts</span><span class="sxs-lookup"><span data-stu-id="8421b-113">Configure the service</span></span>  
  
    ```xml  
    <configuration>  
        <appSettings>  
          <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />
        </appSettings>  
        <system.web>  
          <compilation debug="true" targetFramework="4.5" />
        </system.web>  
        <system.serviceModel>  
            <protocolMapping>  
              <add scheme="http" binding="netHttpBinding"/>  
              <add scheme="https" binding="netHttpsBinding"/>  
            </protocolMapping>  
            <behaviors>  
                <serviceBehaviors>  
                    <behavior name="">  
                        <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                        <serviceDebug includeExceptionDetailInFaults="false" />  
                    </behavior>  
                </serviceBehaviors>  
            </behaviors>  
            <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
                multipleSiteBindingsEnabled="true" />  
        </system.serviceModel>  
    </configuration>  
    ```  
  
     <span data-ttu-id="8421b-114">Die Konfigurationsdatei des Diensts basiert auf WCF-Standardendpunkten.</span><span class="sxs-lookup"><span data-stu-id="8421b-114">The service’s configuration file relies on WCF’s default endpoints.</span></span> <span data-ttu-id="8421b-115">Mit dem `<protocolMapping>`-Abschnitt wird angegeben, dass für die erstellten Standardendpunkte die `NetHttpBinding` verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8421b-115">The `<protocolMapping>` section is used to specify that the `NetHttpBinding` should be used for the default endpoints created.</span></span>  
  
### <a name="define-the-client"></a><span data-ttu-id="8421b-116">Definieren des Clients</span><span class="sxs-lookup"><span data-stu-id="8421b-116">Define the Client</span></span>  
  
1. <span data-ttu-id="8421b-117">Implementieren Sie den Rückrufvertrag.</span><span class="sxs-lookup"><span data-stu-id="8421b-117">Implement the callback contract.</span></span>  
  
    ```csharp  
    private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
    ```  
  
     <span data-ttu-id="8421b-118">Der Rückrufvertragsvorgang wird als asynchrone Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="8421b-118">The callback contract operation is implemented as an asynchronous method.</span></span>  
  
    1. <span data-ttu-id="8421b-119">Implementieren Sie den Clientcode.</span><span class="sxs-lookup"><span data-stu-id="8421b-119">Implement the client code.</span></span>  
  
        ```csharp  
        class Program  
        {  
            static void Main(string[] args)  
            {  
                var context = new InstanceContext(new CallbackHandler());  
                var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
                client.StartSendingQuotes();
                Console.ReadLine();  
            }  
  
            private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
            {  
                public async Task SendQuoteAsync(string code, double value)  
                {  
                    Console.WriteLine("{0}: {1:f2}", code, value);  
                }  
            }  
        }  
        ```  
  
         <span data-ttu-id="8421b-120">Der CallbackHandler wird hier aus Gründen der Übersichtlichkeit wiederholt.</span><span class="sxs-lookup"><span data-stu-id="8421b-120">The CallbackHandler is repeated here for clarity.</span></span> <span data-ttu-id="8421b-121">Die Clientanwendung erstellt einen neuen InstanceContext und gibt die Implementierung der Rückrufschnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="8421b-121">The client application creates a new InstanceContext and specifies the implementation of the callback interface.</span></span> <span data-ttu-id="8421b-122">Danach erstellt sie eine Instanz der Proxyklasse, die einen Verweis an den neu erstellten InstanceContext sendet.</span><span class="sxs-lookup"><span data-stu-id="8421b-122">Next it creates an instance of the proxy class sending a reference to the newly created InstanceContext.</span></span> <span data-ttu-id="8421b-123">Wenn der Client den Dienst aufruft, ruft der Dienst den Client mithilfe des angegebenen Rückrufvertrags auf.</span><span class="sxs-lookup"><span data-stu-id="8421b-123">When the client calls the service, the service will call the client using the callback contract specified.</span></span>  
  
    2. <span data-ttu-id="8421b-124">Konfigurieren des Clients</span><span class="sxs-lookup"><span data-stu-id="8421b-124">Configure the client</span></span>  
  
        ```xml  
        <?xml version="1.0" encoding="utf-8" ?>  
        <configuration>  
            <startup>
                <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
            </startup>  
            <system.serviceModel>  
                <bindings>  
                    <netHttpBinding>  
                        <binding name="NetHttpBinding_IStockQuoteService">  
                            <webSocketSettings transportUsage="Always" />  
                        </binding>  
                    </netHttpBinding>  
                </bindings>  
                <client>  
                    <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                        binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                        contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
                </client>  
            </system.serviceModel>  
        </configuration>  
        ```  
  
         <span data-ttu-id="8421b-125">In der Clientkonfiguration sind keine besonderen Schritte erforderlich. Sie geben einfach den clientseitigen Endpunkt mithilfe der `NetHttpBinding` an.</span><span class="sxs-lookup"><span data-stu-id="8421b-125">There is nothing special you need to do in the client configuration, just specify the client side endpoint using the `NetHttpBinding`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8421b-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8421b-126">Example</span></span>  
 <span data-ttu-id="8421b-127">In Folgenden finden Sie den vollständigen Code, der in diesem Thema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8421b-127">The following is the complete code used in this topic.</span></span>  
  
```csharp  
// IStockQuoteService.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    [ServiceContract(CallbackContract = typeof(IStockQuoteCallback))]  
    public interface IStockQuoteService  
    {  
        [OperationContract(IsOneWay = true)]  
        Task StartSendingQuotes();  
    }  
  
    [ServiceContract]  
    public interface IStockQuoteCallback  
    {  
        [OperationContract(IsOneWay = true)]  
        Task SendQuote(string code, double value);  
    }  
}  
```  
  
```csharp
// StockQuoteService.svc.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Runtime.Serialization;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Server  
{  
    public class StockQuoteService : IStockQuoteService  
    {  
        public async Task StartSendingQuotes()  
        {  
            var callback = OperationContext.Current.GetCallbackChannel<IStockQuoteCallback>();  
            var random = new Random();  
            double price = 29.00;  
  
            while (((IChannel)callback).State == CommunicationState.Opened)  
            {  
                await callback.SendQuote("MSFT", price);  
                price += random.NextDouble();  
                await Task.Delay(1000);  
            }  
        }  
    }  
}  
```  
  
```xml  
<?xml version="1.0"?>  
  
<!--  
  For more information on how to configure your ASP.NET application, please visit  
  https://go.microsoft.com/fwlink/?LinkId=169433  
  -->  
  
<configuration>  
    <appSettings>  
      <add key="aspnet:UseTaskFriendlySynchronizationContext" value="true" />
    </appSettings>  
    <system.web>  
      <compilation debug="true" targetFramework="4.5" />
    </system.web>  
    <system.serviceModel>  
        <protocolMapping>  
          <add scheme="http" binding="netHttpBinding"/>  
          <add scheme="https" binding="netHttpsBinding"/>  
        </protocolMapping>  
        <behaviors>  
            <serviceBehaviors>  
                <behavior name="">  
                    <serviceMetadata httpGetEnabled="true" httpsGetEnabled="true" />  
                    <serviceDebug includeExceptionDetailInFaults="false" />  
                </behavior>  
            </serviceBehaviors>  
        </behaviors>  
        <serviceHostingEnvironment aspNetCompatibilityEnabled="true"  
            multipleSiteBindingsEnabled="true" />  
    </system.serviceModel>  
</configuration>  
```  
  
```
<!-- StockQuoteService.svc -->  
<%@ ServiceHost Language="C#" Debug="true" Service="Server.StockQuoteService" CodeBehind="StockQuoteService.svc.cs" %>  
```  
  
```csharp  
// Client.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.Text;  
using System.Threading.Tasks;  
  
namespace Client  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            var context = new InstanceContext(new CallbackHandler());  
            var client = new StockQuoteServiceReference.StockQuoteServiceClient(context);  
            client.StartSendingQuotes();
            Console.ReadLine();  
        }  
  
        private class CallbackHandler : StockQuoteServiceReference.IStockQuoteServiceCallback  
        {  
            public async Task SendQuoteAsync(string code, double value)  
            {  
                Console.WriteLine("{0}: {1:f2}", code, value);  
            }  
        }  
    }  
}  
```  
  
```xml  
<!--App.config -->  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <startup>
        <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5" />  
    </startup>  
    <system.serviceModel>  
        <bindings>  
            <netHttpBinding>  
                <binding name="NetHttpBinding_IStockQuoteService">  
                    <webSocketSettings transportUsage="Always" />  
                </binding>  
            </netHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="ws://localhost/NetHttpSampleServer/StockQuoteService.svc"  
                binding="netHttpBinding" bindingConfiguration="NetHttpBinding_IStockQuoteService"  
                contract="StockQuoteServiceReference.IStockQuoteService" name="NetHttpBinding_IStockQuoteService" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8421b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8421b-128">See also</span></span>

- [<span data-ttu-id="8421b-129">Synchrone und asynchrone Vorgänge</span><span class="sxs-lookup"><span data-stu-id="8421b-129">Synchronous and Asynchronous Operations</span></span>](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md)
- [<span data-ttu-id="8421b-130">Verwenden der NetHttpBinding</span><span class="sxs-lookup"><span data-stu-id="8421b-130">Using the NetHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/using-the-nethttpbinding.md)
