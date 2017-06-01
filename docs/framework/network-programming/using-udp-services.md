---
title: "Verwenden von UDP-Diensten | Microsoft Docs"
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
  - "Protokolle, UDP"
  - "Netzwerkressourcen, UDP"
  - "Anfordern von Daten aus dem Internet, UDP"
  - "UDP"
  - "Empfangen von Daten, UDP"
  - "Internet, UDP"
  - "Übertragen von Nachrichten an mehrere Adressen"
  - "Datenanforderungen, UDP"
  - "UdpClient-Klasse, Informationen zur UdpClient-Klasse"
  - "Senden von Daten, UDP"
  - "Anwendungsprotokolle, UDP"
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# Verwenden von UDP-Diensten
Die <xref:System.Net.Sockets.UdpClient>\-Klasse kommuniziert mit Netzwerkdiensten über UDP.  Die Eigenschaften und Methoden der <xref:System.Net.Sockets.UdpClient>\-Klasse extrahieren die Erstellung von <xref:System.Net.Sockets.Socket> zum Anfordern und Empfangen von Daten mit UDP.  
  
 User Datagram\-Protokoll \(UDP\) ist ein einfaches Protokoll, das eine optimale Anstrengung unternimmt, Daten zu einem Remotehost bereitzustellen.  Da das UDP\-Protokoll ein verbindungsloses Protokoll, werden UDP\-Datagramme, die auf den Endpunkt gesendet werden, nicht gewährleistet, dass anzukommen, noch sie garantiert, um in der gleichen Reihenfolge anzukommen, in der sie gesendet werden.  Anwendungen, die UDP verwenden, müssen vorbereitet werden, fehlen, Duplikat und ungeordnete Datagramme zu behandeln.  
  
 Um ein Datagramm mit UDP zu senden, müssen Sie die Netzwerkadresse des Netzwerkgeräts kennen den Dienst hostet, den Sie und die UDP\-Portnummer erfordern die der Dienst zu übermitteln.  Die Internet Assigned Numbers Authority \(Iana\) definiert Portnummern für gemeinsame Dienste \(finden Sie unter www.iana.org\/assignments\/port\-numbers\).  Dienste nicht auf der IANA\-Liste Portnummern können im Bereich 1.024 bis 65.535 aufweisen.  
  
 Besondere Endsystemadressen werden verwendet, um UDP\-Broadcastmeldungen auf IP\-basierten Netzwerke zu unterstützen.  Die folgende Diskussion verwendet die Adressenfamilie IP\-Version 4, die als Beispiel im Internet verwendet wird.  
  
 Adressen IP\-Version 32 Bits 4 verwenden, um eine Netzwerkadresse anzugeben.  Für Klasse C\-Adressen mithilfe einer Netmask von 255.255.255.0, werden diese Bits in vier Oktette getrennt.  Wenn sie im Dezimalformat ausgedrückt werden, bilden die vier Oktette das bekannte Punktformat \(Dotted Quad\-Notation\), wie 192.168.100.2.  Die ersten beiden Oktette \(192.168 in diesem Beispiel\) bilden das network number, das dritte Oktett \(100\) definiert das Subnetz und das endgültige Oktett, die \(2\) der Hostbezeichner ist.  
  
 Alle Bits einer IP\-Adresse bis eine oder 255.255.255.255, Formulare festlegen die eingeschränkte Broadcastadresse.  Ein UDP\-Datagramm an diese Adresse zu senden, stellt die Meldung zu einem Host im Segment des lokalen Netzwerks zu.  Da Router die Meldungen nie weiterleiten, die an diese Adresse gesendet werden, empfangen nur Hosts auf dem Netzwerksegment die Broadcastmeldung.  
  
 Übertragungen können auf bestimmte Teile eines Netzwerks verwiesen werden, indem alle Bits des Hostbezeichners festgelegt werden.  Wenn beispielsweise eine Übertragung für alle Hosts im Netzwerk zu senden, das von IP\-Adressen beginnend mit 192.168.1 identifiziert wird, verwenden Sie die Adresse 192.168.1.255.  
  
 Im folgenden Codebeispiel wird <xref:System.Net.Sockets.UdpClient>, um auf UDP\-Datagramme zu überwachen, die zur verwiesen wird Broadcastadresse 192.168.1.255 auf Port 11.000 gesendet werden.  Der Client empfängt eine Meldungszeichenfolge und schreibt die Meldung an die Konsole.  
  
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
  
 Im folgenden Codebeispiel wird <xref:System.Net.Sockets.UdpClient>, um UDP\-Datagramme zur verwiesen wird Broadcastadresse 192.168.1.255, mit Anschluss 11.000 zu senden.  Der Client sendet die Meldungszeichenfolge, die in der Befehlszeile angegeben wird.  
  
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
  
## Siehe auch  
 <xref:System.Net.Sockets.UdpClient>   
 <xref:System.Net.IPAddress>   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)