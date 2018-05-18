---
title: 'Gewusst wie: Senden von Daten mithilfe der WebRequest-Klasse'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WebRequest class, sending data to a host
- Sending data to a host, using WebRequest class
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: a40ab63e0fbac4227d74999c8c83f02e3c9e4b4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-send-data-using-the-webrequest-class"></a>Gewusst wie: Senden von Daten mithilfe der WebRequest-Klasse
In diesem Thema wird die Vorgehensweise zum Senden von Daten an einen Server beschrieben. Die Prozedur wird häufig verwendet, um einer Webseite Daten bereitzustellen.  
  
### <a name="to-send-data-to-a-host-server"></a>Senden von Daten an einen Hostserver  
  
1.  Erstellen Sie eine <xref:System.Net.WebRequest>-Instanz, indem Sie <xref:System.Net.WebRequest.Create%2A> mit dem URI der Ressource aufrufen, die Daten akzeptiert, wie z.B. ein Skript oder eine ASP.NET-Seite.  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
    ```  
  
    > [!NOTE]
    >  .NET Framework stellt von **WebRequest** und **WebResponse** abgeleitete protokollspezifische Klassen für URIs bereit, die mit „http:“, „https:“, „ftp:“ und „file:“ beginnen. Wenn Sie mit anderen Protokollen auf Ressourcen zugreifen möchten, müssen Sie protokollspezifische Klassen implementieren, die von **WebRequest** und **WebResponse** abgeleitet sind. Weitere Informationen finden Sie unter [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
2.  Legen Sie alle Eigenschaftswerte, die Sie brauchen, in **WebRequest** fest. Legen Sie z.B. zum Aktivieren der Authentifizierung die Eigenschaft **Anmeldeinformationen** auf eine Instanz der Klasse <xref:System.Net.NetworkCredential> fest.  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
    ```  
  
     In den meisten Fällen ist die **WebRequest**-Instanz selbst ausreichend, um Daten zu senden. Wenn Sie dennoch protokollspezifische Eigenschaften festlegen müssen, wandeln Sie **WebRequest** in einen protokollspezifischen Typ um. Wandeln Sie z.B. **WebRequest** in einen **HttpWebRequest**-Verweis um, wenn Sie auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebRequest> zugreifen möchten. Das folgende Codebeispiel veranschaulicht, wie die HTTP-spezifische Eigenschaft <xref:System.Net.HttpWebRequest.UserAgent%2A> festgelegt wird.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Geben Sie eine Protokollmethode an, die das Senden von Daten mit einer Anforderung ermöglicht, wie z.B. die HTTP-Methode **POST**.  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  Legen Sie die **ContentLength**-Eigenschaft fest.  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  Legen Sie die **ContentType**-Eigenschaft auf einen geeigneten Wert fest.  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  Rufen Sie den Datenstrom ab, der die Anforderungsdaten enthält, indem Sie die Methode <xref:System.Net.WebRequest.GetRequestStream%2A> aufrufen.  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  Schreiben Sie die Daten in das von dieser Methode zurückgegebene <xref:System.IO.Stream>-Objekt.  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  Schließen Sie den Anforderungsdatenstrom durch Aufrufen der **Stream.Close**-Methode.  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. Senden Sie die Anforderung an den Server durch Aufrufen von <xref:System.Net.WebRequest.GetResponse%2A>. Diese Methode gibt ein Objekt zurück, das die Antwort des Servers enthält. Der Typ des zurückgegebenen <xref:System.Net.WebResponse>-Objekts wird durch das URI-Schema der Anforderung bestimmt.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  Wenn Sie ein <xref:System.Net.WebResponse>-Objekt nicht mehr benötigen, schließen Sie es durch Aufrufen der <xref:System.Net.WebResponse.Close%2A>-Methode. Wenn Sie den Antwortstream vom Antwortobjekt abgerufen haben, können Sie den Datenstrom alternativ dazu auch durch Aufrufen der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode schließen. Wird die Antwort oder der Datenstrom nicht geschlossen, verfügt die Anwendung möglicherweise nicht mehr über genügend Verbindungen mit dem Server und kann somit weitere Anforderungen nicht mehr verarbeiten.  
  
10. Sie können die protokollspezifischen Eigenschaften lesen, indem Sie auf die Eigenschaften von **WebResponse** zugreifen oder **WebResponse** in eine protokollspezifische Instanz umwandeln. Sie können z.B. auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebResponse> zugreifen, indem Sie **WebRequest** in einen **HttpWebRequest**-Verweis umwandeln.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Zum Abrufen des Datenstroms, der die vom Server gesendeten Antwortdaten enthält, rufen Sie die Methode <xref:System.Net.WebResponse.GetResponseStream%2A> der **WebResponse** auf.  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. Nachdem Sie die Daten der Antwort gelesen haben, schließen Sie entweder den Antwortstream mithilfe der **Stream.Close**-Methode, oder schließen Sie die Antwort mithilfe der **WebResponse.Close**-Methode. Es ist zwar nicht notwendig, die **Close**-Methode für sowohl Antwortdatenstrom als auch **WebResponse** aufzurufen, doch es ist auch nicht schädlich.  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
    ```  
  
## <a name="example"></a>Beispiel  
  
```csharp  
using System;  
using System.IO;  
using System.Net;  
using System.Text;  
  
namespace Examples.System.Net  
{  
    public class WebRequestPostExample  
    {  
        public static void Main ()  
        {  
            // Create a request using a URL that can receive a post.   
            WebRequest request = WebRequest.Create ("http://www.contoso.com/PostAccepter.aspx ");  
            // Set the Method property of the request to POST.  
            request.Method = "POST";  
            // Create POST data and convert it to a byte array.  
            string postData = "This is a test that posts this string to a Web server.";  
            byte[] byteArray = Encoding.UTF8.GetBytes (postData);  
            // Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded";  
            // Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length;  
            // Get the request stream.  
            Stream dataStream = request.GetRequestStream ();  
            // Write the data to the request stream.  
            dataStream.Write (byteArray, 0, byteArray.Length);  
            // Close the Stream object.  
            dataStream.Close ();  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams.  
            reader.Close ();  
            dataStream.Close ();  
            response.Close ();  
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
    Public Class WebRequestPostExample  
  
        Public Shared Sub Main()  
            ' Create a request using a URL that can receive a post.   
            Dim request As WebRequest = WebRequest.Create("http://www.contoso.com/PostAccepter.aspx ")  
            ' Set the Method property of the request to POST.  
            request.Method = "POST"  
            ' Create POST data and convert it to a byte array.  
            Dim postData As String = "This is a test that posts this string to a Web server."  
            Dim byteArray As Byte() = Encoding.UTF8.GetBytes(postData)  
            ' Set the ContentType property of the WebRequest.  
            request.ContentType = "application/x-www-form-urlencoded"  
            ' Set the ContentLength property of the WebRequest.  
            request.ContentLength = byteArray.Length  
            ' Get the request stream.  
            Dim dataStream As Stream = request.GetRequestStream()  
            ' Write the data to the request stream.  
            dataStream.Write(byteArray, 0, byteArray.Length)  
            ' Close the Stream object.  
            dataStream.Close()  
            ' Get the response.  
            Dim response As WebResponse = request.GetResponse()  
            ' Display the status.  
            Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
            ' Get the stream containing content returned by the server.  
            dataStream = response.GetResponseStream()  
            ' Open the stream using a StreamReader for easy access.  
            Dim reader As New StreamReader(dataStream)  
            ' Read the content.  
            Dim responseFromServer As String = reader.ReadToEnd()  
            ' Display the content.  
            Console.WriteLine(responseFromServer)  
            ' Clean up the streams.  
            reader.Close()  
            dataStream.Close()  
            response.Close()  
        End Sub  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen von Internetanforderungen](../../../docs/framework/network-programming/creating-internet-requests.md)  
 [Verwenden von Datenströmen im Netzwerk](../../../docs/framework/network-programming/using-streams-on-the-network.md)  
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 [Requesting Data (Anfordern von Daten)](../../../docs/framework/network-programming/requesting-data.md)  
 [Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
