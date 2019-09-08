---
title: Zugreifen auf den Dienst mit einem Webbrowser (WCF Data Services-Schnellstart)
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: eb7f1c97722b45a93c310fb8bcbdb42beece2553
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780541"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="27120-102">Zugreifen auf den Dienst mit einem Webbrowser (WCF Data Services-Schnellstart)</span><span class="sxs-lookup"><span data-stu-id="27120-102">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="27120-103">Dies ist die zweite Aufgabe des WCF Data Services Schnellstarts.</span><span class="sxs-lookup"><span data-stu-id="27120-103">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="27120-104">In dieser Aufgabe starten Sie den WCF Data Services aus Visual Studio und deaktivieren optional das Lesen von Feeds im Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="27120-104">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="27120-105">Anschließend rufen Sie das Dienst Definitions Dokument ab und greifen auf Datendienst Ressourcen zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser an die verfügbar gemachten Ressourcen senden.</span><span class="sxs-lookup"><span data-stu-id="27120-105">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="27120-106">Standardmäßig weist Visual Studio dem `localhost`-URI auf dem Computer automatisch eine Portnummer zu.</span><span class="sxs-lookup"><span data-stu-id="27120-106">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="27120-107">Für diese Aufgabe wird in den URI-Beispielen die Portnummer `12345` verwendet.</span><span class="sxs-lookup"><span data-stu-id="27120-107">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="27120-108">Weitere Informationen zum Festlegen einer bestimmten Portnummer in Ihrem Visual Studio-Projekt finden Sie unter [Erstellen des Daten Dienstanbieter](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="27120-108">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="27120-109">So fordern Sie das Standarddienstdokument mithilfe von Internet Explorer an</span><span class="sxs-lookup"><span data-stu-id="27120-109">To request the default service document by using Internet Explorer</span></span>

1. <span data-ttu-id="27120-110">Wählen Sie in Internet Explorer im **Menü Extras** die **Option Internet Optionen**aus, klicken Sie auf die Registerkarte **Inhalt** , klicken Sie auf **Einstellungen**, und deaktivieren Sie **Feed-Anzeige**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="27120-110">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="27120-111">Dadurch wird sichergestellt, dass das Lesen von Feeds deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="27120-111">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="27120-112">Wenn Sie diese Funktionalität nicht deaktivieren, behandelt der Webbrowser das zurückgegebene AtomPub-codierte Dokument als XML-Feed, statt die unformatierten XML-Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27120-112">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="27120-113">Wenn der Browser den Feed nicht als unformatierte XML-Daten anzeigen kann, sollten es dennoch möglich sein, den Feed als Quellcode der Seite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="27120-113">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2. <span data-ttu-id="27120-114">Drücken Sie in Visual Studio die Taste **F5** , um mit dem Debuggen der Anwendung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="27120-114">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3. <span data-ttu-id="27120-115">Öffnen Sie auf dem lokalen Computer einen Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="27120-115">Open a Web browser on the local computer.</span></span> <span data-ttu-id="27120-116">Geben Sie in der Adressleiste den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="27120-116">In the address bar, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="27120-117">Dadurch wird das Standarddienstdokument zurückgegeben, das eine Liste von Entitätenmengen enthält, die von diesem Datendienst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="27120-117">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="27120-118">So greifen Sie auf Entitätenmengenressourcen in einem Webbrowser zu</span><span class="sxs-lookup"><span data-stu-id="27120-118">To access entity set resources from a Web browser</span></span>

1. <span data-ttu-id="27120-119">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="27120-119">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="27120-120">Dadurch wird ein Satz aller Kunden in der Northwind-Beispieldatenbank zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27120-120">This returns a set of all customers in the Northwind sample database.</span></span>

2. <span data-ttu-id="27120-121">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="27120-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="27120-122">Dadurch wird eine Entitätsinstanz für einen bestimmten Kunden, `ALFKI`, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="27120-122">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3. <span data-ttu-id="27120-123">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="27120-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="27120-124">Dadurch wird die Beziehung zwischen Kunden und Bestellungen durchlaufen, um einen Satz aller Bestellungen für den Kunden `ALFKI` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="27120-124">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4. <span data-ttu-id="27120-125">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="27120-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="27120-126">Dadurch werden Bestellungen gefiltert, die zum Kunden `ALFKI` gehören, sodass auf der Grundlage des angegebenen `OrderID`-Werts nur eine bestimmte Bestellung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="27120-126">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="27120-127">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="27120-127">Next Steps</span></span>

<span data-ttu-id="27120-128">Sie haben erfolgreich auf die WCF Data Services über einen Webbrowser zugegriffen, wobei der Browser HTTP GET-Anforderungen an angegebene Ressourcen ausgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="27120-128">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="27120-129">Mithilfe eines Webbrowsers können Sie leicht mit der Adressierungssyntax von Anforderungen experimentieren und die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="27120-129">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="27120-130">Auf einen Produktionsdatendienst wird jedoch im Allgemeinen nicht mit dieser Methode zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="27120-130">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="27120-131">Normalerweise interagieren Anwendungen mit dem Datendienst über Anwendungscode oder Skriptsprachen.</span><span class="sxs-lookup"><span data-stu-id="27120-131">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="27120-132">Als Nächstes erstellen Sie eine Clientanwendung, die Clientbibliotheken verwendet, um auf Datendienstressourcen zuzugreifen, als ob sie Common Language Runtime (CLR)-Objekte wären:</span><span class="sxs-lookup"><span data-stu-id="27120-132">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="27120-133">Erstellen der .NET Framework-Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="27120-133">Creating the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="27120-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="27120-134">See also</span></span>

- [<span data-ttu-id="27120-135">Zugreifen auf Datendienstressourcen</span><span class="sxs-lookup"><span data-stu-id="27120-135">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
