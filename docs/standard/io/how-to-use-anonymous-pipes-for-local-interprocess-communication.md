---
title: 'Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- anonymous pipes [.NET Framework]
- parent-child communication [.NET Framework]
- pipes [.NET Framework]
- one-way communication [.NET Framework]
- local computer communication [.NET Framework], pipes
ms.assetid: e7773c77-c646-4a01-8a96-a003d59fc4c9
ms.openlocfilehash: ea4aee60d090a56eb0cf3f2a81c1b05c04806d4b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "77627993"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a>Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation
Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit. Sie bieten zwar weniger Funktionen als benannte Pipes, erfordern aber auch weniger Mehraufwand. Sie können anonyme Pipes verwenden, um die prozessübergreifende Kommunikation auf einem lokalen Computer zu vereinfachen. Anonyme Pipes können nicht zur Kommunikation über ein Netzwerk verwendet werden.  
  
 Um anonyme Pipes zu implementieren, verwenden Sie die <xref:System.IO.Pipes.AnonymousPipeServerStream>- und <xref:System.IO.Pipes.AnonymousPipeClientStream>-Klassen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie eine Zeichenfolge mithilfe von anonymen Pipes von einem übergeordneten Prozess an einen untergeordneten Prozess gesendet werden kann. In diesem Beispiel wird ein <xref:System.IO.Pipes.AnonymousPipeServerStream>-Objekt in einem übergeordneten Prozess mit dem <xref:System.IO.Pipes.PipeDirection>-Wert <xref:System.IO.Pipes.PipeDirection.Out> erstellt. Anschließend wird vom übergeordneten Prozess ein untergeordneter Prozess erstellt, indem ein Clienthandle zur Erstellung eines <xref:System.IO.Pipes.AnonymousPipeClientStream>-Objekts verwendet wird. Der untergeordnete Prozess hat den <xref:System.IO.Pipes.PipeDirection>-Wert <xref:System.IO.Pipes.PipeDirection.In>.  
  
 Der übergeordnete Prozess sendet daraufhin eine vom Benutzer bereitgestellte Zeichenfolge an den untergeordneten Prozess. Die Zeichenfolge wird im untergeordneten Prozess auf der Konsole angezeigt.  
  
 Das folgende Codebeispiel zeigt den Serverprozess:  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel zeigt den Clientprozess: Der Serverprozess startet den Clientprozess und übergibt ein Clienthandle an diesen Prozess. Die resultierende ausführbare Datei aus dem Clientcode sollte `pipeClient.exe` genannt und in dasselbe Verzeichnis kopiert werden wie die ausführbare Datei des Servers, bevor der Serverprozess ausgeführt wird.  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Pipes](../../../docs/standard/io/pipe-operations.md)
- [Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
