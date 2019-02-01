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
# <a name="how-to-request-data-using-the-webrequest-class"></a>Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse
Das folgende Verfahren beschreibt die Schritte zum Anfordern einer Ressource von einem Server, z.B. einer Webseite oder Webdatei. Die Ressource muss von einem URI identifiziert werden.  
  
### <a name="to-request-data-from-a-host-server"></a>Anfordern von Daten von einem Hostserver  
  
1.  Erstellen einer <xref:System.Net.WebRequest>-Instanz durch Aufrufen von <xref:System.Net.WebRequest.Create%2A> mit dem URI der Ressource.  
  
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
  
     In den meisten Fällen reicht die **WebRequest**-Klasse aus, um Daten zu empfangen. Wenn Sie dennoch protokollspezifische Eigenschaften festlegen müssen, wandeln Sie **WebRequest** in einen protokollspezifischen Typ um. Wandeln Sie z.B. **WebRequest** in einen **HttpWebRequest**-Verweis um, wenn Sie auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebRequest> zugreifen möchten. Das folgende Codebeispiel veranschaulicht, wie die HTTP-spezifische Eigenschaft <xref:System.Net.HttpWebRequest.UserAgent%2A> festgelegt wird.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Senden Sie die Anforderung an den Server durch Aufrufen von <xref:System.Net.HttpWebRequest.GetResponse%2A>. Der tatsächliche Typ des zurückgegebenen **WebResponse**-Objekts richtet sich nach dem Schema des angeforderten URI.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
    ```  
  
    > [!NOTE]
    >  Wenn Sie ein <xref:System.Net.WebResponse>-Objekt nicht mehr benötigen, schließen Sie es durch Aufrufen der <xref:System.Net.WebResponse.Close%2A>-Methode. Wenn Sie den Antwortdatenstrom vom Antwortobjekt abgerufen haben, können Sie den Datenstrom alternativ dazu auch durch Aufrufen der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode schließen. Wird die Antwort oder der Datenstrom nicht geschlossen, verfügt die Anwendung möglicherweise nicht mehr über genügend Verbindungen mit dem Server und kann somit weitere Anforderungen nicht mehr verarbeiten.  
  
4.  Sie können die protokollspezifischen Eigenschaften lesen, indem Sie auf die Eigenschaften von **WebResponse** zugreifen oder **WebResponse** in eine protokollspezifische Instanz umwandeln. Sie können z.B. auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebResponse> zugreifen, indem Sie **WebRequest** in einen **HttpWebRequest**-Verweis umwandeln. Das folgende Codebeispiel zeigt die Vorgehensweise beim Anzeigen von Statusinformationen, die mit einer Antwort gesendet werden.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Zum Abrufen des Datenstroms, der die vom Server gesendeten Antwortdaten enthält, rufen Sie die Methode <xref:System.Net.HttpWebResponse.GetResponseStream%2A> der **WebResponse** auf.  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
    ```  
  
6.  Nachdem Sie die Daten der Antwort gelesen haben, schließen Sie den Antwortdatenstrom entweder mithilfe der **Stream.Close**- oder der **WebResponse.Close**-Methode. Es ist zwar nicht notwendig, die **Close**-Methode für sowohl Antwortdatenstrom als auch **WebResponse** aufzurufen, doch es ist auch nicht schädlich. **WebResponse.Close** ruft **Stream.Close** beim Schließen der Antwort auf.  
  
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
  
## <a name="see-also"></a>Siehe auch
- [Erstellen von Internetanforderungen](../../../docs/framework/network-programming/creating-internet-requests.md)
- [Verwenden von Datenströmen im Netzwerk](../../../docs/framework/network-programming/using-streams-on-the-network.md)
- [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)
- [Requesting Data (Anfordern von Daten)](../../../docs/framework/network-programming/requesting-data.md)
- [Vorgehensweise: Senden von Daten mithilfe der WebRequest-Klasse](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)
