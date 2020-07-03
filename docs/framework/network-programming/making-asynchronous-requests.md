---
title: Vornehmen von asynchronen Anforderungen
description: Hier erfahren Sie, wie System.Net-Klassen das .NET Framework-Standardmodell für asynchrones Programmieren für den asynchronen Zugriff auf Internetressourcen verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Internet, asynchronous access
- Networking
- asynchronous requests, Internet resources
- Network Resources
- WebRequest class, asynchronous access
ms.assetid: 735d3fce-f80c-437f-b02c-5c47f5739674
ms.openlocfilehash: 0af143b723c90b146dc5de8447d4a7e1866e7105
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502300"
---
# <a name="making-asynchronous-requests"></a><span data-ttu-id="f28ab-103">Vornehmen von asynchronen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f28ab-103">Making Asynchronous Requests</span></span>
<span data-ttu-id="f28ab-104">Die <xref:System.Net>-Klassen verwenden das .NET Framework-Standardmodell für asynchrones Programmieren für den asynchronen Zugriff auf Internetressourcen.</span><span class="sxs-lookup"><span data-stu-id="f28ab-104">The <xref:System.Net> classes use the .NET Framework's standard asynchronous programming model for asynchronous access to Internet resources.</span></span> <span data-ttu-id="f28ab-105">Die Methoden <xref:System.Net.WebRequest.BeginGetResponse%2A> und <xref:System.Net.WebRequest.EndGetResponse%2A> der Klasse <xref:System.Net.WebRequest> starten asynchrone Anforderungen für eine Internetressource und schließen diese ab.</span><span class="sxs-lookup"><span data-stu-id="f28ab-105">The <xref:System.Net.WebRequest.BeginGetResponse%2A> and <xref:System.Net.WebRequest.EndGetResponse%2A> methods of the <xref:System.Net.WebRequest> class start and complete asynchronous requests for an Internet resource.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f28ab-106">Das Verwenden von synchronen Aufrufen in asynchronen Rückrufmethoden kann zu schwerwiegenden Leistungseinbußen führen.</span><span class="sxs-lookup"><span data-stu-id="f28ab-106">Using synchronous calls in asynchronous callback methods can result in severe performance penalties.</span></span> <span data-ttu-id="f28ab-107">Internet-Anforderungen mit **WebRequest** und den direkt untergeordneten Elementen müssen <xref:System.IO.Stream.BeginRead%2A?displayProperty=nameWithType> verwenden, um den von der <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>-Methode zurückgegebenen Datenstrom zu lesen.</span><span class="sxs-lookup"><span data-stu-id="f28ab-107">Internet requests made with **WebRequest** and its descendants must use <xref:System.IO.Stream.BeginRead%2A?displayProperty=nameWithType> to read the stream returned by the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="f28ab-108">Der folgende Beispielcode veranschaulicht, wie asynchrone Aufrufe mit der **WebRequest**-Klasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f28ab-108">The following sample code demonstrates how to use asynchronous calls with the **WebRequest** class.</span></span> <span data-ttu-id="f28ab-109">Das Beispiel ist ein Konsolenprogramm, das einen URI aus der Befehlszeile verwendet, die Ressource am URI anfordert und dann die Daten auf der Konsole druckt, wenn sie aus dem Internet empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="f28ab-109">The sample is a console program that takes a URI from the command line, requests the resource at the URI, and then prints data to the console as it is received from the Internet.</span></span>  
  
 <span data-ttu-id="f28ab-110">Das Programm definiert zwei Klassen für die eigene Verwendung. Die **RequestState**-Klasse, die Daten zwischen asynchronen Aufrufen überträgt, und die **ClientGetAsync**-Klasse, die die asynchrone Anforderung in eine Internetressource implementiert.</span><span class="sxs-lookup"><span data-stu-id="f28ab-110">The program defines two classes for its own use, the **RequestState** class, which passes data across asynchronous calls, and the **ClientGetAsync** class, which implements the asynchronous request to an Internet resource.</span></span>  
  
 <span data-ttu-id="f28ab-111">Die **RequestState**-Klasse behält den Status der Anforderung über Aufrufe der asynchronen Methoden für die Anforderung hinweg.</span><span class="sxs-lookup"><span data-stu-id="f28ab-111">The **RequestState** class preserves the state of the request across calls to the asynchronous methods that service the request.</span></span> <span data-ttu-id="f28ab-112">Sie enthält **WebRequest**- und <xref:System.IO.Stream>-Instanzen, die die aktuelle Anforderung der Ressource und den als Antwort empfangenen Datenstrom enthalten, einen Puffer, der die aktuell von der Internetressource empfangenen Daten enthält, sowie eine <xref:System.Text.StringBuilder>-Klasse, die die vollständige Antwort enthält.</span><span class="sxs-lookup"><span data-stu-id="f28ab-112">It contains **WebRequest** and <xref:System.IO.Stream> instances that contain the current request to the resource and the stream received in response, a buffer that contains the data currently received from the Internet resource, and a <xref:System.Text.StringBuilder> that contains the complete response.</span></span> <span data-ttu-id="f28ab-113">Eine **RequestState**-Klasse wird als *state*-Parameter übergeben, wenn die <xref:System.AsyncCallback>-Methode bei **WebRequest.BeginGetResponse** registriert ist.</span><span class="sxs-lookup"><span data-stu-id="f28ab-113">A **RequestState** is passed as the *state* parameter when the <xref:System.AsyncCallback> method is registered with **WebRequest.BeginGetResponse**.</span></span>  
  
 <span data-ttu-id="f28ab-114">Die **ClientGetAsync**-Klasse implementiert eine asynchrone Anforderung einer Internetressource und schreibt die resultierende Antwort in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="f28ab-114">The **ClientGetAsync** class implements an asynchronous request to an Internet resource and writes the resulting response to the console.</span></span> <span data-ttu-id="f28ab-115">Sie enthält die in der folgenden Liste aufgeführten Methoden und Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f28ab-115">It contains the methods and properties described in the following list.</span></span>  
  
- <span data-ttu-id="f28ab-116">Die `allDone`-Eigenschaft enthält eine Instanz der <xref:System.Threading.ManualResetEvent>-Klasse, die die Vervollständigung der Anforderung signalisiert.</span><span class="sxs-lookup"><span data-stu-id="f28ab-116">The `allDone` property contains an instance of the <xref:System.Threading.ManualResetEvent> class that signals the completion of the request.</span></span>  
  
- <span data-ttu-id="f28ab-117">Die `Main()`-Methode liest die Befehlszeile und startet die Anforderung für die angegebene Internetressource.</span><span class="sxs-lookup"><span data-stu-id="f28ab-117">The `Main()` method reads the command line and begins the request for the specified Internet resource.</span></span> <span data-ttu-id="f28ab-118">Sie erstellt die **WebRequest**-Klasse `wreq` und die **RequestState**-Klasse `rs`, ruft **BeginGetResponse** auf, um die Verarbeitung der Anforderung zu starten, und ruft dann die `allDone.WaitOne()`-Methode auf, sodass die Anwendung nicht beendet wird, bis der Rückruf abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f28ab-118">It creates the **WebRequest** `wreq` and the **RequestState** `rs`, calls **BeginGetResponse** to begin processing the request, and then calls the `allDone.WaitOne()`method so that the application will not exit until the callback is complete.</span></span> <span data-ttu-id="f28ab-119">Nachdem die Antwort von der Internetressource gelesen wurde, schreibt `Main()` diese in die Konsole, und die Anwendung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="f28ab-119">After the response is read from the Internet resource, `Main()` writes it to the console and the application ends.</span></span>  
  
- <span data-ttu-id="f28ab-120">Die `showusage()`-Methode schreibt eine Beispielbefehlszeile in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="f28ab-120">The `showusage()` method writes an example command line on the console.</span></span> <span data-ttu-id="f28ab-121">Sie wird von `Main()` aufgerufen, wenn in der Befehlszeile kein URI angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f28ab-121">It is called by `Main()` when no URI is provided on the command line.</span></span>  
  
- <span data-ttu-id="f28ab-122">Die `RespCallBack()`-Methode implementiert die asynchrone Rückrufmethode für die Internetanforderung.</span><span class="sxs-lookup"><span data-stu-id="f28ab-122">The `RespCallBack()` method implements the asynchronous callback method for the Internet request.</span></span> <span data-ttu-id="f28ab-123">Sie erstellt die **WebResponse**-Instanz, die die Antwort der Internetressource enthält, ruft den Antwortdatenstrom ab und startet dann mit dem asynchronen Lesen der Daten aus dem Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="f28ab-123">It creates the **WebResponse** instance containing the response from the Internet resource, gets the response stream, and then starts reading the data from the stream asynchronously.</span></span>  
  
- <span data-ttu-id="f28ab-124">Die `ReadCallBack()`-Methode implementiert die asynchrone Rückrufmethode zum Lesen des Antwortdatenstroms.</span><span class="sxs-lookup"><span data-stu-id="f28ab-124">The `ReadCallBack()` method implements the asynchronous callback method for reading the response stream.</span></span> <span data-ttu-id="f28ab-125">Sie überträgt von der Internetressource empfangene Daten in die **ResponseData**-Eigenschaft der **RequestState**-Instanz und startet dann ein weiteres asynchrones Lesen des Antwortdatenstroms, bis keine Daten mehr zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f28ab-125">It transfers data received from the Internet resource into the **ResponseData** property of the **RequestState** instance, then starts another asynchronous read of the response stream until no more data is returned.</span></span> <span data-ttu-id="f28ab-126">Nachdem alle Daten gelesen wurden, schließt `ReadCallBack()` den Antwortdatenstrom und ruft die `allDone.Set()`-Methode auf, um anzugeben, dass sich die gesamte Antwort in **ResponseData** befindet.</span><span class="sxs-lookup"><span data-stu-id="f28ab-126">Once all the data has been read, `ReadCallBack()` closes the response stream and calls the `allDone.Set()` method to indicate that the entire response is present in **ResponseData**.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f28ab-127">Es ist wichtig, dass alle Netzwerkdatenströme geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="f28ab-127">It is critical that all network streams are closed.</span></span> <span data-ttu-id="f28ab-128">Wird nicht jede Antwort und jeder Datenstrom geschlossen, verfügt die Anwendung nicht mehr über genügend Verbindungen mit dem Server und kann weitere Anforderungen nicht mehr verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="f28ab-128">If you do not close each request and response stream, your application will run out of connections to the server and be unable to process additional requests.</span></span>  
  
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
  
       ' Start reading data from the response stream.  
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
  
## <a name="see-also"></a><span data-ttu-id="f28ab-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f28ab-129">See also</span></span>

- [<span data-ttu-id="f28ab-130">Requesting Data (Anfordern von Daten)</span><span class="sxs-lookup"><span data-stu-id="f28ab-130">Requesting Data</span></span>](requesting-data.md)
