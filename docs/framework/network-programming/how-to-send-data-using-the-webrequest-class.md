---
title: 'Vorgehensweise: Senden von Daten mithilfe der WebRequest-Klasse'
ms.date: 03/25/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
ms.openlocfilehash: 2467b289df7a0361b51ad91d4458d32742c42275
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "70040829"
---
# <a name="how-to-send-data-by-using-the-webrequest-class"></a><span data-ttu-id="0714a-102">Vorgehensweise: Senden von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="0714a-102">How to: Send data by using the WebRequest class</span></span>

<span data-ttu-id="0714a-103">In diesem Thema wird die Vorgehensweise beim Senden von Daten an einen Server beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0714a-103">The following procedure describes the steps to send data to a server.</span></span> <span data-ttu-id="0714a-104">Die Prozedur wird häufig verwendet, um einer Webseite Daten bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0714a-104">This procedure is commonly used to post data to a Web page.</span></span>

## <a name="to-send-data-to-a-host-server"></a><span data-ttu-id="0714a-105">Senden von Daten an einen Hostserver</span><span class="sxs-lookup"><span data-stu-id="0714a-105">To send data to a host server</span></span>

1. <span data-ttu-id="0714a-106">Erstellen Sie eine <xref:System.Net.WebRequest>-Instanz, indem Sie <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> mit dem URI einer Ressource aufrufen, die Daten akzeptiert, wie z.B. ein Skript oder eine ASP.NET-Seite.</span><span class="sxs-lookup"><span data-stu-id="0714a-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource, such as a script or ASP.NET page, that accepts data.</span></span> <span data-ttu-id="0714a-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-107">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx")
    ```

    > [!NOTE]
    > <span data-ttu-id="0714a-108">.NET Framework stellt von den Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitete protokollspezifische Klassen für URIs bereit, die mit *http:* , *https:* , *ftp:* und *file:* beginnen.</span><span class="sxs-lookup"><span data-stu-id="0714a-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="0714a-109">Wenn Sie protokollspezifische Eigenschaften festlegen oder lesen müssen, wandeln Sie Ihr <xref:System.Net.WebRequest>- oder <xref:System.Net.WebResponse>-Objekt in einen protokollspezifischen Objekttyp um.</span><span class="sxs-lookup"><span data-stu-id="0714a-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="0714a-110">Weitere Informationen finden Sie unter [Programmieren austauschbarer Protokolle](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="0714a-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="0714a-111">Legen Sie alle Eigenschaftswerte, die Sie benötigen, in Ihrem `WebRequest`-Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="0714a-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="0714a-112">Legen Sie z.B. zum Aktivieren der Authentifizierung die Eigenschaft <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> auf eine Instanz der <xref:System.Net.NetworkCredential>-Klasse fest:</span><span class="sxs-lookup"><span data-stu-id="0714a-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="0714a-113">Geben Sie eine Protokollmethode an, die das Senden von Daten mit einer Anforderung zulässt, wie z.B. die HTTP-Methode `POST`:</span><span class="sxs-lookup"><span data-stu-id="0714a-113">Specify a protocol method that permits data to be sent with a request, such as the HTTP `POST` method:</span></span>

    ```csharp
    request.Method = "POST";
    ```

    ```vb
    request.Method = "POST"
    ```

4. <span data-ttu-id="0714a-114">Legen Sie die Eigenschaft <xref:System.Web.HttpRequest.ContentLength> auf die Anzahl von Bytes fest, die Ihre Anforderung enthält.</span><span class="sxs-lookup"><span data-stu-id="0714a-114">Set the <xref:System.Web.HttpRequest.ContentLength> property to the number of bytes you're including with your request.</span></span> <span data-ttu-id="0714a-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-115">For example:</span></span>

    ```csharp
    request.ContentLength = byteArray.Length;
    ```

    ```vb
    request.ContentLength = byteArray.Length
    ```

5. <span data-ttu-id="0714a-116">Legen Sie für die <xref:System.Web.HttpRequest.ContentType>-Eigenschaft einen geeigneten Wert fest.</span><span class="sxs-lookup"><span data-stu-id="0714a-116">Set the <xref:System.Web.HttpRequest.ContentType> property to an appropriate value.</span></span> <span data-ttu-id="0714a-117">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-117">For example:</span></span>

    ```csharp
    request.ContentType = "application/x-www-form-urlencoded";
    ```

    ```vb
    request.ContentType = "application/x-www-form-urlencoded"
    ```

6. <span data-ttu-id="0714a-118">Rufen Sie den Datenstrom ab, der die Anforderungsdaten enthält, indem Sie die Methode <xref:System.Net.WebRequest.GetRequestStream%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0714a-118">Get the stream that holds request data by calling the <xref:System.Net.WebRequest.GetRequestStream%2A> method.</span></span> <span data-ttu-id="0714a-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-119">For example:</span></span>

    ```csharp
    Stream dataStream = request.GetRequestStream();
    ```

    ```vb
    Dim dataStream As Stream = request.GetRequestStream()
    ```

7. <span data-ttu-id="0714a-120">Schreiben Sie die Daten in das von der `GetRequestStream`-Methode zurückgegebene <xref:System.IO.Stream>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="0714a-120">Write the data to the <xref:System.IO.Stream> object returned by the `GetRequestStream` method.</span></span> <span data-ttu-id="0714a-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-121">For example:</span></span>

    ```csharp
    dataStream.Write(byteArray, 0, byteArray.Length);
    ```

    ```vb
    dataStream.Write(byteArray, 0, byteArray.Length)
    ```

8. <span data-ttu-id="0714a-122">Schließen Sie den Anforderungsdatenstrom durch Aufrufen der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="0714a-122">Close the request stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0714a-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-123">For example:</span></span>

    ```csharp
    dataStream.Close();
    ```

    ```vb
    dataStream.Close()
    ```

9. <span data-ttu-id="0714a-124">Senden Sie die Anforderung an den Server durch Aufrufen von <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0714a-124">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="0714a-125">Diese Methode gibt ein Objekt zurück, das die Antwort des Servers enthält.</span><span class="sxs-lookup"><span data-stu-id="0714a-125">This method returns an object containing the server's response.</span></span> <span data-ttu-id="0714a-126">Der Typ des zurückgegebenen `WebResponse`-Objekts wird durch das URI-Schema der Anforderung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="0714a-126">The returned `WebResponse` object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="0714a-127">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-127">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

10. <span data-ttu-id="0714a-128">Sie können die protokollspezifischen Eigenschaften lesen, indem Sie auf die Eigenschaften des `WebResponse`-Objekts zugreifen oder das Objekt in eine protokollspezifische Instanz umwandeln.</span><span class="sxs-lookup"><span data-stu-id="0714a-128">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="0714a-129">Wandeln Sie z.B. das `WebResponse`-Objekt in einen <xref:System.Net.HttpWebResponse>-Verweis um, wenn Sie auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebResponse> zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="0714a-129">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an <xref:System.Net.HttpWebResponse> reference.</span></span> <span data-ttu-id="0714a-130">Das folgende Codebeispiel zeigt die Vorgehensweise beim Anzeigen der HTTP-spezifischen Eigenschaft <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType>, die mit einer Antwort gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="0714a-130">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine(((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)
    ```

11. <span data-ttu-id="0714a-131">Zum Abrufen des Datenstroms, der die vom Server gesendeten Antwortdaten enthält, rufen Sie die <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>-Methode des `WebResponse`-Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="0714a-131">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method of your `WebResponse` object.</span></span> <span data-ttu-id="0714a-132">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-132">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

12. <span data-ttu-id="0714a-133">Nachdem Sie die Daten des Antwortobjekts gelesen haben, können Sie entweder das Objekt mit der <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType>-Methode oder den Antwortdatenstrom mit der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode schließen.</span><span class="sxs-lookup"><span data-stu-id="0714a-133">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0714a-134">Wird weder die Antwort noch der Datenstrom geschlossen, verfügt die Anwendung möglicherweise nicht mehr über genügend Serververbindungen und kann somit weitere Anforderungen nicht mehr verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0714a-134">If you don't close either the response or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="0714a-135">Da die `WebResponse.Close`-Methode beim Schließen der Antwort `Stream.Close` aufruft, ist das Aufrufen von `Close` für Antwort- und Datenstromobjekt nicht notwendig (aber auch nicht schädlich).</span><span class="sxs-lookup"><span data-stu-id="0714a-135">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="0714a-136">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0714a-136">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="0714a-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0714a-137">Example</span></span>

<span data-ttu-id="0714a-138">Im folgenden Beispiel wird die Vorgehensweise beim Senden von Daten an einen Webserver und dem Lesen der Daten in der Antwort veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="0714a-138">The following example shows how to send data to a web server and read the data in its response:</span></span>

[!code-csharp[SendDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/SendDataUsingWebRequest/cs/WebRequestPostExample.cs)]
[!code-vb[SendDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/SendDataUsingWebRequest/vb/WebRequestPostExample.vb)]

## <a name="see-also"></a><span data-ttu-id="0714a-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0714a-139">See also</span></span>

- [<span data-ttu-id="0714a-140">Erstellen von Internetanforderungen</span><span class="sxs-lookup"><span data-stu-id="0714a-140">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="0714a-141">Verwenden von Datenströmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="0714a-141">Using streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="0714a-142">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="0714a-142">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="0714a-143">Anfordern von Daten</span><span class="sxs-lookup"><span data-stu-id="0714a-143">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="0714a-144">How to: Anfordern von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="0714a-144">How to: Request data by using the WebRequest class</span></span>](how-to-request-data-using-the-webrequest-class.md)
