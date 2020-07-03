---
title: 'Vorgehensweise: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation'
description: Erfahren Sie, wie Sie in .NET anonyme Pipes zur lokalen prozessübergreifenden Kommunikation auf einem lokalen Computer verwenden. Anonyme Pipes verursachen weniger Verwaltungsaufwand als Named Pipes.
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
ms.openlocfilehash: 090a25aea4f280fc2ad00cf7777a501c475dfc66
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594802"
---
# <a name="how-to-use-anonymous-pipes-for-local-interprocess-communication"></a><span data-ttu-id="3d408-104">Vorgehensweise: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation</span><span class="sxs-lookup"><span data-stu-id="3d408-104">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>
<span data-ttu-id="3d408-105">Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit.</span><span class="sxs-lookup"><span data-stu-id="3d408-105">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="3d408-106">Sie bieten zwar weniger Funktionen als benannte Pipes, erfordern aber auch weniger Mehraufwand.</span><span class="sxs-lookup"><span data-stu-id="3d408-106">They offer less functionality than named pipes, but also require less overhead.</span></span> <span data-ttu-id="3d408-107">Sie können anonyme Pipes verwenden, um die prozessübergreifende Kommunikation auf einem lokalen Computer zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="3d408-107">You can use anonymous pipes to make interprocess communication on a local computer easier.</span></span> <span data-ttu-id="3d408-108">Anonyme Pipes können nicht zur Kommunikation über ein Netzwerk verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d408-108">You cannot use anonymous pipes for communication over a network.</span></span>  
  
 <span data-ttu-id="3d408-109">Um anonyme Pipes zu implementieren, verwenden Sie die <xref:System.IO.Pipes.AnonymousPipeServerStream>- und <xref:System.IO.Pipes.AnonymousPipeClientStream>-Klassen.</span><span class="sxs-lookup"><span data-stu-id="3d408-109">To implement anonymous pipes, use the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d408-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3d408-110">Example</span></span>  
 <span data-ttu-id="3d408-111">Das folgende Beispiel zeigt, wie eine Zeichenfolge mithilfe von anonymen Pipes von einem übergeordneten Prozess an einen untergeordneten Prozess gesendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3d408-111">The following example demonstrates a way to send a string from a parent process to a child process using anonymous pipes.</span></span> <span data-ttu-id="3d408-112">In diesem Beispiel wird ein <xref:System.IO.Pipes.AnonymousPipeServerStream>-Objekt in einem übergeordneten Prozess mit dem <xref:System.IO.Pipes.PipeDirection>-Wert <xref:System.IO.Pipes.PipeDirection.Out> erstellt.</span><span class="sxs-lookup"><span data-stu-id="3d408-112">This example creates an <xref:System.IO.Pipes.AnonymousPipeServerStream> object in a parent process with a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.Out>.</span></span> <span data-ttu-id="3d408-113">Anschließend wird vom übergeordneten Prozess ein untergeordneter Prozess erstellt, indem ein Clienthandle zur Erstellung eines <xref:System.IO.Pipes.AnonymousPipeClientStream>-Objekts verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3d408-113">The parent process then creates a child process by using a client handle to create an <xref:System.IO.Pipes.AnonymousPipeClientStream> object.</span></span> <span data-ttu-id="3d408-114">Der untergeordnete Prozess hat den <xref:System.IO.Pipes.PipeDirection>-Wert <xref:System.IO.Pipes.PipeDirection.In>.</span><span class="sxs-lookup"><span data-stu-id="3d408-114">The child process has a <xref:System.IO.Pipes.PipeDirection> value of <xref:System.IO.Pipes.PipeDirection.In>.</span></span>  
  
 <span data-ttu-id="3d408-115">Der übergeordnete Prozess sendet daraufhin eine vom Benutzer bereitgestellte Zeichenfolge an den untergeordneten Prozess.</span><span class="sxs-lookup"><span data-stu-id="3d408-115">The parent process then sends a user-supplied string to the child process.</span></span> <span data-ttu-id="3d408-116">Die Zeichenfolge wird im untergeordneten Prozess auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d408-116">The string is displayed to the console in the child process.</span></span>  
  
 <span data-ttu-id="3d408-117">Das folgende Codebeispiel zeigt den Serverprozess:</span><span class="sxs-lookup"><span data-stu-id="3d408-117">The following example shows the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeServerStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeServerStream_Sample/vb/program.vb#01)]  

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]
  
## <a name="example"></a><span data-ttu-id="3d408-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3d408-118">Example</span></span>  
 <span data-ttu-id="3d408-119">Das folgende Codebeispiel zeigt den Clientprozess:</span><span class="sxs-lookup"><span data-stu-id="3d408-119">The following example shows the client process.</span></span> <span data-ttu-id="3d408-120">Der Serverprozess startet den Clientprozess und übergibt ein Clienthandle an diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="3d408-120">The server process starts the client process and gives that process a client handle.</span></span> <span data-ttu-id="3d408-121">Die resultierende ausführbare Datei aus dem Clientcode sollte `pipeClient.exe` genannt und in dasselbe Verzeichnis kopiert werden wie die ausführbare Datei des Servers, bevor der Serverprozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3d408-121">The resulting executable from the client code should be named `pipeClient.exe` and be copied to the same directory as the server executable before running the server process.</span></span>  
  
 [!code-cpp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cpp/program.cpp#01)]
 [!code-csharp[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/cs/Program.cs#01)]
 [!code-vb[System.IO.Pipes.AnonymousPipeClientStream_Sample#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Pipes.AnonymousPipeClientStream_Sample/vb/program.vb#01)]  
  
## <a name="see-also"></a><span data-ttu-id="3d408-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d408-122">See also</span></span>

- [<span data-ttu-id="3d408-123">Pipes</span><span class="sxs-lookup"><span data-stu-id="3d408-123">Pipes</span></span>](pipe-operations.md)
- [<span data-ttu-id="3d408-124">How to: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk</span><span class="sxs-lookup"><span data-stu-id="3d408-124">How to: Use Named Pipes for Network Interprocess Communication</span></span>](how-to-use-named-pipes-for-network-interprocess-communication.md)
