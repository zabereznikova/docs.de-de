---
title: 'Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen'
ms.date: 03/30/2017
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
ms.openlocfilehash: 8894fdc4fd085b9d55a8fc25043e5258c306024c
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143477"
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="75f75-102">Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen</span><span class="sxs-lookup"><span data-stu-id="75f75-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="75f75-103">Nachdem Sie einige neue WCF-Dienste entwickelt haben, können Sie entscheiden, ob Sie in der Lage sein möchten, diese Dienste aus einem Skript oder einer Visual Basic 6,0-Anwendung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="75f75-103">After developing some new WCF services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="75f75-104">Eine Methode wäre das Generieren einer WCF-Clientassembly, das Registrieren der Assembly bei com, das Installieren der Assembly im GAC und das anschließende verweisen auf die COM-Typen aus dem Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="75f75-104">One method would be to generate a WCF client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="75f75-105">Wenn Sie die Anwendung verteilen, müssen Sie die WCF-Clientassembly ebenfalls verteilen.</span><span class="sxs-lookup"><span data-stu-id="75f75-105">When you distribute the application, you will have to distribute the WCF Client assembly as well.</span></span> <span data-ttu-id="75f75-106">Der Benutzer muss dann die WCF-Clientassembly bei COM registrieren und im GAC platzieren.</span><span class="sxs-lookup"><span data-stu-id="75f75-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> <span data-ttu-id="75f75-107">Mit WCF COM Interop können Sie auch dieselben Dienst Aufrufe ausführen, ohne sich auf eine WCF-Clientassembly verlassen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="75f75-107">WCF COM Interop also allows you to make the same service calls without relying on a WCF client assembly.</span></span> <span data-ttu-id="75f75-108">Der WCF-Moniker ermöglicht das Aufrufen eines beliebigen WCF-Dienstanbieter von jeder com-kompatiblen Sprache (Visual Basic, VBScript, Visual Basic for Applications (VBA) usw.) durch Angabe eines MEX-Endpunkt-URIs (Metadata Exchange), der vom Dienstmoniker zum Extrahieren von Typinformationen über den Dienst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="75f75-108">The WCF moniker allows you to call any WCF service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="75f75-109">In diesem Thema wird beschrieben, wie das Beispiel für die ersten Schritte mit einem WCF-Moniker aufgerufen wird, der einen MEX-Endpunkt angibt.</span><span class="sxs-lookup"><span data-stu-id="75f75-109">This topic describes how to call the Getting Started WCF sample using a WCF moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75f75-110">Die von der WCF-Clientassembly definierten Typen werden nie tatsächlich instanziiert.</span><span class="sxs-lookup"><span data-stu-id="75f75-110">The types defined by the WCF client assembly are never actually instantiated.</span></span> <span data-ttu-id="75f75-111">Die Assembly wird nur für Metadaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="75f75-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="75f75-112">Verwenden des Dienstmonikers mit einer MEX-Adresse</span><span class="sxs-lookup"><span data-stu-id="75f75-112">Using the service moniker with a Mex address</span></span>  
  
1. <span data-ttu-id="75f75-113">Erstellen Sie das Beispiel "Getting Started", und verwenden Sie Internet Explorer, um die URL () zu suchen und `http://localhost/ServiceModelSamples/Service.svc` sicherzustellen, dass der Dienst funktioniert.</span><span class="sxs-lookup"><span data-stu-id="75f75-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (`http://localhost/ServiceModelSamples/Service.svc`) to ensure that the service is working.</span></span>  
  
2. <span data-ttu-id="75f75-114">Erstellen Sie ein Visual Basic-Skript oder eine Visual Basic-Anwendung, die den folgenden Code enthält:</span><span class="sxs-lookup"><span data-stu-id="75f75-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```vb
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3. <span data-ttu-id="75f75-115">Führen Sie die Visual Basic-Anwendung oder das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="75f75-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="75f75-116">Der Dienst, den Sie aufrufen, muss einen MEX-Endpunkt für den Moniker verfügbar machen, damit dieser die Metadaten aus dem Dienst lesen kann.</span><span class="sxs-lookup"><span data-stu-id="75f75-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="75f75-117">Weitere Informationen finden Sie unter Gewusst [wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="75f75-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="75f75-118">Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="75f75-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="75f75-119">Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="75f75-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75f75-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75f75-120">See also</span></span>

- [<span data-ttu-id="75f75-121">Vorgehensweise: Verwenden des Windows Communication Foundation-Dienstmonikers ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="75f75-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)
- [<span data-ttu-id="75f75-122">Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen</span><span class="sxs-lookup"><span data-stu-id="75f75-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
