---
title: "Zuverlässiges Messaging-Protokoll, Version 1,1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 67df8b539109d7e4dafcbc42ad7679643767021a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="9de30-102">Zuverlässiges Messaging-Protokoll, Version 1,1</span><span class="sxs-lookup"><span data-stu-id="9de30-102">Reliable Messaging Protocol version 1.1</span></span>
<span data-ttu-id="9de30-103">In diesem Thema werden [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Implementierungsdetails für das WS-ReliableMessaging-Protokoll in der Version 1.1 vom Februar 2007 beschrieben, die für die Interoperation mithilfe des HTTP-Transports erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9de30-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-104"> orientiert sich an der WS-ReliableMessaging-Spezifikation mit den in diesem Thema erläuterten Einschränkungen und Klarstellungen.</span><span class="sxs-lookup"><span data-stu-id="9de30-104"> follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="9de30-105">Beachten Sie, dass das zuverlässige WS-Messaging-Protokoll in der Version&#160;1.1 ab [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="9de30-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>  
  
 <span data-ttu-id="9de30-106">Das zuverlässige WS-Messaging-Protokoll vom Februar&#160;2007 ist in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durch das <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> implementiert.</span><span class="sxs-lookup"><span data-stu-id="9de30-106">The WS-ReliableMessaging February 2007 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="9de30-107">Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="9de30-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="9de30-108">Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert</span><span class="sxs-lookup"><span data-stu-id="9de30-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>  
  
-   <span data-ttu-id="9de30-109">Beantworter: der Dienst, der die Anforderungen des Initiators empfängt</span><span class="sxs-lookup"><span data-stu-id="9de30-109">Responder: The service that receives the initiator's requests.</span></span>  
  
 <span data-ttu-id="9de30-110">In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.</span><span class="sxs-lookup"><span data-stu-id="9de30-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="9de30-111">Präfix</span><span class="sxs-lookup"><span data-stu-id="9de30-111">Prefix</span></span>|<span data-ttu-id="9de30-112">Namespace</span><span class="sxs-lookup"><span data-stu-id="9de30-112">Namespace</span></span>|  
|-|-|  
|<span data-ttu-id="9de30-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="9de30-113">wsrm</span></span>|<span data-ttu-id="9de30-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span><span class="sxs-lookup"><span data-stu-id="9de30-114">http://docs.oasis-open.org/ws-rx/wsrm/200702</span></span>|  
|<span data-ttu-id="9de30-115">netrm</span><span class="sxs-lookup"><span data-stu-id="9de30-115">netrm</span></span>|<span data-ttu-id="9de30-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="9de30-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="9de30-117">s</span><span class="sxs-lookup"><span data-stu-id="9de30-117">s</span></span>|<span data-ttu-id="9de30-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="9de30-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="9de30-119">wsa</span><span class="sxs-lookup"><span data-stu-id="9de30-119">wsa</span></span>|<span data-ttu-id="9de30-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="9de30-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="9de30-121">wsse</span><span class="sxs-lookup"><span data-stu-id="9de30-121">wsse</span></span>|<span data-ttu-id="9de30-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="9de30-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="9de30-123">wsrmp</span><span class="sxs-lookup"><span data-stu-id="9de30-123">wsrmp</span></span>|<span data-ttu-id="9de30-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="9de30-124">http://docs.oasis-open.org/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="9de30-125">netrmp</span><span class="sxs-lookup"><span data-stu-id="9de30-125">netrmp</span></span>|<span data-ttu-id="9de30-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span><span class="sxs-lookup"><span data-stu-id="9de30-126">http://schemas.microsoft.com/ws-rx/wsrmp/200702</span></span>|  
|<span data-ttu-id="9de30-127">wsp</span><span class="sxs-lookup"><span data-stu-id="9de30-127">wsp</span></span>|<span data-ttu-id="9de30-128">(Entweder WS-Policy&#160;1.2 oder WS-Policy&#160;1.5)</span><span class="sxs-lookup"><span data-stu-id="9de30-128">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="9de30-129">Messaging</span><span class="sxs-lookup"><span data-stu-id="9de30-129">Messaging</span></span>  
  
### <a name="sequence-creation"></a><span data-ttu-id="9de30-130">Sequenzerstellung</span><span class="sxs-lookup"><span data-stu-id="9de30-130">Sequence Creation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-131"> implementiert `CreateSequence`- und `CreateSequenceResponse`-Nachrichten, um eine zuverlässige Messaging-Sequenz einzurichten.</span><span class="sxs-lookup"><span data-stu-id="9de30-131"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="9de30-132">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="9de30-132">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="9de30-133">B1101: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator verwendet den gleichen Endpunktverweis wie `CreateSequence`, `ReplyTo` und `AcksTo` der `Offer/Endpoint`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9de30-133">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>  
  
-   <span data-ttu-id="9de30-134">R1102: Die `AcksTo`-, `ReplyTo`- und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen über Adresswerte mit identischen Zeichenfolgendarstellungen verfügen, die sich oktettweise entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9de30-134">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>  
  
    -   <span data-ttu-id="9de30-135">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überprüft, ob der URI-Teil der `AcksTo`-, `ReplyTo`- und `Endpoint`-Endpunktreferenzen identisch ist, bevor die Sequenz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="9de30-135">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="9de30-136">R1103: Die `AcksTo`- und `ReplyTo` und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen den gleichen Satz an Verweisparametern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="9de30-136">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-137"> geht davon aus, dass die Verweisparameter der `AcksTo`-, `ReplyTo`- und `Offer/Endpoint`-Endpunktverweise für `CreateSequence` identisch sind, erzwingt dies jedoch nicht, und verwendet Verweisparameter vom `ReplyTo`-Endpunktverweis für Bestätigungen und Nachrichten umgekehrter Sequenz.</span><span class="sxs-lookup"><span data-stu-id="9de30-137"> does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="9de30-138">B1104: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert das optionale `Expires`-Element oder `Offer/Expires`-Element in der `CreateSequence`-Nachricht nicht.</span><span class="sxs-lookup"><span data-stu-id="9de30-138">B1104: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="9de30-139">B1105: Beim Zugriff auf die `CreateSequence`-Nachricht verwendet der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter den `Expires`-Wert im `CreateSequence`-Element als `Expires`-Wert im `CreateSequenceResponse`-Element.</span><span class="sxs-lookup"><span data-stu-id="9de30-139">B1105: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="9de30-140">Andernfalls liest und ignoriert der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter die Werte für `Expires` und `Offer/Expires`.</span><span class="sxs-lookup"><span data-stu-id="9de30-140">Otherwise, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>  
  
-   <span data-ttu-id="9de30-141">B1106: Bei Zugreifen auf die `CreateSequenceResponse`-Nachricht liest der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator den optionalen `Expires`-Wert, verwendet ihn aber nicht.</span><span class="sxs-lookup"><span data-stu-id="9de30-141">B1106: When accessing the `CreateSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator reads the optional `Expires` value but does not use it.</span></span>  
  
-   <span data-ttu-id="9de30-142">B1107: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator und -Beantworter generieren immer das optionale `IncompleteSequenceBehavior`-Element im `CreateSequence/Offer`-Element und `CreateSequenceResponse`-Element.</span><span class="sxs-lookup"><span data-stu-id="9de30-142">B1107: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>  
  
-   <span data-ttu-id="9de30-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet nur den `DiscardFollowingFirstGap`-Wert und den `NoDiscard`-Wert im `IncompleteSequenceBehavior`-Element.</span><span class="sxs-lookup"><span data-stu-id="9de30-143">B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>  
  
    -   <span data-ttu-id="9de30-144">Zuverlässiges WS-Messaging verwendet den `Offer`-Mechanismus, um die beiden umgekehrt korrelierten Sequenzen einzurichten, die eine Sitzung bilden.</span><span class="sxs-lookup"><span data-stu-id="9de30-144">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="9de30-145">B1109: Wenn `CreateSequence` ein `Offer`-Element enthält, weist der unidirektionale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter die angebotene Sequenz ab, indem er mit einer `CreateSequenceResponse`-Nachricht ohne `Accept`-Element antwortet.</span><span class="sxs-lookup"><span data-stu-id="9de30-145">B1109: If `CreateSequence` contains an `Offer` element, the one way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>  
  
-   <span data-ttu-id="9de30-146">B1110: Wenn ein zuverlässiger Messaging-Beantworter die angebotene Sequenz zurückweist, gibt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator einen Fehler für die neu erstellte Sequenz zurück.</span><span class="sxs-lookup"><span data-stu-id="9de30-146">B1110: If a Reliable Messaging Responder rejects the offered sequence, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator faults the newly established sequence.</span></span>  
  
-   <span data-ttu-id="9de30-147">B1111: Wenn `CreateSequence` kein `Offer`-Element enthält, weist der bidirektionale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter die angebotene Sequenz ab, indem er mit einem `CreateSequenceRefused`-Fehler antwortet.</span><span class="sxs-lookup"><span data-stu-id="9de30-147">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>  
  
-   <span data-ttu-id="9de30-148">R1112: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, muss die `[address]`-Eigenschaft des `CreateSequenceResponse/Accept/AcksTo`-Endpunktverweises mit dem Ziel-URI der `CreateSequence`-Nachricht Byte für Byte übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="9de30-148">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>  
  
-   <span data-ttu-id="9de30-149">R1113: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, müssen alle Nachrichten in beiden Sequenzen, die vom Initiator an den Beantworter übermittelt werden, an den gleichen Endpunktverweis gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-149">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-150"> verwendet zuverlässiges WS-Messaging, um zuverlässige Sitzungen zwischen dem Initiator und dem Beantworter einzurichten.</span><span class="sxs-lookup"><span data-stu-id="9de30-150"> uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="9de30-151">Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging-Implementierung bietet eine zuverlässige Sitzung für unidirektionale, Anforderung-Antwort- und Vollduplex-Nachrichtenmuster.</span><span class="sxs-lookup"><span data-stu-id="9de30-151">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="9de30-152">Der `Offer`-Mechanismus von zuverlässigem WS-Messaging für `CreateSequence` und `CreateSequenceResponse` ermöglicht es Ihnen, zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein für alle Nachrichtenendpunkte geeignetes Sitzungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="9de30-152">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="9de30-153">Da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Sicherheit solcher Sitzungen sowie End-to-End-Schutz der Sitzungsintegrität garantiert, kann sichergestellt werden, dass alle an den gleichen Teilnehmer gerichteten Nachrichten am selben Ziel ankommen.</span><span class="sxs-lookup"><span data-stu-id="9de30-153">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="9de30-154">Dadurch wird es zudem ermöglicht, Sequenzbestätigungen im Piggyback-Verfahren mit Anwendungsnachrichten zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="9de30-154">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="9de30-155">Daher gelten die Einschränkungen R1102 R1112 und R1113 für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9de30-155">Therefore, constraints R1102, R1112, and R1113 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="9de30-156">Ein Beispiel für eine `CreateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9de30-156">An example of a `CreateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:MessageID>  
    <wsa:ReplyTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>   
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequence>  
      <wsrm:AcksTo>  
        <wsa:Address>http://Business456.com/clientA</wsa:Address>  
      </wsrm:AcksTo>  
      <wsrm:Offer>  
        <wsrm:Identifier>urn:uuid:066b4730-fc82-458a-a5c1-210be4fb4e4e</wsrm:Identifier>  
        <wsrm:Endpoint>  
          <wsa:Address>http://Business456.com/clientA</wsa:Address>  
        </wsrm:Endpoint>  
        <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      </wsrm:Offer>  
    </wsrm:CreateSequence>  
  </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="9de30-157">Ein Beispiel für eine `CreateSequenceResponse`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9de30-157">An example of a `CreateSequenceResponse` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CreateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:949cca61-8813-42ff-ab33-18d9e3fa82fa</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CreateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:IncompleteSequenceBehavior>DiscardFollowingFirstGap</wsrm:IncompleteSequenceBehavior>  
      <wsrm:Accept>  
        <wsrm:AcksTo>  
          <wsa:Address>http://BusinessABC.com/serviceA</wsa:Address>  
        </wsrm:AcksTo>  
      </wsrm:Accept>  
    </wsrm:CreateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="closing-a-sequence"></a><span data-ttu-id="9de30-158">Schließen einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="9de30-158">Closing a Sequence</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-159"> verwendet die `CloseSequence`-Nachricht und die `CloseSequenceResponse`-Nachricht, um das von einer zuverlässigen Messaging-Quelle initiierte Schließen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="9de30-159"> uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="9de30-160">Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging-Ziel initiiert das Schließen nicht, und die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging-Quelle unterstützt keinen Schließen-Vorgang, der von einem zuverlässigen Messaging-Ziel initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="9de30-160">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate shutdown and the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="9de30-161">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="9de30-161">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="9de30-162">B1201: Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable&#160;Messaging-Quelle sendet immer eine `CloseSequence`-Nachricht, um die Sequenz zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9de30-162">B1201: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>  
  
-   <span data-ttu-id="9de30-163">B1202: Die zuverlässige Messaging-Quelle wartet auf die Bestätigung aller Sequenznachrichten, bevor sie die `CloseSequence`-Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="9de30-163">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="9de30-164">B1203: Die zuverlässige Messaging-Quelle fügt immer das optionale `LastMsgNumber`-Element ein, es sei denn, die Sequenz enthält keine Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9de30-164">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>  
  
-   <span data-ttu-id="9de30-165">R1204: Das zuverlässige Messaging-Ziel darf das Schließen nicht durch Senden einer `CloseSequence`-Nachricht initiieren.</span><span class="sxs-lookup"><span data-stu-id="9de30-165">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>  
  
-   <span data-ttu-id="9de30-166">B1205: Bei Empfang einer `CloseSequence`-Nachricht betrachtet die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable&#160;Messaging-Quelle die Sequenz als unvollständig und sendet einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="9de30-166">B1205: Upon receiving a `CloseSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>  
  
 <span data-ttu-id="9de30-167">Ein Beispiel für eine `CloseSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9de30-167">An example of a `CloseSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
    </wsrm:CloseSequence>  
  </s:Body>  
</s:Envelope>  
Example CloseSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/CloseSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:6ce1d4c3-e1c1-474f-a8c9-4210e37f7877</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">http://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:CloseSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:CloseSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequence-termination"></a><span data-ttu-id="9de30-168">Sequenzbeendigung</span><span class="sxs-lookup"><span data-stu-id="9de30-168">Sequence Termination</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-169"> verwendet hauptsächlich den `TerminateSequence/TerminateSequenceResponse`-Handshake, nachdem der `CloseSequence/CloseSequenceResponse`-Handshake abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9de30-169"> primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="9de30-170">Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable&#160;Messaging-Ziel initiiert die Beendigung nicht, und die zuverlässige Messaging-Quelle unterstützt keine Beendigung, die von einem zuverlässigen Messaging-Ziel initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="9de30-170">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="9de30-171">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="9de30-171">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="9de30-172">B1301: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator schickt die `TerminateSequence`-Nachricht erst nach dem erfolgreichen Abschluss des `CloseSequence/CloseSequenceResponse`-Handshake.</span><span class="sxs-lookup"><span data-stu-id="9de30-172">B1301: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>  
  
-   <span data-ttu-id="9de30-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] überprüft, ob das `LastMsgNumber`-Element in allen `CloseSequence`-Nachrichten und `TerminateSequence`-Nachrichten für eine bestimmte Sequenz konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="9de30-173">R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="9de30-174">Das bedeutet, dass `LastMsgNumber` entweder in keiner `CloseSequence`-Nachricht und keiner `TerminateSequence`-Nachricht vorhanden ist oder in allen `CloseSequence`-Nachrichten und `TerminateSequence`-Nachrichten vorhanden und identisch ist.</span><span class="sxs-lookup"><span data-stu-id="9de30-174">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>  
  
-   <span data-ttu-id="9de30-175">B1303: Bei Empfang einer `TerminateSequence`-Nachricht nach dem `CloseSequence/CloseSequenceResponse`-Handshake antwortet das zuverlässige Messaging-Ziel mit einer `TerminateSequenceResponse`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9de30-175">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="9de30-176">Da die zuverlässige Messaging-Quelle die `TerminateSequence`-Nachricht erst nach Erhalt der letzten Bestätigung sendet, weiß das zuverlässige Messaging-Ziel mit Sicherheit, dass die Sequenz beendet ist, und fordert die Ressourcen unverzüglich zurück.</span><span class="sxs-lookup"><span data-stu-id="9de30-176">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>  
  
-   <span data-ttu-id="9de30-177">B1304: Bei Empfang einer `TerminateSequence`-Nachricht vor dem `CloseSequence/CloseSequenceResponse`-Handshake antwortet das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable&#160;Messaging-Ziel mit einer `TerminateSequenceResponse`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9de30-177">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="9de30-178">Wenn das zuverlässige Messaging-Ziel ermittelt, dass die Sequenz keine Inkonsistenzen aufweist, wartet das zuverlässige Messaging-Ziel so lange, wie vom Anwendungsziel angegeben, bevor es die Ressourcen zurückverlangt, um es dem Client zu ermöglichen, die letzte Bestätigung zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="9de30-178">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="9de30-179">Anderenfalls fordert das zuverlässige Messaging-Ziel die Ressourcen unverzüglich zurück und teilt dem Anwendungsziel mit, dass die Sequenz nicht ordnungsgemäß beendet wurde, indem es das `Faulted`-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="9de30-179">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>  
  
 <span data-ttu-id="9de30-180">Ein Beispiel für eine `TerminateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9de30-180">An example of a `TerminateSequence` message.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequence</wsa:Action>  
    <wsa:MessageID>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:MessageID>  
    <wsa:ReplyTo>  
      <wsa:Address>http://Business456.com/clientA</wsa:Address>  
    </wsa:ReplyTo>  
    <wsa:To s:mustUnderstand="1">http://BusinessABC.com/serviceA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequence>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:LastMsgNumber>30</wsrm:LastMsgNumber>  
      </wsrm:TerminateSequence>  
  </s:Body>  
</s:Envelope>  
Example TerminateSequenceResponse message:  
<s:Envelope>  
  <s:Header>  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Lower="1" Upper="30"></wsrm:AcknowledgementRange>  
      <wsrm:Final></wsrm:Final>  
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    <wsa:Action s:mustUnderstand="1">http://docs.oasis-open.org/ws-rx/wsrm/200702/TerminateSequenceResponse</wsa:Action>  
    <wsa:RelatesTo>urn:uuid:3597a398-4f3c-40f4-9335-8f1515572fdf</wsa:RelatesTo>  
    <wsa:To s:mustUnderstand="1">://Business456.com/clientA</wsa:To>  
  </s:Header>  
  <s:Body>  
    <wsrm:TerminateSequenceResponse>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
    </wsrm:TerminateSequenceResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="sequences"></a><span data-ttu-id="9de30-181">Sequenzen</span><span class="sxs-lookup"><span data-stu-id="9de30-181">Sequences</span></span>  
 <span data-ttu-id="9de30-182">Die folgende Liste enthält die Einschränkungen, die für Sequenzen gelten:</span><span class="sxs-lookup"><span data-stu-id="9de30-182">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="9de30-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und greift auf die Sequenznummern, die nicht höher als `xs:long`des inklusive Maximalwert 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="9de30-183">B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
 <span data-ttu-id="9de30-184">Ein Beispiel für einen `Sequence`-Header.</span><span class="sxs-lookup"><span data-stu-id="9de30-184">An example of a `Sequence` header.</span></span>  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a><span data-ttu-id="9de30-185">Anfordern einer Bestätigung</span><span class="sxs-lookup"><span data-stu-id="9de30-185">Request Acknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-186"> verwendet den `AckRequested`-Header als Keep-alive-Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="9de30-186"> uses the `AckRequested` header as a keep-alive mechanism.</span></span>  
  
 <span data-ttu-id="9de30-187">Ein Beispiel für einen `AckRequested`-Header.</span><span class="sxs-lookup"><span data-stu-id="9de30-187">An example of an `AckRequested` header.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a><span data-ttu-id="9de30-188">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="9de30-188">SequenceAcknowledgement</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-189"> verwendet den Piggyback-Mechanismus für die im zuverlässigen WS-Messaging bereitgestellten Sequenzbestätigungen.</span><span class="sxs-lookup"><span data-stu-id="9de30-189"> uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="9de30-190">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="9de30-190">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="9de30-191">R1601: Wenn zwei umgekehrte Sequenzen eingerichtet sind mit den `Offer` Mechanismus, der `SequenceAcknowledgement` Header kann in jeder an den beabsichtigten Empfänger Anwendungsnachricht aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-191">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="9de30-192">Der Remoteendpunkt muss in der Lage sein, auf einen per Piggyback-Verfahren gesendeten `SequenceAcknowledgement`-Header zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9de30-192">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="9de30-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert keine `SequenceAcknowledgement`-Header, die `Nack`-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="9de30-193">B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-194"> überprüft, ob jedes `Nack`-Element eine Sequenznummer enthält. Wenn dies nicht der Fall ist, werden das `Nack`-Element und sein Wert ignoriert.</span><span class="sxs-lookup"><span data-stu-id="9de30-194"> validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>  
  
 <span data-ttu-id="9de30-195">Ein Beispiel für einen `SequenceAcknowledgement`-Header.</span><span class="sxs-lookup"><span data-stu-id="9de30-195">An example of a `SequenceAcknowledgement` header.</span></span>  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="9de30-196">WS-ReliableMessaging-Fehler</span><span class="sxs-lookup"><span data-stu-id="9de30-196">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="9de30-197">Die folgende Liste enthält die Einschränkungen, die für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierung der WS-ReliableMessaging-Fehler gelten.</span><span class="sxs-lookup"><span data-stu-id="9de30-197">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="9de30-198">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="9de30-198">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="9de30-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert keine `MessageNumberRollover` Fehler.</span><span class="sxs-lookup"><span data-stu-id="9de30-199">B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="9de30-200">B1702: Wenn der Dienstendpunkt über SOAP&#160;1.2 seine Verbindungsgrenze erreicht und keine weiteren Verbindungen verarbeiten kann, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] den geschachtelten `CreateSequenceRefused`-Fehlersubcode `netrm:ConnectionLimitReached` (siehe folgendes Beispiel).</span><span class="sxs-lookup"><span data-stu-id="9de30-200">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <wsa:Action>http://docs.oasis-open.org/ws-rx/wsrm/200702/fault</wsa:Action>  
  </s:Header>  
  <s:Body>  
    <s:Fault>  
      <s:Code>  
        <s:Value>s:Receiver</s:Value>  
        <s:Subcode>  
          <s:Value>wsrm:CreateSequenceRefused</s:Value>  
          <s:Subcode>  
            <s:Value>netrm:ConnectionLimitReached</s:Value>  
          </s:Subcode>  
        </s:Subcode>  
      </s:Code>  
      <s:Reason>  
        <s:Text xml:lang="en">Server 'http://BusinessABC.com/serviceA' is too busy to process this request. Try again later.</s:Text>  
      </s:Reason>  
    </s:Fault>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="9de30-201">WS-Adressierungsfehler</span><span class="sxs-lookup"><span data-stu-id="9de30-201">WS-Addressing Faults</span></span>  
 <span data-ttu-id="9de30-202">Da zuverlässiges WS-Messaging die WS-Adressierung verwendet, generiert und überträgt die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierung möglicherweise WS-Adressierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="9de30-202">Because WS-ReliableMessaging uses WS-Addressing, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="9de30-203">In diesem Abschnitt werden die WS-Adressierungsfehler erläutert, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explizit auf der WS-ReliableMessaging-Schicht generiert und überträgt.</span><span class="sxs-lookup"><span data-stu-id="9de30-203">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>  
  
-   <span data-ttu-id="9de30-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und überträgt die `Message Addressing Header Required` fehl, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="9de30-204">B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="9de30-205">Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `MessageId`-Header.</span><span class="sxs-lookup"><span data-stu-id="9de30-205">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="9de30-206">Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `ReplyTo`-Header.</span><span class="sxs-lookup"><span data-stu-id="9de30-206">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>  
  
    -   <span data-ttu-id="9de30-207">Bei einer Nachricht vom Typ `CreateSequenceResponse`, `CloseSequenceResponse` oder `TerminateSequenceResponse` fehlt ein `RelatesTo`-Header.</span><span class="sxs-lookup"><span data-stu-id="9de30-207">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>  
  
-   <span data-ttu-id="9de30-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und überträgt die `Endpoint Unavailable` Fehler, um anzugeben, dass es kein Endpunkt gelauscht, die die Sequenz basierend auf der Prüfung der Adressierungsheader in verarbeiten kann die `CreateSequence` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="9de30-208">B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="9de30-209">Protokollkomposition</span><span class="sxs-lookup"><span data-stu-id="9de30-209">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="9de30-210">Komposition mit WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="9de30-210">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-211"> unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung&#160;2004/08 [WS-ADDR] und die Empfehlungen für W3C die WS-Addressierung&#160;1.0 [WS-WS-ADDR-CORE] und [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="9de30-211"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="9de30-212">Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die Verwendung der WS-Adressierung nicht auf diese Version ein.</span><span class="sxs-lookup"><span data-stu-id="9de30-212">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="9de30-213">Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:</span><span class="sxs-lookup"><span data-stu-id="9de30-213">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="9de30-214">R2101: Sowohl WS-Adressierung&#160;2004/08 als auch WS-Adressierung&#160;1.0 können mit zuverlässigem WS-Messaging verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-214">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="9de30-215">R2102: Für eine gegebene WS-ReliableMessaging-Sequenz oder ein Paar umgekehrter Sequenzen, die mithilfe des `Offer`-Mechanismus korreliert wurden, darf nur eine Version der WS-Adressierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-215">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="9de30-216">Komposition mit SOAP</span><span class="sxs-lookup"><span data-stu-id="9de30-216">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-217"> unterstützt die Verwendung sowohl von SOAP&#160;1.1 als auch von SOAP&#160;1.2 mit zuverlässigem WS-Messaging.</span><span class="sxs-lookup"><span data-stu-id="9de30-217"> supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="9de30-218">Komposition mit WS-Sicherheit und WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="9de30-218">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-219"> bietet Schutz für die WS-ReliableMessaging-Sequenzen durch die Verwendung einer sicheren Transportmethode (HTTPS), die Erstellung mit WS-Sicherheit und die Erstellung mit WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="9de30-219"> provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="9de30-220">Das WS-ReliableMessaging&#160;1.1-Protokoll, das WS-Security&#160;1.1- und das WS-Secure Conversation&#160;1.3-Protokoll sollten zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-220">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="9de30-221">Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:</span><span class="sxs-lookup"><span data-stu-id="9de30-221">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="9de30-222">R2301: Damit die Integrität einer WS-ReliableMessaging-Sequenz sowie die Integrität und Vertraulichkeit einzelner Nachrichten sichergestellt ist, muss WS-Secure Conversation für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-222">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="9de30-223">R2302:AWS-Secure Conversation-Sitzung muss vor dem Einrichten von WS-ReliableMessaging Sequence(s) eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-223">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>  
  
-   <span data-ttu-id="9de30-224">R2303: Wenn die Lebensdauer einer WS-ReliableMessaging-Sequenz die Lebensdauer der WS-SecureConversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-SecureConversationRenewal-Bindung erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-224">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="9de30-225">B2304:WS-ReliableMessaging-Sequenz oder ein paar umgekehrt korrelierte Sequenzen immer an eine einzelne WS-SecureConversation-Sitzung gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="9de30-225">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
-   <span data-ttu-id="9de30-226">R2305: Wenn WS-Secure Conversation zur Erstellung verwendet wird, erfordert es der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter, dass die `CreateSequence`-Nachricht das `wsse:SecurityTokenReference`-Element und den `wsrm:UsesSequenceSTR`-Header enthält.</span><span class="sxs-lookup"><span data-stu-id="9de30-226">R2305: When composed with WS-Secure Conversation, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>  
  
 <span data-ttu-id="9de30-227">Ein Beispiel für einen `UsesSequenceSTR`-Header.</span><span class="sxs-lookup"><span data-stu-id="9de30-227">An example of a `UsesSequenceSTR` header.</span></span>  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="9de30-228">Komposition mit SSL/TLS-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="9de30-228">Composition with SSL/TLS sessions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-229"> unterstützt keine Komposition mit SSL/TLS-Sitzungen:</span><span class="sxs-lookup"><span data-stu-id="9de30-229"> does not support composition with SSL/TLS sessions:</span></span>  
  
-   <span data-ttu-id="9de30-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert den `wsrm:UsesSequenceSSL`-Header nicht.</span><span class="sxs-lookup"><span data-stu-id="9de30-230">B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate the `wsrm:UsesSequenceSSL` header.</span></span>  
  
-   <span data-ttu-id="9de30-231">R2402: Ein zuverlässiger Messaging-Initiator darf keine `CreateSequence`-Nachricht mit einem `wsrm:UsesSequenceSSL`-Header an einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter senden.</span><span class="sxs-lookup"><span data-stu-id="9de30-231">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder.</span></span>  
  
### <a name="composition-with-ws-policy"></a><span data-ttu-id="9de30-232">Komposition mit WS-Policy</span><span class="sxs-lookup"><span data-stu-id="9de30-232">Composition with WS-Policy</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-233"> unterstützt zwei Versionen von WS-Policy: WS-Policy&#160;1.2 und WS-Policy&#160;1.5.</span><span class="sxs-lookup"><span data-stu-id="9de30-233"> supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="9de30-234">WS-ReliableMessaging WS-Richtlinienassertion</span><span class="sxs-lookup"><span data-stu-id="9de30-234">WS-ReliableMessaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-235"> verwendet die WS-Richtlinienassertion von zuverlässigem WS-Messaging, `wsrm:RMAssertion`, um die Fähigkeiten von Endpunkten zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="9de30-235"> uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="9de30-236">Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:</span><span class="sxs-lookup"><span data-stu-id="9de30-236">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="9de30-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fügt die `wsrmn:RMAssertion`-WS-Richtlinienassertion an `wsdl:binding`-Elemente an.</span><span class="sxs-lookup"><span data-stu-id="9de30-237">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-238"> unterstützt sowohl das Anfügen an `wsdl:binding`-Elemente als auch an `wsdl:port`-Elemente.</span><span class="sxs-lookup"><span data-stu-id="9de30-238"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="9de30-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert nie das `wsp:Optional`-Tag.</span><span class="sxs-lookup"><span data-stu-id="9de30-239">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never generates the `wsp:Optional` tag.</span></span>  
  
-   <span data-ttu-id="9de30-240">B3003: Beim Zugreifen auf die `wsrmp:RMAssertion`-WS-Richtlinienassertion ignoriert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] das `wsp:Optional`-Tag und behandelt die WS-RM-Richtlinie als obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="9de30-240">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>  
  
-   <span data-ttu-id="9de30-241">R3004: Da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine Erstellung mit SSL/TLS-Sitzungen durchführt, akzeptiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine Richtlinie mit `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="9de30-241">R3004: Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not compose with SSL/TLS sessions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>  
  
-   <span data-ttu-id="9de30-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert immer das `wsrmp:DeliveryAssurance`-Element.</span><span class="sxs-lookup"><span data-stu-id="9de30-242">B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates the `wsrmp:DeliveryAssurance` element.</span></span>  
  
-   <span data-ttu-id="9de30-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gibt immer die `wsrmp:ExactlyOnce`-Zustellungszusicherung an.</span><span class="sxs-lookup"><span data-stu-id="9de30-243">B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>  
  
-   <span data-ttu-id="9de30-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und liest die folgenden Eigenschaften der WS-ReliableMessaging-Assertion und ermöglicht die Steuerung sie auf die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="9de30-244">B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableSessionBindingElement`:</span></span>  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     <span data-ttu-id="9de30-245">Ein Beispiel für eine `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="9de30-245">An example of a `RMAssertion`.</span></span>  
  
    ```xml  
    <wsrmp:RMAssertion>  
      <wsp:Policy>  
        <wsrmp:SequenceSTR/>  
        <wsrmp:DeliveryAssurance>  
          <wsp:Policy>  
            <wsrmp:ExactlyOnce/>  
            <wsrmp:InOrder/>  
          </wsp:Policy>  
        </wsrmp:DeliveryAssurance>  
      </wsp:Policy>  
      <netrmp:InactivityTimeout Milliseconds="600000"/>  
      <netrmp:AcknowledgementInterval Milliseconds="200"/>  
    </wsrmp:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="9de30-246">WS-ReliableMessaging-Erweiterung zur Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="9de30-246">Flow Control WS-ReliableMessaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-247"> verwendet die WS-ReliableMessaging-Erweiterbarkeit, um die optionale stärkere Kontrolle über den Sequenznachrichtenfluss zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9de30-247"> uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="9de30-248">Flusssteuerung aktiviert ist, durch Festlegen der `ReliableSessionBindingElement`des `FlowControlEnabled``boolean` Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="9de30-248">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``boolean` property to `true`.</span></span> <span data-ttu-id="9de30-249">Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:</span><span class="sxs-lookup"><span data-stu-id="9de30-249">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="9de30-250">B4001: Wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ein `netrm:BufferRemaining`-Element in der Elementerweiterbarkeit des `SequenceAcknowledgement`-Headers, wie im folgenden Beispiel zu sehen ist:</span><span class="sxs-lookup"><span data-stu-id="9de30-250">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="9de30-251">B4002: Selbst wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, erfordert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kein `netrm:BufferRemaining`-Element im `SequenceAcknowledgement`-Header.</span><span class="sxs-lookup"><span data-stu-id="9de30-251">B4002: Even when Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="9de30-252">B4003: Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ReliableMessaging-Ziel verwendet `netrm:BufferRemaining`, um anzugeben, wie viele neue Nachrichten es puffern kann.</span><span class="sxs-lookup"><span data-stu-id="9de30-252">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>  
  
-   <span data-ttu-id="9de30-253">B4004:when Reliable Messaging flusssteuerung aktiviert ist, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zuverlässige Messaging-Quelle verwendet den Wert der `netrm:BufferRemaining` zu drosseln nachrichtenübertragung.</span><span class="sxs-lookup"><span data-stu-id="9de30-253">B4004:When Reliable Messaging Flow Control is enabled, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>  
  
-   <span data-ttu-id="9de30-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert `netrm:BufferRemaining`-Ganzzahlwerte zwischen&#160;0 und 4096 einschließlich und liest Ganzzahlwerte zwischen&#160;0 und dem `xs:int`-Wert von `maxInclusive` (214748364) einschließlich.</span><span class="sxs-lookup"><span data-stu-id="9de30-254">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="9de30-255">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="9de30-255">Message Exchange Patterns</span></span>  
 <span data-ttu-id="9de30-256">In diesem Abschnitt wird das Verhalten von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bei Verwendung von WS-ReliableMessaging für verschiedene Nachrichtenaustauschmuster beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9de30-256">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="9de30-257">Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:</span><span class="sxs-lookup"><span data-stu-id="9de30-257">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="9de30-258">Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall; der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.</span><span class="sxs-lookup"><span data-stu-id="9de30-258">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="9de30-259">Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="9de30-259">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="9de30-260">Unidirektionaler, nicht adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="9de30-260">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9de30-261">Bindung</span><span class="sxs-lookup"><span data-stu-id="9de30-261">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-262"> stellt ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen HTTP-Kanal bereit.</span><span class="sxs-lookup"><span data-stu-id="9de30-262"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-263"> verwendet HTTP-Anforderungen, um Nachrichten vom Initiator an den Beantworter zu übertragen, und HTTP-Antworten, um Nachrichten vom Beantworter an den Initiator zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="9de30-263"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9de30-264">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-264">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9de30-265">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht ohne `Offer`-Element in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-265">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="9de30-266">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht ohne `Accept`-Element in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-266">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="9de30-267">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="9de30-267">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="9de30-268">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator erstellt Bestätigungen als Antwort auf alle Nachrichten mit Ausnahme von `CreateSequence`-Nachrichten und Fehlernachrichten.</span><span class="sxs-lookup"><span data-stu-id="9de30-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="9de30-269">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überträgt stets eine eigenständige Bestätigung als HTTP-Antwort auf alle Sequenzen und `AckRequested`-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9de30-269">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="9de30-270">CloseSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-270">CloseSequence Exchange</span></span>  
 <span data-ttu-id="9de30-271">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CloseSequence`-Nachricht in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-271">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="9de30-272">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überträgt die `CloseSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-272">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="9de30-273">TerminateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-273">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="9de30-274">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `TerminateSequence`-Nachricht in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-274">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="9de30-275">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überträgt die `TerminateSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="9de30-276">Unidirektionaler, adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="9de30-276">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9de30-277">Bindung</span><span class="sxs-lookup"><span data-stu-id="9de30-277">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-278"> bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="9de30-278"> provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-279"> verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9de30-279"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="9de30-280">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="9de30-280">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9de30-281">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-281">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9de30-282">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht ohne `Offer`-Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9de30-282">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="9de30-283">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht ohne `Accept`-Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9de30-283">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="9de30-284">Adressierbarer Duplex-Initiator</span><span class="sxs-lookup"><span data-stu-id="9de30-284">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9de30-285">Bindung</span><span class="sxs-lookup"><span data-stu-id="9de30-285">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-286"> bietet ein vollständig asynchrones bidirektionales Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="9de30-286"> provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="9de30-287">Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Request/Reply`, `Addressable`-Initiator kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9de30-287">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-288"> verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9de30-288"> uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="9de30-289">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="9de30-289">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9de30-290">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-290">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9de30-291">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9de30-291">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="9de30-292">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt sicher, dass `CreateSequence` ein `Offer`-Element enthält, erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht mit einem `Accept`-Element.</span><span class="sxs-lookup"><span data-stu-id="9de30-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="9de30-293">Sequenzlebensdauer</span><span class="sxs-lookup"><span data-stu-id="9de30-293">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-294"> behandelt die zwei Sequenzen als eine Vollduplexsitzung.</span><span class="sxs-lookup"><span data-stu-id="9de30-294"> treats the two sequences as one fully-duplex session.</span></span>  
  
 <span data-ttu-id="9de30-295">Nach dem Generieren eines Fehlers für eine Sequenz erwartet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], dass der Remoteendpunkt einen Fehler für beide Sequenzen auslöst.</span><span class="sxs-lookup"><span data-stu-id="9de30-295">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="9de30-296">Nach dem Lesen eines Fehlers, der zum Fehlschlagen einer Sequenz führt, löst [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen Fehler für beide Sequenzen aus.</span><span class="sxs-lookup"><span data-stu-id="9de30-296">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-297"> kann seine ausgehende Sequenz schließen und damit fortfahren, Nachrichten in seiner eingehenden Sequenz zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9de30-297"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="9de30-298">Umgekehrt kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auch das Schließen der eingehenden Sequenz durchführen und weiter Nachrichten in seiner ausgehenden Sequenz senden.</span><span class="sxs-lookup"><span data-stu-id="9de30-298">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="9de30-299">Anforderung-Antwort- und unidirektionaler, nicht adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="9de30-299">Request-Reply and One-Way, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9de30-300">Bindung</span><span class="sxs-lookup"><span data-stu-id="9de30-300">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-301"> bietet ein unidirektionales Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="9de30-301"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-302"> verwendet HTTP-Anforderungen, um Nachrichten vom Initiator an den Beantworter zu übertragen, und HTTP-Antworten, um Nachrichten vom Beantworter an den Initiator zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="9de30-302"> uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9de30-303">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-303">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9de30-304">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-304">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="9de30-305">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht mit einem `Accept`-Element in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-305">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="9de30-306">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="9de30-306">One-way Message</span></span>  
 <span data-ttu-id="9de30-307">Um einen unidirektionalen Nachrichtenaustausch erfolgreich durchzuführen, überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine eigenständige `SequenceAcknowledgement`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-307">To complete a one-way message exchange successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="9de30-308">Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.</span><span class="sxs-lookup"><span data-stu-id="9de30-308">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="9de30-309">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter kann mit einer Bestätigung, einem Fehler oder einer Antwort mit leerem Textbereich und dem HTTP-Statuscode 202 auf die Anforderung reagieren.</span><span class="sxs-lookup"><span data-stu-id="9de30-309">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="9de30-310">Bidirektionale Nachrichten</span><span class="sxs-lookup"><span data-stu-id="9de30-310">Two Way Messages</span></span>  
 <span data-ttu-id="9de30-311">Um ein bidirektionales Nachrichtenaustauschprotokoll erfolgreich durchzuführen, überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine Antwortsequenznachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-311">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="9de30-312">Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.</span><span class="sxs-lookup"><span data-stu-id="9de30-312">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="9de30-313">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter kann mit einer Anwendungsantwort, einem Fehler oder einer Antwort mit leerem Textbereich und dem HTTP-Statuscode&#160;202 auf die Anforderung reagieren.</span><span class="sxs-lookup"><span data-stu-id="9de30-313">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="9de30-314">Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.</span><span class="sxs-lookup"><span data-stu-id="9de30-314">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="9de30-315">Wiederholen von Antworten</span><span class="sxs-lookup"><span data-stu-id="9de30-315">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-316"> nutzt die HTTP-Anforderung-Antwort-Korrelation für das bidirektionale Nachrichtenaustauschprotokoll.</span><span class="sxs-lookup"><span data-stu-id="9de30-316"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="9de30-317">Daher wiederholt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht auch dann weiter, wenn die Anforderungssequenznachricht bestätigt wird. Er hört erst dann auf, wenn die HTTP-Antwort eine `SequenceAcknowledgement`, eine Anwendungsantwort oder einen Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="9de30-317">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="9de30-318">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter wiederholt die Antworten in der HTTP-Antwort auf die Anforderung, mit der die Antwort korreliert ist.</span><span class="sxs-lookup"><span data-stu-id="9de30-318">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>  
  
#### <a name="closesequence-exchange"></a><span data-ttu-id="9de30-319">CloseSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-319">CloseSequence Exchange</span></span>  
 <span data-ttu-id="9de30-320">Nach dem Empfang aller Antwortsequenznachrichten und Bestätigungen für alle unidirektionalen Anforderungssequenznachrichten überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine `CloseSequence`-Nachricht für die Anforderungssequenz in einer HTTP-Anforderung und erwartet die `CloseSequenceResponse` in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-320">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="9de30-321">Durch Schließen der Anforderungssequenz wird die Antwortsequenz implizit geschlossen.</span><span class="sxs-lookup"><span data-stu-id="9de30-321">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="9de30-322">Das bedeutet, der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator fügt die abschließende `SequenceAcknowledgement` der Antwortsequenz in die `CloseSequence`-Nachricht ein, und die Antwortsequenz verfügt über keinen `CloseSequence`-Austausch.</span><span class="sxs-lookup"><span data-stu-id="9de30-322">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>  
  
 <span data-ttu-id="9de30-323">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt sicher, dass alle Antworten bestätigt werden, und überträgt die `CloseSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-323">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="9de30-324">TerminateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-324">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="9de30-325">Nach Empfang der `CloseSequenceResponse`-Nachricht überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine `TerminateSequence`-Nachricht für die Anforderungssequenz in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse` in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-325">After receiving the `CloseSequenceResponse` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>  
  
 <span data-ttu-id="9de30-326">Wie beim `CloseSequence`-Austausch wird durch Beendigung der Anforderungssequenz die Antwortsequenz implizit beendet.</span><span class="sxs-lookup"><span data-stu-id="9de30-326">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="9de30-327">Das bedeutet, der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator fügt die abschließende `SequenceAcknowledgement` der Antwortsequenz in die `TerminateSequence`-Nachricht ein, und die Antwortsequenz verfügt über keinen `TerminateSequence`-Austausch.</span><span class="sxs-lookup"><span data-stu-id="9de30-327">This means the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>  
  
 <span data-ttu-id="9de30-328">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überträgt die `TerminateSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="9de30-328">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="9de30-329">Adressierbarer Anforderung/Antwort-Initiator</span><span class="sxs-lookup"><span data-stu-id="9de30-329">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="9de30-330">Bindung</span><span class="sxs-lookup"><span data-stu-id="9de30-330">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-331"> bietet ein Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="9de30-331"> provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="9de30-332">Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Duplex, Addressable`-Initiator kombinieren.</span><span class="sxs-lookup"><span data-stu-id="9de30-332">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-333"> verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="9de30-333"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="9de30-334">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="9de30-334">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="9de30-335">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="9de30-335">CreateSequence Exchange</span></span>  
 <span data-ttu-id="9de30-336">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="9de30-336">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="9de30-337">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt sicher, dass `CreateSequence` ein `Offer`-Element enthält, erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht mit einem `Accept`-Element.</span><span class="sxs-lookup"><span data-stu-id="9de30-337">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="9de30-338">Anforderung/Antwort-Korrelation</span><span class="sxs-lookup"><span data-stu-id="9de30-338">Request/Reply Correlation</span></span>  
 <span data-ttu-id="9de30-339">Folgendes gilt für alle korrelierenden Anforderungen und Antworten:</span><span class="sxs-lookup"><span data-stu-id="9de30-339">The following applies to all correlated requests and replies:</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-340"> stellt sicher, dass alle Anwendungsanforderungsnachrichten einen `ReplyTo`-Endpunktverweis und eine `MessageId` enthalten.</span><span class="sxs-lookup"><span data-stu-id="9de30-340"> ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-341"> wendet den lokalen Endpunktverweis als `ReplyTo` jeder einzelnen Anwendungsanforderungsnachricht an.</span><span class="sxs-lookup"><span data-stu-id="9de30-341"> applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="9de30-342">Der lokale Endpunktverweis ist der `CreateSequence`-Verweis der `ReplyTo`-Nachricht für den Initiator und der `CreateSequence`-Verweis der `To`-Nachricht für den Beantworter.</span><span class="sxs-lookup"><span data-stu-id="9de30-342">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-343"> stellt sicher, dass eingehende Anforderungsnachrichten eine `MessageId` und einen `ReplyTo`-Verweis besitzen.</span><span class="sxs-lookup"><span data-stu-id="9de30-343"> ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-344"> stellt zudem sicher, dass der URI des `ReplyTo`-Endpunktverweises aller Anwendungsanforderungsnachrichten wie weiter oben definiert mit dem lokalen Endpunktverweis übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="9de30-344"> ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="9de30-345"> stellt sicher, dass alle Antworten den richtigen `RelatesTo`-Header und `To`-Header gemäß den `wsa`-Anforderung-Antwort-Korrelationsregeln tragen.</span><span class="sxs-lookup"><span data-stu-id="9de30-345"> ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
