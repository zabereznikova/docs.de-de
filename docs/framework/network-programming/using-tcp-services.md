---
title: Verwenden von TCP-Diensten
description: Die TcpClient-Klasse abstrahiert die Details, um einen Socket zum Anfordern und Empfangen von Daten mithilfe von TCP zu erstellen. Verwenden Sie die .NET Framework-Streamverarbeitung, um Daten zu lesen und zu schreiben.
ms.date: 03/30/2017
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
ms.openlocfilehash: 329701e8f11ca7f87c40ee8b2cc6a337435242b5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501962"
---
# <a name="using-tcp-services"></a>Verwenden von TCP-Diensten

Die <xref:System.Net.Sockets.TcpClient>-Klasse fordert über TCP Daten von einer Internetressource an. Die Eigenschaften und Methoden von **TcpClient** abstrahieren die Details zum Erstellen einer <xref:System.Net.Sockets.Socket> zum Anfordern und Empfangen von Daten mithilfe von TCP. Da die Verbindung mit dem Remotegerät als Datenstrom dargestellt wird, können Daten mit Techniken zur Datenstromverarbeitung von .NET Framework gelesen und geschrieben werden.

Das TCP-Protokoll stellt eine Verbindung mit einem Remoteendpunkt her, und verwendet dann diese Verbindung zum Senden und Empfangen von Datenpaketen. TCP ist dafür verantwortlich, dass die Datenpakete an den Endpunkt gesendet und in der richtigen Reihenfolge zusammengestellt werden, wenn sie ankommen.

Zur Erstellung einer TCP-Verbindung müssen Sie die Adresse des Netzwerkgeräts kennen, das den benötigten Dienst hostet und den TCP-Port, den der Dienst zum Kommunizieren verwendet. Die Internet Assigned Numbers Authority (IANA) definiert Portnummern für gemeinsame Dienste. Weitere Informationen finden Sie unter [Registrierung von Portnummern für Dienstnamen und Transportprotokolle](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (in englischer Sprache). Dienste, die sich nicht auf der Iana-Liste befinden, können Portnummern im Bereich von 1.024 bis 65.535 aufweisen.

Das folgende Beispiel veranschaulicht das Festlegen eines **TcpClient** zur Verbindung mit einem Zeitserver an TCP-Port 13:

```vb
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

    Overloads Public Shared Function Main(args As String()) As Integer
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
    End Function
End Class
```

```csharp
using System;
using System.Net.Sockets;
using System.Text;

public class TcpTimeClient
{
    private const int portNum = 13;
    private const string hostName = "host.contoso.com";

    public static int Main(String[] args)
    {
        try
        {
            var client = new TcpClient(hostName, portNum);

            NetworkStream ns = client.GetStream();

            byte[] bytes = new byte[1024];
            int bytesRead = ns.Read(bytes, 0, bytes.Length);

            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));

            client.Close();

        }
        catch (Exception e)
        {
            Console.WriteLine(e.ToString());
        }

        return 0;
    }
}
```

<xref:System.Net.Sockets.TcpListener> wird verwendet, um einen TCP-Port auf eingehende Anforderungen zu überwachen, und entweder einen **Socket** oder ein **TcpClient** zu erstellen, der die Verbindung mit dem Client verwaltet. Die <xref:System.Net.Sockets.TcpListener.Start%2A>-Methode ermöglicht die Überwachung, und die <xref:System.Net.Sockets.TcpListener.Stop%2A>-Methode deaktiviert die Überwachung des Ports. Die <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A>-Methode akzeptiert eingehende Verbindungsanforderungen und erstellt einen **TcpClient** zur Verarbeitung der Anforderung. Die <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A>-Methode akzeptiert eingehende Verbindungsanforderungen und erstellt einen **Socket** zur Verarbeitung der Anforderung.

Das folgende Beispiel veranschaulicht das Erstellen eines Netzwerkzeitservers mithilfe eines **TcpListener** zur Überwachung des TCP-Ports 13. Wenn eine eingehende Verbindungsanforderung akzeptiert wird, antwortet der Zeitserver mit dem aktuellen Datum und der Uhrzeit vom Hostserver.

```vb
Imports System.Net
Imports System.Net.Sockets
Imports System.Text

Public Class TcpTimeServer

    Private const portNum As Integer = 13

    ' Entry point that delegates to C-style main Private Function.
    Public Overloads Shared Sub Main()
        System.Environment.ExitCode = _
            Main(System.Environment.GetCommandLineArgs())
    End Sub

    Overloads Public Shared Function Main(args As String()) As Integer
        Dim done As Boolean = False

        Dim listener As New TcpListener(IPAddress.Any, portNum)

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
    End Function
End Class
```

```csharp
using System;
using System.Net;
using System.Net.Sockets;
using System.Text;

public class TcpTimeServer
{

    private const int portNum = 13;

    public static int Main(String[] args)
    {
        bool done = false;

        var listener = new TcpListener(IPAddress.Any, portNum);

        listener.Start();

        while (!done)
        {
            Console.Write("Waiting for connection...");
            TcpClient client = listener.AcceptTcpClient();

            Console.WriteLine("Connection accepted.");
            NetworkStream ns = client.GetStream();

            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());

            try
            {
                ns.Write(byteTime, 0, byteTime.Length);
                ns.Close();
                client.Close();
            }
            catch (Exception e)
            {
                Console.WriteLine(e.ToString());
            }
        }

        listener.Stop();

        return 0;
    }

}
```
