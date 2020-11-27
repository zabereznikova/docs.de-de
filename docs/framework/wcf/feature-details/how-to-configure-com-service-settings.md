---
title: 'Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen'
ms.date: 03/30/2017
helpviewer_keywords:
- COM+ [WCF], configuring service settings
ms.assetid: f42a55a8-3af8-4394-9fdd-bf12a93780eb
ms.openlocfilehash: b75f5c2a64b7184959e929439893b33193aa7bae
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257469"
---
# <a name="how-to-configure-com-service-settings"></a><span data-ttu-id="051bd-102">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="051bd-102">How to: Configure COM+ Service Settings</span></span>

<span data-ttu-id="051bd-103">Wird eine Anwendungsschnittstelle durch Verwendung des COM+-Dienskonfigurationstools hinzugefügt oder entfernt, wird die Webdienstkonfiguration innerhalb der Konfigurationsdatei der Anwendung aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="051bd-103">When an application interface is added or removed by using the COM+ Service Configuration tool, the Web service configuration is updated within the application's configuration file.</span></span> <span data-ttu-id="051bd-104">Im gehosteten com+-Modus wird die Application.config-Datei im Stammverzeichnis der Anwendung abgelegt (%ProgramFiles%\ComPlus Applications \\ {AppID} ist die Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="051bd-104">In the COM+ hosted mode, the Application.config file is placed in the Application Root Directory (%PROGRAMFILES%\ComPlus Applications\\{appid} is the default).</span></span> <span data-ttu-id="051bd-105">In beiden im Internet gehosteten Modi wird die Datei Web.config im angegebenen vroot-Verzeichnis abgelegt.</span><span class="sxs-lookup"><span data-stu-id="051bd-105">In either of the Web-hosted modes, the Web.config file is placed in the specified vroot directory.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="051bd-106">Nachrichtensignaturen sollten zum Schutz vor Manipulation von Nachrichten zwischen einem Client und einem Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="051bd-106">Message signing should be used to protect against tampering of messages between a client and a server.</span></span> <span data-ttu-id="051bd-107">Außerdem sollte Verschlüsselung auf Nachrichten- oder Transportebene verwendet werden, um Schutz vor der Offenlegung von Informationen in Nachrichten zu bieten, die zwischen einem Client und einem Server übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="051bd-107">Also, message or transport layer encryption should be used to protect against information disclosure from messages between a client and a server.</span></span> <span data-ttu-id="051bd-108">Wie bei den Windows Communication Foundation (WCF)-Diensten sollten Sie die Drosselung verwenden, um die Anzahl gleichzeitiger Aufrufe, Verbindungen, Instanzen und ausstehende Vorgänge einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="051bd-108">As with Windows Communication Foundation (WCF) services, you should use throttling to limit the number of concurrent calls, connections, instances, and pending operations.</span></span> <span data-ttu-id="051bd-109">Dies trägt zur Vermeidung einer übermäßigen Ressourcenbeanspruchung bei.</span><span class="sxs-lookup"><span data-stu-id="051bd-109">This helps prevent over-consumption of resources.</span></span> <span data-ttu-id="051bd-110">Das Drosselungsverhalten wird durch Dienstkonfigurations-Dateieinstellungen angegeben.</span><span class="sxs-lookup"><span data-stu-id="051bd-110">Throttling behavior is specified through service configuration file settings.</span></span>  
  
## <a name="example"></a><span data-ttu-id="051bd-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="051bd-111">Example</span></span>  

 <span data-ttu-id="051bd-112">Beispiel: Eine Komponente, mit der die folgende Schnittstelle implementiert wird:</span><span class="sxs-lookup"><span data-stu-id="051bd-112">Consider a component that implements the following interface:</span></span>  
  
```csharp
[Guid("C551FBA9-E3AA-4272-8C2A-84BD8D290AC7")]  
public interface IFinances  
{  
    string Debit(string accountNo, double amount);  
    string Credit(string accountNo, double amount);  
}  
```  
  
 <span data-ttu-id="051bd-113">Wird die Komponente als Webdienst verfügbar gemacht, sieht der entsprechende verfügbare Dienstvertrag, dessen Vorgaben die Clients entsprechen müssen, folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="051bd-113">If the component is exposed as a Web service, the corresponding service contract that is exposed, and that clients would need to conform to, is as follows:</span></span>  
  
```csharp
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
> <span data-ttu-id="051bd-114">IID bildet einen Teil des ursprünglichen Namespaces für den Vertrag.</span><span class="sxs-lookup"><span data-stu-id="051bd-114">IID forms part of the initial namespace for the contract.</span></span>  
  
 <span data-ttu-id="051bd-115">Clientanwendungen, die diesen Dienst verwenden, müssen den Vorgaben dieses Vertrags entsprechen und eine Bindung verwenden, die mit der in der Anwendungskonfiguration angegebenen Bindung kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="051bd-115">Client applications that use this service would need to conform to this contract, along with using a binding that is compatible with the one specified in the application configuration.</span></span>  
  
 <span data-ttu-id="051bd-116">Das folgende Codebeispiel zeigt eine standardmäßige Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="051bd-116">The following code example shows a default configuration file.</span></span> <span data-ttu-id="051bd-117">Da es sich um einen Windows Communication Foundation (WCF)-Webdienst handelt, entspricht dieser dem Standard Konfigurations Schema des Dienst Modells und kann auf die gleiche Weise wie andere Konfigurationsdateien für WCF-Dienste bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="051bd-117">Being a Windows Communication Foundation (WCF) Web service, this conforms to the standard service model configuration schema and can be edited in the same way as other WCF services configuration files.</span></span>  
  
 <span data-ttu-id="051bd-118">Folgende Änderungen sind üblich:</span><span class="sxs-lookup"><span data-stu-id="051bd-118">Typical modifications would include:</span></span>  
  
- <span data-ttu-id="051bd-119">Das Ändern der Endpunktadresse vom standardmäßigen Format Anwendungsname/Komponentenname/Schnittstellenname in eine benutzerfreundlichere Form.</span><span class="sxs-lookup"><span data-stu-id="051bd-119">Changing the endpoint address from the default ApplicationName/ComponentName/InterfaceName form to a more usable form.</span></span>  
  
- <span data-ttu-id="051bd-120">Ändern des Namespaces des Dienstanbieter von der Standard `http://tempuri.org/InterfaceID` Form in eine relevantere Form.</span><span class="sxs-lookup"><span data-stu-id="051bd-120">Modifying the namespace of the service from the default `http://tempuri.org/InterfaceID` form to a more relevant form.</span></span>  
  
- <span data-ttu-id="051bd-121">Das Ändern des Endpunkts, um eine andere Transportbindung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="051bd-121">Changing the endpoint to use a different transport binding.</span></span>  
  
     <span data-ttu-id="051bd-122">Bei einem Hosting durch COM+ wird standardmäßig der Transport mittels benannter Pipes verwendet, doch es kann auch ein Datentransportprotokoll wie TCP verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="051bd-122">In the COM+-hosted case, the named pipes transport is used by default, but an off-machine transport like TCP can be used instead.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="051bd-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="051bd-123">See also</span></span>

- [<span data-ttu-id="051bd-124">Integration in com+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="051bd-124">Integrating with COM+ Applications</span></span>](integrating-with-com-plus-applications.md)
