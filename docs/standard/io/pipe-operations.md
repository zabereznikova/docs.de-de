---
title: Pipevorgänge in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- pipes [.NET Framework]
- pipe operations [.NET Framework]
- interprocess communication [.NET Framework], pipes
- I/O [.NET Framework], pipes
ms.assetid: 7b964ebd-7a4f-4d28-8194-7841f9e4c702
ms.openlocfilehash: 693dd1eb0b0b9bb87973eead26a344ed67641e34
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706555"
---
# <a name="pipe-operations-in-net"></a><span data-ttu-id="29f73-102">Pipevorgänge in .NET</span><span class="sxs-lookup"><span data-stu-id="29f73-102">Pipe Operations in .NET</span></span>
<span data-ttu-id="29f73-103">Pipes stellen eine Möglichkeit zur prozessübergreifenden Kommunikation dar.</span><span class="sxs-lookup"><span data-stu-id="29f73-103">Pipes provide a means for interprocess communication.</span></span> <span data-ttu-id="29f73-104">Es gibt zwei Arten von Pipes:</span><span class="sxs-lookup"><span data-stu-id="29f73-104">There are two types of pipes:</span></span>  
  
- <span data-ttu-id="29f73-105">Anonyme Pipes.</span><span class="sxs-lookup"><span data-stu-id="29f73-105">Anonymous pipes.</span></span>  
  
     <span data-ttu-id="29f73-106">Anonyme Pipes stellen prozessübergreifende Kommunikation auf einem lokalen Computer bereit.</span><span class="sxs-lookup"><span data-stu-id="29f73-106">Anonymous pipes provide interprocess communication on a local computer.</span></span> <span data-ttu-id="29f73-107">Anonyme Pipes erfordern weniger Mehraufwand als benannte Pipes, bieten jedoch nur begrenzte Dienste.</span><span class="sxs-lookup"><span data-stu-id="29f73-107">Anonymous pipes require less overhead than named pipes but offer limited services.</span></span> <span data-ttu-id="29f73-108">Anonyme Pipes sind unidirektional und können nicht über ein Netzwerk verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29f73-108">Anonymous pipes are one-way and cannot be used over a network.</span></span> <span data-ttu-id="29f73-109">Sie unterstützen nur eine einzelne Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="29f73-109">They support only a single server instance.</span></span> <span data-ttu-id="29f73-110">Anonyme Pipes eignen sich für die Kommunikation zwischen Threads oder über- und untergeordneten Prozessen, wobei die Pipehandles einfach an den untergeordneten Prozess übergeben werden können, wenn er erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="29f73-110">Anonymous pipes are useful for communication between threads, or between parent and child processes where the pipe handles can be easily passed to the child process when it is created.</span></span>  
  
     <span data-ttu-id="29f73-111">In .NET implementieren Sie anonyme Pipes mithilfe der <xref:System.IO.Pipes.AnonymousPipeServerStream>- und <xref:System.IO.Pipes.AnonymousPipeClientStream>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="29f73-111">In .NET, you implement anonymous pipes by using the <xref:System.IO.Pipes.AnonymousPipeServerStream> and <xref:System.IO.Pipes.AnonymousPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="29f73-112">Weitere Informationen finden Sie unter [How to: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="29f73-112">See [How to: Use Anonymous Pipes for Local Interprocess Communication](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md).</span></span>  
  
- <span data-ttu-id="29f73-113">Benannte Pipes.</span><span class="sxs-lookup"><span data-stu-id="29f73-113">Named pipes.</span></span>  
  
     <span data-ttu-id="29f73-114">Benannte Pipes stellen prozessübergreifende Kommunikation zwischen einem Pipeserver und einem oder mehreren Pipeclients bereit.</span><span class="sxs-lookup"><span data-stu-id="29f73-114">Named pipes provide interprocess communication between a pipe server and one or more pipe clients.</span></span> <span data-ttu-id="29f73-115">Benannte Pipes können unidirektional oder bidirektional sein.</span><span class="sxs-lookup"><span data-stu-id="29f73-115">Named pipes can be one-way or duplex.</span></span> <span data-ttu-id="29f73-116">Sie unterstützen die meldungsbasierte Kommunikation und erlauben mehreren Clients, gleichzeitig mit dem gleichen Pipenamen eine Verbindung mit dem Serverprozess herzustellen.</span><span class="sxs-lookup"><span data-stu-id="29f73-116">They support message-based communication and allow multiple clients to connect simultaneously to the server process using the same pipe name.</span></span> <span data-ttu-id="29f73-117">Benannte Pipes unterstützen zudem Identitätswechsel, sodass Verbindungen mit Prozessen hergestellt werden können, um ihre eigenen Berechtigungen auf Remoteservern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="29f73-117">Named pipes also support impersonation, which enables connecting processes to use their own permissions on remote servers.</span></span>  
  
     <span data-ttu-id="29f73-118">In .NET implementieren Sie benannte Pipes mithilfe der <xref:System.IO.Pipes.NamedPipeServerStream>- und <xref:System.IO.Pipes.NamedPipeClientStream>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="29f73-118">In .NET, you implement named pipes by using the <xref:System.IO.Pipes.NamedPipeServerStream> and <xref:System.IO.Pipes.NamedPipeClientStream> classes.</span></span>  
  
     <span data-ttu-id="29f73-119">Weitere Informationen finden Sie unter [How to: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span><span class="sxs-lookup"><span data-stu-id="29f73-119">See [How to: Use Named Pipes for Network Interprocess Communication](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f73-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29f73-120">See also</span></span>

- [<span data-ttu-id="29f73-121">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="29f73-121">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
- [<span data-ttu-id="29f73-122">Vorgehensweise: Verwenden von anonymen Pipes zur lokalen prozessübergreifenden Kommunikation</span><span class="sxs-lookup"><span data-stu-id="29f73-122">How to: Use Anonymous Pipes for Local Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-anonymous-pipes-for-local-interprocess-communication.md)
- [<span data-ttu-id="29f73-123">Vorgehensweise: Verwenden von Named Pipes zur prozessübergreifenden Kommunikation über ein Netzwerk</span><span class="sxs-lookup"><span data-stu-id="29f73-123">How to: Use Named Pipes for Network Interprocess Communication</span></span>](../../../docs/standard/io/how-to-use-named-pipes-for-network-interprocess-communication.md)
