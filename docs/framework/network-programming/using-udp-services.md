---
title: Verwenden von UDP-Diensten
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
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
caps.latest.revision: 15
author: mcleblanc
ms.author: markl
manager: markl
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2986feda76b035e3651712609364b4194378a64c
ms.contentlocale: de-de
ms.lasthandoff: 08/21/2017

---
# <a name="using-udp-services"></a>Verwenden von UDP-Diensten
Die <xref:System.Net.Sockets.UdpClient>-Klasse kommuniziert über UDP-Netzwerkdienste. Die Eigenschaften und Methoden der <xref:System.Net.Sockets.UdpClient>-Klasse abstrahieren Details zum Erstellen einer <xref:System.Net.Sockets.Socket> zum Anfordern und Empfangen von Daten mithilfe von UDP.  
  
 User Datagram Protocol (UDP) ist ein einfaches Protokoll, das Daten an einen Remotehost übermittelt. Da das UDP-Protokoll ein verbindungsloses Protokoll ist, kann jedoch nicht garantiert werden, dass die an den Remoteendpunkt gesendeten UDP-Datagramme eingehen oder dass sie in der Reihenfolge eintreffen, in der sie gesendet werden. Anwendungen, die UDP verwenden, müssen darauf vorbereitet sein, fehlende, doppelte und ungeordnete Datagramme zu behandeln.  
  
 Um ein Datagramm über UDP zu senden, müssen Sie die Netzwerkadresse des Netzwerkgeräts kennen, das den Dienst hostet und die UDP-Portnummer, die vom Dienst zum Kommunizieren verwendet wird. Internet Assigned Numbers Authority (Iana) definiert die Portnummern für gemeinsame Dienste (weitere Informationen finden Sie unter www.iana.org/assignments/port-numbers). Dienste, die sich nicht auf der Iana-Liste befinden können Portnummern im Bereich von 1024 bis 65.535 aufweisen.  
  
 Spezielle Netzwerkadressen dienen zur Unterstützung von UDP-Broadcastmeldungen auf IP-basierten Netzwerken. Die folgende Darstellung verwendet die IPv4-Adressfamilie im Internet als Beispiel.  
  
 IPv4-Adressen verwenden 32 Bits zur Angabe einer Netzwerkadresse. Bei C-Adressen der Klasse, die eine Netzmaske 255.255.255.0 verwenden, werden diese Bits in vier Oktette aufgeteilt. Als Dezimalzahlen ausgedrückt, bilden die vier Oktette die vertraute Punktnotation, z.B. 192.168.100.2. Die ersten beiden Oktette (in diesem Beispiel 192.168.) bilden die Netzwerknummer, das dritte Oktett (100) definiert das Subnetz, und das letzte Oktett (2) ist der Hostbezeichner.  
  
 Wenn alle Bits einer IP-Adresse auf einem oder 255.255.255.255 festgelegt werden, wird die begrenzte Broadcastadresse gebildet. Das Senden eines UDP-Datagramms an diese Adresse übermittelt die Nachricht an jeden Host im LAN-Segment. Da Router an diese Adresse gesendete Nachrichten nie weiterleiten, erhalten nur die Hosts im Netzwerksegment die Broadcastmeldung.  
  
 Broadcasts können auf bestimmte Teile eines Netzwerks geleitet werden, indem alle Bits des Hostbezeichners festgelegt werden. Um einen Broadcast an alle Hosts im Netzwerk zu senden, die eine IP-Adresse beginnend mit 192.168.1 aufweisen, verwenden Sie beispielsweise die Adresse 192.168.1.255.  
  
 Das folgende Codebeispiel verwendet <xref:System.Net.Sockets.UdpClient> zum Abhören von UDP-Datagrammen, die an die gesteuerte Broadcastadresse 192.168.1.255 auf Port 11.000 gesendet werden. Der Client empfängt eine Meldungszeichenfolge und schreibt die Nachricht in die Konsole.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class UDPListener  
   Private Const listenPort As Integer = 11000  
  
   Private Shared Sub StartListener()  
      Dim done As Boolean = False  
      Dim listener As New UdpClient(listenPort)  
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)  
      Try  
         While Not done  
            Console.WriteLine("Waiting for broadcast")  
            Dim bytes As Byte() = listener.Receive(groupEP)  
            Console.WriteLine("Received broadcast from {0} :", _  
                groupEP.ToString())   
            Console.WriteLine( _  
                Encoding.ASCII.GetString(bytes, 0, bytes.Length))  
            Console.WriteLine()  
         End While  
      Catch e As Exception  
         Console.WriteLine(e.ToString())  
      Finally  
         listener.Close()  
      End Try  
   End Sub 'StartListener  
  
   Public Shared Function Main() As Integer  
      StartListener()  
      Return 0  
   End Function 'Main  
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
        bool done = false;  
  
        UdpClient listener = new UdpClient(listenPort);  
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any,listenPort);  
  
        try   
        {  
            while (!done)   
            {  
                Console.WriteLine("Waiting for broadcast");  
                byte[] bytes = listener.Receive( ref groupEP);  
  
                Console.WriteLine("Received broadcast from {0} :\n {1}\n",  
                    groupEP.ToString(),  
                    Encoding.ASCII.GetString(bytes,0,bytes.Length));  
            }  
  
        }   
        catch (Exception e)   
        {  
            Console.WriteLine(e.ToString());  
        }  
        finally  
        {  
            listener.Close();  
        }  
    }  
  
    public static int Main()   
    {  
        StartListener();  
  
        return 0;  
    }  
}  
```  
  
 Das folgende Codebeispiel verwendet <xref:System.Net.Sockets.UdpClient> zum Senden von UDP-Datagrammen an die gesteuerte Broadcastadresse 192.168.1.255 auf Port 11.000. Der Client sendet die Meldungszeichenfolge, die in der Befehlszeile angegeben ist.  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class Program  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
          ProtocolType.Udp)  
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")  
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))  
      Dim ep As New IPEndPoint(broadcast, 11000)  
      s.SendTo(sendbuf, ep)  
      Console.WriteLine("Message sent to the broadcast address")  
   End Function 'Main  
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
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
            ProtocolType.Udp);  
  
        IPAddress broadcast = IPAddress.Parse("192.168.1.255");  
  
        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);  
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);  
  
        s.SendTo(sendbuf, ep);  
  
        Console.WriteLine("Message sent to the broadcast address");  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Net.Sockets.UdpClient>   
 <xref:System.Net.IPAddress>   
 

