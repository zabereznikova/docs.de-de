---
title: 'Vorgehensweise: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk'
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
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706633"
---
# <a name="how-to-use-named-pipes-for-network-interprocess-communication"></a><span data-ttu-id="dd57b-102">Vorgehensweise: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk</span><span class="sxs-lookup"><span data-stu-id="dd57b-102">How to: Use Named Pipes for Network Interprocess Communication</span></span>
<span data-ttu-id="dd57b-103">Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit.</span><span class="sxs-lookup"><span data-stu-id="dd57b-103">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="dd57b-104">Sie bieten mehr Funktionen als anonyme Pipes, die eine prozessübergreifende Kommunikation auf einem lokalen Computer bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dd57b-104">They offer more functionality than anonymous pipes, which provide interprocess communication on a local computer.</span></span> <span data-ttu-id="dd57b-105">Benannte Pipes unterstützen Vollduplexkommunikation über ein Netzwerk und mehrere Serverinstanzen, meldungsbasierte Kommunikation und Clientidentitätswechsel, die verbindenden Prozessen die Verwendung ihrer eigenen Berechtigungen auf Remoteservern ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="dd57b-105">Named pipes support full duplex communication over a network and multiple server instances, message-based communication, and client impersonation, which enables connecting processes to use their own set of permissions on remote servers.</span></span>  
  
 <span data-ttu-id="dd57b-106">Um Namenspipes zu implementieren, verwenden Sie die <xref:System.IO.Pipes.NamedPipeServerStream>- und <xref:System.IO.Pipes.NamedPipeClientStream>-Klassen.</span><span class="sxs-lookup"><span data-stu-id="dd57b-106">To implement name pipes, use the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd57b-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd57b-107">Example</span></span>  
 <span data-ttu-id="dd57b-108">Das folgende Beispiel zeigt, wie eine benannte Pipe mit der <xref:System.IO.Pipes.NamedPipeServerStream>-Klasse erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="dd57b-108">The following example demonstrates how to create a named pipe by using the <xref:System.IO.Pipes.NamedPipeServerStream> class.</span></span> <span data-ttu-id="dd57b-109">In diesem Beispiel erstellt der Serverprozess vier Threads.</span><span class="sxs-lookup"><span data-stu-id="dd57b-109">In this example, the server process creates four threads.</span></span> <span data-ttu-id="dd57b-110">Jeder Thread kann eine Clientverbindung akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="dd57b-110">Each thread can accept a client connection.</span></span> <span data-ttu-id="dd57b-111">Der verbundene Clientprozess sendet daraufhin einen Dateinamen an den Server.</span><span class="sxs-lookup"><span data-stu-id="dd57b-111">The connected client process then supplies the server with a file name.</span></span> <span data-ttu-id="dd57b-112">Wenn der Client über ausreichende Berechtigungen verfügt, öffnet der Serverprozess die Datei und sendet ihren Inhalt an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="dd57b-112">If the client has sufficient permissions, the server process opens the file and sends its contents back to the client.</span></span>  
  
 [!code-cpp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeServerStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeServerStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="example"></a><span data-ttu-id="dd57b-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd57b-113">Example</span></span>  
 <span data-ttu-id="dd57b-114">Das folgende Beispiel zeigt den Clientprozess, der die <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd57b-114">The following example shows the client process, which uses the <xref:System.IO.Pipes.NamedPipeClientStream> class.</span></span> <span data-ttu-id="dd57b-115">Der Client stellt eine Verbindung mit dem Serverprozess her und sendet einen Dateinamen an den Server.</span><span class="sxs-lookup"><span data-stu-id="dd57b-115">The client connects to the server process and sends a file name to the server.</span></span> <span data-ttu-id="dd57b-116">In diesem Beispiel wird ein Identitätswechsel verwendet, sodass die Identität, die die Clientanwendung ausführt, eine Berechtigung für den Zugriff auf die Datei benötigt.</span><span class="sxs-lookup"><span data-stu-id="dd57b-116">The example uses impersonation, so the identity that is running the client application must have permission to access the file.</span></span> <span data-ttu-id="dd57b-117">Anschließend sendet der Server den Inhalt der Datei an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="dd57b-117">The server then sends the contents of the file back to the client.</span></span> <span data-ttu-id="dd57b-118">Der Inhalt der Datei wird daraufhin auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd57b-118">The file contents are then displayed to the console.</span></span>  
  
 [!code-csharp[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.NamedPipeClientStream_ImpersonationSample1#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.NamedPipeClientStream_ImpersonationSample1/vb/program.vb#01)]  
  
## <a name="robust-programming"></a><span data-ttu-id="dd57b-119">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="dd57b-119">Robust Programming</span></span>  
 <span data-ttu-id="dd57b-120">Der Client- und der Serverprozess in diesem Beispiel sind zur Ausführung auf dem gleichen Computer vorgesehen, sodass der Servername, der dem <xref:System.IO.Pipes.NamedPipeClientStream>-Objekt bereitgestellt wird, `"."` lautet.</span><span class="sxs-lookup"><span data-stu-id="dd57b-120">The client and server processes in this example are intended to run on the same computer, so the server name provided to the <xref:System.IO.Pipes.NamedPipeClientStream> object is `"."`.</span></span> <span data-ttu-id="dd57b-121">Wenn der Client- und der Serverprozess auf verschiedenen Computern ausgeführt würden, würde `"."` durch den Netzwerknamen des Computers ersetzt, auf dem der Serverprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd57b-121">If the client and server processes were on separate computers, `"."` would be replaced with the network name of the computer that runs the server process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd57b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd57b-122">See also</span></span>

- <xref:System.Security.Principal.TokenImpersonationLevel>
- <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName%2A>
- [<span data-ttu-id="dd57b-123">Pipes</span><span class="sxs-lookup"><span data-stu-id="dd57b-123">Pipes</span></span>](../../../docs/standard/io/pipe-operations.md)
- [<span data-ttu-id="dd57b-124">Vorgehensweise: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation</span><span class="sxs-lookup"><span data-stu-id="dd57b-124">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
