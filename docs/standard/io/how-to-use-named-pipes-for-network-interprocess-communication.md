---
title: 'Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- message-based communication [.NET Framework], named pipes
- named pipes [.NET Framework]
- pipes [.NET Framework]
- multiple connections via named pipes
- network communications [.NET Framework], named pipes
- impersonation [.NET Framework], named pipes
- full duplex communication [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
ms.openlocfilehash: 71f3a8d38b46993762b2673ea5fe735d8d54d351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706633"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a>Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk
Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit. Sie bieten mehr Funktionen als anonyme Pipes, die eine prozessübergreifende Kommunikation auf einem lokalen Computer bereitstellen. Benannte Pipes unterstützen Vollduplexkommunikation über ein Netzwerk und mehrere Serverinstanzen, meldungsbasierte Kommunikation und Clientidentitätswechsel, die verbindenden Prozessen die Verwendung ihrer eigenen Berechtigungen auf Remoteservern ermöglichen.  
  
 Um Namenspipes zu implementieren, verwenden Sie die <xref:System.IO.Pipes.NamedPipeServerStream>- und <xref:System.IO.Pipes.NamedPipeClientStream>-Klassen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie eine benannte Pipe mit der <xref:System.IO.Pipes.NamedPipeServerStream>-Klasse erstellt wird. In diesem Beispiel erstellt der Serverprozess vier Threads. Jeder Thread kann eine Clientverbindung akzeptieren. Der verbundene Clientprozess sendet daraufhin einen Dateinamen an den Server. Wenn der Client über ausreichende Berechtigungen verfügt, öffnet der Serverprozess die Datei und sendet ihren Inhalt an den Client zurück.  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt den Clientprozess, der die <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse verwendet. Der Client stellt eine Verbindung mit dem Serverprozess her und sendet einen Dateinamen an den Server. In diesem Beispiel wird ein Identitätswechsel verwendet, sodass die Identität, die die Clientanwendung ausführt, eine Berechtigung für den Zugriff auf die Datei benötigt. Anschließend sendet der Server den Inhalt der Datei an den Client zurück. Der Inhalt der Datei wird daraufhin auf der Konsole angezeigt.  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Der Client- und der Serverprozess in diesem Beispiel sind zur Ausführung auf dem gleichen Computer vorgesehen, sodass der Servername, der dem <xref:System.IO.Pipes.NamedPipeClientStream>-Objekt bereitgestellt wird, `"."` lautet. Wenn der Client- und der Serverprozess auf verschiedenen Computern ausgeführt würden, würde `"."` durch den Netzwerknamen des Computers ersetzt, auf dem der Serverprozess ausgeführt wird.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [Pipes](../../../docs/standard/io/pipe-operations.md)
- [Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
