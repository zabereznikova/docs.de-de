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
ms.openlocfilehash: 477095ada6e44f66cbc60cd80375da9a87f38e39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180603"
---
# <a name="using-udp-services"></a>Verwenden von UDP-Diensten
Die <xref:System.Net.Sockets.UdpClient>-Klasse kommuniziert über UDP-Netzwerkdienste. Die Eigenschaften und Methoden der <xref:System.Net.Sockets.UdpClient>-Klasse abstrahieren Details zum Erstellen einer <xref:System.Net.Sockets.Socket> zum Anfordern und Empfangen von Daten mithilfe von UDP.

User Datagram Protocol (UDP) ist ein einfaches Protokoll, das Daten an einen Remotehost übermittelt. Da das UDP-Protokoll ein verbindungsloses Protokoll ist, kann jedoch nicht garantiert werden, dass die an den Remoteendpunkt gesendeten UDP-Datagramme eingehen oder dass sie in der Reihenfolge eintreffen, in der sie gesendet werden. Anwendungen, die UDP verwenden, müssen darauf vorbereitet sein, fehlende, doppelte und ungeordnete Datagramme zu behandeln.

Um ein Datagramm über UDP zu senden, müssen Sie die Netzwerkadresse des Netzwerkgeräts kennen, das den Dienst hostet und die UDP-Portnummer, die vom Dienst zum Kommunizieren verwendet wird. Die Internet Assigned Numbers Authority (IANA) definiert Portnummern für gemeinsame Dienste. Weitere Informationen finden Sie unter [Registrierung von Portnummern für Dienstnamen und Transportprotokolle](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (in englischer Sprache). Dienste, die sich nicht auf der Iana-Liste befinden, können Portnummern im Bereich von 1.024 bis 65.535 aufweisen.

Spezielle Netzwerkadressen dienen zur Unterstützung von UDP-Broadcastmeldungen auf IP-basierten Netzwerken. Die folgende Darstellung verwendet die IPv4-Adressfamilie im Internet als Beispiel.

IPv4-Adressen verwenden 32 Bits zur Angabe einer Netzwerkadresse. Bei C-Adressen der Klasse, die eine Netzmaske 255.255.255.0 verwenden, werden diese Bits in vier Oktette aufgeteilt. Als Dezimalzahlen ausgedrückt, bilden die vier Oktette die vertraute Punktnotation, z.B. 192.168.100.2. Die ersten beiden Oktette (in diesem Beispiel 192.168.) bilden die Netzwerknummer, das dritte Oktett (100) definiert das Subnetz, und das letzte Oktett (2) ist der Hostbezeichner.

Wenn alle Bits einer IP-Adresse auf einem oder 255.255.255.255 festgelegt werden, wird die begrenzte Broadcastadresse gebildet. Das Senden eines UDP-Datagramms an diese Adresse übermittelt die Nachricht an jeden Host im LAN-Segment. Da Router an diese Adresse gesendete Nachrichten nie weiterleiten, erhalten nur die Hosts im Netzwerksegment die Broadcastmeldung.

Broadcasts können auf bestimmte Teile eines Netzwerks geleitet werden, indem alle Bits des Hostbezeichners festgelegt werden. Um einen Broadcast an alle Hosts im Netzwerk zu senden, die eine IP-Adresse beginnend mit 192.168.1 aufweisen, verwenden Sie beispielsweise die Adresse 192.168.1.255.

In dem folgenden Codebeispiel wird ein <xref:System.Net.Sockets.UdpClient> verwendet, um UDP-Datagramme auf Port 11.000 abzuhören. Der Client empfängt eine Meldungszeichenfolge und schreibt die Nachricht in die Konsole.

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

Das folgende Codebeispiel verwendet <xref:System.Net.Sockets.Socket> zum Senden von UDP-Datagrammen an die gesteuerte Broadcastadresse 192.168.1.255 auf Port 11.000. Der Client sendet die Meldungszeichenfolge, die in der Befehlszeile angegeben ist.

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

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Net.Sockets.UdpClient>
- <xref:System.Net.IPAddress>
