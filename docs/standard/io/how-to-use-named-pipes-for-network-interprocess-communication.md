---
title: "Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
- full duplex communcation [.NET Framework], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 952600e71311184c4a4f906734addbf335d0358a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="fc9d4-102">Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk</span><span class="sxs-lookup"><span data-stu-id="fc9d4-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="fc9d4-103">Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="fc9d4-104">Sie bieten mehr Funktionen als anonyme Pipes, die eine prozessübergreifende Kommunikation auf einem lokalen Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="fc9d4-105">Benannte Pipes unterstützen Vollduplexkommunikation über ein Netzwerk und mehrere Serverinstanzen, meldungsbasierte Kommunikation und Clientidentitätswechsel, die verbindenden Prozessen die Verwendung ihrer eigenen Berechtigungen auf Remoteservern ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="fc9d4-106">Um Namenspipes zu implementieren, verwenden Sie die <xref:System.IO.Pipes.NamedPipeServerStream>- und <xref:System.IO.Pipes.NamedPipeClientStream>-Klassen.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc9d4-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc9d4-107">Example</span></span>  
 <span data-ttu-id="fc9d4-108">Das folgende Beispiel zeigt, wie eine benannte Pipe mit der <xref:System.IO.Pipes.NamedPipeServerStream>-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="fc9d4-109">In diesem Beispiel erstellt der Serverprozess vier Threads.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="fc9d4-110">Jeder Thread kann eine Clientverbindung akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="fc9d4-111">Der verbundene Clientprozess sendet daraufhin einen Dateinamen an den Server.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="fc9d4-112">Wenn der Client über ausreichende Berechtigungen verfügt, öffnet der Serverprozess die Datei und sendet ihren Inhalt an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="fc9d4-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc9d4-113">Example</span></span>  
 <span data-ttu-id="fc9d4-114">Das folgende Beispiel zeigt den Clientprozess, der die <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="fc9d4-115">Der Client stellt eine Verbindung mit dem Serverprozess her und sendet einen Dateinamen an den Server.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="fc9d4-116">In diesem Beispiel wird ein Identitätswechsel verwendet, sodass die Identität, die die Clientanwendung ausführt, eine Berechtigung für den Zugriff auf die Datei benötigt.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="fc9d4-117">Anschließend sendet der Server den Inhalt der Datei an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="fc9d4-118">Der Inhalt der Datei wird daraufhin auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="fc9d4-119">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="fc9d4-119">Robust Programming</span></span>  
 <span data-ttu-id="fc9d4-120">Der Client- und der Serverprozess in diesem Beispiel sind zur Ausführung auf dem gleichen Computer vorgesehen, sodass der Servername, der dem <xref:System.IO.Pipes.NamedPipeClientStream>-Objekt bereitgestellt wird, `"."` lautet.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="fc9d4-121">Wenn der Client- und der Serverprozess auf verschiedenen Computern ausgeführt würden, würde `"."` durch den Netzwerknamen des Computers ersetzt, auf dem der Serverprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fc9d4-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc9d4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc9d4-122">See Also</span></span>  
 <xref:System.Security.Principal.TokenImpersonationLevel>  
 <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>  
 [<span data-ttu-id="fc9d4-123">Pipes</span><span class="sxs-lookup"><span data-stu-id="fc9d4-123">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)  
 [<span data-ttu-id="fc9d4-124">Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation</span><span class="sxs-lookup"><span data-stu-id="fc9d4-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
