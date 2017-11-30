---
title: Pipeoperationen in .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 879e5a73417f9347224bc22b397814b83972751c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pipe-operations-in-the-net-framework"></a><span data-ttu-id="f0f63-102">Pipeoperationen in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f0f63-102">Pipe Operations in the .NET Framework</span></span>
<span data-ttu-id="f0f63-103">Pipes stellen eine Möglichkeit für die prozessübergreifende Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="f0f63-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="f0f63-104">Es gibt zwei Arten von Pipes:</span><span class="sxs-lookup"><span data-stu-id="f0f63-104">There are two types of pipes:</span></span>  
  
-   <span data-ttu-id="f0f63-105">Anonyme Pipes.</span><span class="sxs-lookup"><span data-stu-id="f0f63-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="f0f63-106">Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit.</span><span class="sxs-lookup"><span data-stu-id="f0f63-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="f0f63-107">Anonyme Pipes erfordern weniger Mehraufwand als benannte Pipes, jedoch begrenzte Diensten bieten.</span><span class="sxs-lookup"><span data-stu-id="f0f63-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="f0f63-108">Anonyme Pipes sind unidirektionale und können nicht über ein Netzwerk verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0f63-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="f0f63-109">Außerdem unterstützen Sie nur eine einzelne Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="f0f63-109">They support only a single server instance.</span></span> <span data-ttu-id="f0f63-110">Anonyme Pipes eignen sich für die Kommunikation zwischen Threads oder zwischen über- und untergeordnete Prozesse, in denen die Pipehandles einfach an den untergeordneten Prozess übergeben werden können während der Erstellung.</span><span class="sxs-lookup"><span data-stu-id="f0f63-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="f0f63-111">In .NET Framework, implementieren Sie anonyme Pipes mithilfe der <xref:System.IO.Pipes.AnonymousPipeServerStream> und <xref:System.IO.Pipes.AnonymousPipeClientStream> Klassen.</span><span class="sxs-lookup"><span data-stu-id="f0f63-111">In the .NET Framework, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="f0f63-112">Finden Sie unter [wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="f0f63-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
-   <span data-ttu-id="f0f63-113">Benannte Pipes.</span><span class="sxs-lookup"><span data-stu-id="f0f63-113">Named pipes.</span></span>  
  
     <span data-ttu-id="f0f63-114">Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit.</span><span class="sxs-lookup"><span data-stu-id="f0f63-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="f0f63-115">Benannte Pipes können unidirektional oder bidirektional sein.</span><span class="sxs-lookup"><span data-stu-id="f0f63-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="f0f63-116">Sie unterstützen die meldungsbasierte Kommunikation und Zulassen von mehreren Clients gleichzeitig an den Serverprozess mit dem gleichen Pipenamen zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="f0f63-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="f0f63-117">Benannte Pipes unterstützen zudem Identitätswechsel, durch den verbindende Prozessen die Verwendung ihrer eigenen Berechtigungen auf Remoteservern verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="f0f63-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="f0f63-118">In .NET Framework, implementieren Sie named Pipes mithilfe der <xref:System.IO.Pipes.NamedPipeServerStream> und <xref:System.IO.Pipes.NamedPipeClientStream> Klassen.</span><span class="sxs-lookup"><span data-stu-id="f0f63-118">In the .NET Framework, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="f0f63-119">Finden Sie unter [wie: Verwenden von benannten Pipes zur prozessübergreifenden Netzwerkkommunikation](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="f0f63-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f63-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0f63-120">See Also</span></span>  
 [<span data-ttu-id="f0f63-121">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="f0f63-121">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="f0f63-122">Gewusst wie: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation</span><span class="sxs-lookup"><span data-stu-id="f0f63-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)  
 [<span data-ttu-id="f0f63-123">Gewusst wie: Verwenden von Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk</span><span class="sxs-lookup"><span data-stu-id="f0f63-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
