---
title: "Gewusst wie: Anfordern von Daten mithilfe der WebRequest-Klasse | Microsoft Docs"
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
  - "Downloaden von Internetressourcen, Schritte"
  - "Anfordern von Daten aus dem Internet, Schritte"
  - "WebRequest-Klasse, Empfangen von Daten"
  - "Empfangen von Daten, WebRequest-Klasse"
  - "Internet, Anfordern von Daten"
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
caps.latest.revision: 8
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 8
---
# Gewusst wie: Anfordern von Daten mithilfe der WebRequest-Klasse
Die folgende Prozedur beschreibt die Schritte, die verwendet werden, um eine Ressource von einem Server, beispielsweise, von einer Webseite oder einer Datei anzufordern.  Die Ressource muss durch einen URI angegeben werden.  
  
### So fügen Sie Daten von einem Hostserver benötigen  
  
1.  Erstellen Sie eine Instanz <xref:System.Net.WebRequest>, indem Sie <xref:System.Net.WebRequest.Create%2A> mit dem URI der Ressource aufrufen.  
  
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
  
     In den meisten Fällen ist die **WebRequest**\-Klasse ausreichend, Daten zu empfangen.  Wenn Sie jedoch protokollspezifische Eigenschaften festlegen müssen, müssen Sie **WebRequest** zum protokollspezifischen Typ umwandeln.  Um beispielsweise auf die HTTP\-spezifische Eigenschaften von <xref:System.Net.HttpWebRequest> zuzugreifen, wandeln Sie **WebRequest** zu einem **HttpWebRequest**\-Verweis um.  Das folgende Codebeispiel veranschaulicht, wie die HTTP\-spezifische <xref:System.Net.HttpWebRequest.UserAgent%2A>\-Eigenschaft festlegt.  
  
    ```csharp  
    ((HttpWebRequest)request).UserAgent = ".NET Framework Example Client";  
    ```  
  
    ```vb  
    Ctype(request,HttpWebRequest).UserAgent = ".NET Framework Example Client"  
  
    ```  
  
3.  Um die Anforderung an den Server zu senden, rufen Sie <xref:System.Net.HttpWebRequest.GetResponse%2A> auf.  Der tatsächliche Typ des zurückgegebenen Objekts **WebResponse** wird durch das Schema des angeforderten URI bestimmt.  
  
    ```csharp  
    WebResponse response = request.GetResponse();  
    ```  
  
    ```vb  
    Dim response As WebResponse = request.GetResponse()  
  
    ```  
  
    > [!NOTE]
    >  Nachdem Sie mit einem <xref:System.Net.WebResponse>\-Objekt abgeschlossen sind, müssen Sie es schließen, indem Sie die <xref:System.Net.WebResponse.Close%2A>\-Methode aufrufen.  Falls Sie den Antwortdatenstrom vom Warteobjekt abgerufen haben, können Sie den Stream schließen, indem Sie die <xref:System.IO.Stream.Close%2A?displayProperty=fullName>\-Methode aufrufen.  Wenn Sie weder die Antwort oder den Stream schließen, kann die Anwendung kein Verbindungen mit dem Server mehr haben kann, und werden zusätzliche Anforderungen zu verarbeiten.  
  
4.  Sie können auf die Eigenschaften **WebResponse** zugreifen oder **WebResponse** zu einer protokollspezifischen Instanz umwandeln, um protokollspezifische Eigenschaften zu lesen.  Um beispielsweise auf die HTTP\-spezifische Eigenschaften von <xref:System.Net.HttpWebResponse> zuzugreifen, wandeln Sie **WebResponse** zu einem **HttpWebResponse** Verweis um.  Im folgenden Codebeispiel wird gezeigt, wie die Statusinformationen anzeigt, die mit einer Antwort gesendet werden.  
  
    ```csharp  
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
    ```  
  
    ```vb  
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)  
    ```  
  
5.  Um den Stream abzurufen, der die Antwortdaten gesendet werden vom Server enthält, verwenden Sie die <xref:System.Net.HttpWebResponse.GetResponseStream%2A>\-Methode der **WebResponse**.  
  
    ```csharp  
    Stream dataStream = response.GetResponseStream ();  
    ```  
  
    ```vb  
    Dim dataStream As Stream = response.GetResponseStream()  
  
    ```  
  
6.  Nachdem Sie die Daten aus der Antwort gelesen haben, müssen Sie entweder den Antwortdatenstrom mithilfe der **Stream.Close**\-Methode schließen oder die Antwort mit der **WebResponse.Close**\-Methode schließen.  Es ist nicht erforderlich, die **Schließen**\-Methode auf dem Antwortstream und **WebResponse** aufzurufen, es ist nicht schädlich.  **WebResponse.Close** Aufrufe **Stream.Close**, wenn die Antwort geschlossen wird.  
  
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
    public class WebRequestGetExample  
    {  
        public static void Main ()  
        {  
            // Create a request for the URL.   
            WebRequest request = WebRequest.Create (  
              "http://www.contoso.com/default.html");  
            // If required by the server, set the credentials.  
            request.Credentials = CredentialCache.DefaultCredentials;  
            // Get the response.  
            WebResponse response = request.GetResponse ();  
            // Display the status.  
            Console.WriteLine (((HttpWebResponse)response).StatusDescription);  
            // Get the stream containing content returned by the server.  
            Stream dataStream = response.GetResponseStream ();  
            // Open the stream using a StreamReader for easy access.  
            StreamReader reader = new StreamReader (dataStream);  
            // Read the content.  
            string responseFromServer = reader.ReadToEnd ();  
            // Display the content.  
            Console.WriteLine (responseFromServer);  
            // Clean up the streams and the response.  
            reader.Close ();  
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
  
## Siehe auch  
 [Erstellen von Internetanforderungen](../../../docs/framework/network-programming/creating-internet-requests.md)   
 [Verwenden von Streams im Netzwerk](../../../docs/framework/network-programming/using-streams-on-the-network.md)   
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)   
 [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)   
 [Gewusst wie: Senden von Daten mithilfe der WebRequest\-Klasse](../../../docs/framework/network-programming/how-to-send-data-using-the-webrequest-class.md)