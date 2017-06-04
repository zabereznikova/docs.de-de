---
title: "Gewusst wie: Senden von Daten mithilfe der WebRequest-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "WebRequest-Klasse, Senden von Daten an einen Host"
  - "Senden von Daten an einen Host, mit WebRequest-Klasse"
ms.assetid: 66686878-38ac-4aa6-bf42-ffb568ffc459
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Gewusst wie: Senden von Daten mithilfe der WebRequest-Klasse
Die folgende Prozedur beschreibt die Schritte, die verwendet werden, um Daten zu einem Server zu senden.  Diese Prozedur wird häufig verwendet, um Daten an eine Webseite zu senden.  
  
### So fügen Sie Daten zu einem Hostserver senden  
  
1.  Erstellen Sie eine Instanz <xref:System.Net.WebRequest>, indem Sie <xref:System.Net.WebRequest.Create%2A> mit dem URI der Ressource aufrufen, die Daten, beispielsweise, ein Skript oder Eine ASP.NET\-Seite akzeptiert.  
  
    ```csharp  
    WebRequest request = WebRequest.Create("http://www.contoso.com/");  
    ```  
  
    ```vb  
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/")  
  
    ```  
  
    > [!NOTE]
    >  . .NET Framework stellt die protokollspezifischen Klassen bereit, die von **WebRequest** und von **WebResponse** für URIs abgeleitet werden, die mit "HTTP beginnen: ", "https:'' ", " Ziel\-FTP\-Site: " und "Datei: ".  Um auf Ressourcen mit anderen Protokolle zuzugreifen, müssen Sie protokollspezifische Klassen implementieren die von **WebRequest** und von **WebResponse** berechnen.  Weitere Informationen finden Sie unter [Programmieren austauschbarer Protokolle](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
2.  Legen Sie alle Eigenschaftswerte fest, die Sie in **WebRequest** erfordern.  Um beispielsweise Authentifizierung zu aktivieren, legen Sie die **Credentials**\-Eigenschaft auf eine Instanz der <xref:System.Net.NetworkCredential>\-Klasse fest.  
  
    ```csharp  
    request.Credentials = CredentialCache.DefaultCredentials;  
    ```  
  
    ```vb  
    request.Credentials = CredentialCache.DefaultCredentials  
  
    ```  
  
     In den meisten Fällen ist die Instanz selbst **WebRequest** ausreichend, Daten zu senden.  Wenn Sie jedoch protokollspezifische Eigenschaften festlegen müssen, müssen Sie **WebRequest** zum protokollspezifischen Typ umwandeln.  Um beispielsweise auf die HTTP\-spezifische Eigenschaften von <xref:System.Net.HttpWebRequest> zuzugreifen, wandeln Sie **WebRequest** zu einem **HttpWebRequest**\-Verweis um.  Das folgende Codebeispiel veranschaulicht, wie die HTTP\-spezifische <xref:System.Net.HttpWebRequest.UserAgent%2A>\-Eigenschaft festlegt.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
    ```  
  
3.  Geben Sie eine Protokollmethode, die Daten zulässt, mit einer Anforderung gesendet werden, wie der Methode HTTP **POST** an.  
  
    ```csharp  
    request.Method = "POST";  
    ```  
  
    ```vb  
    request.Method = "POST"  
    ```  
  
4.  Legen Sie die **ContentLength**\-Eigenschaft fest.  
  
    ```csharp  
    request.ContentLength = byteArray.Length;  
    ```  
  
    ```vb  
    request.ContentLength = byteArray.Length  
    ```  
  
5.  Legen Sie die **ContentType**\-Eigenschaft einen geeigneten Wert fest.  
  
    ```csharp  
    request.ContentType = "application/x-www-form-urlencoded";  
    ```  
  
    ```vb  
    request.ContentType = "application/x-www-form-urlencoded"  
    ```  
  
6.  Rufen Sie den Stream ab, der Daten enthält, indem die <xref:System.Net.WebRequest.GetRequestStream%2A>\-Methode aufruft.  
  
    ```csharp  
    Stream dataStream = request.GetRequestStream ();  
    ```  
  
    ```vb  
    Stream dataStream = request.GetRequestStream ()  
    ```  
  
7.  Schreiben Sie die Daten auf dem <xref:System.IO.Stream>\-Objekt, das dieser Methode zurückgegeben wird.  
  
    ```csharp  
    dataStream.Write (byteArray, 0, byteArray.Length);  
    ```  
  
    ```vb  
    dataStream.Write (byteArray, 0, byteArray.Length)  
    ```  
  
8.  Schließen Sie den Anforderungsstream, indem Sie die **Stream.Close**\-Methode aufrufen.  
  
    ```csharp  
    dataStream.Close ();  
    ```  
  
    ```vb  
    dataStream.Close ()  
    ```  
  
9. Senden Sie die Anforderung dem Server, indem Sie <xref:System.Net.WebRequest.GetResponse%2A> aufrufen.  Diese Methode gibt ein Objekt zurück, das die Antwort des Servers enthält.  Der Typ zurückgegeben <xref:System.Net.WebResponse> wird durch das Schema des URI der Anforderung bestimmt.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
  
    ```  
  
    > [!NOTE]
    >  Nachdem Sie mit einem <xref:System.Net.WebResponse>\-Objekt abgeschlossen sind, müssen Sie es schließen, indem Sie die <xref:System.Net.WebResponse.Close%2A>\-Methode aufrufen.  Falls Sie den Antwortdatenstrom vom Warteobjekt abgerufen haben, können Sie den Stream schließen, indem Sie die <xref:System.IO.Stream.Close%2A?displayProperty=fullName>\-Methode aufrufen.  Wenn Sie nicht die Antwort oder den Stream schließen, kann die Anwendung kein Verbindungen mit dem Server mehr haben kann, und werden zusätzliche Anforderungen zu verarbeiten.  
  
10. Sie können auf die Eigenschaften **WebResponse** zugreifen oder **WebResponse** zu einer protokollspezifischen Instanz umwandeln, um protokollspezifische Eigenschaften zu lesen.  Um beispielsweise auf die HTTP\-spezifische Eigenschaften von <xref:System.Net.HttpWebResponse> zuzugreifen, wandeln Sie **WebResponse** zu einem **HttpWebResponse** Verweis um.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response, HttpWebResponse).StatusDescription)  
    ```  
  
11. Um den Stream abzurufen, der die Antwortdaten gesendet werden vom Server enthält, rufen Sie die <xref:System.Net.WebResponse.GetResponseStream%2A>\-Methode der **WebResponse** auf.  
  
    ```csharp  
    Stream data = response.GetResponseStream;  
    ```  
  
    ```vb  
    Dim data As Stream = response.GetResponseStream  
    ```  
  
12. Nachdem Sie die Daten aus der Antwort gelesen haben, müssen Sie entweder den Antwortdatenstrom mithilfe der **Stream.Close**\-Methode schließen oder die Antwort mit der **WebResponse.Close**\-Methode schließen.  Es ist nicht erforderlich, die **Schließen**\-Methode auf dem Antwortstream und **WebResponse** aufzurufen, es ist nicht schädlich.  
  
    ```csharp  
    response.Close();  
    ```  
  
    ```vb  
    response.Close()  
  
    ```  
  
## Beispiel  
  
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
  
## Siehe auch  
 [Erstellen von Internetanforderungen](../../../docs/framework/network-programming/creating-internet-requests.md)   
 [Verwenden von Streams im Netzwerk](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)   
 [Gewusst wie: Anfordern von Daten mithilfe der WebRequest\-Klasse](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)