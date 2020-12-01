---
title: Synchroner Serversocket, Beispiel
description: Dieses Beispiel für ein .NET Framework-Programm erstellt einen Server, der über einen synchronen Socket Verbindungen von Clients empfängt. Er empfängt eine Zeichenfolge und gibt sie zurück.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronous server sockets
- sockets, code examples
- sockets, synchronous server sockets
ms.assetid: 5916c764-879f-4716-99fb-1d21c6237f1c
ms.openlocfilehash: 49646a71c979eda04f8bf932a3dbfac11677a8e0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96239522"
---
# <a name="synchronous-server-socket-example"></a><span data-ttu-id="259bc-104">Synchroner Serversocket, Beispiel</span><span class="sxs-lookup"><span data-stu-id="259bc-104">Synchronous Server Socket Example</span></span>

<span data-ttu-id="259bc-105">Das folgende Beispielprogramm erstellt einen Server, der Verbindungsanforderungen von Clients empfängt.</span><span class="sxs-lookup"><span data-stu-id="259bc-105">The following example program creates a server that receives connection requests from clients.</span></span> <span data-ttu-id="259bc-106">Der Server wird mit einem synchronen Socket erstellt, damit die Ausführung der Serveranwendung nicht anhält, während auf eine Verbindung von einem Client gewartet wird.</span><span class="sxs-lookup"><span data-stu-id="259bc-106">The server is built with a synchronous socket, so execution of the server application is suspended while it waits for a connection from a client.</span></span> <span data-ttu-id="259bc-107">Die Anwendung empfängt eine Zeichenfolge vom Client, zeigt die Zeichenfolge in der Konsole an und gibt sie dann an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="259bc-107">The application receives a string from the client, displays the string on the console, and then echoes the string back to the client.</span></span> <span data-ttu-id="259bc-108">Die Zeichenfolge vom Client muss die Zeichenfolge "\<EOF>EOF>" enthalten, um das Ende der Meldung zu signalisieren.</span><span class="sxs-lookup"><span data-stu-id="259bc-108">The string from the client must contain the string "\<EOF>" to signal the end of the message.</span></span>  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
Imports Microsoft.VisualBasic  
  
Public Class SynchronousSocketListener  
  
    ' Incoming data from the client.  
    Public Shared data As String = Nothing  
  
    Public Shared Sub Main()  
        ' Data buffer for incoming data.  
        Dim bytes() As Byte = New [Byte](1024) {}  
  
        ' Establish the local endpoint for the socket.  
        ' Dns.GetHostName returns the name of the
        ' host running the application.  
        Dim ipHostInfo As IPHostEntry = Dns.GetHostEntry(Dns.GetHostName())  
        Dim ipAddress As IPAddress = ipHostInfo.AddressList(0)  
        Dim localEndPoint As New IPEndPoint(ipAddress, 11000)  
  
        ' Create a TCP/IP socket.  
        Dim listener As New Socket(ipAddress.AddressFamily, _  
            SocketType.Stream, ProtocolType.Tcp)  
  
        ' Bind the socket to the local endpoint and
        ' listen for incoming connections.  
  
        listener.Bind(localEndPoint)  
        listener.Listen(10)  
  
        ' Start listening for connections.  
        While True  
            Console.WriteLine("Waiting for a connection...")  
            ' Program is suspended while waiting for an incoming connection.  
            Dim handler As Socket = listener.Accept()  
            data = Nothing  
  
            ' An incoming connection needs to be processed.  
            While True  
                Dim bytesRec As Integer = handler.Receive(bytes)  
                data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
                If data.IndexOf("<EOF>") > -1 Then  
                    Exit While  
                End If  
            End While  
            ' Show the data on the console.  
            Console.WriteLine("Text received : {0}", data)  
            ' Echo the data back to the client.  
            Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
            handler.Send(msg)  
            handler.Shutdown(SocketShutdown.Both)  
            handler.Close()  
        End While  
    End Sub  
  
End Class 'SynchronousSocketListener  
```  
  
```csharp  
using System;  
using System.Net;  
using System.Net.Sockets;  
using System.Text;  
  
public class SynchronousSocketListener {  
  
    // Incoming data from the client.  
    public static string data = null;  
  
    public static void StartListening() {  
        // Data buffer for incoming data.  
        byte[] bytes = new Byte[1024];  
  
        // Establish the local endpoint for the socket.  
        // Dns.GetHostName returns the name of the
        // host running the application.  
        IPHostEntry ipHostInfo = Dns.GetHostEntry(Dns.GetHostName());  
        IPAddress ipAddress = ipHostInfo.AddressList[0];  
        IPEndPoint localEndPoint = new IPEndPoint(ipAddress, 11000);  
  
        // Create a TCP/IP socket.  
        Socket listener = new Socket(ipAddress.AddressFamily,  
            SocketType.Stream, ProtocolType.Tcp );  
  
        // Bind the socket to the local endpoint and
        // listen for incoming connections.  
        try {  
            listener.Bind(localEndPoint);  
            listener.Listen(10);  
  
            // Start listening for connections.  
            while (true) {  
                Console.WriteLine("Waiting for a connection...");  
                // Program is suspended while waiting for an incoming connection.  
                Socket handler = listener.Accept();  
                data = null;  
  
                // An incoming connection needs to be processed.  
                while (true) {  
                    int bytesRec = handler.Receive(bytes);  
                    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
                    if (data.IndexOf("<EOF>") > -1) {  
                        break;  
                    }  
                }  
  
                // Show the data on the console.  
                Console.WriteLine( "Text received : {0}", data);  
  
                // Echo the data back to the client.  
                byte[] msg = Encoding.ASCII.GetBytes(data);  
  
                handler.Send(msg);  
                handler.Shutdown(SocketShutdown.Both);  
                handler.Close();  
            }  
  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
  
        Console.WriteLine("\nPress ENTER to continue...");  
        Console.Read();  
  
    }  
  
    public static int Main(String[] args) {  
        StartListening();  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="259bc-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="259bc-109">See also</span></span>

- [<span data-ttu-id="259bc-110">Synchrone Clientsockets - Beispiel</span><span class="sxs-lookup"><span data-stu-id="259bc-110">Synchronous Client Socket Example</span></span>](synchronous-client-socket-example.md)
- [<span data-ttu-id="259bc-111">Verwenden eines synchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="259bc-111">Using a Synchronous Server Socket</span></span>](using-a-synchronous-server-socket.md)
- [<span data-ttu-id="259bc-112">Socketcodebeispiele</span><span class="sxs-lookup"><span data-stu-id="259bc-112">Socket Code Examples</span></span>](socket-code-examples.md)
