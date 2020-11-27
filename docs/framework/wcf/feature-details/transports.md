---
title: Transporte in Windows Communication Foundation
ms.date: 03/30/2017
helpviewer_keywords:
- transports [WCF]
- WCF, transports
- Windows Communication Foundation, transports
ms.assetid: 005c894b-af70-48aa-a1c1-c99338083c27
ms.openlocfilehash: 8623b788b848867f25836a657b07349dd50c2780
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96251684"
---
# <a name="transports-in-windows-communication-foundation"></a><span data-ttu-id="543a6-102">Transporte in Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="543a6-102">Transports in Windows Communication Foundation</span></span>

<span data-ttu-id="543a6-103">Die Transportschicht befindet sich auf der niedrigsten Ebene des Kanalstapels.</span><span class="sxs-lookup"><span data-stu-id="543a6-103">The transport layer is at the lowest level of the channel stack.</span></span> <span data-ttu-id="543a6-104">Die in Windows Communication Foundation (WCF) verwendeten Haupt Transporte sind http, HTTPS, TCP und Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="543a6-104">The main transports used in Windows Communication Foundation (WCF) are HTTP, HTTPS, TCP, and named pipes.</span></span> <span data-ttu-id="543a6-105">Die Themen in diesem Abschnitt behandeln die Auswahl dieser Transporte, das Konfigurieren des Transports und das Festlegen von Optimierungseigenschaften.</span><span class="sxs-lookup"><span data-stu-id="543a6-105">The topics in this section discuss choosing among these transports, configuring the transport, and setting tuning properties.</span></span>  
  
 <span data-ttu-id="543a6-106">WCF umfasst weitere Transporte.</span><span class="sxs-lookup"><span data-stu-id="543a6-106">WCF includes additional transports.</span></span> <span data-ttu-id="543a6-107">Weitere Informationen zu Message Queuing (auch als MSMQ bezeichnet)-Transport finden Sie unter [Warteschlangen und zuverlässige Sitzungen](queues-and-reliable-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="543a6-107">For information about Message Queuing (also known as MSMQ) transport, see [Queues and Reliable Sessions](queues-and-reliable-sessions.md).</span></span> <span data-ttu-id="543a6-108">Weitere Informationen zum Peer-to-Peer-Transport finden Sie unter [Peer-to-Peer-Netzwerke](peer-to-peer-networking.md).</span><span class="sxs-lookup"><span data-stu-id="543a6-108">For information about peer-to-peer transport, see [Peer-to-Peer Networking](peer-to-peer-networking.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="543a6-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="543a6-109">In This Section</span></span>  

 [<span data-ttu-id="543a6-110">Wählen eines Transports</span><span class="sxs-lookup"><span data-stu-id="543a6-110">Choosing a Transport</span></span>](choosing-a-transport.md)  
 <span data-ttu-id="543a6-111">Beschreibt die drei Haupttransporte und die Überlegungen für die Auswahl.</span><span class="sxs-lookup"><span data-stu-id="543a6-111">Describes the three main transports and considerations in selecting one.</span></span>  
  
 [<span data-ttu-id="543a6-112">Auswählen eines Nachrichtenencoders</span><span class="sxs-lookup"><span data-stu-id="543a6-112">Choosing a Message Encoder</span></span>](choosing-a-message-encoder.md)  
 <span data-ttu-id="543a6-113">Beschreibt Faktoren, die bei der Auswahl eines Nachrichtencodierung-Bindungselements zu berücksichtigen sind.</span><span class="sxs-lookup"><span data-stu-id="543a6-113">Describes factors to consider when choosing a message-encoding binding element.</span></span>  
  
 [<span data-ttu-id="543a6-114">Nachrichtenübertragung per Stream</span><span class="sxs-lookup"><span data-stu-id="543a6-114">Streaming Message Transfer</span></span>](streaming-message-transfer.md)  
 <span data-ttu-id="543a6-115">Beschreibt, wie die Transportschicht konfiguriert wird, um Streaming zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="543a6-115">Describes how to configure the transport layer to do streaming.</span></span>  
  
 [<span data-ttu-id="543a6-116">Konfigurieren von HTTP und HTTPS</span><span class="sxs-lookup"><span data-stu-id="543a6-116">Configuring HTTP and HTTPS</span></span>](configuring-http-and-https.md)  
 <span data-ttu-id="543a6-117">Beschreibt, wie HTTP- und HTTPS-Transportbindungselemente konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="543a6-117">Describes how to configure the HTTP and HTTPS transport binding elements.</span></span>  
  
 [<span data-ttu-id="543a6-118">Vorgehensweise: Ersetzen der WCF URL-Reservierung durch eine eingeschränkte Reservierung</span><span class="sxs-lookup"><span data-stu-id="543a6-118">How to: Replace the WCF URL Reservation with a Restricted Reservation</span></span>](how-to-replace-the-wcf-url-reservation-with-a-restricted-reservation.md)  
 <span data-ttu-id="543a6-119">Hier wird beschrieben, wie eingeschränkte wcfurl-Reservierungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="543a6-119">Describes how to use WCFURL restricted reservations.</span></span>  
  
 [<span data-ttu-id="543a6-120">Transportkontingente</span><span class="sxs-lookup"><span data-stu-id="543a6-120">Transport Quotas</span></span>](transport-quotas.md)  
 <span data-ttu-id="543a6-121">Beschreibt Überlegungen für das Festlegen von Kontingenten, die in der Transportschicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="543a6-121">Describes considerations in setting the quotas available in the transport layer.</span></span>  
  
 [<span data-ttu-id="543a6-122">Arbeiten mit NATs und Firewalls</span><span class="sxs-lookup"><span data-stu-id="543a6-122">Working with NATs and Firewalls</span></span>](working-with-nats-and-firewalls.md)  
 <span data-ttu-id="543a6-123">Beschreibt, wie die Transportschicht konfiguriert wird, wenn Nachrichten hinter einer Firewall gesendet oder empfangen werden oder wenn NAT (Network Address Translation) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="543a6-123">Describes how to configure the transport layer when messages are sent or received behind a firewall or when network address translation (NAT) is present.</span></span>  
  
 [<span data-ttu-id="543a6-124">Net.TCP-Anschlussfreigabe</span><span class="sxs-lookup"><span data-stu-id="543a6-124">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)  
 <span data-ttu-id="543a6-125">Beschreibt, wie die net. TCP-Port Freigabe Komponente von WCF verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="543a6-125">Describes how to use the Net.TCP Port Sharing component of WCF.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="543a6-126">Referenz</span><span class="sxs-lookup"><span data-stu-id="543a6-126">Reference</span></span>  

 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
## <a name="related-sections"></a><span data-ttu-id="543a6-127">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="543a6-127">Related Sections</span></span>  

 [<span data-ttu-id="543a6-128">Bindungen</span><span class="sxs-lookup"><span data-stu-id="543a6-128">Bindings</span></span>](bindings.md)  
  
 [<span data-ttu-id="543a6-129">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="543a6-129">Extending Bindings</span></span>](../extending/extending-bindings.md)
