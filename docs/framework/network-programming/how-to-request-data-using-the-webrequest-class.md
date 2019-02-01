---
title: 'Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse'
ms.date: 03/30/2017
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
ms.openlocfilehash: ac7f9fc4a3c7a376d96d7cf820d2051bf2103e51
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623065"
---
# <a name="how-to-request-data-using-the-webrequest-class"></a><span data-ttu-id="c59f0-102">Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="c59f0-102">How to: Request Data Using the WebRequest Class</span></span>
<span data-ttu-id="c59f0-103">Das folgende Verfahren beschreibt die Schritte zum Anfordern einer Ressource von einem Server, z.B. einer Webseite oder Webdatei.</span><span class="sxs-lookup"><span data-stu-id="c59f0-103">The following procedure describes the steps used to request a resource from a server, for example, a Web page or file.</span></span> <span data-ttu-id="c59f0-104">Die Ressource muss von einem URI identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="c59f0-104">The resource must be identified by a URI.</span></span>  
  
### <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="c59f0-105">Anfordern von Daten von einem Hostserver</span><span class="sxs-lookup"><span data-stu-id="c59f0-105">To request data from a host server</span></span>  
  
1.  <span data-ttu-id="c59f0-106">Erstellen einer <xref:System.Net.WebRequest>-Instanz durch Aufrufen von <xref:System.Net.WebRequest.Create%2A> mit dem URI der Ressource.</span><span class="sxs-lookup"><span data-stu-id="c59f0-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A> with the URI of the resource.</span></span>  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c59f0-107">.NET Framework stellt von **WebRequest** und **WebResponse** abgeleitete protokollspezifische Klassen für URIs bereit, die mit „http:“, „https:“, „ftp:“ und „file:“ beginnen.</span><span class="sxs-lookup"><span data-stu-id="c59f0-107">The .NET Framework provides protocol-specific classes derived from **WebRequest** and **WebResponse** for URIs that begin with "http:", "https:'', "ftp:", and "file:".</span></span> <span data-ttu-id="c59f0-108">Wenn Sie mit anderen Protokollen auf Ressourcen zugreifen möchten, müssen Sie protokollspezifische Klassen implementieren, die von **WebRequest** und **WebResponse** abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="c59f0-108">To access resources using other protocols, you must implement protocol-specific classes that derive from **WebRequest** and **WebResponse**.</span></span> <span data-ttu-id="c59f0-109">Weitere Informationen finden Sie unter [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](../../../docs/framework/network-programming/programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="c59f0-109">For more information, see [Programming Pluggable Protocols](../../../docs/framework/network-programming/programming-pluggable-protocols.md) .</span></span>  
  
2.  <span data-ttu-id="c59f0-110">Legen Sie alle Eigenschaftswerte, die Sie brauchen, in **WebRequest** fest.</span><span class="sxs-lookup"><span data-stu-id="c59f0-110">Set any property values that you need in the **WebRequest**.</span></span> <span data-ttu-id="c59f0-111">Legen Sie z.B. zum Aktivieren der Authentifizierung die Eigenschaft **Anmeldeinformationen** auf eine Instanz der Klasse <xref:System.Net.NetworkCredential> fest.</span><span class="sxs-lookup"><span data-stu-id="c59f0-111">For example, to enable authentication, set the **Credentials** property to an instance of the <xref:System.Net.NetworkCredential> class.</span></span>  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     <span data-ttu-id="c59f0-112">In den meisten Fällen reicht die **WebRequest**-Klasse aus, um Daten zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="c59f0-112">In most cases, the **WebRequest** class is sufficient to receive data.</span></span> <span data-ttu-id="c59f0-113">Wenn Sie dennoch protokollspezifische Eigenschaften festlegen müssen, wandeln Sie **WebRequest** in einen protokollspezifischen Typ um.</span><span class="sxs-lookup"><span data-stu-id="c59f0-113">However, if you need to set protocol-specific properties, you must cast the **WebRequest** to the protocol-specific type.</span></span> <span data-ttu-id="c59f0-114">Wandeln Sie z.B. **WebRequest** in einen **HttpWebRequest**-Verweis um, wenn Sie auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebRequest> zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="c59f0-114">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebRequest>, cast the **WebRequest** to an **HttpWebRequest** reference.</span></span> <span data-ttu-id="c59f0-115">Das folgende Codebeispiel veranschaulicht, wie die HTTP-spezifische Eigenschaft <xref:System.Net.HttpWebRequest.UserAgent%2A> festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="c59f0-115">The following code example shows how to set the HTTP-specific <xref:System.Net.HttpWebRequest.UserAgent%2A> property.</span></span>  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  <span data-ttu-id="c59f0-116">Senden Sie die Anforderung an den Server durch Aufrufen von <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span><span class="sxs-lookup"><span data-stu-id="c59f0-116">To send the request to the server, call <xref:System.Net.HttpWebRequest.GetResponse%2A>.</span></span> <span data-ttu-id="c59f0-117">Der tatsächliche Typ des zurückgegebenen **WebResponse**-Objekts richtet sich nach dem Schema des angeforderten URI.</span><span class="sxs-lookup"><span data-stu-id="c59f0-117">The actual type of the returned **WebResponse** object is determined by the scheme of the requested URI.</span></span>  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="c59f0-118">Wenn Sie ein <xref:System.Net.WebResponse>-Objekt nicht mehr benötigen, schließen Sie es durch Aufrufen der <xref:System.Net.WebResponse.Close%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="c59f0-118">After you are finished with a <xref:System.Net.WebResponse> object, you must close it by calling the <xref:System.Net.WebResponse.Close%2A> method.</span></span> <span data-ttu-id="c59f0-119">Wenn Sie den Antwortdatenstrom vom Antwortobjekt abgerufen haben, können Sie den Datenstrom alternativ dazu auch durch Aufrufen der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode schließen.</span><span class="sxs-lookup"><span data-stu-id="c59f0-119">Alternatively, if you have gotten the response stream from the response object, you can close the stream by calling the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c59f0-120">Wird die Antwort oder der Datenstrom nicht geschlossen, verfügt die Anwendung möglicherweise nicht mehr über genügend Verbindungen mit dem Server und kann somit weitere Anforderungen nicht mehr verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="c59f0-120">If you do not close either the response or the stream, your application can run out of connections to the server and become unable to process additional requests.</span></span>  
  
4.  <span data-ttu-id="c59f0-121">Sie können die protokollspezifischen Eigenschaften lesen, indem Sie auf die Eigenschaften von **WebResponse** zugreifen oder **WebResponse** in eine protokollspezifische Instanz umwandeln.</span><span class="sxs-lookup"><span data-stu-id="c59f0-121">You can access the properties of the **WebResponse** or cast the **WebResponse** to a protocol-specific instance to read protocol-specific properties.</span></span> <span data-ttu-id="c59f0-122">Sie können z.B. auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebResponse> zugreifen, indem Sie **WebRequest** in einen **HttpWebRequest**-Verweis umwandeln.</span><span class="sxs-lookup"><span data-stu-id="c59f0-122">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast the **WebResponse** to a **HttpWebResponse** reference.</span></span> <span data-ttu-id="c59f0-123">Das folgende Codebeispiel zeigt die Vorgehensweise beim Anzeigen von Statusinformationen, die mit einer Antwort gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="c59f0-123">The following code example shows how to display the status information sent with a response.</span></span>  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  <span data-ttu-id="c59f0-124">Zum Abrufen des Datenstroms, der die vom Server gesendeten Antwortdaten enthält, rufen Sie die Methode <xref:System.Net.HttpWebResponse.GetResponseStream%2A> der **WebResponse** auf.</span><span class="sxs-lookup"><span data-stu-id="c59f0-124">To get the stream containing response data sent by the server, use the <xref:System.Net.HttpWebResponse.GetResponseStream%2A> method of the **WebResponse**.</span></span>  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  <span data-ttu-id="c59f0-125">Nachdem Sie die Daten der Antwort gelesen haben, schließen Sie den Antwortdatenstrom entweder mithilfe der **Stream.Close**- oder der **WebResponse.Close**-Methode.</span><span class="sxs-lookup"><span data-stu-id="c59f0-125">After reading the data from the response, you must either close the response stream using the **Stream.Close** method or close the response using the **WebResponse.Close** method.</span></span> <span data-ttu-id="c59f0-126">Es ist zwar nicht notwendig, die **Close**-Methode für sowohl Antwortdatenstrom als auch **WebResponse** aufzurufen, doch es ist auch nicht schädlich.</span><span class="sxs-lookup"><span data-stu-id="c59f0-126">It is not necessary to call the **Close** method on both the response stream and the **WebResponse**, but doing so is not harmful.</span></span> <span data-ttu-id="c59f0-127">**WebResponse.Close** ruft **Stream.Close** beim Schließen der Antwort auf.</span><span class="sxs-lookup"><span data-stu-id="c59f0-127">**WebResponse.Close** calls **Stream.Close** when closing the response.</span></span>  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a><span data-ttu-id="c59f0-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c59f0-128">Example</span></span>  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestGetExample  
    {  
        public static void Main()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create(  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader(dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd();  
            // Display the content.  
            Console.WriteLine(responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close();  
            response.Close();  
        }  
    }  
}  
```  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Net  
Imports System.Text  
Namespace Examples.System.Net  
    Public Class WebRequestGetExample  
  
        Public Shared Sub Main()  
            ' Create a request for the URL.   
            Dim request As WebRequest = _  
              WebRequest.Create("http://www.contoso.com/default.html")  
            ' If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            Dim dataStream As Stream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams and the response.  
            reader.Close()  
            response.Close()  
        End Sub   
    End Class   
End Namespace  
```  
  
## <a name="see-also"></a><span data-ttu-id="c59f0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c59f0-129">See also</span></span>
- [<span data-ttu-id="c59f0-130">Erstellen von Internetanforderungen</span><span class="sxs-lookup"><span data-stu-id="c59f0-130">Creating Internet Requests</span></span>](../../../docs/framework/network-programming/creating-internet-requests.md)
- [<span data-ttu-id="c59f0-131">Verwenden von Datenströmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="c59f0-131">Using Streams on the Network</span></span>](../../../docs/framework/network-programming/using-streams-on-the-network.md)
- [<span data-ttu-id="c59f0-132">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="c59f0-132">Accessing the Internet Through a Proxy</span></span>](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="c59f0-133">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="c59f0-133">Requesting Data</span></span>](../../../docs/framework/network-programming/requesting-data.md)
- [<span data-ttu-id="c59f0-134">Vorgehensweise: Senden von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="c59f0-134">How to: Send Data Using the WebRequest Class</span></span>](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
