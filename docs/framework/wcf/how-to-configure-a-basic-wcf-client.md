---
title: 'Gewusst wie: Konfigurieren eines grundlegenden Windows Communication Foundation-Clients'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c9ee75734349210ac9379aaf30523a98c4a14f94
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="a853c-102">Gewusst wie: Konfigurieren eines grundlegenden Windows Communication Foundation-Clients</span><span class="sxs-lookup"><span data-stu-id="a853c-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>
<span data-ttu-id="a853c-103">Dies ist die fünfte von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]-Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a853c-103">This is the fifth of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="a853c-104">Einen Überblick über alle sechs Aufgaben finden Sie unter der [Lernprogramm für erste Schritte](../../../docs/framework/wcf/getting-started-tutorial.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="a853c-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="a853c-105">Dieses Thema Disuccess die Clientkonfigurationsdatei, die generiert wurde, mit der Funktion "Dienstverweis hinzufügen" des [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] oder [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="a853c-105">This topic disuccess the client configuration file that was generated using the Add Service Reference functionality of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="a853c-106">Für die Konfiguration des Clients muss der Endpunkt angegeben werden, den der Client verwendet, um auf den Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a853c-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="a853c-107">Ein Endpunkt hat eine Adresse, eine Bindung und einen Vertrag. Bei der Konfiguration eines Clients muss jedes dieser Elemente angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a853c-107">An endpoint has an address, a binding and a contract, and each of these must be specified in the process of configuring the client.</span></span>  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a><span data-ttu-id="a853c-108">So konfigurieren Sie einen Windows Communication Foundation-Client</span><span class="sxs-lookup"><span data-stu-id="a853c-108">To configure a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="a853c-109">Öffnen Sie die generierte Konfigurationsdatei (App.config) aus dem GettingStartedClient-Projekt.</span><span class="sxs-lookup"><span data-stu-id="a853c-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="a853c-110">Im folgenden Beispiel wird der Inhalt der generierten Konfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a853c-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="a853c-111">Klicken Sie unter der [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Abschnitt aus, suchen Sie die [ \<Endpunkt >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) Element.</span><span class="sxs-lookup"><span data-stu-id="a853c-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     <span data-ttu-id="a853c-112">In diesem Beispiel wird der Endpunkt konfiguriert, den der Client verwendet, um auf den unter der Adresse http://localhost:8000/ServiceModelSamples/Service/CalculatorService zu findenden Dienst zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="a853c-112">This example configures the endpoint that the client uses to access the service that is located at the following address: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span></span>  
  
     <span data-ttu-id="a853c-113">Das Endpunktelement gibt an, dass für die Kommunikation zwischen dem WCF-Client und dem Dienst der `ServiceReference1.ICalculator`-Dienstvertrag verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a853c-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="a853c-114">Der WCF-Kanal mit der vom System bereitgestellten konfiguriert ist <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span><span class="sxs-lookup"><span data-stu-id="a853c-114">The WCF channel is configured with the system-provided <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span></span> <span data-ttu-id="a853c-115">Dieser Vertrag wurde mithilfe der Visual Studio-Funktion Dienstverweis hinzufügen generiert.</span><span class="sxs-lookup"><span data-stu-id="a853c-115">This contract was generated by using Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="a853c-116">Es handelt sich eigentlich um eine Kopie des Vertrags, der im GettingStartedLib-Projekt definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="a853c-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="a853c-117">Die <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>-Bindung gibt HTTP als Transport, interoperable Sicherheit und weitere Einzelheiten der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a853c-117">The <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="a853c-118">zum Verwenden des generierten Clients mit dieser Konfiguration finden Sie unter [Vorgehensweise: Verwenden Sie einen Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="a853c-118"> how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a853c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a853c-119">See Also</span></span>  
 [<span data-ttu-id="a853c-120">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="a853c-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="a853c-121">ServiceModel Metadata Utility-Tool (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="a853c-121">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="a853c-122">Vorgehensweise: Erstellen eines Clients</span><span class="sxs-lookup"><span data-stu-id="a853c-122">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="a853c-123">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="a853c-123">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="a853c-124">Selbsthosting</span><span class="sxs-lookup"><span data-stu-id="a853c-124">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
