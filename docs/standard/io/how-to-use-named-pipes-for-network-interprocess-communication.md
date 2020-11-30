---
title: 'Vorgehensweise: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk'
description: Zwei Beispiele für die Verwendung von Named Pipes für die prozessübergreifende Kommunikation zwischen einem Pipeserver und mindestens einem Pipeclient in einem Netzwerk
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- message-based communication [.NET], named pipes
- named pipes [.NET]
- pipes [.NET]
- multiple connections via named pipes
- network communications [.NET], named pipes
- impersonation [.NET], named pipes
- full duplex communication [.NET], named pipes
ms.assetid: 4e4d7e64-9f1b-4026-98f7-20488ac7b42b
ms.openlocfilehash: 421fe06ce24fe8d78c7f8306db6a32ae83da694a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734542"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="f1e71-103">Vorgehensweise: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk</span><span class="sxs-lookup"><span data-stu-id="f1e71-103">How to: Use Named Pipes for Network Interprocess Communication</span></span>

<span data-ttu-id="f1e71-104">Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit.</span><span class="sxs-lookup"><span data-stu-id="f1e71-104">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="f1e71-105">Sie bieten mehr Funktionen als anonyme Pipes, die eine prozessübergreifende Kommunikation auf einem lokalen Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f1e71-105">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="f1e71-106">Benannte Pipes unterstützen Vollduplexkommunikation über ein Netzwerk und mehrere Serverinstanzen, meldungsbasierte Kommunikation und Clientidentitätswechsel, die verbindenden Prozessen die Verwendung ihrer eigenen Berechtigungen auf Remoteservern ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f1e71-106">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="f1e71-107">Um Namenspipes zu implementieren, verwenden Sie die <xref:System.IO.Pipes.NamedPipeServerStream>- und <xref:System.IO.Pipes.NamedPipeClientStream>-Klassen.</span><span class="sxs-lookup"><span data-stu-id="f1e71-107">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1e71-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1e71-108">Example</span></span>  

 <span data-ttu-id="f1e71-109">Das folgende Beispiel zeigt, wie eine benannte Pipe mit der <xref:System.IO.Pipes.NamedPipeServerStream>-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="f1e71-109">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="f1e71-110">In diesem Beispiel erstellt der Serverprozess vier Threads.</span><span class="sxs-lookup"><span data-stu-id="f1e71-110">In this example, the server process creates four threads.</span></span> <span data-ttu-id="f1e71-111">Jeder Thread kann eine Clientverbindung akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="f1e71-111">Each thread can accept a client connection.</span></span> <span data-ttu-id="f1e71-112">Der verbundene Clientprozess sendet daraufhin einen Dateinamen an den Server.</span><span class="sxs-lookup"><span data-stu-id="f1e71-112">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="f1e71-113">Wenn der Client über ausreichende Berechtigungen verfügt, öffnet der Serverprozess die Datei und sendet ihren Inhalt an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="f1e71-113">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="f1e71-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f1e71-114">Example</span></span>  

 <span data-ttu-id="f1e71-115">Das folgende Beispiel zeigt den Clientprozess, der die <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1e71-115">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="f1e71-116">Der Client stellt eine Verbindung mit dem Serverprozess her und sendet einen Dateinamen an den Server.</span><span class="sxs-lookup"><span data-stu-id="f1e71-116">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="f1e71-117">In diesem Beispiel wird ein Identitätswechsel verwendet, sodass die Identität, die die Clientanwendung ausführt, eine Berechtigung für den Zugriff auf die Datei benötigt.</span><span class="sxs-lookup"><span data-stu-id="f1e71-117">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="f1e71-118">Anschließend sendet der Server den Inhalt der Datei an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="f1e71-118">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="f1e71-119">Der Inhalt der Datei wird daraufhin auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f1e71-119">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="f1e71-120">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="f1e71-120">Robust Programming</span></span>  

 <span data-ttu-id="f1e71-121">Der Client- und der Serverprozess in diesem Beispiel sind zur Ausführung auf dem gleichen Computer vorgesehen, sodass der Servername, der dem <xref:System.IO.Pipes.NamedPipeClientStream>-Objekt bereitgestellt wird, `"."` lautet.</span><span class="sxs-lookup"><span data-stu-id="f1e71-121">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="f1e71-122">Wenn der Client- und der Serverprozess auf verschiedenen Computern ausgeführt würden, würde `"."` durch den Netzwerknamen des Computers ersetzt, auf dem der Serverprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f1e71-122">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1e71-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1e71-123">See also</span></span>

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [<span data-ttu-id="f1e71-124">Pipes</span><span class="sxs-lookup"><span data-stu-id="f1e71-124">Pipes</span></span>](pipe-operations.md)
- [<span data-ttu-id="f1e71-125">How to: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation</span><span class="sxs-lookup"><span data-stu-id="f1e71-125">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
