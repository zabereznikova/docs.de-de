---
title: Sockets
description: Informationen zur .NET Framework-Klasse „Socket“, bei der es sich um eine verwaltete Codeversion von Socketdiensten handelt, die von der Winsock32-API bereitgestellt wird
ms.date: 03/30/2017
helpviewer_keywords:
- application protocols, sockets
- sending data, sockets
- data requests, sockets
- Windows Sockets
- sockets, about sockets
- Socket class, about Socket class
- sockets
- requesting data from Internet, sockets
- network, sockets
- receiving data, sockets
- protocols, sockets
- Internet, sockets
ms.assetid: 10d22735-bd37-42c1-a2be-c1932f979a7d
ms.openlocfilehash: b44409a0fafc770625be55881ccef3b57045acef
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502131"
---
# <a name="sockets"></a><span data-ttu-id="410eb-103">Sockets</span><span class="sxs-lookup"><span data-stu-id="410eb-103">Sockets</span></span>
<span data-ttu-id="410eb-104">Der <xref:System.Net.Sockets>-Namespace enthält eine verwaltete Implementierung der Windows Sockets-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="410eb-104">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="410eb-105">Alle anderen Netzwerkzugriffsklassen im <xref:System.Net>-Namespace sind auf dieser Implementierung von Sockets aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="410eb-105">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="410eb-106">Die .NET Framework-Klasse <xref:System.Net.Sockets.Socket> ist eine verwaltete Codeversion von Socket-Diensten, die von der Winsock32-API bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="410eb-106">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="410eb-107">In den meisten Fällen marshallen die **Socket**-Klassenmethoden einfach Daten in die nativen Win32-Entsprechungen und bearbeiten alle erforderlichen Überprüfungen.</span><span class="sxs-lookup"><span data-stu-id="410eb-107">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="410eb-108">Die **Socket**-Klasse unterstützt zwei grundlegende Modi: synchron und asynchron.</span><span class="sxs-lookup"><span data-stu-id="410eb-108">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="410eb-109">Im synchronen Modus werden Funktionen, die Netzwerkvorgänge ausführen (z.B. <xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.Receive%2A>), erst aufgerufen, wenn der Vorgang abgeschlossen ist, bevor die Steuerung an das aufrufende Programm zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="410eb-109">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="410eb-110">Im asynchronen Modus werden diese Aufrufe sofort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="410eb-110">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410eb-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="410eb-111">See also</span></span>

- [<span data-ttu-id="410eb-112">How to: Erstellen eines Sockets</span><span class="sxs-lookup"><span data-stu-id="410eb-112">How to: Create a Socket</span></span>](how-to-create-a-socket.md)

- [<span data-ttu-id="410eb-113">Verwenden von Anwendungsprotokollen</span><span class="sxs-lookup"><span data-stu-id="410eb-113">Using Application Protocols</span></span>](using-application-protocols.md)
