---
title: 'Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen'
ms.date: 03/30/2017
ms.assetid: a88d9650-bb50-4f48-8c85-12f5ce98a83a
ms.openlocfilehash: 70d7e9ff45616f832597ebc48db00198967935c6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601139"
---
# <a name="how-to-use-a-service-moniker-with-wsdl-contracts"></a><span data-ttu-id="b99ef-102">Vorgehensweise: Verwenden eines Dienstmonikers mit WSDL-Verträgen</span><span class="sxs-lookup"><span data-stu-id="b99ef-102">How to: Use a Service Moniker with WSDL Contracts</span></span>
<span data-ttu-id="b99ef-103">Es gibt Situationen, in denen Sie sich möglicherweise einen vollständig unabhängigen COM Interop-Client wünschen.</span><span class="sxs-lookup"><span data-stu-id="b99ef-103">There are situations when you may want to have a completely self-contained COM Interop client.</span></span> <span data-ttu-id="b99ef-104">Der Dienst, den Sie aufrufen möchten, stellt vielleicht keinen MEX-Endpunkt bereit, oder die WCF-Client-DLL ist nicht für COM-Interop registriert.</span><span class="sxs-lookup"><span data-stu-id="b99ef-104">The service you want to call may not expose a MEX endpoint, and the WCF client DLL may not be registered for COM interop.</span></span> <span data-ttu-id="b99ef-105">In diesen Fällen können Sie eine WSDL-Datei erstellen, die den Dienst beschreibt, und die Datei an den WCF-Dienstmoniker übergeben.</span><span class="sxs-lookup"><span data-stu-id="b99ef-105">In these cases, you can create a WSDL file that describes the service and pass it into the WCF service moniker.</span></span> <span data-ttu-id="b99ef-106">In diesem Thema wird beschrieben, wie das Beispiel für Erste Schritte mit WCF zur Verwendung eines WSDL-Monikers in WCF aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b99ef-106">This topic describes how to call the Getting Started WCF sample using a WCF WSDL moniker.</span></span>  
  
### <a name="using-the-wsdl-service-moniker"></a><span data-ttu-id="b99ef-107">Verwenden des WSDL-Dienstmonikers</span><span class="sxs-lookup"><span data-stu-id="b99ef-107">Using the WSDL service moniker</span></span>  
  
1. <span data-ttu-id="b99ef-108">Öffnen und erstellen Sie die GettingStarted-Beispiellösung.</span><span class="sxs-lookup"><span data-stu-id="b99ef-108">Open and build the GettingStarted sample solution.</span></span>  
  
2. <span data-ttu-id="b99ef-109">Öffnen Sie Internet Explorer, und navigieren Sie zu, `http://localhost/ServiceModelSamples/Service.svc` um sicherzustellen, dass der Dienst funktioniert.</span><span class="sxs-lookup"><span data-stu-id="b99ef-109">Open Internet Explorer and browse to `http://localhost/ServiceModelSamples/Service.svc` to make sure that the service is working.</span></span>  
  
3. <span data-ttu-id="b99ef-110">Fügen Sie in der Datei Service.cs der CalculatorService-Klasse das folgende Attribut hinzu:</span><span class="sxs-lookup"><span data-stu-id="b99ef-110">In the Service.cs file, add the following attribute on the CalculatorService class:</span></span>  
  
     [!code-csharp[S_WSDL_Client#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_wsdl_client/cs/service.cs#0)]  
  
4. <span data-ttu-id="b99ef-111">Fügen Sie dem Dienst App.config einen Bindungsnamespace hinzu:</span><span class="sxs-lookup"><span data-stu-id="b99ef-111">Add a binding namespace to the service App.config:</span></span>  

5. <span data-ttu-id="b99ef-112">Erstellen Sie eine WSDL-Datei, die von der Anwendung gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="b99ef-112">Create a WSDL file for the application to read.</span></span> <span data-ttu-id="b99ef-113">Da die-Namespaces in den Schritten 3 und 4 hinzugefügt wurden, können Sie Internet Explorer verwenden, um die gesamte WSDL-Beschreibung des Dienstanbieter abzufragen, indem Sie zu navigieren `http://localhost/ServiceModelSamples/Service.svc?wsdl` .</span><span class="sxs-lookup"><span data-stu-id="b99ef-113">Because the namespaces were added in steps 3 and 4, you can use IE to query for the entire WSDL description of the service by browsing to `http://localhost/ServiceModelSamples/Service.svc?wsdl`.</span></span> <span data-ttu-id="b99ef-114">Sie können die Datei dann in Internet Explorer als serviceWSDL.xml speichern.</span><span class="sxs-lookup"><span data-stu-id="b99ef-114">You can then save the file from Internet Explorer as serviceWSDL.xml.</span></span> <span data-ttu-id="b99ef-115">Wenn Sie die Namespaces nicht in den Schritten 3 und 4 angeben, ist das von der Abfrage der obigen URL zurückgegebene WSDL-Dokument nicht vollständig.</span><span class="sxs-lookup"><span data-stu-id="b99ef-115">If you do not specify the namespaces in steps 3 and 4, the WSDL document returned from querying the above URL will not be the complete WSDL.</span></span> <span data-ttu-id="b99ef-116">Das zurückgegebene WSDL-Dokument enthält verschiedene Importanweisungen, die andere WSDL-Dokumente importieren.</span><span class="sxs-lookup"><span data-stu-id="b99ef-116">The WSDL document returned will include several import statements that import other WSDL documents.</span></span> <span data-ttu-id="b99ef-117">Sie müssen dann die einzelnen Importanweisungen durchgehen und das vollständige WSDL-Dokument erstellen, wobei Sie das vom Dienst zurückgegebene WSDL mit dem importierten WSDL kombinieren.</span><span class="sxs-lookup"><span data-stu-id="b99ef-117">You will have to go through each import statement and build the complete WSDL document, combining the WSDL returned from the service with the WSDL imported.</span></span>  
  
6. <span data-ttu-id="b99ef-118">Öffnen Sie Visual Basic 6.0, und erstellen Sie eine neue Standard-EXE-Datei.</span><span class="sxs-lookup"><span data-stu-id="b99ef-118">Open Visual Basic 6.0 and create a new Standard .exe file.</span></span> <span data-ttu-id="b99ef-119">Fügen Sie dem Formular eine Schaltfläche hinzu, und doppelklicken Sie darauf, um dem Click-Handler den folgenden Code hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b99ef-119">Add a button to the form and double-click the button to add the following code to the Click handler:</span></span>  
  
    ```vb
    ' Open the WSDL contract file and read it all into the wsdlContract string.  
    Const ForReading = 1  
    Set objFSO = CreateObject("Scripting.FileSystemObject")  
    Set objFile = objFSO.OpenTextFile("c:\serviceWsdl.xml", ForReading)  
    wsdlContract = objFile.ReadAll  
    objFile.Close  
  
    ' Create a string for the service moniker including the content of the WSDL contract file.  
    wsdlMonikerString = "service4:address='http://localhost/ServiceModelSamples/service.svc'"  
    wsdlMonikerString = wsdlMonikerString + ", wsdl='" & wsdlContract & "'"  
    wsdlMonikerString = wsdlMonikerString + ", binding=WSHttpBinding_ICalculator, bindingNamespace='http://Microsoft.ServiceModel.Samples'"  
    wsdlMonikerString = wsdlMonikerString + ", contract=ICalculator, contractNamespace='http://Microsoft.ServiceModel.Samples'"  
  
    ' Create the service moniker object.  
    Set wsdlServiceMoniker = GetObject(wsdlMonikerString)  
  
    ' Call the service operations using the moniker object.  
    MsgBox "WSDL service moniker: 145 - 76.54 = " & wsdlServiceMoniker.Subtract(145, 76.54)  
    ```  
  
    > [!NOTE]
    > Ist der Moniker nicht ordnungsgemäß formatiert oder der Dienst nicht verfügbar, wird nach dem `GetObject`-Aufruf ein Syntaxfehler zurückgegeben.  <span data-ttu-id="b99ef-121">Vergewissern Sie sich bei Auftreten dieses Fehlers, dass der verwendete Moniker korrekt und der Dienst verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b99ef-121">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
7. <span data-ttu-id="b99ef-122">Führen Sie die Visual Basic-Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="b99ef-122">Run the Visual Basic application.</span></span> <span data-ttu-id="b99ef-123">Ein Meldungsfeld wird mit den Ergebnissen des Aufrufs Subtract(145, 76.54) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b99ef-123">A message box will be displayed with the results of calling Subtract(145, 76.54).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b99ef-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b99ef-124">See also</span></span>

- [<span data-ttu-id="b99ef-125">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="b99ef-125">Getting Started</span></span>](../samples/getting-started-sample.md)
- [<span data-ttu-id="b99ef-126">Übersicht über die Integration von COM-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="b99ef-126">Integrating with COM Applications Overview</span></span>](integrating-with-com-applications-overview.md)
