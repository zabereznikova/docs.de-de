---
title: Verwenden von UDP-Diensten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- protocols, UDP
- network resources, UDP
- requesting data from Internet, UDP
- UDP
- receiving data, UDP
- Internet, UDP
- broadcasting messages to multiple addresses
- data requests, UDP
- UdpClient class, about UdpClient class
- sending data, UDP
- application protocols, UDP
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
ms.openlocfilehash: 5ff40e8759b1732d4ad228b1414f96f9c37e5ac5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209772"
---
# <a name="use-udp-services"></a><span data-ttu-id="32588-102">Verwenden von UDP-Diensten</span><span class="sxs-lookup"><span data-stu-id="32588-102">Use UDP services</span></span>

<span data-ttu-id="32588-103">Die <xref:System.Net.Sockets.UdpClient>-Klasse kommuniziert über UDP-Netzwerkdienste.</span><span class="sxs-lookup"><span data-stu-id="32588-103">The <xref:System.Net.Sockets.UdpClient> class communicates with network services using UDP.</span></span> <span data-ttu-id="32588-104">Die Eigenschaften und Methoden der <xref:System.Net.Sockets.UdpClient>-Klasse abstrahieren Details zum Erstellen einer <xref:System.Net.Sockets.Socket> zum Anfordern und Empfangen von Daten mithilfe von UDP.</span><span class="sxs-lookup"><span data-stu-id="32588-104">The properties and methods of the <xref:System.Net.Sockets.UdpClient> class abstract the details of creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using UDP.</span></span>

<span data-ttu-id="32588-105">User Datagram Protocol (UDP) ist ein einfaches Protokoll, das Daten an einen Remotehost übermittelt.</span><span class="sxs-lookup"><span data-stu-id="32588-105">User Datagram Protocol (UDP) is a simple protocol that makes a best effort to deliver data to a remote host.</span></span> <span data-ttu-id="32588-106">Da das UDP-Protokoll ein verbindungsloses Protokoll ist, kann jedoch nicht garantiert werden, dass die an den Remoteendpunkt gesendeten UDP-Datagramme eingehen oder dass sie in der Reihenfolge eintreffen, in der sie gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="32588-106">However, because the UDP protocol is a connectionless protocol, UDP datagrams sent to the remote endpoint are not guaranteed to arrive, nor are they guaranteed to arrive in the same sequence in which they are sent.</span></span> <span data-ttu-id="32588-107">Anwendungen, die UDP verwenden, müssen darauf vorbereitet sein, fehlende, doppelte und ungeordnete Datagramme zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="32588-107">Applications that use UDP must be prepared to handle missing, duplicate, and out-of-sequence datagrams.</span></span>

<span data-ttu-id="32588-108">Um ein Datagramm über UDP zu senden, müssen Sie die Netzwerkadresse des Netzwerkgeräts kennen, das den Dienst hostet und die UDP-Portnummer, die vom Dienst zum Kommunizieren verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="32588-108">To send a datagram using UDP, you must know the network address of the network device hosting the service you need and the UDP port number that the service uses to communicate.</span></span> <span data-ttu-id="32588-109">Die Internet Assigned Numbers Authority (IANA) definiert Portnummern für gemeinsame Dienste. Weitere Informationen finden Sie unter [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (Registrierung von Portnummern für Dienstnamen und Transportprotokolle).</span><span class="sxs-lookup"><span data-stu-id="32588-109">The Internet Assigned Numbers Authority (IANA) defines port numbers for common services (see [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)).</span></span> <span data-ttu-id="32588-110">Dienste, die sich nicht auf der IANA-Liste befinden, können Portnummern im Bereich von 1.024 bis 65.535 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="32588-110">Services not on the IANA list can have port numbers in the range 1,024 to 65,535.</span></span>

<span data-ttu-id="32588-111">Spezielle Netzwerkadressen dienen zur Unterstützung von UDP-Broadcastmeldungen auf IP-basierten Netzwerken.</span><span class="sxs-lookup"><span data-stu-id="32588-111">Special network addresses are used to support UDP broadcast messages on IP-based networks.</span></span> <span data-ttu-id="32588-112">Die folgende Darstellung verwendet die IPv4-Adressfamilie im Internet als Beispiel.</span><span class="sxs-lookup"><span data-stu-id="32588-112">The following discussion uses the IP version 4 address family used on the Internet as an example.</span></span>

<span data-ttu-id="32588-113">IPv4-Adressen verwenden 32 Bits zur Angabe einer Netzwerkadresse.</span><span class="sxs-lookup"><span data-stu-id="32588-113">IP version 4 addresses use 32 bits to specify a network address.</span></span> <span data-ttu-id="32588-114">Bei C-Adressen der Klasse, die eine Netzmaske 255.255.255.0 verwenden, werden diese Bits in vier Oktette aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="32588-114">For class C addresses using a netmask of 255.255.255.0, these bits are separated into four octets.</span></span> <span data-ttu-id="32588-115">Als Dezimalzahlen ausgedrückt, bilden die vier Oktette die vertraute Punktnotation, z.B. 192.168.100.2.</span><span class="sxs-lookup"><span data-stu-id="32588-115">When expressed in decimal, the four octets form the familiar dotted-quad notation, such as 192.168.100.2.</span></span> <span data-ttu-id="32588-116">Die ersten beiden Oktette (in diesem Beispiel 192.168.) bilden die Netzwerknummer, das dritte Oktett (100) definiert das Subnetz, und das letzte Oktett (2) ist der Hostbezeichner.</span><span class="sxs-lookup"><span data-stu-id="32588-116">The first two octets (192.168 in this example) form the network number, the third octet (100) defines the subnet, and the final octet (2) is the host identifier.</span></span>

<span data-ttu-id="32588-117">Wenn alle Bits einer IP-Adresse auf einem oder 255.255.255.255 festgelegt werden, wird die begrenzte Broadcastadresse gebildet.</span><span class="sxs-lookup"><span data-stu-id="32588-117">Setting all the bits of an IP address to one, or 255.255.255.255, forms the limited broadcast address.</span></span> <span data-ttu-id="32588-118">Das Senden eines UDP-Datagramms an diese Adresse übermittelt die Nachricht an jeden Host im LAN-Segment.</span><span class="sxs-lookup"><span data-stu-id="32588-118">Sending a UDP datagram to this address delivers the message to any host on the local network segment.</span></span> <span data-ttu-id="32588-119">Da Router an diese Adresse gesendete Nachrichten nie weiterleiten, erhalten nur die Hosts im Netzwerksegment die Broadcastmeldung.</span><span class="sxs-lookup"><span data-stu-id="32588-119">Because routers never forward messages sent to this address, only hosts on the network segment receive the broadcast message.</span></span>

<span data-ttu-id="32588-120">Broadcasts können auf bestimmte Teile eines Netzwerks geleitet werden, indem alle Bits des Hostbezeichners festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="32588-120">Broadcasts can be directed to specific portions of a network by setting all bits of the host identifier.</span></span> <span data-ttu-id="32588-121">Um einen Broadcast an alle Hosts im Netzwerk zu senden, die eine IP-Adresse beginnend mit 192.168.1 aufweisen, verwenden Sie beispielsweise die Adresse 192.168.1.255.</span><span class="sxs-lookup"><span data-stu-id="32588-121">For example, to send a broadcast to all hosts on the network identified by IP addresses starting with 192.168.1, use the address 192.168.1.255.</span></span>

<span data-ttu-id="32588-122">In dem folgenden Codebeispiel wird ein <xref:System.Net.Sockets.UdpClient> verwendet, um UDP-Datagramme auf Port 11.000 abzuhören.</span><span class="sxs-lookup"><span data-stu-id="32588-122">The following code example uses a <xref:System.Net.Sockets.UdpClient> to listen for UDP datagrams on port 11,000.</span></span> <span data-ttu-id="32588-123">Der Client empfängt eine Meldungszeichenfolge und schreibt die Nachricht in die Konsole.</span><span class="sxs-lookup"><span data-stu-id="32588-123">The client receives a message string and writes the message to the console.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class UDPListener
   Private Const listenPort As Integer = 11000

   Private Shared Sub StartListener()
      Dim listener As New UdpClient(listenPort)
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)
      Try
         While True
            Console.WriteLine("Waiting for broadcast")
            Dim bytes As Byte() = listener.Receive(groupEP)
            Console.WriteLine("Received broadcast from {0} :", groupEP)
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytes.Length))
         End While
      Catch e As SocketException
         Console.WriteLine(e)
      Finally
         listener.Close()
      End Try
   End Sub 'StartListener

   Public Shared Sub Main()
      StartListener()
   End Sub 'Main
End Class 'UDPListener
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class UDPListener
{
    private const int listenPort = 11000;

    private static void StartListener()
    {
        UdpClient listener = new UdpClient(listenPort);
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any, listenPort);

        try
        {
            while (true)
            {
                Console.WriteLine("Waiting for broadcast");
                byte[] bytes = listener.Receive(ref groupEP);

                Console.WriteLine($"Received broadcast from {groupEP} :");
                Console.WriteLine($" {Encoding.ASCII.GetString(bytes, 0, bytes.Length)}");
            }
        }
        catch (SocketException e)
        {
            Console.WriteLine(e);
        }
        finally
        {
            listener.Close();
        }
    }

    public static void Main()
    {
        StartListener();
    }
}
```

<span data-ttu-id="32588-124">Das folgende Codebeispiel verwendet <xref:System.Net.Sockets.Socket> zum Senden von UDP-Datagrammen an die gesteuerte Broadcastadresse 192.168.1.255 auf Port 11.000.</span><span class="sxs-lookup"><span data-stu-id="32588-124">The following code example uses a <xref:System.Net.Sockets.Socket> to send UDP datagrams to the directed broadcast address 192.168.1.255, using port 11,000.</span></span> <span data-ttu-id="32588-125">Der Client sendet die Meldungszeichenfolge, die in der Befehlszeile angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="32588-125">The client sends the message string specified on the command line.</span></span>

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class Program
    Public Shared Sub Main(args() As [String])
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram, ProtocolType.Udp)
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))
      Dim ep As New IPEndPoint(broadcast, 11000)
      s.SendTo(sendbuf, ep)
      Console.WriteLine("Message sent to the broadcast address")
   End Sub 'Main
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

class Program
{
    static void Main(string[] args)
    {
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram, ProtocolType.Udp);

        IPAddress broadcast = IPAddress.Parse("192.168.1.255");

        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);

        s.SendTo(sendbuf, ep);

        Console.WriteLine("Message sent to the broadcast address");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="32588-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32588-126">See also</span></span>

- <xref:System.Net.Sockets.UdpClient>
- <xref:System.Net.IPAddress>
