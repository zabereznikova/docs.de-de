---
title: 'Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fa497567c5cf380d7764499991ad9e7e95a5cbe0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-configure-com-service-settings"></a><span data-ttu-id="58a3c-102">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="58a3c-102">How to: Configure COM+ Service Settings</span></span>
<span data-ttu-id="58a3c-103">Wird eine Anwendungsschnittstelle durch Verwendung des COM+-Dienskonfigurationstools hinzugefügt oder entfernt, wird die Webdienstkonfiguration innerhalb der Konfigurationsdatei der Anwendung aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="58a3c-103">When an application interface is added or removed by using the COM+ Service Configuration tool, the Web service configuration is updated within the application's configuration file.</span></span> <span data-ttu-id="58a3c-104">In der COM+-gehosteten Modus, befindet sich die Datei Application.config im Stammverzeichnis Anwendung (%PROGRAMFILES%\ComPlus Anwendungen\\{Appid} ist die Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="58a3c-104">In the COM+ hosted mode, the Application.config file is placed in the Application Root Directory (%PROGRAMFILES%\ComPlus Applications\\{appid} is the default).</span></span> <span data-ttu-id="58a3c-105">In beiden im Internet gehosteten Modi wird die Datei Web.config im angegebenen vroot-Verzeichnis abgelegt.</span><span class="sxs-lookup"><span data-stu-id="58a3c-105">In either of the Web-hosted modes, the Web.config file is placed in the specified vroot directory.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58a3c-106">Nachrichtensignaturen sollten zum Schutz vor Manipulation von Nachrichten zwischen einem Client und einem Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58a3c-106">Message signing should be used to protect against tampering of messages between a client and a server.</span></span> <span data-ttu-id="58a3c-107">Außerdem sollte Verschlüsselung auf Nachrichten- oder Transportebene verwendet werden, um Schutz vor der Offenlegung von Informationen in Nachrichten zu bieten, die zwischen einem Client und einem Server übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="58a3c-107">Also, message or transport layer encryption should be used to protect against information disclosure from messages between a client and a server.</span></span> <span data-ttu-id="58a3c-108">Ebenso wie bei den [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Diensten wird die Verwendung der Drosselung empfohlen, um die Anzahl der gleichzeitigen Anrufe, Verbindungen, Instanzen und ausstehenden Vorgänge zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="58a3c-108">As with [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services, you should use throttling to limit the number of concurrent calls, connections, instances, and pending operations.</span></span> <span data-ttu-id="58a3c-109">Dies trägt zur Vermeidung einer übermäßigen Ressourcenbeanspruchung bei.</span><span class="sxs-lookup"><span data-stu-id="58a3c-109">This helps prevent over-consumption of resources.</span></span> <span data-ttu-id="58a3c-110">Das Drosselungsverhalten wird durch Dienstkonfigurations-Dateieinstellungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="58a3c-110">Throttling behavior is specified through service configuration file settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="58a3c-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="58a3c-111">Example</span></span>  
 <span data-ttu-id="58a3c-112">Beispiel: Eine Komponente, mit der die folgende Schnittstelle implementiert wird:</span><span class="sxs-lookup"><span data-stu-id="58a3c-112">Consider a component that implements the following interface:</span></span>  
  
```  
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 <span data-ttu-id="58a3c-113">Wird die Komponente als Webdienst verfügbar gemacht, sieht der entsprechende verfügbare Dienstvertrag, dessen Vorgaben die Clients entsprechen müssen, folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="58a3c-113">If the component is exposed as a Web service, the corresponding service contract that is exposed, and that clients would need to conform to, is as follows:</span></span>  
  
```  
[ServiceContract(Session = true,  
Namespace = "http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7",  
Name = "IFinances")]  
public interface IFinancesContract : IDisposable  
{  
    [OperationContract]  
    string Debit(string accountNo, double amount);  
    [OperationContract]  
    string Credit(string accountNo, double amount);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="58a3c-114">IID bildet einen Teil des ursprünglichen Namespaces für den Vertrag.</span><span class="sxs-lookup"><span data-stu-id="58a3c-114">IID forms part of the initial namespace for the contract.</span></span>  
  
 <span data-ttu-id="58a3c-115">Clientanwendungen, die diesen Dienst verwenden, müssen den Vorgaben dieses Vertrags entsprechen und eine Bindung verwenden, die mit der in der Anwendungskonfiguration angegebenen Bindung kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="58a3c-115">Client applications that use this service would need to conform to this contract, along with using a binding that is compatible with the one specified in the application configuration.</span></span>  
  
 <span data-ttu-id="58a3c-116">Das folgende Codebeispiel zeigt eine standardmäßige Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="58a3c-116">The following code example shows a default configuration file.</span></span> <span data-ttu-id="58a3c-117">Als [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Webdienst entspricht diese Datei dem standardmäßigen Konfigurationsschema für Dienstmodelle und kann genauso wie andere [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienstkonfigurationsdateien bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="58a3c-117">Being a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Web service, this conforms to the standard service model configuration schema and can be edited in the same way as other [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services configuration files.</span></span>  
  
 <span data-ttu-id="58a3c-118">Folgende Änderungen sind üblich:</span><span class="sxs-lookup"><span data-stu-id="58a3c-118">Typical modifications would include:</span></span>  
  
-   <span data-ttu-id="58a3c-119">Das Ändern der Endpunktadresse vom standardmäßigen Format Anwendungsname/Komponentenname/Schnittstellenname in eine benutzerfreundlichere Form.</span><span class="sxs-lookup"><span data-stu-id="58a3c-119">Changing the endpoint address from the default ApplicationName/ComponentName/InterfaceName form to a more usable form.</span></span>  
  
-   <span data-ttu-id="58a3c-120">Das Ändern des Dienst-Namespace von der standardmäßigen Form "http://tempuri.org/InterfaceID" in eine aussagekräftigere Form.</span><span class="sxs-lookup"><span data-stu-id="58a3c-120">Modifying the namespace of the service from the default "http://tempuri.org/InterfaceID" form to a more relevant form.</span></span>  
  
-   <span data-ttu-id="58a3c-121">Das Ändern des Endpunkts, um eine andere Transportbindung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="58a3c-121">Changing the endpoint to use a different transport binding.</span></span>  
  
     <span data-ttu-id="58a3c-122">Bei einem Hosting durch COM+ wird standardmäßig der Transport mittels benannter Pipes verwendet, doch es kann auch ein Datentransportprotokoll wie TCP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58a3c-122">In the COM+-hosted case, the named pipes transport is used by default, but an off-machine transport like TCP can be used instead.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="comNonTransactionalBinding" />  
                <binding name="comTransactionalBinding" transactionFlow="true" />  
            </netNamedPipeBinding>  
        </bindings>  
        <comContracts>  
            <comContract contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}"  
                name="IFinances" namespace="http://tempuri.org/C551FBA9-E3AA-4272-8C2A-84BD8D290AC7"  
                requiresSession="true">  
                <exposedMethods>  
                    <add exposedMethod="Debit" />  
                    <add exposedMethod="Credit" />  
                </exposedMethods>  
            </comContract>  
        </comContracts>  
        <services>  
            <service name="{DCDB24CC-0B19-4534-95CD-FBBFF4D67DD9},{C942B840-AD54-4A44-B5F7-928130980AB9}">  
                <endpoint address="IFinances" binding="netNamedPipeBinding" bindingConfiguration="comNonTransactionalBinding"  
                    contract="{C551FBA9-E3AA-4272-8C2A-84BD8D290AC7}" />  
                <host>  
                    <baseAddresses>  
                        <add baseAddress="net.pipe://localhost/ServiceModelDocSampleApp/ServiceModelDocSample.esFinance" />  
                    </baseAddresses>  
                </host>  
            </service>  
        </services>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="58a3c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58a3c-123">See Also</span></span>  
 [<span data-ttu-id="58a3c-124">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="58a3c-124">Integrating with COM+ Applications</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
