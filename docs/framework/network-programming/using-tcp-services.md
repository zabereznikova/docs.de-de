---
title: "Verwenden von TCP-Diensten | Microsoft Docs"
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
  - "Anfordern von Daten aus dem Internet, TCP"
  - "Empfangen von Daten, TCP"
  - "TcpClient-Klasse, Informationen zur TcpClient-Klasse"
  - "Datenanforderungen, TCP"
  - "Anwendungsprotokolle, TCP"
  - "Netzwerkressourcen, TCP"
  - "Senden von Daten, TCP"
  - "TCP"
  - "Protokolle, TCP"
  - "Internet, TCP"
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Verwenden von TCP-Diensten
Die <xref:System.Net.Sockets.TcpClient>\-Klasse fordert Daten von einer Internetressource mit TCP.  Die Methoden und Eigenschaften von **TcpClient** extrahieren die Details zum Erstellen von <xref:System.Net.Sockets.Socket> zum Anfordern und Empfangen von Daten mit TCP.  Da die Verbindung zum Remotegerät als Stream dargestellt wird, können Daten mit .NET Framework\-StreamBehandlung Techniken gelesen und geschrieben werden.  
  
 Das TCP\-Protokoll wird eine Verbindung mit einem Remoteberichtsserver Endpunkt und dann anhand fest, die die Verbindung, von Datenpaketen zu senden und zu empfangen.  TCP ist dafür verantwortlich, dass Datenpakete an den Endpunkt gesendet werden und in der richtigen Reihenfolge assembliert, wenn sie erhält.  
  
 Um eine TCP\-Verbindung festzulegen, müssen Sie die Adresse des Netzwerkgeräts kennen den Dienst hostet, den Sie benötigen und die TCP\-Port kennen die der Dienst zu übermitteln.  Die Internet Assigned Numbers Authority \(Iana\) definiert Portnummern für gemeinsame Dienste \(finden Sie unter www.iana.org\/assignments\/port\-numbers\).  Dienste nicht auf der IANA\-Liste Portnummern können im Bereich 1.024 bis 65.535 aufweisen.  
  
 Im folgenden Beispiel wird das Installieren von **TcpClient**, um an einen Zeitserver auf TCP\-Port 13 herzustellen.  
  
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
  
 <xref:System.Net.Sockets.TcpListener> wird verwendet, um eine TCP\-Port für eingehende Anforderungen zu überwachen und entweder **Socket** oder **TcpClient** dann zu erstellen, die die Verbindung mit dem Client verwaltet.  Die <xref:System.Net.Sockets.TcpListener.Start%2A>\-Methode ermöglicht das Lauschen, und die <xref:System.Net.Sockets.TcpListener.Stop%2A>\-Methode deaktiviert das Lauschen auf dem Port.  Die <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A>\-Methode akzeptiert eingehende Aufforderungen zum Aufbau einer Verbindung und erstellt **TcpClient**, um die Anforderung zu bearbeiten, und die <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A>\-Methode akzeptiert eingehende Aufforderungen zum Aufbau einer Verbindung und erstellt **Socket**, um die Anforderung zu bearbeiten.  
  
 Im folgenden Beispiel wird das Erstellen eines Netzwerkzeitservers mithilfe **TcpListener**, um TCP\-Port 13 zu überwachen.  Wenn eine eingehende Aufforderung zum Aufbau einer Verbindung akzeptiert wird, reagiert der Zeitserver mit dem aktuellen Datum und der Uhrzeit vom Hostserver.  
  
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
  
## Siehe auch  
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)