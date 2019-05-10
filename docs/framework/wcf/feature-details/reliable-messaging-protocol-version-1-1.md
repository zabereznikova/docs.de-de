---
title: Zuverlässiges Messaging-Protokoll, Version 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 349c4dec8f127640d2709abcd63295aace6826df
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754119"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="776b9-102">Zuverlässiges Messaging-Protokoll, Version 1,1</span><span class="sxs-lookup"><span data-stu-id="776b9-102">Reliable Messaging Protocol version 1.1</span></span>

<span data-ttu-id="776b9-103">Dieses Thema enthält Details zur Implementierung von Windows Communication Foundation (WCF) für die WS-ReliableMessaging vom Februar 2007 (Version 1.1)-Protokoll für die Interoperation mithilfe des HTTP-Transports erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="776b9-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="776b9-104">WCF folgt die WS-ReliableMessaging-Spezifikation mit den Einschränkungen und klarstellungen, die in diesem Thema erläutert.</span><span class="sxs-lookup"><span data-stu-id="776b9-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="776b9-105">Beachten Sie, dass das zuverlässige WS-Messaging-Protokoll in der Version&amp;#160;1.1 ab [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="776b9-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with the [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)].</span></span>

<span data-ttu-id="776b9-106">Die WS-ReliableMessaging vom Februar 2007 Protokoll wird in WCF von implementiert die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="776b9-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="776b9-107">Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="776b9-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="776b9-108">Initiator: Der Client, der Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert.</span><span class="sxs-lookup"><span data-stu-id="776b9-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>

- <span data-ttu-id="776b9-109">Beantworter: Der Dienst, der die Anforderungen des Initiators empfängt.</span><span class="sxs-lookup"><span data-stu-id="776b9-109">Responder: The service that receives the initiator's requests.</span></span>

 <span data-ttu-id="776b9-110">In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.</span><span class="sxs-lookup"><span data-stu-id="776b9-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="776b9-111">Präfix</span><span class="sxs-lookup"><span data-stu-id="776b9-111">Prefix</span></span>|<span data-ttu-id="776b9-112">Namespace</span><span class="sxs-lookup"><span data-stu-id="776b9-112">Namespace</span></span>|
|-|-|
|<span data-ttu-id="776b9-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="776b9-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|
|<span data-ttu-id="776b9-114">netrm</span><span class="sxs-lookup"><span data-stu-id="776b9-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|
|<span data-ttu-id="776b9-115">s</span><span class="sxs-lookup"><span data-stu-id="776b9-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|
|<span data-ttu-id="776b9-116">wsa</span><span class="sxs-lookup"><span data-stu-id="776b9-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|
|<span data-ttu-id="776b9-117">wsse</span><span class="sxs-lookup"><span data-stu-id="776b9-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|
|<span data-ttu-id="776b9-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="776b9-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|
|<span data-ttu-id="776b9-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="776b9-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|
|<span data-ttu-id="776b9-120">wsp</span><span class="sxs-lookup"><span data-stu-id="776b9-120">wsp</span></span>|<span data-ttu-id="776b9-121">(Entweder WS-Policy&amp;#160;1.2 oder WS-Policy&amp;#160;1.5)</span><span class="sxs-lookup"><span data-stu-id="776b9-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|

## <a name="messaging"></a><span data-ttu-id="776b9-122">Messaging</span><span class="sxs-lookup"><span data-stu-id="776b9-122">Messaging</span></span>

### <a name="sequence-creation"></a><span data-ttu-id="776b9-123">Sequenzerstellung</span><span class="sxs-lookup"><span data-stu-id="776b9-123">Sequence Creation</span></span>

<span data-ttu-id="776b9-124">WCF implementiert `CreateSequence` und `CreateSequenceResponse` sequenzieren von Nachrichten an ein zuverlässiges messaging einrichten.</span><span class="sxs-lookup"><span data-stu-id="776b9-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="776b9-125">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="776b9-125">The following constraints apply:</span></span>

- <span data-ttu-id="776b9-126">B1101: Der WCF-Initiator verwendet den gleichen Endpunktverweis als die `CreateSequence` Nachricht `ReplyTo`, `AcksTo` und `Offer/Endpoint`.</span><span class="sxs-lookup"><span data-stu-id="776b9-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>

- <span data-ttu-id="776b9-127">R1102: Die `AcksTo`, `ReplyTo` und `Offer/Endpoint` -Endpunktverweise in der `CreateSequence` Nachricht müssen Adresswerte mit identischen zeichenfolgendarstellungen, die sich oktettweise entsprechen.</span><span class="sxs-lookup"><span data-stu-id="776b9-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>

  - <span data-ttu-id="776b9-128">Der WCF-Beantworter überprüft, ob die URI-Teil der `AcksTo`, `ReplyTo` und `Endpoint` Endpunktverweise identisch sind, bevor Sie eine Sequenz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="776b9-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>

- <span data-ttu-id="776b9-129">R1103: Die `AcksTo`, `ReplyTo` und `Offer/Endpoint` -Endpunktverweise in der `CreateSequence` -Nachricht müssen den gleichen Satz an Verweisparametern.</span><span class="sxs-lookup"><span data-stu-id="776b9-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>

  - <span data-ttu-id="776b9-130">WCF wird nicht erzwungen, sondern setzt voraus, die auf Parameter von der `AcksTo`, `ReplyTo` und `Offer/Endpoint` -Endpunktverweise für `CreateSequence` identisch sind und verwendet Verweisparameter vom die `ReplyTo` -Endpunktverweis für Bestätigungen und Nachrichten umgekehrter Sequenz.</span><span class="sxs-lookup"><span data-stu-id="776b9-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="776b9-131">B1104: Der WCF-Initiator generiert nicht das optionale `Expires` oder `Offer/Expires` Element in der `CreateSequence` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>

- <span data-ttu-id="776b9-132">B1105: Beim Zugriff auf die `CreateSequence` Nachricht, die WCF-Antwortdienst verwendet die `Expires` Wert in der `CreateSequence` Element als die `Expires` Wert in der `CreateSequenceResponse` Element.</span><span class="sxs-lookup"><span data-stu-id="776b9-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="776b9-133">Andernfalls der WCF-Beantworter liest und ignoriert die `Expires` und `Offer/Expires` Werte.</span><span class="sxs-lookup"><span data-stu-id="776b9-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>

- <span data-ttu-id="776b9-134">B1106: Beim Zugriff auf die `CreateSequenceResponse` Nachricht, die den WCF-Initiator liest das optionale `Expires` Wert aber nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="776b9-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>

- <span data-ttu-id="776b9-135">B1107: Der WCF-Initiator und der Beantworter generieren immer das optionale `IncompleteSequenceBehavior` Element in der `CreateSequence/Offer` und `CreateSequenceResponse` Elemente.</span><span class="sxs-lookup"><span data-stu-id="776b9-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>

- <span data-ttu-id="776b9-136">B1108: WCF verwendet nur die `DiscardFollowingFirstGap` und `NoDiscard` Werte in der `IncompleteSequenceBehavior` Element.</span><span class="sxs-lookup"><span data-stu-id="776b9-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>

  - <span data-ttu-id="776b9-137">Zuverlässiges WS-Messaging verwendet den `Offer`-Mechanismus, um die beiden umgekehrt korrelierten Sequenzen einzurichten, die eine Sitzung bilden.</span><span class="sxs-lookup"><span data-stu-id="776b9-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="776b9-138">B1109: Wenn `CreateSequence` enthält ein `Offer` -Element, lehnt die unidirektionalen WCF-Beantworter die angebotene Sequenz durch die Antwort mit einem `CreateSequenceResponse` ohne eine `Accept` Element.</span><span class="sxs-lookup"><span data-stu-id="776b9-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>

- <span data-ttu-id="776b9-139">B1110: Wenn eine zuverlässige Messaging-Beantworter die angebotene Sequenz zurückweist, stört den WCF-Initiator die neu erstellte Sequenz.</span><span class="sxs-lookup"><span data-stu-id="776b9-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>

- <span data-ttu-id="776b9-140">B1111: Wenn `CreateSequence` enthält kein `Offer` -Element, lehnt der bidirektionalen WCF-Beantworter die angebotene Sequenz durch die Antwort mit einem `CreateSequenceRefused` Fehler.</span><span class="sxs-lookup"><span data-stu-id="776b9-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>

- <span data-ttu-id="776b9-141">R1112: Bei zwei umgekehrte Sequenzen eingerichtet werden, mithilfe der `Offer` Mechanismus, der `[address]` Eigenschaft der `CreateSequenceResponse/Accept/AcksTo` Endpunktverweis muss mit das Ziel-URI übereinstimmen von der `CreateSequence` -Nachricht Byte für Byte.</span><span class="sxs-lookup"><span data-stu-id="776b9-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>

- <span data-ttu-id="776b9-142">R1113: Wenn zwei umgekehrte Sequenzen eingerichtet werden, mithilfe der `Offer` Mechanismus, alle Nachrichten in beiden Sequenzen vom Initiator an den Antwortdienst gesendet werden an den gleichen Endpunktverweis.</span><span class="sxs-lookup"><span data-stu-id="776b9-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>

<span data-ttu-id="776b9-143">WCF verwendet WS-ReliableMessaging um zuverlässige Sitzungen zwischen dem Initiator und Beantworter einzurichten.</span><span class="sxs-lookup"><span data-stu-id="776b9-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="776b9-144">Die WCF-WS-ReliableMessaging-Implementierung bietet eine zuverlässige Sitzung für unidirektionale, Anforderung-Antwort- und Vollduplex-Nachrichtenmuster.</span><span class="sxs-lookup"><span data-stu-id="776b9-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="776b9-145">Der `Offer`-Mechanismus von zuverlässigem WS-Messaging für `CreateSequence` und `CreateSequenceResponse` ermöglicht es Ihnen, zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein für alle Nachrichtenendpunkte geeignetes Sitzungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="776b9-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="776b9-146">Da WCF eine Sicherheitsgarantie für solcher Sitzungen sowie End-to-End-Schutz bietet, ist es ratsam, um sicherzustellen, dass Nachrichten für den gleichen Teilnehmer am selben Ziel ankommen.</span><span class="sxs-lookup"><span data-stu-id="776b9-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="776b9-147">Dadurch wird es zudem ermöglicht, Sequenzbestätigungen im Piggyback-Verfahren mit Anwendungsnachrichten zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="776b9-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="776b9-148">Daher gelten Einschränkungen R1102, R1112 und R1113 für WCF.</span><span class="sxs-lookup"><span data-stu-id="776b9-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>

<span data-ttu-id="776b9-149">Ein Beispiel für eine `CreateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-149">An example of a `CreateSequence` message.</span></span>

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

<span data-ttu-id="776b9-150">Ein Beispiel für eine `CreateSequenceResponse`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-150">An example of a `CreateSequenceResponse` message.</span></span>

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

### <a name="closing-a-sequence"></a><span data-ttu-id="776b9-151">Schließen einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="776b9-151">Closing a Sequence</span></span>

<span data-ttu-id="776b9-152">WCF verwendet die `CloseSequence` und `CloseSequenceResponse` Nachrichten für die ein zuverlässiges Messaging Quelle initiierte schließen durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="776b9-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="776b9-153">Das WCF Reliable Messaging-Ziel initiiert das Schließen nicht, und die WCF-Reliable Messaging-Quelle unterstützt keine zuverlässige Messaging-Ziel Herunterfahren durch einen.</span><span class="sxs-lookup"><span data-stu-id="776b9-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="776b9-154">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="776b9-154">The following constraints apply:</span></span>

- <span data-ttu-id="776b9-155">B1201: Der WCF-Reliable Messaging-Quelle sendet immer eine `CloseSequence` Nachricht, um die Sequenz zu schließen.</span><span class="sxs-lookup"><span data-stu-id="776b9-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>

- <span data-ttu-id="776b9-156">B1202: Die zuverlässige Messaging-Quelle wartet auf die Bestätigung aller sequenznachrichten das gesamte Spektrum vor dem Senden der `CloseSequence` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>

- <span data-ttu-id="776b9-157">B1203: Die zuverlässige Messaging-Quelle enthält immer das optionale `LastMsgNumber` Element, wenn die Sequenz keine Nachrichten enthält.</span><span class="sxs-lookup"><span data-stu-id="776b9-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>

- <span data-ttu-id="776b9-158">R1204: Das zuverlässige Messaging-Ziel muss initiiert das Schließen nicht durch Senden einer `CloseSequence` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>

- <span data-ttu-id="776b9-159">B1205: Bei Empfang einer `CloseSequence` Nachricht, die WCF-Reliable Messaging-Quelle berücksichtigt die Sequenz als unvollständig und sendet einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="776b9-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>

 <span data-ttu-id="776b9-160">Ein Beispiel für eine `CloseSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-160">An example of a `CloseSequence` message.</span></span>

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
```

<span data-ttu-id="776b9-161">Beispiel `CloseSequenceResponse` Nachricht:</span><span class="sxs-lookup"><span data-stu-id="776b9-161">Example `CloseSequenceResponse` message:</span></span>

```xml
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

### <a name="sequence-termination"></a><span data-ttu-id="776b9-162">Sequenzbeendigung</span><span class="sxs-lookup"><span data-stu-id="776b9-162">Sequence Termination</span></span>

<span data-ttu-id="776b9-163">WCF verwendet hauptsächlich die `TerminateSequence/TerminateSequenceResponse` Handshake nach Abschluss der `CloseSequence/CloseSequenceResponse` Handshake.</span><span class="sxs-lookup"><span data-stu-id="776b9-163">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="776b9-164">Das WCF Reliable Messaging-Ziel initiiert die Beendigung nicht, und die zuverlässige Messaging-Quelle eine zuverlässiges Messaging-Ziel initiierte Beendigung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="776b9-164">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="776b9-165">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="776b9-165">The following constraints apply:</span></span>

- <span data-ttu-id="776b9-166">B1301: Der WCF--Initiator schickt die `TerminateSequence` Nachricht nach dem erfolgreichen Abschluss der `CloseSequence/CloseSequenceResponse` Handshake.</span><span class="sxs-lookup"><span data-stu-id="776b9-166">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>

- <span data-ttu-id="776b9-167">R1302: WCF überprüft, ob die `LastMsgNumber` -Element ist konsistent in allen `CloseSequence` und `TerminateSequence` Nachrichten für eine bestimmte Sequenz.</span><span class="sxs-lookup"><span data-stu-id="776b9-167">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="776b9-168">Das bedeutet, dass `LastMsgNumber` entweder in keiner `CloseSequence`-Nachricht und keiner `TerminateSequence`-Nachricht vorhanden ist oder in allen `CloseSequence`-Nachrichten und `TerminateSequence`-Nachrichten vorhanden und identisch ist.</span><span class="sxs-lookup"><span data-stu-id="776b9-168">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>

- <span data-ttu-id="776b9-169">B1303: Beim Empfang von einer `TerminateSequence` -Nachricht nach der `CloseSequence/CloseSequenceResponse` Handshake, der die zuverlässige Messaging-Ziel antwortet mit einer `TerminateSequenceResponse` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-169">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="776b9-170">Da die zuverlässige Messaging-Quelle die `TerminateSequence`-Nachricht erst nach Erhalt der letzten Bestätigung sendet, weiß das zuverlässige Messaging-Ziel mit Sicherheit, dass die Sequenz beendet ist, und fordert die Ressourcen unverzüglich zurück.</span><span class="sxs-lookup"><span data-stu-id="776b9-170">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>

- <span data-ttu-id="776b9-171">B1304: Beim Empfang einer `TerminateSequence` -Nachricht vor der `CloseSequence/CloseSequenceResponse` Handshake, der WCF-Reliable Messaging-Ziel gibt eine `TerminateSequenceResponse` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-171">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="776b9-172">Wenn das zuverlässige Messaging-Ziel ermittelt, dass die Sequenz keine Inkonsistenzen aufweist, wartet das zuverlässige Messaging-Ziel so lange, wie vom Anwendungsziel angegeben, bevor es die Ressourcen zurückverlangt, um es dem Client zu ermöglichen, die letzte Bestätigung zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="776b9-172">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="776b9-173">Anderenfalls fordert das zuverlässige Messaging-Ziel die Ressourcen unverzüglich zurück und teilt dem Anwendungsziel mit, dass die Sequenz nicht ordnungsgemäß beendet wurde, indem es das `Faulted`-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="776b9-173">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>

<span data-ttu-id="776b9-174">Ein Beispiel für eine `TerminateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-174">An example of a `TerminateSequence` message.</span></span>

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
```

<span data-ttu-id="776b9-175">Beispiel `TerminateSequenceResponse` Nachricht:</span><span class="sxs-lookup"><span data-stu-id="776b9-175">Example `TerminateSequenceResponse` message:</span></span>

```xml
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

### <a name="sequences"></a><span data-ttu-id="776b9-176">Sequenzen</span><span class="sxs-lookup"><span data-stu-id="776b9-176">Sequences</span></span>

<span data-ttu-id="776b9-177">Die folgende Liste enthält die Einschränkungen, die für Sequenzen gelten:</span><span class="sxs-lookup"><span data-stu-id="776b9-177">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="776b9-178">B1401:WCF generiert und Zugriffe Sequenznummern nicht höher als `xs:long`des inklusive Maximalwert 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="776b9-178">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

<span data-ttu-id="776b9-179">Ein Beispiel für einen `Sequence`-Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-179">An example of a `Sequence` header.</span></span>

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a><span data-ttu-id="776b9-180">Anfordern einer Bestätigung</span><span class="sxs-lookup"><span data-stu-id="776b9-180">Request Acknowledgement</span></span>

<span data-ttu-id="776b9-181">WCF verwendet die `AckRequested` -Header als Keep-alive-Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="776b9-181">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>

<span data-ttu-id="776b9-182">Ein Beispiel für einen `AckRequested`-Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-182">An example of an `AckRequested` header.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a><span data-ttu-id="776b9-183">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="776b9-183">SequenceAcknowledgement</span></span>

<span data-ttu-id="776b9-184">WCF verwendet einen "Piggyback"-Mechanismus für in WS-Reliable-Messaging bereitgestellten sequenzbestätigungen.</span><span class="sxs-lookup"><span data-stu-id="776b9-184">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="776b9-185">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="776b9-185">The following constraints apply:</span></span>

- <span data-ttu-id="776b9-186">R1601: Wenn zwei umgekehrte Sequenzen eingerichtet werden, mithilfe der `Offer` Mechanismus, der `SequenceAcknowledgement` Header kann in jede Anwendungsnachricht mit dem beabsichtigten Empfänger enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="776b9-186">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="776b9-187">Der Remoteendpunkt muss in der Lage sein, auf einen per Piggyback-Verfahren gesendeten `SequenceAcknowledgement`-Header zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="776b9-187">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="776b9-188">B1602: WCF generiert keine `SequenceAcknowledgement` -Header mit `Nack` Elemente.</span><span class="sxs-lookup"><span data-stu-id="776b9-188">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="776b9-189">WCF überprüft, ob jedes `Nack` -Element eine Sequenznummer enthält, andernfalls ignoriert jedoch die `Nack` Element und Wert.</span><span class="sxs-lookup"><span data-stu-id="776b9-189">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>

 <span data-ttu-id="776b9-190">Ein Beispiel für einen `SequenceAcknowledgement`-Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-190">An example of a `SequenceAcknowledgement` header.</span></span>

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="776b9-191">WS-ReliableMessaging-Fehler</span><span class="sxs-lookup"><span data-stu-id="776b9-191">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="776b9-192">Folgendes ist eine Liste der Einschränkungen, die für die WCF-Implementierung der WS-ReliableMessaging Fehler gelten.</span><span class="sxs-lookup"><span data-stu-id="776b9-192">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="776b9-193">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="776b9-193">The following constraints apply:</span></span>

- <span data-ttu-id="776b9-194">B1701: WCF generiert keine `MessageNumberRollover` Fehler.</span><span class="sxs-lookup"><span data-stu-id="776b9-194">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="776b9-195">B1702: Über SOAP 1.2, wenn der Dienstendpunkt seine Verbindungsgrenze erreicht und keine weiteren Verbindungen verarbeiten WCF generiert eine geschachtelte `CreateSequenceRefused` -Fehlersubcode `netrm:ConnectionLimitReached`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="776b9-195">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

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

### <a name="ws-addressing-faults"></a><span data-ttu-id="776b9-196">WS-Adressierungsfehler</span><span class="sxs-lookup"><span data-stu-id="776b9-196">WS-Addressing Faults</span></span>

<span data-ttu-id="776b9-197">Da WS-ReliableMessaging WS-Adressierung verwendet wird, kann die Implementierung des WCF-WS-ReliableMessaging generieren und Übertragen von WS-Adressierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="776b9-197">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="776b9-198">Dieser Abschnitt behandelt die WS-Adressierungsfehler, die WCF explizit generiert und überträgt auf der Ebene WS-ReliableMessaging:</span><span class="sxs-lookup"><span data-stu-id="776b9-198">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>

- <span data-ttu-id="776b9-199">B1801:WCF generiert und überträgt die `Message Addressing Header Required` Fehler, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="776b9-199">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>

  - <span data-ttu-id="776b9-200">Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `MessageId`-Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-200">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="776b9-201">Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `ReplyTo`-Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-201">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>

  - <span data-ttu-id="776b9-202">Bei einer Nachricht vom Typ `CreateSequenceResponse`, `CloseSequenceResponse` oder `TerminateSequenceResponse` fehlt ein `RelatesTo`-Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-202">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>

- <span data-ttu-id="776b9-203">B1802:WCF generiert und überträgt die `Endpoint Unavailable` verarbeiten Fehler, um anzugeben, es ist kein Endpunkt gelauscht, der die Sequenz basierend auf der Untersuchung der Adressheader in der `CreateSequence` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="776b9-203">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="776b9-204">Protokollkomposition</span><span class="sxs-lookup"><span data-stu-id="776b9-204">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="776b9-205">Komposition mit WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="776b9-205">Composition with WS-Addressing</span></span>

<span data-ttu-id="776b9-206">WCF unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung 2004/08 [WS-ADDR] und W3C WS-Adressierung 1.0 Empfehlungen [WS-ADDR-CORE] und [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="776b9-206">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="776b9-207">Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&amp;#160;2004/08, schränkt jedoch die Verwendung der WS-Adressierung nicht auf diese Version ein.</span><span class="sxs-lookup"><span data-stu-id="776b9-207">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="776b9-208">Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="776b9-208">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="776b9-209">R2101: Sowohl WS-Adressierung 2004/08 als auch WS-Adressierung 1.0 können mit zuverlässigem WS-Messaging verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="776b9-209">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="776b9-210">R2102: Muss eine einzelne Version der WS-Adressierung verwendet werden, in einer bestimmten WS-ReliableMessaging Sequenz oder ein Paar umgekehrter Sequenzen korreliert mit der `Offer` Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="776b9-210">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="776b9-211">Komposition mit SOAP</span><span class="sxs-lookup"><span data-stu-id="776b9-211">Composition with SOAP</span></span>

<span data-ttu-id="776b9-212">WCF unterstützt die Verwendung von SOAP 1.1 und SOAP 1.2 mit zuverlässigem WS-Messaging.</span><span class="sxs-lookup"><span data-stu-id="776b9-212">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="776b9-213">Komposition mit WS-Sicherheit und WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="776b9-213">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="776b9-214">WCF bietet Schutz für die WS-ReliableMessaging Sequenzen unter Verwendung von sicheren Transportmethode (HTTPS), Komposition mit WS-Security und Komposition mit WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="776b9-214">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="776b9-215">Das WS-ReliableMessaging&amp;#160;1.1-Protokoll, das WS-Security&amp;#160;1.1- und das WS-Secure Conversation&amp;#160;1.3-Protokoll sollten zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="776b9-215">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="776b9-216">Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="776b9-216">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="776b9-217">R2301: Um die Integrität einer Sequenz WS-ReliableMessaging sowie die Integrität und Vertraulichkeit einzelner Nachrichten zu schützen, muss WCF WS-Secure Conversation verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="776b9-217">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="776b9-218">R2302:AWS-Secure Conversation-Sitzung muss vor der Erstellung WS-ReliableMessaging-Sequenzen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="776b9-218">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>

- <span data-ttu-id="776b9-219">R2303: Wenn die WS-ReliableMessaging sequenzlebensdauer der WS-Secure Conversation Sitzung überschreitet die `SecurityContextToken` hergestellt, indem Sie mithilfe von WS-Secure Conversation muss mithilfe der entsprechenden WS-Secure Conversation Renewal-Bindung erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="776b9-219">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="776b9-220">B2304:WS-ReliableMessaging-Sequenz bzw. das Paar korrelierter umgekehrter Sequenzen ist immer an eine einzelne WS-SecureConversation-Sitzung gebunden.</span><span class="sxs-lookup"><span data-stu-id="776b9-220">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

- <span data-ttu-id="776b9-221">R2305: Mit WS-Secure Conversation aus der WCF-Beantworter erfordert, dass die `CreateSequence` Nachricht enthält die `wsse:SecurityTokenReference` Element und die `wsrm:UsesSequenceSTR` Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-221">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>

 <span data-ttu-id="776b9-222">Ein Beispiel für einen `UsesSequenceSTR`-Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-222">An example of a `UsesSequenceSTR` header.</span></span>

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="776b9-223">Komposition mit SSL/TLS-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="776b9-223">Composition with SSL/TLS sessions</span></span>

<span data-ttu-id="776b9-224">WCF unterstützt keine Komposition mit SSL/TLS-Sitzungen:</span><span class="sxs-lookup"><span data-stu-id="776b9-224">WCF does not support composition with SSL/TLS sessions:</span></span>

- <span data-ttu-id="776b9-225">B2401: WCF generiert nicht das `wsrm:UsesSequenceSSL` Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-225">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>

- <span data-ttu-id="776b9-226">R2402: Ein zuverlässiger Messaging-Initiator muss nicht senden eine `CreateSequence` -Nachricht mit einer `wsrm:UsesSequenceSSL` Header zu einer WCF-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-226">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>

### <a name="composition-with-ws-policy"></a><span data-ttu-id="776b9-227">Komposition mit WS-Policy</span><span class="sxs-lookup"><span data-stu-id="776b9-227">Composition with WS-Policy</span></span>

<span data-ttu-id="776b9-228">WCF unterstützt zwei Versionen der WS-Richtlinie: WS-Richtlinie 1.2 und WS-Richtlinie 1.5.</span><span class="sxs-lookup"><span data-stu-id="776b9-228">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>

## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="776b9-229">WS-ReliableMessaging WS-Richtlinienassertion</span><span class="sxs-lookup"><span data-stu-id="776b9-229">WS-ReliableMessaging WS-Policy Assertion</span></span>

<span data-ttu-id="776b9-230">WCF verwendet WS-ReliableMessaging WS-Richtlinienassertion `wsrm:RMAssertion` Fähigkeiten von Endpunkten zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="776b9-230">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="776b9-231">Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="776b9-231">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="776b9-232">B3001: Fügt WCF `wsrmn:RMAssertion` WS-Richtlinienassertion `wsdl:binding` Elemente.</span><span class="sxs-lookup"><span data-stu-id="776b9-232">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="776b9-233">WCF unterstützt sowohl Anlagen in `wsdl:binding` und `wsdl:port` Elemente.</span><span class="sxs-lookup"><span data-stu-id="776b9-233">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="776b9-234">B3002: WCF generiert nie das `wsp:Optional` Tag.</span><span class="sxs-lookup"><span data-stu-id="776b9-234">B3002: WCF never generates the `wsp:Optional` tag.</span></span>

- <span data-ttu-id="776b9-235">B3003: Beim Zugriff auf die `wsrmp:RMAssertion` WS-Richtlinienassertion WCF ignoriert den `wsp:Optional` -Tag und behandelt die WS-RM-Richtlinie als obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="776b9-235">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>

- <span data-ttu-id="776b9-236">R3004: Da WCF nicht mit SSL/TLS-Sitzungen erstellt werden, WCF akzeptiert keine Richtlinie mit `wsrmp:SequenceTransportSecurity`.</span><span class="sxs-lookup"><span data-stu-id="776b9-236">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>

- <span data-ttu-id="776b9-237">B3005: WCF generiert immer die `wsrmp:DeliveryAssurance` Element.</span><span class="sxs-lookup"><span data-stu-id="776b9-237">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>

- <span data-ttu-id="776b9-238">B3006: WCF gibt immer an die `wsrmp:ExactlyOnce` übermittlungssicherung.</span><span class="sxs-lookup"><span data-stu-id="776b9-238">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>

- <span data-ttu-id="776b9-239">B3007: WCF generiert und liest die folgenden Eigenschaften der Assertion WS-ReliableMessaging und Kontrolle über die sie auf der WCF`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="776b9-239">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  <span data-ttu-id="776b9-240">Ein Beispiel für eine `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="776b9-240">An example of a `RMAssertion`.</span></span>

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

## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="776b9-241">WS-ReliableMessaging-Erweiterung zur Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="776b9-241">Flow Control WS-ReliableMessaging Extension</span></span>

<span data-ttu-id="776b9-242">WCF verwendet WS-ReliableMessaging Erweiterbarkeit um optionale Steuerung des sequenznachrichtenflusses Sequenz Nachrichtenfluss zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="776b9-242">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="776b9-243">Flusssteuerung aktiviert ist, durch Festlegen der <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="776b9-243">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="776b9-244">Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="776b9-244">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="776b9-245">B4001: WCF wird generiert, wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, eine `netrm:BufferRemaining` Element in der elementerweiterbarkeit des der `SequenceAcknowledgement` -Header, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="776b9-245">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="776b9-246">B4002: Selbst wenn der zuverlässige Messaging-Ablaufsteuerung aktiviert ist, WCF erfordert keine `netrm:BufferRemaining` Element in der `SequenceAcknowledgement` Header.</span><span class="sxs-lookup"><span data-stu-id="776b9-246">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="776b9-247">B4003: WCF-Reliable Messaging-Ziel verwendet `netrm:BufferRemaining` um anzugeben, wie viele neue Nachrichten es Puffern kann.</span><span class="sxs-lookup"><span data-stu-id="776b9-247">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>

- <span data-ttu-id="776b9-248">B4004:when Reliable Messaging-Ablaufsteuerung aktiviert ist, wird die WCF Reliable-Messaging-Quelle verwendet den Wert der `netrm:BufferRemaining` , Drosselung nachrichtenübertragung.</span><span class="sxs-lookup"><span data-stu-id="776b9-248">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>

- <span data-ttu-id="776b9-249">B4005: WCF generiert `netrm:BufferRemaining` ganzzahlige Werte zwischen 0 und 4096 einschließlich und liest Ganzzahlwerte zwischen 0 und `xs:int`des `maxInclusive` Wert (214748364) einschließlich.</span><span class="sxs-lookup"><span data-stu-id="776b9-249">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="776b9-250">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="776b9-250">Message Exchange Patterns</span></span>

<span data-ttu-id="776b9-251">Dieser Abschnitt beschreibt WCFs-Verhalten, wenn WS-ReliableMessaging für verschiedene Nachrichtenaustauschmuster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="776b9-251">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="776b9-252">Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:</span><span class="sxs-lookup"><span data-stu-id="776b9-252">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="776b9-253">Nicht Adressierbarer Initiator: Initiator befindet sich hinter einer Firewall; Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.</span><span class="sxs-lookup"><span data-stu-id="776b9-253">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="776b9-254">Adressierbarer Initiator: Initiator und Beantworter können HTTP-Anforderungen gesendet werden. Anders gesagt können zwei entgegengesetzte HTTP-Verbindungen hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="776b9-254">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="776b9-255">Unidirektionaler, nicht adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="776b9-255">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="776b9-256">Bindung</span><span class="sxs-lookup"><span data-stu-id="776b9-256">Binding</span></span>

<span data-ttu-id="776b9-257">WCF bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="776b9-257">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="776b9-258">WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten vom Initiator an den Beantworter und HTTP-Antworten zur Übertragung aller Nachrichten vom Beantworter an den Initiator.</span><span class="sxs-lookup"><span data-stu-id="776b9-258">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="776b9-259">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-259">CreateSequence Exchange</span></span>

<span data-ttu-id="776b9-260">Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht ohne `Offer` -Element in einer HTTP-Anforderung und erwartet, dass die `CreateSequenceResponse` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-260">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="776b9-261">Der WCF-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht ohne `Accept` Element, für die HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-261">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="776b9-262">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="776b9-262">SequenceAcknowledgement</span></span>

<span data-ttu-id="776b9-263">Der WCF-Initiator erstellt Bestätigungen als Antwort alle Nachrichten mit Ausnahme der `CreateSequence` -Nachrichten und Fehlernachrichten.</span><span class="sxs-lookup"><span data-stu-id="776b9-263">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="776b9-264">Der WCF-Beantworter überträgt stets eine eigenständige Bestätigung in der HTTP-Antwort auf alle Sequenzen und `AckRequested` Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="776b9-264">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="776b9-265">CloseSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-265">CloseSequence Exchange</span></span>

<span data-ttu-id="776b9-266">Der WCF--Initiator überträgt eine `CloseSequence` -Nachricht in einer HTTP-Anforderung und erwartet, dass die `CreateSequenceResponse` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-266">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="776b9-267">Der WCF-Beantworter überträgt die `CloseSequenceResponse` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-267">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="776b9-268">TerminateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-268">TerminateSequence Exchange</span></span>

<span data-ttu-id="776b9-269">Der WCF--Initiator überträgt eine `TerminateSequence` -Nachricht in einer HTTP-Anforderung und erwartet, dass die `TerminateSequenceResponse` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-269">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="776b9-270">Der WCF-Beantworter überträgt die `TerminateSequenceResponse` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-270">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="776b9-271">Unidirektionaler, adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="776b9-271">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="776b9-272">Bindung</span><span class="sxs-lookup"><span data-stu-id="776b9-272">Binding</span></span>

<span data-ttu-id="776b9-273">WCF bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="776b9-273">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="776b9-274">WCF verwendet die HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="776b9-274">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="776b9-275">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&amp;#160;202.</span><span class="sxs-lookup"><span data-stu-id="776b9-275">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="776b9-276">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-276">CreateSequence Exchange</span></span>

<span data-ttu-id="776b9-277">Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht ohne `Offer` -Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="776b9-277">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="776b9-278">Der WCF-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht ohne `Accept` -Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="776b9-278">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="776b9-279">Adressierbarer Duplex-Initiator</span><span class="sxs-lookup"><span data-stu-id="776b9-279">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="776b9-280">Bindung</span><span class="sxs-lookup"><span data-stu-id="776b9-280">Binding</span></span>

<span data-ttu-id="776b9-281">WCF bietet ein vollständig asynchrones, bidirektionales Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="776b9-281">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="776b9-282">Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Request/Reply`, `Addressable`-Initiator kombinieren.</span><span class="sxs-lookup"><span data-stu-id="776b9-282">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="776b9-283">WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="776b9-283">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="776b9-284">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&amp;#160;202.</span><span class="sxs-lookup"><span data-stu-id="776b9-284">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="776b9-285">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-285">CreateSequence Exchange</span></span>

<span data-ttu-id="776b9-286">Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht mit einer `Offer` -Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="776b9-286">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="776b9-287">Der WCF-Beantworter stellt sicher, dass die `CreateSequence` verfügt über eine `Offer` -Element, dann erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht mit einer `Accept` Element.</span><span class="sxs-lookup"><span data-stu-id="776b9-287">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="776b9-288">Sequenzlebensdauer</span><span class="sxs-lookup"><span data-stu-id="776b9-288">Sequence Lifetime</span></span>

<span data-ttu-id="776b9-289">WCF behandelt die beiden Sequenzen als eine vollduplexsitzung.</span><span class="sxs-lookup"><span data-stu-id="776b9-289">WCF treats the two sequences as one fully-duplex session.</span></span>

<span data-ttu-id="776b9-290">Nach dem Generieren eines Fehlers, der eine Sequenz einen Fehler an, erwartet, dass WCF den Remoteendpunkt für beide Sequenzen auslöst.</span><span class="sxs-lookup"><span data-stu-id="776b9-290">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="776b9-291">Nach dem Lesen eines Fehlers, der eine Sequenz einen Fehler, Fehler WCF für beide Sequenzen.</span><span class="sxs-lookup"><span data-stu-id="776b9-291">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="776b9-292">WCF kann seine ausgehende Sequenz schließen und zum Verarbeiten von Nachrichten in seiner eingehenden Sequenz fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="776b9-292">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="776b9-293">Im Gegensatz dazu kann WCF das Schließen der eingehenden Sequenz und weiter Nachrichten in seiner ausgehenden Sequenz senden.</span><span class="sxs-lookup"><span data-stu-id="776b9-293">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="776b9-294">Anforderung-Antwort- und unidirektionaler, nicht adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="776b9-294">Request-Reply and One-Way, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="776b9-295">Bindung</span><span class="sxs-lookup"><span data-stu-id="776b9-295">Binding</span></span>

<span data-ttu-id="776b9-296">WCF stellt einen unidirektionalen und Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="776b9-296">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="776b9-297">WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten vom Initiator an den Beantworter und HTTP-Antworten zur Übertragung aller Nachrichten vom Beantworter an den Initiator.</span><span class="sxs-lookup"><span data-stu-id="776b9-297">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="776b9-298">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-298">CreateSequence Exchange</span></span>

<span data-ttu-id="776b9-299">Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht mit einer `Offer` -Element in einer HTTP-Anforderung und erwartet, dass die `CreateSequenceResponse` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-299">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="776b9-300">Der WCF-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht mit einer `Accept` Element, für die HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-300">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="776b9-301">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="776b9-301">One-way Message</span></span>

<span data-ttu-id="776b9-302">Um einen unidirektionalen Nachrichtenaustausch erfolgreich abgeschlossen haben, den WCF-Initiator eine anforderungssequenznachricht in der HTTP-Anforderung sendet und empfängt eine eigenständige `SequenceAcknowledgement` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-302">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="776b9-303">Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.</span><span class="sxs-lookup"><span data-stu-id="776b9-303">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="776b9-304">Der WCF-Beantworter kann mit einer Bestätigung, einem Fehler oder eine Antwort mit leerem Textbereich und dem HTTP 202-Statuscode auf die Anforderung antworten.</span><span class="sxs-lookup"><span data-stu-id="776b9-304">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="776b9-305">Bidirektionale Nachrichten</span><span class="sxs-lookup"><span data-stu-id="776b9-305">Two Way Messages</span></span>

<span data-ttu-id="776b9-306">Um eine zwei-Wege-Nachrichtenaustauschprotokoll erfolgreich abgeschlossen haben, den WCF-Initiator eine anforderungssequenznachricht in der HTTP-Anforderung sendet und empfängt eine antwortsequenznachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-306">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="776b9-307">Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.</span><span class="sxs-lookup"><span data-stu-id="776b9-307">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="776b9-308">Der WCF-Beantworter antwortet möglicherweise auf die Anforderung mit einer Anwendungsantwort, einem Fehler oder eine Antwort mit leerem Textbereich und dem HTTP 202-Statuscode.</span><span class="sxs-lookup"><span data-stu-id="776b9-308">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="776b9-309">Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.</span><span class="sxs-lookup"><span data-stu-id="776b9-309">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="776b9-310">Wiederholen von Antworten</span><span class="sxs-lookup"><span data-stu-id="776b9-310">Retrying Replies</span></span>

<span data-ttu-id="776b9-311">WCF basiert auf HTTP-Anforderung-Antwort-Korrelation für bidirektionale Nachrichtenaustauschprotokoll.</span><span class="sxs-lookup"><span data-stu-id="776b9-311">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="776b9-312">Aus diesem Grund der WCF-Initiator wird nicht beendet eine anforderungssequenznachricht wiederholen, wenn die anforderungssequenznachricht bestätigt wird, aber stattdessen bei die HTTP-Antwort enthält einen `SequenceAcknowledgement`, Anwendungsantwort oder einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="776b9-312">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="776b9-313">Der WCF-Beantworter wiederholt die Antworten auf die HTTP-Antwort der Anforderung mit der die Antwort korreliert ist.</span><span class="sxs-lookup"><span data-stu-id="776b9-313">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="776b9-314">CloseSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-314">CloseSequence Exchange</span></span>

<span data-ttu-id="776b9-315">Nach dem Empfang aller Antwortsequenznachrichten und Bestätigungen für alle unidirektionalen anforderungssequenznachrichten, die WCF--Initiator überträgt eine `CloseSequence` -Nachricht für die anforderungssequenz in einer HTTP-Anforderung und erwartet die `CloseSequenceResponse` auf die HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-315">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="776b9-316">Durch Schließen der Anforderungssequenz wird die Antwortsequenz implizit geschlossen.</span><span class="sxs-lookup"><span data-stu-id="776b9-316">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="776b9-317">Dies bedeutet, dass der Initiator WCF umfasst der Antwortsequenz endgültige `SequenceAcknowledgement` auf die `CloseSequence` Nachricht und die Antwortsequenz verfügt nicht über eine `CloseSequence` Exchange.</span><span class="sxs-lookup"><span data-stu-id="776b9-317">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>

<span data-ttu-id="776b9-318">Der WCF-Beantworter stellt sicher, alle Antworten bestätigt werden, und überträgt die `CloseSequenceResponse` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-318">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="776b9-319">TerminateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-319">TerminateSequence Exchange</span></span>

<span data-ttu-id="776b9-320">Nach dem Empfang der `CloseSequenceResponse` Nachricht, die WCF--Initiator überträgt eine `TerminateSequence` -Nachricht für die anforderungssequenz in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse` auf die HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-320">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="776b9-321">Wie beim `CloseSequence`-Austausch wird durch Beendigung der Anforderungssequenz die Antwortsequenz implizit beendet.</span><span class="sxs-lookup"><span data-stu-id="776b9-321">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="776b9-322">Dies bedeutet, dass der Initiator WCF umfasst der Antwortsequenz endgültige `SequenceAcknowledgement` auf die `TerminateSequence` Nachricht und die Antwortsequenz verfügt nicht über eine `TerminateSequence` Exchange.</span><span class="sxs-lookup"><span data-stu-id="776b9-322">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>

<span data-ttu-id="776b9-323">Der WCF-Beantworter überträgt die `TerminateSequenceResponse` -Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="776b9-323">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="776b9-324">Adressierbarer Anforderung/Antwort-Initiator</span><span class="sxs-lookup"><span data-stu-id="776b9-324">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="776b9-325">Bindung</span><span class="sxs-lookup"><span data-stu-id="776b9-325">Binding</span></span>

<span data-ttu-id="776b9-326">WCF bietet ein Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="776b9-326">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="776b9-327">Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Duplex, Addressable`-Initiator kombinieren.</span><span class="sxs-lookup"><span data-stu-id="776b9-327">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="776b9-328">WCF verwendet die HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="776b9-328">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="776b9-329">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&amp;#160;202.</span><span class="sxs-lookup"><span data-stu-id="776b9-329">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="776b9-330">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="776b9-330">CreateSequence Exchange</span></span>

<span data-ttu-id="776b9-331">Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht mit einer `Offer` -Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="776b9-331">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="776b9-332">Der WCF-Beantworter stellt sicher, dass die `CreateSequence` verfügt über eine `Offer` Element dann erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht mit einer `Accept` Element.</span><span class="sxs-lookup"><span data-stu-id="776b9-332">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="776b9-333">Anforderung/Antwort-Korrelation</span><span class="sxs-lookup"><span data-stu-id="776b9-333">Request/Reply Correlation</span></span>

<span data-ttu-id="776b9-334">Folgendes gilt für alle korrelierenden Anforderungen und Antworten:</span><span class="sxs-lookup"><span data-stu-id="776b9-334">The following applies to all correlated requests and replies:</span></span>

- <span data-ttu-id="776b9-335">WCF stellt sicher, alle anwendungsanforderungsnachrichten eine `ReplyTo` -Endpunktverweis und eine `MessageId`.</span><span class="sxs-lookup"><span data-stu-id="776b9-335">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>

- <span data-ttu-id="776b9-336">WCF wendet den lokalen Endpunktverweis als jede anwendungsanforderungsnachricht an `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="776b9-336">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="776b9-337">Der lokale Endpunktverweis ist der `CreateSequence`-Verweis der `ReplyTo`-Nachricht für den Initiator und der `CreateSequence`-Verweis der `To`-Nachricht für den Beantworter.</span><span class="sxs-lookup"><span data-stu-id="776b9-337">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>

- <span data-ttu-id="776b9-338">WCF wird sichergestellt, dass eingehende Anforderungsnachrichten beachten einer `MessageId` und `ReplyTo`.</span><span class="sxs-lookup"><span data-stu-id="776b9-338">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>

- <span data-ttu-id="776b9-339">WCF stellt sicher die `ReplyTo` -Endpunktverweises aller anwendungsanforderungsnachrichten URI mit den lokalen Endpunktverweis übereinstimmen, wie weiter oben definiert.</span><span class="sxs-lookup"><span data-stu-id="776b9-339">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>

- <span data-ttu-id="776b9-340">WCF wird sichergestellt, dass alle Antworten den richtigen tragen `RelatesTo` und `To` -Header gemäß `wsa` Anforderung/Antwort-Korrelationsregeln.</span><span class="sxs-lookup"><span data-stu-id="776b9-340">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
