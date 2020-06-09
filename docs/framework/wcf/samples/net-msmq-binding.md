---
title: Net MSMQ-Bindung
ms.date: 03/30/2017
ms.assetid: fe4bb696-f57c-4cb3-9b7e-9d95fe6b8323
ms.openlocfilehash: 622341ef00f5d8950fa0c013e427f20e02187893
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602426"
---
# <a name="net-msmq-binding"></a><span data-ttu-id="e9423-102">Net MSMQ-Bindung</span><span class="sxs-lookup"><span data-stu-id="e9423-102">Net MSMQ Binding</span></span>
<span data-ttu-id="e9423-103">Dieser Abschnitt enthält Beispiele, in denen die Verwendung von MSMQ-Bindungsattributen eines Endpunktelements veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="e9423-103">This section contains samples that demonstrate using MSMQ binding attributes of an endpoint element.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9423-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e9423-104">In This Section</span></span>  
 [<span data-ttu-id="e9423-105">Abgewickelte MSMQ-Bindung</span><span class="sxs-lookup"><span data-stu-id="e9423-105">Transacted MSMQ Binding</span></span>](transacted-msmq-binding.md)  
 <span data-ttu-id="e9423-106">In diesem Beispiel wird veranschaulicht, wie eine abgewickelte Warteschlangenkommunikation mithilfe von Message Queuing (MSMQ) durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e9423-106">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ).</span></span>  
  
 [<span data-ttu-id="e9423-107">Flüchtige Kommunikation unter Verwendung von Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="e9423-107">Volatile Queued Communication</span></span>](volatile-queued-communication.md)  
 <span data-ttu-id="e9423-108">Veranschaulicht, wie eine flüchtige Kommunikation unter Verwendung von Warteschlangen über Message Queuing (MSMQ)-Transport durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e9423-108">Demonstrates how to perform volatile queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="e9423-109">Warteschlangen für unzustellbare Meldungen</span><span class="sxs-lookup"><span data-stu-id="e9423-109">Dead Letter Queues</span></span>](dead-letter-queues.md)  
 <span data-ttu-id="e9423-110">Veranschaulicht das Behandeln und Verarbeiten von Nachrichten mit Fehlern bei der Zustellung.</span><span class="sxs-lookup"><span data-stu-id="e9423-110">Demonstrates how to handle and process messages that have failed delivery.</span></span>  
  
 [<span data-ttu-id="e9423-111">Behandlung nicht verarbeitbarer Nachrichten in MSMQ 4,0</span><span class="sxs-lookup"><span data-stu-id="e9423-111">Poison Message Handling in MSMQ 4.0</span></span>](poison-message-handling-in-msmq-4-0.md)  
 <span data-ttu-id="e9423-112">Veranschaulicht die Behandlung nicht verarbeitbarer Nachrichten in einem Dienst mithilfe von MSMQ 4.0.</span><span class="sxs-lookup"><span data-stu-id="e9423-112">Demonstrates how to perform poison message handling in a service using MSMQ 4.0.</span></span>  
  
 [<span data-ttu-id="e9423-113">Sitzungen und Warteschlangen</span><span class="sxs-lookup"><span data-stu-id="e9423-113">Sessions and Queues</span></span>](sessions-and-queues.md)  
 <span data-ttu-id="e9423-114">Dieses Beispiel veranschaulicht, wie ein Satz zusammengehöriger Nachrichten bei der Kommunikation unter Verwendung von Warteschlangen über den MSMQ-Transport (Message Queuing) gesendet und empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="e9423-114">Demonstrates how to send and receive a set of related messages in queued communication over the Message Queuing (MSMQ) transport.</span></span>  
  
 [<span data-ttu-id="e9423-115">Bidirektionale Kommunikation</span><span class="sxs-lookup"><span data-stu-id="e9423-115">Two-Way Communication</span></span>](two-way-communication.md)  
 <span data-ttu-id="e9423-116">Veranschaulicht das Ausführen der transaktiven bidirektionalen Warteschlangenkommunikation über MSMQ.</span><span class="sxs-lookup"><span data-stu-id="e9423-116">Demonstrates how to perform transacted two-way queued communication over MSMQ.</span></span>
  
 [<span data-ttu-id="e9423-117">SRMP</span><span class="sxs-lookup"><span data-stu-id="e9423-117">SRMP</span></span>](srmp.md)  
 <span data-ttu-id="e9423-118">In diesem Beispiel wird veranschaulicht, wie eine abgewickelte Warteschlangenkommunikation mithilfe von Message Queuing (MSMQ) über HTTP durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e9423-118">Demonstrates how to perform transacted queued communication by using Message Queuing (MSMQ) over HTTP.</span></span>  
  
 [<span data-ttu-id="e9423-119">Nachrichtensicherheit über Message Queuing</span><span class="sxs-lookup"><span data-stu-id="e9423-119">Message Security over Message Queuing</span></span>](message-security-over-message-queuing.md)  
 <span data-ttu-id="e9423-120">Veranschaulicht das Implementieren einer Anwendung, in der WS-Sicherheit mit X.509v3-Zertifikatauthentifizierung für den Client verwendet wird und die die Serverauthentifizierung mit dem X.509v3-Zertifikat des Servers über MSMQ erfordert.</span><span class="sxs-lookup"><span data-stu-id="e9423-120">Demonstrates how to implement an application that uses WS-Security with X.509v3 certificate authentication for the client and requires server authentication using the server's X.509v3 certificate over MSMQ.</span></span>
