---
title: Zugreifen auf den Dienst mit einem Webbrowser (WCF Data Services-Schnellstart)
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: b7fcead5eed2dd4c0c779d9a881563a39f88d094
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33364004"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="6e893-102">Zugreifen auf den Dienst mit einem Webbrowser (WCF Data Services-Schnellstart)</span><span class="sxs-lookup"><span data-stu-id="6e893-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>
<span data-ttu-id="6e893-103">In dieser Aufgabe starten Sie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] aus Visual Studio und deaktivieren optional das Feedlesen im Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="6e893-103">In this task, you will start the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="6e893-104">Sie werden dann Dienstdokuments Definition abrufen sowie greifen auf datendienstressourcen von HTTP-GET-Anforderungen über einen Webbrowser auf die verfügbar gemachten Ressourcen senden.</span><span class="sxs-lookup"><span data-stu-id="6e893-104">You will then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e893-105">Standardmäßig weist Visual Studio dem `localhost`-URI auf dem Computer automatisch eine Portnummer zu.</span><span class="sxs-lookup"><span data-stu-id="6e893-105">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="6e893-106">Für diese Aufgabe wird in den URI-Beispielen die Portnummer `12345` verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e893-106">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="6e893-107">Weitere Informationen dazu, wie Sie in Visual Studio-Projekt eine bestimmte Portnummer festlegen finden Sie unter [Erstellen des Datendiensts](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="6e893-107">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](../../../../docs/framework/data/wcf/creating-the-data-service.md).</span></span>  
  
### <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="6e893-108">So fordern Sie das Standarddienstdokument mithilfe von Internet Explorer an</span><span class="sxs-lookup"><span data-stu-id="6e893-108">To request the default service document by using Internet Explorer</span></span>  
  
1.  <span data-ttu-id="6e893-109">In Internet Explorer aus der **Tools** klicken Sie im Menü **Internetoptionen**, klicken Sie auf die **Content** Registerkarte, klicken Sie auf **Einstellungen**, und Deaktivieren von  **Aktivieren Sie feed anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6e893-109">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>  
  
     <span data-ttu-id="6e893-110">Dadurch wird sichergestellt, dass das Lesen von Feeds deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6e893-110">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="6e893-111">Wenn Sie diese Funktionalität nicht deaktivieren, behandelt der Webbrowser das zurückgegebene AtomPub-codierte Dokument als XML-Feed, statt die unformatierten XML-Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e893-111">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6e893-112">Wenn der Browser den Feed nicht als unformatierte XML-Daten anzeigen kann, sollten es dennoch möglich sein, den Feed als Quellcode der Seite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e893-112">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>  
  
2.  <span data-ttu-id="6e893-113">Drücken Sie in Visual Studio die F5-TASTE, um die Anwendung zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="6e893-113">In Visual Studio, press the F5 key to start debugging the application.</span></span>  
  
3.  <span data-ttu-id="6e893-114">Öffnen Sie auf dem lokalen Computer einen Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="6e893-114">Open a Web browser on the local computer.</span></span> <span data-ttu-id="6e893-115">Geben Sie in der Adressleiste den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="6e893-115">In the address bar, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc  
    ```  
  
     <span data-ttu-id="6e893-116">Dadurch wird das Standarddienstdokument zurückgegeben, das eine Liste von Entitätenmengen enthält, die von diesem Datendienst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="6e893-116">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>  
  
### <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="6e893-117">So greifen Sie auf Entitätenmengenressourcen in einem Webbrowser zu</span><span class="sxs-lookup"><span data-stu-id="6e893-117">To access entity set resources from a Web browser</span></span>  
  
1.  <span data-ttu-id="6e893-118">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="6e893-118">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers  
    ```  
  
     <span data-ttu-id="6e893-119">Dadurch wird ein Satz aller Kunden in der Northwind-Beispieldatenbank zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6e893-119">This returns a set of all customers in the Northwind sample database.</span></span>  
  
2.  <span data-ttu-id="6e893-120">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="6e893-120">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')  
    ```  
  
     <span data-ttu-id="6e893-121">Dadurch wird eine Entitätsinstanz für einen bestimmten Kunden, `ALFKI`, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6e893-121">This returns an entity instance for the specific customer, `ALFKI`.</span></span>  
  
3.  <span data-ttu-id="6e893-122">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="6e893-122">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders  
    ```  
  
     <span data-ttu-id="6e893-123">Dadurch wird die Beziehung zwischen Kunden und Bestellungen durchlaufen, um einen Satz aller Bestellungen für den Kunden `ALFKI` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6e893-123">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>  
  
4.  <span data-ttu-id="6e893-124">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="6e893-124">In the address bar of your Web browser, enter the following URI:</span></span>  
  
    ```  
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643  
    ```  
  
     <span data-ttu-id="6e893-125">Dadurch werden Bestellungen gefiltert, die zum Kunden `ALFKI` gehören, sodass auf der Grundlage des angegebenen `OrderID`-Werts nur eine bestimmte Bestellung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6e893-125">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6e893-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6e893-126">Next Steps</span></span>  
 <span data-ttu-id="6e893-127">Sie haben erfolgreich in einem Webbrowser auf [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] zugegriffen, wobei der Browser HTTP GET-Anforderungen an angegebene Ressourcen ausgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="6e893-127">You have successfully accessed the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="6e893-128">Mithilfe eines Webbrowsers können Sie leicht mit der Adressierungssyntax von Anforderungen experimentieren und die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6e893-128">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="6e893-129">Auf einen Produktionsdatendienst wird jedoch im Allgemeinen nicht mit dieser Methode zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="6e893-129">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="6e893-130">Normalerweise interagieren Anwendungen mit dem Datendienst über Anwendungscode oder Skriptsprachen.</span><span class="sxs-lookup"><span data-stu-id="6e893-130">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="6e893-131">Als Nächstes erstellen Sie eine Clientanwendung, die Clientbibliotheken verwendet, um auf Datendienstressourcen zuzugreifen, als ob sie Common Language Runtime (CLR)-Objekte wären:</span><span class="sxs-lookup"><span data-stu-id="6e893-131">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>  
  
 [<span data-ttu-id="6e893-132">Erstellen der .NET Framework-Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="6e893-132">Creating the .NET Framework Client Application</span></span>](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
  
## <a name="see-also"></a><span data-ttu-id="6e893-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e893-133">See Also</span></span>  
 [<span data-ttu-id="6e893-134">Zugreifen auf Datendienstressourcen</span><span class="sxs-lookup"><span data-stu-id="6e893-134">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
