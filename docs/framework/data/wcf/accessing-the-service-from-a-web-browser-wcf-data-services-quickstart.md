---
title: Zugreifen auf den Dienst mit einem Webbrowser (WCF Data Services-Schnellstart)
description: Erfahren Sie, wie Sie WCF Data Services in Visual Studio starten und das Lesen von Feeds in einem Browser deaktivieren. Abrufen des Dienst Definitions Dokuments und Zugreifen auf Datendienst Ressourcen.
ms.date: 03/30/2017
ms.assetid: 5a6fa180-3094-4e6e-ba2b-8c80975d18d1
ms.openlocfilehash: 713436c31bc3f622c4f44a83e33fff3fcbba1c1c
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247777"
---
# <a name="accessing-the-service-from-a-web-browser-wcf-data-services-quickstart"></a><span data-ttu-id="958cf-104">Zugreifen auf den Dienst mit einem Webbrowser (WCF Data Services-Schnellstart)</span><span class="sxs-lookup"><span data-stu-id="958cf-104">Accessing the Service from a Web Browser (WCF Data Services Quickstart)</span></span>

<span data-ttu-id="958cf-105">Dies ist die zweite Aufgabe des WCF Data Services Schnellstarts.</span><span class="sxs-lookup"><span data-stu-id="958cf-105">This is the second task of the WCF Data Services quickstart.</span></span> <span data-ttu-id="958cf-106">In dieser Aufgabe starten Sie den WCF Data Services aus Visual Studio und deaktivieren optional das Lesen von Feeds im Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="958cf-106">In this task, you start the WCF Data Services from Visual Studio and optionally disable feed reading in the Web browser.</span></span> <span data-ttu-id="958cf-107">Anschließend rufen Sie das Dienst Definitions Dokument ab und greifen auf Datendienst Ressourcen zu, indem Sie HTTP GET-Anforderungen über einen Webbrowser an die verfügbar gemachten Ressourcen senden.</span><span class="sxs-lookup"><span data-stu-id="958cf-107">You then retrieve the service definition document as well as access data service resources by submitting HTTP GET requests through a Web browser to the exposed resources.</span></span>

> [!NOTE]
> <span data-ttu-id="958cf-108">Standardmäßig weist Visual Studio dem `localhost`-URI auf dem Computer automatisch eine Portnummer zu.</span><span class="sxs-lookup"><span data-stu-id="958cf-108">By default, Visual Studio auto-assigns a port number to the `localhost` URI on your computer.</span></span> <span data-ttu-id="958cf-109">Für diese Aufgabe wird in den URI-Beispielen die Portnummer `12345` verwendet.</span><span class="sxs-lookup"><span data-stu-id="958cf-109">This task uses the port number `12345` in the URI examples.</span></span> <span data-ttu-id="958cf-110">Weitere Informationen zum Festlegen einer bestimmten Portnummer in Ihrem Visual Studio-Projekt finden Sie unter [Erstellen des Daten Dienstanbieter](creating-the-data-service.md).</span><span class="sxs-lookup"><span data-stu-id="958cf-110">For more information about how to set a specific port number in your Visual Studio project see [Creating the Data Service](creating-the-data-service.md).</span></span>

## <a name="to-request-the-default-service-document-by-using-internet-explorer"></a><span data-ttu-id="958cf-111">So fordern Sie das Standarddienstdokument mithilfe von Internet Explorer an</span><span class="sxs-lookup"><span data-stu-id="958cf-111">To request the default service document by using Internet Explorer</span></span>

1. <span data-ttu-id="958cf-112">Wählen Sie in Internet Explorer im **Menü Extras** die **Option Internet Optionen**aus, klicken Sie auf die Registerkarte **Inhalt** , klicken Sie auf **Einstellungen**, und deaktivieren Sie **Feed-Anzeige**aktivieren.</span><span class="sxs-lookup"><span data-stu-id="958cf-112">In Internet Explorer, from the **Tools** menu, select **Internet Options**, click the **Content** tab, click **Settings**, and clear **Turn on feed viewing**.</span></span>

     <span data-ttu-id="958cf-113">Dadurch wird sichergestellt, dass das Lesen von Feeds deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="958cf-113">This makes sure that feed reading is disabled.</span></span> <span data-ttu-id="958cf-114">Wenn Sie diese Funktionalität nicht deaktivieren, behandelt der Webbrowser das zurückgegebene AtomPub-codierte Dokument als XML-Feed, statt die unformatierten XML-Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="958cf-114">If you do not disable this functionality, then the Web browser will treat the returned AtomPub encoded document as an XML feed instead of displaying the raw XML data.</span></span>

    > [!NOTE]
    > <span data-ttu-id="958cf-115">Wenn der Browser den Feed nicht als unformatierte XML-Daten anzeigen kann, sollten es dennoch möglich sein, den Feed als Quellcode der Seite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="958cf-115">If your browser cannot display the feed as raw XML data, you should still be able to view the feed as the source code for the page.</span></span>

2. <span data-ttu-id="958cf-116">Drücken Sie in Visual Studio die Taste **F5** , um mit dem Debuggen der Anwendung zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="958cf-116">In Visual Studio, press the **F5** key to start debugging the application.</span></span>

3. <span data-ttu-id="958cf-117">Öffnen Sie auf dem lokalen Computer einen Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="958cf-117">Open a Web browser on the local computer.</span></span> <span data-ttu-id="958cf-118">Geben Sie in der Adressleiste den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="958cf-118">In the address bar, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc
    ```

     <span data-ttu-id="958cf-119">Dadurch wird das Standarddienstdokument zurückgegeben, das eine Liste von Entitätenmengen enthält, die von diesem Datendienst verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="958cf-119">This returns the default service document, which contains a list of entity sets that are exposed by this data service.</span></span>

## <a name="to-access-entity-set-resources-from-a-web-browser"></a><span data-ttu-id="958cf-120">So greifen Sie auf Entitätenmengenressourcen in einem Webbrowser zu</span><span class="sxs-lookup"><span data-stu-id="958cf-120">To access entity set resources from a Web browser</span></span>

1. <span data-ttu-id="958cf-121">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="958cf-121">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers
    ```

     <span data-ttu-id="958cf-122">Dadurch wird ein Satz aller Kunden in der Northwind-Beispieldatenbank zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="958cf-122">This returns a set of all customers in the Northwind sample database.</span></span>

2. <span data-ttu-id="958cf-123">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="958cf-123">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')
    ```

     <span data-ttu-id="958cf-124">Dadurch wird eine Entitätsinstanz für einen bestimmten Kunden, `ALFKI`, zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="958cf-124">This returns an entity instance for the specific customer, `ALFKI`.</span></span>

3. <span data-ttu-id="958cf-125">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="958cf-125">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders
    ```

     <span data-ttu-id="958cf-126">Dadurch wird die Beziehung zwischen Kunden und Bestellungen durchlaufen, um einen Satz aller Bestellungen für den Kunden `ALFKI` zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="958cf-126">This traverses the relationship between customers and orders to return a set of all orders for the specific customer `ALFKI`.</span></span>

4. <span data-ttu-id="958cf-127">Geben Sie in der Adressleiste des Webbrowsers den folgenden URI ein:</span><span class="sxs-lookup"><span data-stu-id="958cf-127">In the address bar of your Web browser, enter the following URI:</span></span>

    ```http
    http://localhost:12345/northwind.svc/Customers('ALFKI')/Orders?$filter=OrderID eq 10643
    ```

     <span data-ttu-id="958cf-128">Dadurch werden Bestellungen gefiltert, die zum Kunden `ALFKI` gehören, sodass auf der Grundlage des angegebenen `OrderID`-Werts nur eine bestimmte Bestellung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="958cf-128">This filters orders that belong to the specific customer `ALFKI` so that only a specific order is returned based on the supplied `OrderID` value.</span></span>

## <a name="next-steps"></a><span data-ttu-id="958cf-129">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="958cf-129">Next Steps</span></span>

<span data-ttu-id="958cf-130">Sie haben erfolgreich auf die WCF Data Services über einen Webbrowser zugegriffen, wobei der Browser HTTP GET-Anforderungen an angegebene Ressourcen ausgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="958cf-130">You have successfully accessed the WCF Data Services from a Web browser, with the browser issuing HTTP GET requests to specified resources.</span></span> <span data-ttu-id="958cf-131">Mithilfe eines Webbrowsers können Sie leicht mit der Adressierungssyntax von Anforderungen experimentieren und die Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="958cf-131">A Web browser provides an easy way to experiment with the addressing syntax of requests and view the results.</span></span> <span data-ttu-id="958cf-132">Auf einen Produktionsdatendienst wird jedoch im Allgemeinen nicht mit dieser Methode zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="958cf-132">However, a production data service is not generally accessed by this method.</span></span> <span data-ttu-id="958cf-133">Normalerweise interagieren Anwendungen mit dem Datendienst über Anwendungscode oder Skriptsprachen.</span><span class="sxs-lookup"><span data-stu-id="958cf-133">Typically, applications interact with the data service through application code or scripting languages.</span></span> <span data-ttu-id="958cf-134">Als Nächstes erstellen Sie eine Clientanwendung, die Clientbibliotheken verwendet, um auf Datendienstressourcen zuzugreifen, als ob sie Common Language Runtime (CLR)-Objekte wären:</span><span class="sxs-lookup"><span data-stu-id="958cf-134">Next, you will create a client application that uses client libraries to access data service resources as if they were common language runtime (CLR) objects:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="958cf-135">Erstellen der .NET Framework-Clientanwendung</span><span class="sxs-lookup"><span data-stu-id="958cf-135">Creating the .NET Framework Client Application</span></span>](creating-the-dotnet-client-application-wcf-data-services-quickstart.md)

## <a name="see-also"></a><span data-ttu-id="958cf-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="958cf-136">See also</span></span>

- [<span data-ttu-id="958cf-137">Zugreifen auf Datendienstressourcen</span><span class="sxs-lookup"><span data-stu-id="958cf-137">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
