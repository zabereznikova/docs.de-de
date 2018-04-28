---
title: Verwenden von WS-AtomicTransaction
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WS-AT protocol [WCF]
ms.assetid: 04a4c200-0af0-4c5d-a3d9-87cb7339e054
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d437b0bf3b14b60899028e293feecf5b1e36f766
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="using-ws-atomictransaction"></a><span data-ttu-id="5440a-102">Verwenden von WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="5440a-102">Using WS-AtomicTransaction</span></span>
<span data-ttu-id="5440a-103">WS-Atomic-Transaktion (WS-AT) ist ein interoperables Transaktionsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="5440a-103">WS-AtomicTransaction (WS-AT) is an interoperable transaction protocol.</span></span> <span data-ttu-id="5440a-104">Mit diesem Protokoll können Sie verteilte Transaktionen unter Verwendung von Webdienstnachrichten übergeben und interoperativ zwischen heterogenen Transaktionsinfrastrukturen koordinieren.</span><span class="sxs-lookup"><span data-stu-id="5440a-104">It enables you to flow distributed transactions by using Web service messages, and coordinate in an interoperable manner between heterogeneous transaction infrastructures.</span></span> <span data-ttu-id="5440a-105">WS-AT verwendet das Zwei-Phasen-Commitprotokoll, um eine unteilbare Ausgabe zwischen verteilten Anwendungen, Transaktions-Managern und Ressourcen-Managern zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="5440a-105">WS-AT uses the two-phase commit protocol to drive an atomic outcome between distributed applications, transaction managers, and resource managers.</span></span>  
  
 <span data-ttu-id="5440a-106">Die von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] zur Verfügung gestellte WS-AT-Implementierung umfasst einen im Transaktions-Manager von Microsoft Distributed Transaction Coordinator (MSDTC) integrierten Protokolldienst.</span><span class="sxs-lookup"><span data-stu-id="5440a-106">The WS-AT implementation [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides includes a protocol service built into the Microsoft Distributed Transaction Coordinator (MSDTC) transaction manager.</span></span> <span data-ttu-id="5440a-107">Mit WS-AT können [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen Transaktionen an andere Anwendungen übergeben, einschließlich interoperabler Webdienste, die mit der Technologie von Fremdanbietern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5440a-107">Using WS-AT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can flow transactions to other applications, including interoperable Web services built using third-party technology.</span></span>  
  
 <span data-ttu-id="5440a-108">Beim Übergeben einer Transaktion zwischen einer Clientanwendung und einer Serveranwendung wird das verwendete Transaktionsprotokoll anhand der Bindung bestimmt, die der Server an dem vom Client ausgewählten Endpunkt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="5440a-108">When flowing a transaction between a client application and a server application, the transaction protocol used is determined by the binding that the server exposes on the endpoint the client selected.</span></span> <span data-ttu-id="5440a-109">Einige vom System zur Verfügung gestellte [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Bindungen geben standardmäßig das `OleTransactions`-Protokoll als Transaktionsweitergabeformat an, während andere standardmäßig WS-AT angeben.</span><span class="sxs-lookup"><span data-stu-id="5440a-109">Some [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] system-provided bindings default to specifying the `OleTransactions` protocol as the transaction propagation format, while others default to specifying WS-AT.</span></span> <span data-ttu-id="5440a-110">Sie können die Auswahl des Transaktionsprotokolls in einer vorhandenen Bindung auch programmgesteuert ändern.</span><span class="sxs-lookup"><span data-stu-id="5440a-110">You can also programmatically modify the choice of transaction protocol inside a given binding.</span></span>  
  
 <span data-ttu-id="5440a-111">Die Protokollauswahl beeinflusst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5440a-111">The choice of protocol influences:</span></span>  
  
-   <span data-ttu-id="5440a-112">Das Format der Nachrichtenheader, das zur Weitergabe der Transaktion vom Client an den Server verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5440a-112">The format of the message headers used to flow the transaction from client to server.</span></span>  
  
-   <span data-ttu-id="5440a-113">Das Netzwerkprotokoll, mit dem das Zwei-Phasen-Commitprotokoll zwischen dem Transaktions-Manager des Clients und der Transaktion des Servers ausgeführt wird, um das Ergebnis der Transaktion aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="5440a-113">The network protocol used to run the two-phase commit protocol between the client's transaction manager and the server's transaction, in order to resolve the outcome of the transaction.</span></span>  
  
 <span data-ttu-id="5440a-114">Wenn Server und Client mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geschrieben werden, müssen Sie kein WS-AT verwenden.</span><span class="sxs-lookup"><span data-stu-id="5440a-114">If the server and client are written using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], you do not need to use WS-AT.</span></span> <span data-ttu-id="5440a-115">Sie können stattdessen die Standardeinstellungen von `NetTcpBinding` mit aktiviertem `TransactionFlow`-Attribut verwenden. Dieses nutzt dann stattdessen das `OleTransactions`-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="5440a-115">Instead, you can use the default settings of `NetTcpBinding` with the `TransactionFlow` attribute enabled, which will use the `OleTransactions` protocol instead.</span></span> <span data-ttu-id="5440a-116">Weitere Informationen finden Sie unter [ \<NetTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="5440a-116">For more information, see [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md).</span></span> <span data-ttu-id="5440a-117">Andernfalls müssen Sie bei der Weitergabe von Transaktionen an Webdienste, die mit der Technologie von Fremdanbietern erstellt wurden, WS-AT verwenden.</span><span class="sxs-lookup"><span data-stu-id="5440a-117">Otherwise, if you are flowing transactions to Web services built on third-party technologies, you must use WS-AT.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5440a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5440a-118">See Also</span></span>  
 [<span data-ttu-id="5440a-119">Konfigurieren der Unterstützung von WS-Atomic-Transaction</span><span class="sxs-lookup"><span data-stu-id="5440a-119">Configuring WS-Atomic Transaction Support</span></span>](../../../../docs/framework/wcf/feature-details/configuring-ws-atomic-transaction-support.md)
