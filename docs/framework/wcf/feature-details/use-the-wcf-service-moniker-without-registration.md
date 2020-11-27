---
title: 'Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [WCF], service monikers without registration
ms.assetid: ee3cf5c0-24f0-4ae7-81da-73a60de4a1a8
ms.openlocfilehash: 41761313fae68a1a348a73f104e21dc19e07eb65
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293506"
---
# <a name="how-to-use-the-windows-communication-foundation-service-moniker-without-registration"></a><span data-ttu-id="be28e-102">Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="be28e-102">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>

<span data-ttu-id="be28e-103">Zum Herstellen einer Verbindung mit einem Windows Communication Foundation (WCF)-Dienst muss eine WCF-Client Anwendung über die Details der Dienst Adresse, der Bindungs Konfiguration und des Dienstvertrags verfügen.</span><span class="sxs-lookup"><span data-stu-id="be28e-103">To connect to and communicate with a Windows Communication Foundation (WCF) service, a WCF client application must have the details of the service address, the binding configuration, and the service contract.</span></span>  
  
 <span data-ttu-id="be28e-104">Der WCF-Dienstmoniker ruft in der Regel den erforderlichen Vertrag durch vorherige Registrierung der erforderlichen Attributtypen ab, aber es gibt Fälle, in denen dies nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="be28e-104">The WCF service moniker typically obtains the required contract through prior registration of the required attribute types, but there might be cases where this is not feasible.</span></span> <span data-ttu-id="be28e-105">Anstelle der Registrierung kann der Moniker die Definition des Vertrags in Form eines Web Services Definition Language (WSDL)-Dokuments abrufen. Dies geschieht durch Verwendung des `wsdl`-Parameters, durch Metadatenaustausch oder durch Verwendung des `mexAddress`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="be28e-105">In place of registration, the moniker can obtain the definition of the contract in the form of a Web Services Definition Language (WSDL) document, through the use of the `wsdl` parameter or through Metadata Exchange, through the use of the `mexAddress` parameter.</span></span>  
  
 <span data-ttu-id="be28e-106">Dadurch wird beispielsweise die Verteilung eines Excel-Arbeitsblatts, in dem einige Zellenwerte anhand von Webdienstinteraktionen berechnet werden, ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="be28e-106">This enables scenarios such as the distribution of an Excel spreadsheet where some of the cell values are calculated through Web service interactions.</span></span> <span data-ttu-id="be28e-107">In diesem Szenario kann die Dienstvertragassembly möglicherweise nicht auf allen Clients registriert werden, von denen das Dokument ggf. geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="be28e-107">In this scenario, it might not be feasible to register the service contract assembly on all clients that might open the document.</span></span> <span data-ttu-id="be28e-108">Der `wsdl`-Parameter oder der `mexAddress`-Parameter aktiviert eine in sich geschlossene Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="be28e-108">The `wsdl` parameter or the `mexAddress` parameter enables a self-contained solution.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be28e-109">Gegenseitige Authentifizierung muss verwendet werden, um Schutz vor Anforderungs- und Antwortmanipulation oder Spoofing zu bieten.</span><span class="sxs-lookup"><span data-stu-id="be28e-109">Mutual authentication must be used to protect against request and response tampering or spoofing.</span></span> <span data-ttu-id="be28e-110">Insbesondere benötigen Clients die Gewährleistung, dass es sich beim antwortenden Endpunkt des Metadatenaustauschs um die gewünschte vertrauenswürdige Partei handelt.</span><span class="sxs-lookup"><span data-stu-id="be28e-110">Specifically, it is important for clients to be assured that the Metadata Exchange endpoint that is responding is the intended trusted party.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be28e-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be28e-111">Example</span></span>  

 <span data-ttu-id="be28e-112">In diesem Beispiel wird die Verwendung des Dienstmonikers mit einem MEX-Vertrag veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="be28e-112">This example shows the use of the service moniker with a MEX contract.</span></span> <span data-ttu-id="be28e-113">Ein Dienst mit dem folgenden Vertrag wird mit wsHttpBinding verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="be28e-113">A service with the following contract is exposed with a wsHttpBinding.</span></span>  
  
```csharp
using System.ServiceModel;  
  
// ...
  
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Demo")]  
public interface IAffiliate  
{  
    [OperationContract]  
    bool NewAffiliate(string ID, string company, string fullname, string accountsCode);  
    [OperationContract]  
    bool RemoveAffiliate(string ID);  
    [OperationContract]  
    double RevenueCheckMonthly(ref string ID);  
    [OperationContract]  
    double RevenueCheckTotal(ref string ID);  
}  
```  
  
 <span data-ttu-id="be28e-114">Um einen WCF-Client für den Remote Dienst zu erstellen, kann die folgende Beispielmonikerzeichenfolge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="be28e-114">To construct a WCF client for the remote service the following example moniker string can be used.</span></span>  
  
```
service4:mexAddress="http://servername/Affiliates/service.svc/mex",  
address="http://servername/Affiliates/service.svc",  
contract=IAffiliate, contractNamespace=http://Microsoft.ServiceModel.Demo,  
binding=WSHttpBinding_IAffiliate, bindingNamespace=http://tempuri.org/  
```  
  
 <span data-ttu-id="be28e-115">Während der Ausführung der Clientanwendung führt der Client `WS-MetadataExchange` mit der bereitgestellten `mexAddress` aus.</span><span class="sxs-lookup"><span data-stu-id="be28e-115">During the execution of the client application, the client performs a `WS-MetadataExchange` with the provided `mexAddress`.</span></span> <span data-ttu-id="be28e-116">Dabei werden unter Umständen Adresse, Bindung und Vertragsdetails für eine Reihe von Diensten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="be28e-116">This might return the address, binding and contract details for a number of services.</span></span> <span data-ttu-id="be28e-117">Der `address`-Parameter, der `contract`-Parameter, der `contractNamespace`-Parameter, der `binding`-Parameter und der `bindingNamespace`-Parameter werden zum Identifizieren des gewünschten Diensts verwendet.</span><span class="sxs-lookup"><span data-stu-id="be28e-117">The `address`, `contract`, `contractNamespace`, `binding` and `bindingNamespace` parameters are used to identify the intended service.</span></span> <span data-ttu-id="be28e-118">Nachdem diese Parameter abgeglichen wurden, erstellt der Moniker einen WCF-Client mit der entsprechenden Vertrags Definition, und Aufrufe können dann mithilfe des WCF-Clients wie beim typisierten Vertrag durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="be28e-118">Once those parameters have been matched, the moniker constructs a WCF client with the appropriate contract definition and calls can then be made using the WCF client, as with the typed contract.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="be28e-119">Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="be28e-119">If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error saying "Invalid Syntax".</span></span> <span data-ttu-id="be28e-120">Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="be28e-120">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be28e-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="be28e-121">See also</span></span>

- [<span data-ttu-id="be28e-122">Vorgehensweise: Registrieren und Konfigurieren eines Dienstmonikers</span><span class="sxs-lookup"><span data-stu-id="be28e-122">How to: Register and Configure a Service Moniker</span></span>](how-to-register-and-configure-a-service-moniker.md)
