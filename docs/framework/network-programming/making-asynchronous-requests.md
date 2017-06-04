---
title: "Vornehmen von asynchronen Anforderungen | Microsoft Docs"
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
  - "Internet, Asynchroner Zugriff"
  - "Netzwerk"
  - "Asynchrone Anforderungen, Internetressourcen"
  - "Netzwerkressourcen"
  - "WebRequest-Klasse, Asynchroner Zugriff"
ms.assetid: 735d3fce-f80c-437f-b02c-5c47f5739674
caps.latest.revision: 12
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# Vornehmen von asynchronen Anforderungen
Die <xref:System.Net>\-Klassen verwenden das asynchrone StandardProgrammiermodell von .NET Framework für asynchrone Zugriff auf Internetressourcen.  Die <xref:System.Net.WebRequest.BeginGetResponse%2A> und <xref:System.Net.WebRequest.EndGetResponse%2A>\-Methoden der Klasse <xref:System.Net.WebRequest> starten und schließen asynchrone Anforderung einer Internetressource ab.  
  
> [!NOTE]
>  Verwenden der synchronen Aufrufen in asynchronen Rückrufmethoden kann schwere Leistungseinbußen führen.  Die Internet\-Anforderungen, die mit **WebRequest** gemacht und seine Nachfolger müssen <xref:System.IO.Stream.BeginRead%2A?displayProperty=fullName> verwenden, um den Stream lesen, der durch die <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=fullName>\-Methode zurückgegeben wird.  
  
 Im folgenden Beispielcode wird veranschaulicht, wie asynchrone Aufrufe mit der **WebRequest**\-Klasse verwendet.  Das Beispiel ist ein Konsolenprogramm, das ein URI aus der Befehlszeile akzeptiert, fordert die Ressource am URI und gibt dann Daten an die Konsole, da es aus dem Internet empfangen wird.  
  
 Das Programm definiert zwei Klassen zur eigenen Verwendung, die **RequestState**\-Klasse, die die Daten für asynchronen Aufrufen übermittelt, und die **ClientGetAsync**\-Klasse, die die asynchrone Anforderung einer Internetressource implementiert.  
  
 Die **RequestState**\-Klasse behält den Zustand der Anforderung zum Aufrufen der asynchronen Methoden bei, die die Anforderung bedienen.  Es enthält **WebRequest** und <xref:System.IO.Stream>\-Instanzen, die die aktuelle Anforderung an die Ressource und den Stream enthalten, die in der Antwort empfangen wird, einen Puffer, der die Daten enthält, die derzeit von einer Internetressource empfangen werden und <xref:System.Text.StringBuilder>, das die vollständige Antwort enthält.  **RequestState** wird als *Zustandsparameter* übergeben, wenn die <xref:System.AsyncCallback>\-Methode mit **WebRequest.BeginGetResponse** registriert wird.  
  
 Die **ClientGetAsync**\-Klasse implementiert eine asynchrone Anforderung einer Internetressource und schreibt die resultierende Antwort an der Konsole aus.  Sie enthält die Methoden und Eigenschaften, die in der folgenden Liste beschrieben werden.  
  
-   Die `allDone`\-Eigenschaft enthält eine Instanz der <xref:System.Threading.ManualResetEvent>\-Klasse, die dem Abschluss der Anforderung signalisiert.  
  
-   Die `Main()`\-Methode liest die Befehlszeile und startet die Anforderung für die angegebene Internetressource.  Es erstellt **WebRequest**`wreq` und **RequestState**`rs` auf, ruft **BeginGetResponse**, um zu beginnen, die Anforderungsverarbeitung, und ruft dann die `allDone.WaitOne()`\-Methode auf, damit die Anwendung nicht angehalten, bis der Rückruf abgeschlossen ist.  Nachdem die Antwort von einer Internetressource gelesen wurde, schreibt `Main()` sie auf der Konsole und zu dem Beenden der Anwendung.  
  
-   Die `showusage()`\-Methode schreibt eine Beispielbefehlszeile auf der Konsole.  Sie wird von `Main()` aufgerufen, wenn kein URI in der Befehlszeile bereitgestellt wird.  
  
-   Die `RespCallBack()`\-Methode implementiert die asynchrone Rückrufmethode für die Internetanforderung.  Es erstellt die **WebResponse**\-Instanz, die die Antwort von einer Internetressource enthält, ruft den Antwortdatenstrom ab und startet dann die Daten aus dem Stream asynchron lesen.  
  
-   Die `ReadCallBack()`\-Methode implementiert die asynchrone Rückrufmethode zum Lesen des Antwortstreams.  Es überträgt die Daten, die von einer Internetressource in die **ResponseData**\-Eigenschaft der **RequestState**\-Instanz empfangen werden, dann startet eine anderes asynchrones Lesen des Antwortstreams, bis nicht mehr Daten zurückgegeben.  Sobald alle Daten gelesen wurden, schließt `ReadCallBack()` den Antwortdatenstrom und ruft die `allDone.Set()`\-Methode auf, um anzugeben, dass die gesamte Antwort in **ResponseData** vorhanden ist.  
  
    > [!NOTE]
    >  Es ist wichtig, dass alle Netzwerkstreams geschlossen werden.  Wenn Sie nicht jede Anforderung und B schließen, verfügt die Anwendung kein Verbindungen mit dem Server mehr und ist nicht möglich, zusätzliche Anforderungen zu verarbeiten.  
  
```csharp  
using System;  
using System.Net;  
using System.Threading;  
using System.Text;  
using System.IO;  
  
// The RequestState class passes data across async calls.  
public class RequestState  
{  
   const int BufferSize = 1024;  
   public StringBuilder RequestData;  
   public byte[] BufferRead;  
   public WebRequest Request;  
   public Stream ResponseStream;  
   // Create Decoder for appropriate enconding type.  
   public Decoder StreamDecode = Encoding.UTF8.GetDecoder();  
  
   public RequestState()  
   {  
      BufferRead = new byte[BufferSize];  
      RequestData = new StringBuilder(String.Empty);  
      Request = null;  
      ResponseStream = null;  
   }       
}  
  
// ClientGetAsync issues the async request.  
class ClientGetAsync   
{  
   public static ManualResetEvent allDone = new ManualResetEvent(false);  
   const int BUFFER_SIZE = 1024;  
  
   public static void Main(string[] args)   
   {  
      if (args.Length < 1)   
      {  
         showusage();  
         return;  
      }  
  
      // Get the URI from the command line.  
      Uri httpSite = new Uri(args[0]);  
  
      // Create the request object.  
      WebRequest wreq = WebRequest.Create(httpSite);  
  
      // Create the state object.  
      RequestState rs = new RequestState();  
  
      // Put the request into the state object so it can be passed around.  
      rs.Request = wreq;  
  
      // Issue the async request.  
      IAsyncResult r = (IAsyncResult) wreq.BeginGetResponse(  
         new AsyncCallback(RespCallback), rs);  
  
      // Wait until the ManualResetEvent is set so that the application   
      // does not exit until after the callback is called.  
      allDone.WaitOne();  
  
      Console.WriteLine(rs.RequestData.ToString());  
   }  
  
   public static void showusage() {  
      Console.WriteLine("Attempts to GET a URL");  
      Console.WriteLine("\r\nUsage:");  
      Console.WriteLine("   ClientGetAsync URL");  
      Console.WriteLine("   Example:");  
      Console.WriteLine("      ClientGetAsync http://www.contoso.com/");  
   }  
  
   private static void RespCallback(IAsyncResult ar)  
   {  
      // Get the RequestState object from the async result.  
      RequestState rs = (RequestState) ar.AsyncState;  
  
      // Get the WebRequest from RequestState.  
      WebRequest req = rs.Request;  
  
      // Call EndGetResponse, which produces the WebResponse object  
      //  that came from the request issued above.  
      WebResponse resp = req.EndGetResponse(ar);           
  
      //  Start reading data from the response stream.  
      Stream ResponseStream = resp.GetResponseStream();  
  
      // Store the response stream in RequestState to read   
      // the stream asynchronously.  
      rs.ResponseStream = ResponseStream;  
  
      //  Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead  
      IAsyncResult iarRead = ResponseStream.BeginRead(rs.BufferRead, 0,   
         BUFFER_SIZE, new AsyncCallback(ReadCallBack), rs);   
   }  
  
   private static void ReadCallBack(IAsyncResult asyncResult)  
   {  
      // Get the RequestState object from AsyncResult.  
      RequestState rs = (RequestState)asyncResult.AsyncState;  
  
      // Retrieve the ResponseStream that was set in RespCallback.   
      Stream responseStream = rs.ResponseStream;  
  
      // Read rs.BufferRead to verify that it contains data.   
      int read = responseStream.EndRead( asyncResult );  
      if (read > 0)  
      {  
         // Prepare a Char array buffer for converting to Unicode.  
         Char[] charBuffer = new Char[BUFFER_SIZE];  
  
         // Convert byte stream to Char array and then to String.  
         // len contains the number of characters converted to Unicode.  
      int len =   
         rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0);  
  
         String str = new String(charBuffer, 0, len);  
  
         // Append the recently read data to the RequestData stringbuilder  
         // object contained in RequestState.  
         rs.RequestData.Append(  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read));           
  
         // Continue reading data until   
         // responseStream.EndRead returns –1.  
         IAsyncResult ar = responseStream.BeginRead(   
            rs.BufferRead, 0, BUFFER_SIZE,   
            new AsyncCallback(ReadCallBack), rs);  
      }  
      else  
      {  
         if(rs.RequestData.Length>0)  
         {  
            //  Display data to the console.  
            string strContent;                    
            strContent = rs.RequestData.ToString();  
         }  
         // Close down the response stream.  
         responseStream.Close();           
         // Set the ManualResetEvent so the main thread can exit.  
         allDone.Set();                             
      }  
      return;  
   }      
}  
```  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Threading  
Imports System.Text  
Imports System.IO  
  
' The RequestState class passes data across async calls.  
Public Class RequestState  
  
      Public RequestData As New StringBuilder("")  
      Public BufferRead(1024) As Byte  
      Public Request As HttpWebRequest  
      Public ResponseStream As Stream  
      ' Create Decoder for appropriate encoding type.  
      Public StreamDecode As Decoder = Encoding.UTF8.GetDecoder()  
  
      Public Sub New  
         Request = Nothing  
         ResponseStream = Nothing  
      End Sub  
End Class  
  
' ClientGetAsync issues the async request.  
Class ClientGetAsync  
   Shared allDone As New ManualResetEvent(False)  
      Const BUFFER_SIZE As Integer = 1024  
  
    Shared Sub Main()  
        Dim Args As String() = Environment.GetCommandLineArgs()  
  
        If Args.Length < 2 Then  
            ShowUsage()  
            Return  
        End If  
  
      ' Get the URI from the command line.  
        Dim HttpSite As Uri = New Uri(Args(1))  
  
      ' Create the request object.  
        Dim wreq As HttpWebRequest = _  
           CType(WebRequest.Create(HttpSite), HttpWebRequest)  
  
      ' Create the state object.  
      Dim rs As RequestState = New RequestState()  
  
      ' Put the request into the state so it can be passed around.  
      rs.Request = wreq  
  
      ' Issue the async request.  
        Dim r As IAsyncResult = _  
           CType(wreq.BeginGetResponse( _  
           New AsyncCallback(AddressOf RespCallback), rs), IAsyncResult)  
  
      ' Wait until the ManualResetEvent is set so that the application  
      ' does not exit until after the callback is called.  
        allDone.WaitOne()  
    End Sub  
  
    Shared Sub ShowUsage()  
        Console.WriteLine("Attempts to GET a URI")  
        Console.WriteLine()  
        Console.WriteLine("Usage:")  
        Console.WriteLine("ClientGetAsync URI")  
        Console.WriteLine("Examples:")  
        Console.WriteLine("ClientGetAsync http://www.contoso.com/")  
    End Sub  
  
    Shared Sub RespCallback(ar As IAsyncResult)  
       ' Get the RequestState object from the async result.  
       Dim rs As RequestState = CType(ar.AsyncState, RequestState)  
  
       ' Get the HttpWebRequest from RequestState.  
       Dim req As HttpWebRequest= rs.Request  
  
       ' Call EndGetResponse, which returns the HttpWebResponse object  
       ' that came from the request issued above.  
       Dim resp As HttpWebResponse = _  
           CType(req.EndGetResponse(ar), HttpWebResponse)  
  
       ' Start reading data from the respons stream.  
       Dim ResponseStream As Stream = resp.GetResponseStream()  
  
       ' Store the reponse stream in RequestState to read  
       ' the stream asynchronously.  
       rs.ResponseStream = ResponseStream  
  
       ' Pass rs.BufferRead to BeginRead. Read data into rs.BufferRead.  
       Dim iarRead As IAsyncResult = _  
          ResponseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
          New AsyncCallback(AddressOf ReadCallBack), rs)  
    End Sub  
  
   Shared Sub ReadCallBack(asyncResult As IAsyncResult)  
      ' Get the RequestState object from the AsyncResult.  
      Dim rs As RequestState = CType(asyncResult.AsyncState, RequestState)  
  
      ' Retrieve the ResponseStream that was set in RespCallback.  
      Dim responseStream As Stream = rs.ResponseStream  
  
      ' Read rs.BufferRead to verify that it contains data.  
      Dim read As Integer = responseStream.EndRead( asyncResult )  
      If read > 0 Then  
         ' Prepare a Char array buffer for converting to Unicode.  
         Dim charBuffer(1024) As Char  
  
         ' Convert byte stream to Char array and then String.  
         ' len contains the number of characters converted to Unicode.  
         Dim len As Integer = _  
           rs.StreamDecode.GetChars(rs.BufferRead, 0, read, charBuffer, 0)  
         Dim str As String = new String(charBuffer, 0, len)      
  
         ' Append the recently read data to the RequestData stringbuilder   
         ' object contained in RequestState.  
         rs.RequestData.Append( _  
            Encoding.ASCII.GetString(rs.BufferRead, 0, read))  
  
         ' Continue reading data until responseStream.EndRead  
         ' returns –1.  
         Dim ar As IAsyncResult = _  
            responseStream.BeginRead(rs.BufferRead, 0, BUFFER_SIZE, _  
            New AsyncCallback(AddressOf ReadCallBack), rs)  
      Else  
          If rs.RequestData.Length > 1 Then  
            ' Display data to the console.  
            Dim strContent As String  
            strContent = rs.RequestData.ToString()  
            Console.WriteLine(strContent)  
         End If  
  
         ' Close down the response stream.  
         responseStream.Close()  
  
         ' Set the ManualResetEvent so the main thread can exit.  
         allDone.Set()  
      End If  
  
      Return  
   End Sub  
End Class  
```  
  
## Siehe auch  
 [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)