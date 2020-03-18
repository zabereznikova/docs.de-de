---
title: Sockets
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
ms.openlocfilehash: cffad6b4677a880bd63f5ae0232c639f7a262c59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "71047256"
---
# <a name="sockets"></a><span data-ttu-id="3f746-102">Sockets</span><span class="sxs-lookup"><span data-stu-id="3f746-102">Sockets</span></span>
<span data-ttu-id="3f746-103">Der <xref:System.Net.Sockets>-Namespace enthält eine verwaltete Implementierung der Windows Sockets-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="3f746-103">The <xref:System.Net.Sockets> namespace contains a managed implementation of the Windows Sockets interface.</span></span> <span data-ttu-id="3f746-104">Alle anderen Netzwerkzugriffsklassen im <xref:System.Net>-Namespace sind auf dieser Implementierung von Sockets aufgebaut.</span><span class="sxs-lookup"><span data-stu-id="3f746-104">All other network-access classes in the <xref:System.Net> namespace are built on top of this implementation of sockets.</span></span>  
  
 <span data-ttu-id="3f746-105">Die .NET Framework-Klasse <xref:System.Net.Sockets.Socket> ist eine verwaltete Codeversion von Socket-Diensten, die von der Winsock32-API bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="3f746-105">The .NET Framework <xref:System.Net.Sockets.Socket> class is a managed-code version of the socket services provided by the Winsock32 API.</span></span> <span data-ttu-id="3f746-106">In den meisten Fällen marshallen die **Socket**-Klassenmethoden einfach Daten in die nativen Win32-Entsprechungen und bearbeiten alle erforderlichen Überprüfungen.</span><span class="sxs-lookup"><span data-stu-id="3f746-106">In most cases, the **Socket** class methods simply marshal data into their native Win32 counterparts and handle any necessary security checks.</span></span>  
  
 <span data-ttu-id="3f746-107">Die **Socket**-Klasse unterstützt zwei grundlegende Modi: synchron und asynchron.</span><span class="sxs-lookup"><span data-stu-id="3f746-107">The **Socket** class supports two basic modes, synchronous and asynchronous.</span></span> <span data-ttu-id="3f746-108">Im synchronen Modus werden Funktionen, die Netzwerkvorgänge ausführen (z.B. <xref:System.Net.Sockets.Socket.Send%2A> und <xref:System.Net.Sockets.Socket.Receive%2A>), erst aufgerufen, wenn der Vorgang abgeschlossen ist, bevor die Steuerung an das aufrufende Programm zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3f746-108">In synchronous mode, calls to functions that perform network operations (such as <xref:System.Net.Sockets.Socket.Send%2A> and <xref:System.Net.Sockets.Socket.Receive%2A>) wait until the operation completes before returning control to the calling program.</span></span> <span data-ttu-id="3f746-109">Im asynchronen Modus werden diese Aufrufe sofort zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3f746-109">In asynchronous mode, these calls return immediately.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f746-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3f746-110">See also</span></span>

- [<span data-ttu-id="3f746-111">Vorgehensweise: Erstellen eines Sockets</span><span class="sxs-lookup"><span data-stu-id="3f746-111">How to: Create a Socket</span></span>](how-to-create-a-socket.md)

- [<span data-ttu-id="3f746-112">Using Application Protocols (Verwenden von Anwendungsprotokollen)</span><span class="sxs-lookup"><span data-stu-id="3f746-112">Using Application Protocols</span></span>](using-application-protocols.md)
