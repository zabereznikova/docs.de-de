---
title: 'Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse'
description: Hier erfahren Sie, wie Sie eine Ressource wie eine Webseite oder eine Datei von einem Server anfordern, indem Sie die WebRequest-Klasse im .NET Framework verwenden.
ms.date: 03/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
ms.openlocfilehash: 5dcc1a7dad226288e3f74969b86e2dd457c0eed0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502469"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a><span data-ttu-id="325e6-103">Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="325e6-103">How to: Request data by using the WebRequest class</span></span>

<span data-ttu-id="325e6-104">Das folgende Verfahren beschreibt die Schritte zum Anfordern einer Ressource von einem Server, wie z.B. einer Webseite oder Datei.</span><span class="sxs-lookup"><span data-stu-id="325e6-104">The following procedure describes the steps to request a resource, such as a Web page or a file, from a server.</span></span> <span data-ttu-id="325e6-105">Die Ressource muss von einem URI identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="325e6-105">The resource must be identified by a URI.</span></span>

## <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="325e6-106">Anfordern von Daten von einem Hostserver</span><span class="sxs-lookup"><span data-stu-id="325e6-106">To request data from a host server</span></span>

1. <span data-ttu-id="325e6-107">Erstellen Sie eine <xref:System.Net.WebRequest>-Instanz, indem Sie <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> mit dem URI einer Ressource aufrufen.</span><span class="sxs-lookup"><span data-stu-id="325e6-107">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource.</span></span> <span data-ttu-id="325e6-108">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="325e6-108">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("https://docs.microsoft.com");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("https://docs.microsoft.com")
    ```

    > [!NOTE]
    > <span data-ttu-id="325e6-109">.NET Framework stellt von den Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitete protokollspezifische Klassen für URIs bereit, die mit *http:* , *https:* , *ftp:* und *file:* beginnen.</span><span class="sxs-lookup"><span data-stu-id="325e6-109">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="325e6-110">Wenn Sie protokollspezifische Eigenschaften festlegen oder lesen müssen, wandeln Sie Ihr <xref:System.Net.WebRequest>- oder <xref:System.Net.WebResponse>-Objekt in einen protokollspezifischen Objekttyp um.</span><span class="sxs-lookup"><span data-stu-id="325e6-110">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="325e6-111">Weitere Informationen finden Sie unter [Programmieren austauschbarer Protokolle](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="325e6-111">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="325e6-112">Legen Sie alle Eigenschaftswerte, die Sie benötigen, in Ihrem `WebRequest`-Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="325e6-112">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="325e6-113">Legen Sie z.B. zum Aktivieren der Authentifizierung die Eigenschaft <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> auf eine Instanz der <xref:System.Net.NetworkCredential>-Klasse fest:</span><span class="sxs-lookup"><span data-stu-id="325e6-113">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="325e6-114">Senden Sie die Anforderung an den Server durch Aufrufen von <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="325e6-114">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="325e6-115">Diese Methode gibt ein Objekt zurück, das die Antwort des Servers enthält.</span><span class="sxs-lookup"><span data-stu-id="325e6-115">This method returns an object containing the server's response.</span></span> <span data-ttu-id="325e6-116">Der Typ des zurückgegebenen <xref:System.Net.WebResponse>-Objekts wird durch das URI-Schema der Anforderung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="325e6-116">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="325e6-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="325e6-117">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

4. <span data-ttu-id="325e6-118">Sie können die protokollspezifischen Eigenschaften lesen, indem Sie auf die Eigenschaften des `WebResponse`-Objekts zugreifen oder das Objekt in eine protokollspezifische Instanz umwandeln.</span><span class="sxs-lookup"><span data-stu-id="325e6-118">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="325e6-119">Wandeln Sie z.B. das `WebResponse`-Objekt in einen `HttpWebResponse`-Verweis um, wenn Sie auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebResponse> zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="325e6-119">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an `HttpWebResponse` reference.</span></span> <span data-ttu-id="325e6-120">Das folgende Codebeispiel zeigt die Vorgehensweise beim Anzeigen der HTTP-spezifischen Eigenschaft <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType>, die mit einer Antwort gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="325e6-120">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)
    ```

5. <span data-ttu-id="325e6-121">Zum Abrufen des Datenstroms, der die vom Server gesendeten Antwortdaten enthält, rufen Sie die <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="325e6-121">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="325e6-122">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="325e6-122">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

6. <span data-ttu-id="325e6-123">Nachdem Sie die Daten des Antwortobjekts gelesen haben, können Sie entweder das Objekt mit der <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType>-Methode oder den Antwortdatenstrom mit der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode schließen.</span><span class="sxs-lookup"><span data-stu-id="325e6-123">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="325e6-124">Wird weder das Antwortobjekt noch der Datenstrom geschlossen, verfügt die Anwendung möglicherweise nicht mehr über genügend Serververbindungen und kann somit weitere Anforderungen nicht mehr verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="325e6-124">If you don't close either the response object or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="325e6-125">Da die `WebResponse.Close`-Methode beim Schließen der Antwort `Stream.Close` aufruft, ist das Aufrufen von `Close` für Antwort- und Datenstromobjekt nicht notwendig (aber auch nicht schädlich).</span><span class="sxs-lookup"><span data-stu-id="325e6-125">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="325e6-126">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="325e6-126">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="325e6-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="325e6-127">Example</span></span>

<span data-ttu-id="325e6-128">Im folgenden Codebeispiel wird die Vorgehensweise beim Erstellen einer Anforderung an einen Webserver und dem Lesen der Daten in der Antwort veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="325e6-128">The following code example shows how to create a request to a web server and read the data in its response:</span></span>

[!code-csharp[RequestDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/RequestDataUsingWebRequest/cs/WebRequestGetExample.cs)]
[!code-vb[RequestDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/RequestDataUsingWebRequest/vb/WebRequestGetExample.vb)]

## <a name="see-also"></a><span data-ttu-id="325e6-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="325e6-129">See also</span></span>

- [<span data-ttu-id="325e6-130">Erstellen von Internetanforderungen</span><span class="sxs-lookup"><span data-stu-id="325e6-130">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="325e6-131">Verwenden von Datenströmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="325e6-131">Using Streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="325e6-132">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="325e6-132">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="325e6-133">Anfordern von Daten</span><span class="sxs-lookup"><span data-stu-id="325e6-133">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="325e6-134">How to: Senden von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="325e6-134">How to: Send data by using the WebRequest class</span></span>](how-to-send-data-using-the-webrequest-class.md)
