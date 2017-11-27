---
title: Verwenden von TCP-Diensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, TCP
- receiving data, TCP
- TcpClient class, about TcpClient class
- data requests, TCP
- application protocols, TCP
- network resources, TCP
- sending data, TCP
- TCP
- protocols, TCP
- Internet, TCP
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f560ae08c928e9f21def9f69950efbd72ccb6b88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="using-tcp-services"></a><span data-ttu-id="31e26-102">Verwenden von TCP-Diensten</span><span class="sxs-lookup"><span data-stu-id="31e26-102">Using TCP Services</span></span>
<span data-ttu-id="31e26-103">Die <xref:System.Net.Sockets.TcpClient>-Klasse fordert über TCP Daten von einer Internetressource an.</span><span class="sxs-lookup"><span data-stu-id="31e26-103">The <xref:System.Net.Sockets.TcpClient> class requests data from an Internet resource using TCP.</span></span> <span data-ttu-id="31e26-104">Die Eigenschaften und Methoden von **TcpClient** abstrahieren die Details zum Erstellen einer <xref:System.Net.Sockets.Socket> zum Anfordern und Empfangen von Daten mithilfe von TCP.</span><span class="sxs-lookup"><span data-stu-id="31e26-104">The methods and properties of **TcpClient** abstract the details for creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using TCP.</span></span> <span data-ttu-id="31e26-105">Da die Verbindung mit dem Remotegerät als Datenstrom dargestellt wird, können Daten mit Techniken zur Datenstromverarbeitung von .NET Framework gelesen und geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="31e26-105">Because the connection to the remote device is represented as a stream, data can be read and written with .NET Framework stream-handling techniques.</span></span>  
  
 <span data-ttu-id="31e26-106">Das TCP-Protokoll stellt eine Verbindung mit einem Remoteendpunkt her, und verwendet dann diese Verbindung zum Senden und Empfangen von Datenpaketen.</span><span class="sxs-lookup"><span data-stu-id="31e26-106">The TCP protocol establishes a connection with a remote endpoint and then uses that connection to send and receive data packets.</span></span> <span data-ttu-id="31e26-107">TCP ist dafür verantwortlich, dass die Datenpakete an den Endpunkt gesendet und in der richtigen Reihenfolge zusammengestellt werden, wenn sie ankommen.</span><span class="sxs-lookup"><span data-stu-id="31e26-107">TCP is responsible for ensuring that data packets are sent to the endpoint and assembled in the correct order when they arrive.</span></span>  
  
 <span data-ttu-id="31e26-108">Zur Erstellung einer TCP-Verbindung müssen Sie die Adresse des Netzwerkgeräts kennen, das den benötigten Dienst hostet und den TCP-Port, den der Dienst zum Kommunizieren verwendet.</span><span class="sxs-lookup"><span data-stu-id="31e26-108">To establish a TCP connection, you must know the address of the network device hosting the service you need and you must know the TCP port that the service uses to communicate.</span></span> <span data-ttu-id="31e26-109">Internet Assigned Numbers Authority (Iana) definiert die Portnummern für gemeinsame Dienste (weitere Informationen finden Sie unter www.iana.org/assignments/port-numbers).</span><span class="sxs-lookup"><span data-stu-id="31e26-109">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (see www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="31e26-110">Dienste, die sich nicht auf der Iana-Liste befinden, können Portnummern im Bereich von 1.024 bis 65.535 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="31e26-110">Services not on the Iana list can have port numbers in the range 1,024 to 65,535.</span></span>  
  
 <span data-ttu-id="31e26-111">Das folgende Beispiel veranschaulicht das Festlegen eines **TcpClient** zur Verbindung mit einem Zeitserver an TCP-Port 13.</span><span class="sxs-lookup"><span data-stu-id="31e26-111">The following example demonstrates setting up a **TcpClient** to connect to a time server on TCP port 13.</span></span>  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeClient  
    Private const portNum As Integer = 13  
    Private const hostName As String = "host.contoso.com"  
  
    ' Entry point  that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Try  
            Dim client As New TcpClient(hostName, portNum)  
  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim bytes(1024) As Byte  
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))  
  
        Catch e As Exception  
            Console.WriteLine(e.ToString())  
        End Try  
  
        client.Close()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeClient  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeClient {  
    private const int portNum = 13;  
    private const string hostName = "host.contoso.com";  
  
    public static int Main(String[] args) {  
        try {  
            TcpClient client = new TcpClient(hostName, portNum);  
  
            NetworkStream ns = client.GetStream();  
  
            byte[] bytes = new byte[1024];  
            int bytesRead = ns.Read(bytes, 0, bytes.Length);  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));  
  
            client.Close();  
  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
  
        return 0;  
    }  
}  
```  
  
 <span data-ttu-id="31e26-112"><xref:System.Net.Sockets.TcpListener> wird verwendet, um einen TCP-Port auf eingehende Anforderungen zu überwachen, und entweder einen **Socket** oder ein **TcpClient** zu erstellen, der die Verbindung mit dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="31e26-112"><xref:System.Net.Sockets.TcpListener> is used to monitor a TCP port for incoming requests and then create either a **Socket** or a **TcpClient** that manages the connection to the client.</span></span> <span data-ttu-id="31e26-113">Die <xref:System.Net.Sockets.TcpListener.Start%2A>-Methode ermöglicht die Überwachung, und die <xref:System.Net.Sockets.TcpListener.Stop%2A>-Methode deaktiviert die Überwachung des Ports.</span><span class="sxs-lookup"><span data-stu-id="31e26-113">The <xref:System.Net.Sockets.TcpListener.Start%2A> method enables listening, and the <xref:System.Net.Sockets.TcpListener.Stop%2A> method disables listening on the port.</span></span> <span data-ttu-id="31e26-114">Die <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A>-Methode akzeptiert eingehende Verbindungsanforderungen und erstellt einen **TcpClient** zur Verarbeitung der Anforderung. Die <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A>-Methode akzeptiert eingehende Verbindungsanforderungen und erstellt einen **Socket** zur Verarbeitung der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="31e26-114">The <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> method accepts incoming connection requests and creates a **TcpClient** to handle the request, and the <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> method accepts incoming connection requests and creates a **Socket** to handle the request.</span></span>  
  
 <span data-ttu-id="31e26-115">Das folgende Beispiel veranschaulicht das Erstellen eines Netzwerkzeitservers mithilfe eines **TcpListener** zur Überwachung des TCP-Ports 13.</span><span class="sxs-lookup"><span data-stu-id="31e26-115">The following example demonstrates creating a network time server using a **TcpListener** to monitor TCP port 13.</span></span> <span data-ttu-id="31e26-116">Wenn eine eingehende Verbindungsanforderung akzeptiert wird, antwortet der Zeitserver mit dem aktuellen Datum und der Uhrzeit vom Hostserver.</span><span class="sxs-lookup"><span data-stu-id="31e26-116">When an incoming connection request is accepted, the time server responds with the current date and time from the host server.</span></span>  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeServer  
  
    Private const portNum As Integer = 13  
  
    ' Entry point that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Dim done As Boolean = False  
  
        Dim listener As New TcpListener(portNum)  
  
        listener.Start()  
  
        While Not done  
            Console.Write("Waiting for connection...")  
            Dim client As TcpClient = listener.AcceptTcpClient()  
  
            Console.WriteLine("Connection accepted.")  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim byteTime As Byte() = _  
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())  
  
            Try  
                ns.Write(byteTime, 0, byteTime.Length)  
                ns.Close()  
                client.Close()  
            Catch e As Exception  
                Console.WriteLine(e.ToString())  
            End Try  
        End While  
  
        listener.Stop()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeServer  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeServer {  
  
    private const int portNum = 13;  
  
    public static int Main(String[] args) {  
        bool done = false;  
  
        TcpListener listener = new TcpListener(portNum);  
  
        listener.Start();  
  
        while (!done) {  
            Console.Write("Waiting for connection...");  
            TcpClient client = listener.AcceptTcpClient();  
  
            Console.WriteLine("Connection accepted.");  
            NetworkStream ns = client.GetStream();  
  
            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());  
  
            try {  
                ns.Write(byteTime, 0, byteTime.Length);  
                ns.Close();  
                client.Close();  
            } catch (Exception e) {  
                Console.WriteLine(e.ToString());  
            }  
        }  
  
        listener.Stop();  
  
        return 0;  
    }  
  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="31e26-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31e26-117">See Also</span></span>  
 
