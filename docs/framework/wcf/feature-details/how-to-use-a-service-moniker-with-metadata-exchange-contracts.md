---
title: "Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c41a07e5-cb9d-45d6-9ea4-34511e227faf
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31720b0639f9be68a2124b4ff844a2837787ef81
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-a-service-moniker-with-metadata-exchange-contracts"></a><span data-ttu-id="49640-102">Vorgehensweise: Verwenden eines Dienstmonikers mit Metadatenaustausch-Verträgen</span><span class="sxs-lookup"><span data-stu-id="49640-102">How to: Use a Service Moniker with Metadata Exchange Contracts</span></span>
<span data-ttu-id="49640-103">Nach dem Entwickeln neuer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste können Sie entscheiden, ob das Aufrufen dieser Dienste aus einem Skript oder einer Visual Basic 6.0-Anwendung möglich sein soll.</span><span class="sxs-lookup"><span data-stu-id="49640-103">After developing some new [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services, you may decide that you want to be able to call these services from a script or a Visual Basic 6.0 application.</span></span> <span data-ttu-id="49640-104">Eine mögliche Methode ist das Generieren einer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly, das Registrieren der Assembly bei COM, das Installieren der Assembly im GAC und anschließend das Verweisen der COM-Typen aus dem Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="49640-104">One method would be to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly, register the assembly with COM, install the assembly in the GAC, and then reference the COM types from your Visual Basic code.</span></span> <span data-ttu-id="49640-105">Wenn Sie die Anwendung verteilen, müssen Sie auch die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly verteilen.</span><span class="sxs-lookup"><span data-stu-id="49640-105">When you distribute the application, you will have to distribute the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Client assembly as well.</span></span> <span data-ttu-id="49640-106">Der Benutzer muss dann die WCF-Clientassembly bei COM registrieren und im GAC platzieren.</span><span class="sxs-lookup"><span data-stu-id="49640-106">The user will then have to register the WCF client assembly with COM and place it in the GAC.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="49640-107">-COM-Interop ermöglicht Ihnen die gleichen Dienstaufrufe ohne eine [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly.</span><span class="sxs-lookup"><span data-stu-id="49640-107"> COM Interop also allows you to make the same service calls without relying on a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly.</span></span> <span data-ttu-id="49640-108">Mithilfe des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Monikers können Sie einen beliebigen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst aus jeder COM-kompatiblen Sprache (Visual Basic, VBScript, Visual Basic for Applications (VBA) usw.) aufrufen, indem Sie einen Metadatenaustausch (MEX)-Endpunkt-URI angeben, den der Dienstmoniker zum Extrahieren von Typinformationen über den Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="49640-108">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker allows you to call any [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service from any COM-compatible language (Visual Basic, VBScript, Visual Basic for Applications (VBA), and so on) by specifying a metadata exchange (Mex) endpoint URI that the service moniker uses to extract type information about the service.</span></span> <span data-ttu-id="49640-109">In diesem Thema wird beschrieben, wie das Beispiel für Erste Schritte mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unter Verwendung eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Monikers aufgerufen wird, der einen MEX-Endpunkt angibt.</span><span class="sxs-lookup"><span data-stu-id="49640-109">This topic describes how to call the Getting Started [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sample using a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] moniker that specifies a Mex endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="49640-110">Die von der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clientassembly definierten Typen werden nie tatsächlich instanziiert.</span><span class="sxs-lookup"><span data-stu-id="49640-110">The types defined by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly are never actually instantiated.</span></span> <span data-ttu-id="49640-111">Die Assembly wird nur für Metadaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="49640-111">The assembly is used only for metadata.</span></span>  
  
### <a name="using-the-service-moniker-with-a-mex-address"></a><span data-ttu-id="49640-112">Verwenden des Dienstmonikers mit einer MEX-Adresse</span><span class="sxs-lookup"><span data-stu-id="49640-112">Using the service moniker with a Mex address</span></span>  
  
1.  <span data-ttu-id="49640-113">Erstellen Sie das Beispiel für Erste Schritte, und wechseln Sie in Internet Explorer zu seiner URL (http://localhost/ServiceModelSamples/Service.svc), um sicherzustellen, dass der Dienst funktioniert.</span><span class="sxs-lookup"><span data-stu-id="49640-113">Build the Getting Started sample and use Internet Explorer to browse to its URL (http://localhost/ServiceModelSamples/Service.svc) to ensure that the service is working.</span></span>  
  
2.  <span data-ttu-id="49640-114">Erstellen Sie ein Visual Basic-Skript oder eine Visual Basic-Anwendung, die den folgenden Code enthält:</span><span class="sxs-lookup"><span data-stu-id="49640-114">Create a Visual Basic script or Visual Basic application that contains the following code:</span></span>  
  
    ```  
    monString = "service:mexaddress=http://localhost/ServiceModelSamples/Service.svc/MEX"  
    monString = monString + ", address=http://localhost/ServiceModelSamples/Service.svc"  
    monString = monString + ", contract=ICalculator, contractNamespace=http://Microsoft.ServiceModel.Samples"  
    monString = monString + ", binding=WSHttpBinding_ICalculator, bindingNamespace=http://Microsoft.ServiceModel.Samples"  
  
    Set calc = GetObject(monString)  
    MsgBox calc.Add(3, 4)  
    ```  
  
3.  <span data-ttu-id="49640-115">Führen Sie die Visual Basic-Anwendung oder das Skript aus.</span><span class="sxs-lookup"><span data-stu-id="49640-115">Run the Visual Basic application or script.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49640-116">Der Dienst, den Sie aufrufen, muss einen MEX-Endpunkt für den Moniker verfügbar machen, damit dieser die Metadaten aus dem Dienst lesen kann.</span><span class="sxs-lookup"><span data-stu-id="49640-116">The service you are calling must expose a Mex endpoint for the moniker to be able to read the metadata from the service.</span></span> <span data-ttu-id="49640-117">Weitere Informationen finden Sie unter [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span><span class="sxs-lookup"><span data-stu-id="49640-117">For more information, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="49640-118">Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49640-118">If the moniker is malformed or if the service is unavailable, the call to `GetObject` will return an error saying "Invalid Syntax."</span></span>  <span data-ttu-id="49640-119">Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="49640-119">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49640-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49640-120">See Also</span></span>  
 [<span data-ttu-id="49640-121">Vorgehensweise: Verwenden der Windows Communication Foundation-Dienstmonikers ohne Registrierung</span><span class="sxs-lookup"><span data-stu-id="49640-121">How to: Use the Windows Communication Foundation Service Moniker without Registration</span></span>](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 [<span data-ttu-id="49640-122">Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen</span><span class="sxs-lookup"><span data-stu-id="49640-122">How to: Use a Service Moniker with WSDL Contracts</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)
