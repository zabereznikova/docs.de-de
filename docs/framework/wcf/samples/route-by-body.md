---
title: Routen nach Text
ms.date: 03/30/2017
ms.assetid: 07a6fc3b-c360-42e0-b663-3d0f22cf4502
ms.openlocfilehash: 3f6be962db2d07bef3a7adc714e9f4e72d621d37
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172314"
---
# <a name="route-by-body"></a><span data-ttu-id="569ef-102">Routen nach Text</span><span class="sxs-lookup"><span data-stu-id="569ef-102">Route by Body</span></span>
<span data-ttu-id="569ef-103">In diesem Beispiel wird das Implementieren eines Diensts veranschaulicht, der Nachrichtenobjekte mit einer beliebigen SOAP-Aktion annimmt.</span><span class="sxs-lookup"><span data-stu-id="569ef-103">This sample demonstrates how to implement a service that accepts message objects with any SOAP action.</span></span> <span data-ttu-id="569ef-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , das einen rechnerdienst implementiert.</span><span class="sxs-lookup"><span data-stu-id="569ef-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="569ef-105">Der Dienst implementiert einen einzelnen `Calculate`-Vorgang, der einen <xref:System.ServiceModel.Channels.Message>-Anforderungsparameter annimmt und eine <xref:System.ServiceModel.Channels.Message>-Antwort zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="569ef-105">The service implements a single `Calculate` operation that accepts a <xref:System.ServiceModel.Channels.Message> request parameter and returns a <xref:System.ServiceModel.Channels.Message> response.</span></span>  
  
 <span data-ttu-id="569ef-106">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird in IIS gehostet.</span><span class="sxs-lookup"><span data-stu-id="569ef-106">In this sample, the client is a console application (.exe) and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="569ef-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="569ef-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="569ef-108">Im Beispiel wird das Senden von Nachrichten auf Grundlage des Textinhalts veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="569ef-108">The sample demonstrates message dispatch based on the body content.</span></span> <span data-ttu-id="569ef-109">Die integrierte Windows Communication Foundation (WCF) Service Model nachrichtensendemechanismus basiert auf Nachrichtenaktionen.</span><span class="sxs-lookup"><span data-stu-id="569ef-109">The built-in Windows Communication Foundation (WCF) service model message dispatch mechanism is based on message Actions.</span></span> <span data-ttu-id="569ef-110">Es gibt jedoch viele vorhandene Webdienste, die alle Vorgänge mit Action="" definieren.</span><span class="sxs-lookup"><span data-stu-id="569ef-110">However, there are many existing Web services that define all of their operations with Action="".</span></span> <span data-ttu-id="569ef-111">Es ist nicht möglich, einen Dienst auf Grundlage von WSDL zu erstellen, der weiter Anforderungsnachrichten auf Grundlage von Action-Informationen sendet.</span><span class="sxs-lookup"><span data-stu-id="569ef-111">It is impossible to build a service based on WSDL that keeps dispatching request messages based on Action information.</span></span> <span data-ttu-id="569ef-112">In diesem Beispiel wird ein Dienstvertrag veranschaulicht, der auf WSDL basiert (WSDL in der im Beispiel eingeschlossenen Datei Service.wsdl).</span><span class="sxs-lookup"><span data-stu-id="569ef-112">This sample demonstrates a service contract that is based on WSDL (the WSDL is contained in Service.wsdl that is included with the sample).</span></span> <span data-ttu-id="569ef-113">Die Dienstvertrag ist Calculator, ähnlich wie mit [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="569ef-113">The service contract is Calculator, similar to the one used in [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="569ef-114">`[OperationContract]` gibt jedoch `Action=""` für alle Vorgänge an.</span><span class="sxs-lookup"><span data-stu-id="569ef-114">However the `[OperationContract]` specifies `Action=""` for all operations.</span></span>  
  
```  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples"),    
                 XmlSerializerFormat, DispatchByBodyBehavior]  
    public interface ICalculator  
    {  
        [OperationContract(Action="")]  
        double Add(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Subtract(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Multiply(double n1, double n2);  
        [OperationContract(Action = "")]  
        double Divide(double n1, double n2);  
    }  
```  
  
 <span data-ttu-id="569ef-115">Wenn ein Vertrag vorliegt, erfordert ein Dienst das benutzerdefinierte Sendeverhalten `DispatchByBodyBehavior`, damit die Nachrichten zwischen Vorgängen gesendet werden können.</span><span class="sxs-lookup"><span data-stu-id="569ef-115">Given a contract, a service requires custom dispatch behavior `DispatchByBodyBehavior` to allow messages to be dispatched between operations.</span></span> <span data-ttu-id="569ef-116">Dieses Sendeverhalten initialisiert die `DispatchByBodyElementOperationSelector` benutzerdefinierte Vorgangsauswahl mit einer Tabelle der Vorgangsnamen, die nach Argumentnamen geordnet QName der entsprechenden Elemente.</span><span class="sxs-lookup"><span data-stu-id="569ef-116">This dispatch behavior initializes the `DispatchByBodyElementOperationSelector` custom operation selector with a table of the operation names keyed by QName of respective wrapper elements.</span></span> `DispatchByBodyElementOperationSelector` <span data-ttu-id="569ef-117">Sucht nach dem Starttag des ersten untergeordneten Elements des Texts, und wählt den Vorgang anhand der zuvor erwähnten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="569ef-117">looks at the start tag of the first child of the Body and selects the operation using the table previously mentioned.</span></span>  
  
 <span data-ttu-id="569ef-118">Der Client verwendet einen Proxy aus der vom Dienst mit exportierten WSDL automatisch generierten [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="569ef-118">The client uses a proxy auto-generated from the WSDL exported by the service using [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
```  
svcutil.exe  /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples /uxs http://localhost/servicemodelsamples/service.svc?wsdl /out:generatedProxy.cs  
```  
  
 <span data-ttu-id="569ef-119">Dass die Aktionen aller Vorgänge leer sind, hat keine Auswirkungen auf den Clientcode, mit Ausnahme der Action-Parameter im automatisch generierten Proxy.</span><span class="sxs-lookup"><span data-stu-id="569ef-119">The fact that actions of all operations are empty has no impact on the client code, except for the Action parameters in the auto-generated proxy.</span></span>  
  
 <span data-ttu-id="569ef-120">Der Clientcode führt mehrere Berechnungen aus.</span><span class="sxs-lookup"><span data-stu-id="569ef-120">The client code performs several calculations.</span></span> <span data-ttu-id="569ef-121">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="569ef-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="569ef-122">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="569ef-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100, 15.99) = 115.99  
Subtract(145, 76.54) = 68.46  
Multiply(9, 81.25) = 731.25  
Divide(22, 7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="569ef-123">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="569ef-123">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="569ef-124">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="569ef-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="569ef-125">Um die Projektmappe zu erstellen, folgen Sie den Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="569ef-125">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="569ef-126">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="569ef-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="569ef-127">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="569ef-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="569ef-128">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="569ef-128">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="569ef-129">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="569ef-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="569ef-130">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="569ef-130">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Interop\RouteByBody`  
