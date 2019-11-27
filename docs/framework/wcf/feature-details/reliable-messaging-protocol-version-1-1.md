---
title: Zuverlässiges Messaging-Protokoll, Version 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 9320787317131f42c4a82c6114a16fdea87567f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283308"
---
# <a name="reliable-messaging-protocol-version-11"></a><span data-ttu-id="cddfa-102">Zuverlässiges Messaging-Protokoll, Version 1,1</span><span class="sxs-lookup"><span data-stu-id="cddfa-102">Reliable Messaging Protocol version 1.1</span></span>

<span data-ttu-id="cddfa-103">Dieses Thema behandelt Windows Communication Foundation (WCF)-Implementierungsdetails für das WS-ReliableMessaging-Protokoll vom Februar 2007 (Version 1,1), das für die Interoperation mithilfe des http-Transports erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cddfa-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-ReliableMessaging February 2007 (version 1.1) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="cddfa-104">WCF befolgt die WS-ReliableMessaging-Spezifikation mit den in diesem Thema erläuterten Einschränkungen und Erläuterungen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-104">WCF follows the WS-ReliableMessaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="cddfa-105">Beachten Sie, dass das WS-ReliableMessaging-Protokoll, Version 1,1, ab .NET Framework 3,5 implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="cddfa-105">Note that the WS-ReliableMessaging version 1.1 protocol is implemented starting with .NET Framework 3.5.</span></span>

<span data-ttu-id="cddfa-106">Das WS-ReliableMessaging-Protokoll vom Februar 2007 wird vom <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>in WCF implementiert.</span><span class="sxs-lookup"><span data-stu-id="cddfa-106">The WS-ReliableMessaging February 2007 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="cddfa-107">Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="cddfa-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="cddfa-108">Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert</span><span class="sxs-lookup"><span data-stu-id="cddfa-108">Initiator: The client that initiates WS-Reliable Message sequence creation.</span></span>

- <span data-ttu-id="cddfa-109">Beantworter: der Dienst, der die Anforderungen des Initiators empfängt</span><span class="sxs-lookup"><span data-stu-id="cddfa-109">Responder: The service that receives the initiator's requests.</span></span>

 <span data-ttu-id="cddfa-110">In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.</span><span class="sxs-lookup"><span data-stu-id="cddfa-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="cddfa-111">Präfix</span><span class="sxs-lookup"><span data-stu-id="cddfa-111">Prefix</span></span>|<span data-ttu-id="cddfa-112">Namespace</span><span class="sxs-lookup"><span data-stu-id="cddfa-112">Namespace</span></span>|
|-|-|
|<span data-ttu-id="cddfa-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="cddfa-113">wsrm</span></span>|http://docs.oasis-open.org/ws-rx/wsrm/200702|
|<span data-ttu-id="cddfa-114">netrm</span><span class="sxs-lookup"><span data-stu-id="cddfa-114">netrm</span></span>|http://schemas.microsoft.com/ws/2006/05/rm|
|<span data-ttu-id="cddfa-115">s</span><span class="sxs-lookup"><span data-stu-id="cddfa-115">s</span></span>|http://www.w3.org/2003/05/soap-envelope|
|<span data-ttu-id="cddfa-116">wsa</span><span class="sxs-lookup"><span data-stu-id="cddfa-116">wsa</span></span>|http://schemas.xmlsoap.org/ws/2005/08/addressing|
|<span data-ttu-id="cddfa-117">wsse</span><span class="sxs-lookup"><span data-stu-id="cddfa-117">wsse</span></span>|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|
|<span data-ttu-id="cddfa-118">wsrmp</span><span class="sxs-lookup"><span data-stu-id="cddfa-118">wsrmp</span></span>|http://docs.oasis-open.org/ws-rx/wsrmp/200702|
|<span data-ttu-id="cddfa-119">netrmp</span><span class="sxs-lookup"><span data-stu-id="cddfa-119">netrmp</span></span>|http://schemas.microsoft.com/ws-rx/wsrmp/200702|
|<span data-ttu-id="cddfa-120">wsp</span><span class="sxs-lookup"><span data-stu-id="cddfa-120">wsp</span></span>|<span data-ttu-id="cddfa-121">(Entweder WS-Policy&#160;1.2 oder WS-Policy&#160;1.5)</span><span class="sxs-lookup"><span data-stu-id="cddfa-121">(Either WS-Policy 1.2 or WS-Policy 1.5)</span></span>|

## <a name="messaging"></a><span data-ttu-id="cddfa-122">Messaging</span><span class="sxs-lookup"><span data-stu-id="cddfa-122">Messaging</span></span>

### <a name="sequence-creation"></a><span data-ttu-id="cddfa-123">Sequenzerstellung</span><span class="sxs-lookup"><span data-stu-id="cddfa-123">Sequence Creation</span></span>

<span data-ttu-id="cddfa-124">WCF implementiert `CreateSequence` und `CreateSequenceResponse` Nachrichten, um eine zuverlässige Messaging Sequenz einzurichten.</span><span class="sxs-lookup"><span data-stu-id="cddfa-124">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable messaging sequence.</span></span> <span data-ttu-id="cddfa-125">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="cddfa-125">The following constraints apply:</span></span>

- <span data-ttu-id="cddfa-126">B1101: der WCF-Initiator verwendet denselben Endpunkt Verweis wie die `ReplyTo`, `AcksTo` und `Offer/Endpoint`der `CreateSequence` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cddfa-126">B1101: The WCF Initiator uses the same endpoint reference as the `CreateSequence` message’s `ReplyTo`, `AcksTo` and `Offer/Endpoint`.</span></span>

- <span data-ttu-id="cddfa-127">R1102: Die `AcksTo`-, `ReplyTo`- und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen über Adresswerte mit identischen Zeichenfolgendarstellungen verfügen, die sich oktettweise entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-127">R1102: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message must have address values with identical string representations such that they match the octet-wise.</span></span>

  - <span data-ttu-id="cddfa-128">Der WCF-Responder überprüft, ob der URI-Teil der `AcksTo`, `ReplyTo` und `Endpoint` Endpunkt Verweise identisch sind, bevor eine Sequenz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="cddfa-128">The WCF Responder verifies that the URI portion of the `AcksTo`, `ReplyTo` and `Endpoint` endpoint references are identical before creating a sequence.</span></span>

- <span data-ttu-id="cddfa-129">R1103: Die `AcksTo`- und `ReplyTo` und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen den gleichen Satz an Verweisparametern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-129">R1103: The `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references in the `CreateSequence` message should have the same set of reference parameters.</span></span>

  - <span data-ttu-id="cddfa-130">WCF erzwingt nicht, sondern geht davon aus, dass Verweis Parameter der `AcksTo`, `ReplyTo` und `Offer/Endpoint` Endpunkt Verweise auf `CreateSequence` identisch sind, und verwendet Verweis Parameter aus dem `ReplyTo` Endpunkt Verweis für Bestätigungen und umgekehrte Sequenz Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="cddfa-130">WCF does not enforce, but assumes that reference parameters of the `AcksTo`, `ReplyTo` and `Offer/Endpoint` endpoint references on `CreateSequence` are identical and uses reference parameters from the `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="cddfa-131">B1104: der WCF-Initiator generiert nicht den optionalen `Expires` oder `Offer/Expires` Element in der `CreateSequence` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cddfa-131">B1104: The WCF Initiator does not generate the optional `Expires` or `Offer/Expires` element in the `CreateSequence` message.</span></span>

- <span data-ttu-id="cddfa-132">B1105: beim Zugriff auf die `CreateSequence` Nachricht verwendet der WCF-Responder den `Expires`-Wert im `CreateSequence`-Element als `Expires` Wert im `CreateSequenceResponse` Element.</span><span class="sxs-lookup"><span data-stu-id="cddfa-132">B1105: When accessing the `CreateSequence` message, the WCF Responder uses the `Expires` value in the `CreateSequence` element as the `Expires` value in the `CreateSequenceResponse` element.</span></span> <span data-ttu-id="cddfa-133">Andernfalls liest und ignoriert der WCF-Responder die Werte `Expires` und `Offer/Expires`.</span><span class="sxs-lookup"><span data-stu-id="cddfa-133">Otherwise, the WCF Responder reads and ignores the `Expires` and `Offer/Expires` values.</span></span>

- <span data-ttu-id="cddfa-134">B1106: Wenn Sie auf die `CreateSequenceResponse` Nachricht zugreifen, liest der WCF-Initiator den optionalen `Expires` Wert, verwendet ihn aber nicht.</span><span class="sxs-lookup"><span data-stu-id="cddfa-134">B1106: When accessing the `CreateSequenceResponse` message, the WCF Initiator reads the optional `Expires` value but does not use it.</span></span>

- <span data-ttu-id="cddfa-135">B1107: der WCF-Initiator und der-Responder generieren immer das optionale `IncompleteSequenceBehavior`-Element in den Elementen `CreateSequence/Offer` und `CreateSequenceResponse`.</span><span class="sxs-lookup"><span data-stu-id="cddfa-135">B1107: The WCF Initiator and Responder always generate the optional `IncompleteSequenceBehavior` element in the `CreateSequence/Offer` and `CreateSequenceResponse` elements.</span></span>

- <span data-ttu-id="cddfa-136">B1108: WCF verwendet nur die Werte `DiscardFollowingFirstGap` und `NoDiscard` im `IncompleteSequenceBehavior`-Element.</span><span class="sxs-lookup"><span data-stu-id="cddfa-136">B1108: WCF uses only the `DiscardFollowingFirstGap` and `NoDiscard` values in the `IncompleteSequenceBehavior` element.</span></span>

  - <span data-ttu-id="cddfa-137">Zuverlässiges WS-Messaging verwendet den `Offer`-Mechanismus, um die beiden umgekehrt korrelierten Sequenzen einzurichten, die eine Sitzung bilden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-137">WS-ReliableMessaging utilizes the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="cddfa-138">B1109: Wenn `CreateSequence` ein `Offer`-Element enthält, lehnt der unidirektionale WCF-Responder die angebotene Sequenz ab, indem er mit einem `CreateSequenceResponse` ohne `Accept` Element antwortet.</span><span class="sxs-lookup"><span data-stu-id="cddfa-138">B1109: If `CreateSequence` contains an `Offer` element, the one way WCF Responder rejects the offered sequence by responding with a `CreateSequenceResponse` without an `Accept` element.</span></span>

- <span data-ttu-id="cddfa-139">B1110: Wenn ein zuverlässiger Messaging-Responder die angebotene Sequenz ablehnt, gibt der WCF-Initiator einen Fehler in der neu eingerichteten Sequenz aus.</span><span class="sxs-lookup"><span data-stu-id="cddfa-139">B1110: If a Reliable Messaging Responder rejects the offered sequence, the WCF Initiator faults the newly established sequence.</span></span>

- <span data-ttu-id="cddfa-140">B1111: Wenn `CreateSequence` kein `Offer`-Element enthält, lehnt der bidirektionale WCF-Responder die angebotene Sequenz ab, indem er mit einem `CreateSequenceRefused` Fehler antwortet.</span><span class="sxs-lookup"><span data-stu-id="cddfa-140">B1111: If `CreateSequence` does not contain an `Offer` element, the two-way WCF Responder rejects the offered sequence by responding with a `CreateSequenceRefused` fault.</span></span>

- <span data-ttu-id="cddfa-141">R1112: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, muss die `[address]`-Eigenschaft des `CreateSequenceResponse/Accept/AcksTo`-Endpunktverweises mit dem Ziel-URI der `CreateSequence`-Nachricht Byte für Byte übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-141">R1112: When two converse sequences are established using the `Offer` mechanism, the `[address]` property of the `CreateSequenceResponse/Accept/AcksTo` endpoint reference must match the destination URI of the `CreateSequence` message byte for byte.</span></span>

- <span data-ttu-id="cddfa-142">R1113: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, müssen alle Nachrichten in beiden Sequenzen, die vom Initiator an den Beantworter übermittelt werden, an den gleichen Endpunktverweis gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-142">R1113: When two converse sequences are established using the `Offer` mechanism, all messages on both sequences flowing from the Initiator to the Responder must be sent to the same endpoint reference.</span></span>

<span data-ttu-id="cddfa-143">WCF verwendet WS-ReliableMessaging, um zuverlässige Sitzungen zwischen dem Initiator und dem Beantworter einzurichten.</span><span class="sxs-lookup"><span data-stu-id="cddfa-143">WCF uses WS-ReliableMessaging to establish reliable sessions between the Initiator and the Responder.</span></span> <span data-ttu-id="cddfa-144">Die WCF WS-ReliableMessaging-Implementierung bietet eine zuverlässige Sitzung für unidirektionale, Anforderungs-Antwort-und vollständige Duplex Nachrichten Muster.</span><span class="sxs-lookup"><span data-stu-id="cddfa-144">The WCF WS-ReliableMessaging implementation provides a reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="cddfa-145">Der `Offer`-Mechanismus von zuverlässigem WS-Messaging für `CreateSequence` und `CreateSequenceResponse` ermöglicht es Ihnen, zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein für alle Nachrichtenendpunkte geeignetes Sitzungsprotokoll.</span><span class="sxs-lookup"><span data-stu-id="cddfa-145">The WS-ReliableMessaging `Offer` mechanism on `CreateSequence` and `CreateSequenceResponse` lets you establish two correlated converse sequences and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="cddfa-146">Da WCF eine Sicherheitsgarantie für eine solche Sitzung bietet, einschließlich End-to-End-Schutz für die Sitzungs Integrität, ist es praktisch sicherzustellen, dass die für dieselbe Partei vorgesehenen Nachrichten am gleichen Ziel ankommen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-146">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure that messages intended for the same party arrive at the same destination.</span></span> <span data-ttu-id="cddfa-147">Dadurch wird es zudem ermöglicht, Sequenzbestätigungen im Piggyback-Verfahren mit Anwendungsnachrichten zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="cddfa-147">This also allows "piggy-backing" of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="cddfa-148">Daher gelten die Einschränkungen R1102, R1112 und R1113 für WCF.</span><span class="sxs-lookup"><span data-stu-id="cddfa-148">Therefore, constraints R1102, R1112, and R1113 apply to WCF.</span></span>

<span data-ttu-id="cddfa-149">Ein Beispiel für eine `CreateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cddfa-149">An example of a `CreateSequence` message.</span></span>

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

<span data-ttu-id="cddfa-150">Ein Beispiel für eine `CreateSequenceResponse`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cddfa-150">An example of a `CreateSequenceResponse` message.</span></span>

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

### <a name="closing-a-sequence"></a><span data-ttu-id="cddfa-151">Schließen einer Sequenz</span><span class="sxs-lookup"><span data-stu-id="cddfa-151">Closing a Sequence</span></span>

<span data-ttu-id="cddfa-152">WCF verwendet die `CloseSequence` und `CloseSequenceResponse` Nachrichten für eine zuverlässige, von der Messaging Quelle initiierte Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="cddfa-152">WCF uses the `CloseSequence` and `CloseSequenceResponse` messages for a Reliable Messaging source-initiated shutdown.</span></span> <span data-ttu-id="cddfa-153">Das zuverlässige WCF-Messaging-Ziel initiiert das Herunterfahren nicht, und die zuverlässige WCF-Messaging-Quelle unterstützt kein zuverlässiges, von einem Messaging Ziel initiiertes Herunterfahren.</span><span class="sxs-lookup"><span data-stu-id="cddfa-153">The WCF Reliable Messaging destination does not initiate shutdown and the WCF Reliable Messaging source does not support a Reliable Messaging destination-initiated shutdown.</span></span> <span data-ttu-id="cddfa-154">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="cddfa-154">The following constraints apply:</span></span>

- <span data-ttu-id="cddfa-155">B1201: die Quelle für zuverlässiges WCF-Messaging sendet immer eine `CloseSequence` Nachricht, um die Sequenz zu schließen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-155">B1201: The WCF Reliable Messaging source always sends a `CloseSequence` message to shut down the sequence.</span></span>

- <span data-ttu-id="cddfa-156">B1202: Die zuverlässige Messaging-Quelle wartet auf die Bestätigung aller Sequenznachrichten, bevor sie die `CloseSequence`-Nachricht sendet.</span><span class="sxs-lookup"><span data-stu-id="cddfa-156">B1202: The Reliable Messaging source waits for acknowledgement of the full range of sequence messages before sending the `CloseSequence` message.</span></span>

- <span data-ttu-id="cddfa-157">B1203: Die zuverlässige Messaging-Quelle fügt immer das optionale `LastMsgNumber`-Element ein, es sei denn, die Sequenz enthält keine Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="cddfa-157">B1203: The Reliable Messaging source always includes the optional `LastMsgNumber` element unless the sequence does not contain messages.</span></span>

- <span data-ttu-id="cddfa-158">R1204: Das zuverlässige Messaging-Ziel darf das Schließen nicht durch Senden einer `CloseSequence`-Nachricht initiieren.</span><span class="sxs-lookup"><span data-stu-id="cddfa-158">R1204: The Reliable Messaging destination must not initiate shutdown by sending a `CloseSequence` message.</span></span>

- <span data-ttu-id="cddfa-159">B1205: nach dem Empfang einer `CloseSequence` Nachricht betrachtet die Quelle für zuverlässiges WCF-Messaging die Sequenz als unvollständig und sendet einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="cddfa-159">B1205: Upon receiving a `CloseSequence` message, the WCF Reliable Messaging source considers the sequence incomplete and sends a fault.</span></span>

 <span data-ttu-id="cddfa-160">Ein Beispiel für eine `CloseSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cddfa-160">An example of a `CloseSequence` message.</span></span>

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

<span data-ttu-id="cddfa-161">Beispiel `CloseSequenceResponse` Meldung:</span><span class="sxs-lookup"><span data-stu-id="cddfa-161">Example `CloseSequenceResponse` message:</span></span>

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

### <a name="sequence-termination"></a><span data-ttu-id="cddfa-162">Sequenzbeendigung</span><span class="sxs-lookup"><span data-stu-id="cddfa-162">Sequence Termination</span></span>

<span data-ttu-id="cddfa-163">WCF verwendet in erster Linie den `TerminateSequence/TerminateSequenceResponse` Handshake nach Abschluss des `CloseSequence/CloseSequenceResponse` Handshakes.</span><span class="sxs-lookup"><span data-stu-id="cddfa-163">WCF primarily uses the `TerminateSequence/TerminateSequenceResponse` handshake after completing the `CloseSequence/CloseSequenceResponse` handshake.</span></span> <span data-ttu-id="cddfa-164">Das zuverlässige WCF-Messaging-Ziel löst keine Beendigung aus, und die zuverlässige Messaging Quelle unterstützt keine zuverlässige, von einem Messaging Ziel initiierte Beendigung.</span><span class="sxs-lookup"><span data-stu-id="cddfa-164">The WCF Reliable Messaging destination does not initiate termination and the Reliable Messaging source does not support a Reliable Messaging destination-initiated termination.</span></span> <span data-ttu-id="cddfa-165">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="cddfa-165">The following constraints apply:</span></span>

- <span data-ttu-id="cddfa-166">B1301: der WCF-Initiator sendet die `TerminateSequence` Nachricht nur nach dem erfolgreichen Abschluss des `CloseSequence/CloseSequenceResponse` Handshakes.</span><span class="sxs-lookup"><span data-stu-id="cddfa-166">B1301: The WCF Initiator only sends the `TerminateSequence` message after the successful completion of the `CloseSequence/CloseSequenceResponse` handshake.</span></span>

- <span data-ttu-id="cddfa-167">R1302: WCF überprüft, ob das `LastMsgNumber`-Element über alle `CloseSequence`-und `TerminateSequence`-Meldungen für eine bestimmte Sequenz hinweg konsistent ist.</span><span class="sxs-lookup"><span data-stu-id="cddfa-167">R1302: WCF validates that the `LastMsgNumber` element is consistent across all `CloseSequence` and `TerminateSequence` messages for a given sequence.</span></span> <span data-ttu-id="cddfa-168">Das bedeutet, dass `LastMsgNumber` entweder in keiner `CloseSequence`-Nachricht und keiner `TerminateSequence`-Nachricht vorhanden ist oder in allen `CloseSequence`-Nachrichten und `TerminateSequence`-Nachrichten vorhanden und identisch ist.</span><span class="sxs-lookup"><span data-stu-id="cddfa-168">This means that `LastMsgNumber` is either not present on all `CloseSequence` and `TerminateSequence` messages, or it is present and identical on all `CloseSequence` and `TerminateSequence` messages.</span></span>

- <span data-ttu-id="cddfa-169">B1303: Bei Empfang einer `TerminateSequence`-Nachricht nach dem `CloseSequence/CloseSequenceResponse`-Handshake antwortet das zuverlässige Messaging-Ziel mit einer `TerminateSequenceResponse`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cddfa-169">B1303: When receiving a `TerminateSequence` message after the `CloseSequence/CloseSequenceResponse` handshake, the Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="cddfa-170">Da die zuverlässige Messaging-Quelle die `TerminateSequence`-Nachricht erst nach Erhalt der letzten Bestätigung sendet, weiß das zuverlässige Messaging-Ziel mit Sicherheit, dass die Sequenz beendet ist, und fordert die Ressourcen unverzüglich zurück.</span><span class="sxs-lookup"><span data-stu-id="cddfa-170">Because the Reliable Messaging source has the final acknowledgement before sending the `TerminateSequence` message, the Reliable Messaging destination knows without doubt that the sequence ends, and reclaims resources immediately.</span></span>

- <span data-ttu-id="cddfa-171">B1304: beim Empfang einer `TerminateSequence` Nachricht vor dem `CloseSequence/CloseSequenceResponse` Hand Shake antwortet das zuverlässige WCF-Messaging-Ziel mit einer `TerminateSequenceResponse` Meldung.</span><span class="sxs-lookup"><span data-stu-id="cddfa-171">B1304: When receiving a `TerminateSequence` message prior to the `CloseSequence/CloseSequenceResponse` handshake, the WCF Reliable Messaging destination responds with a `TerminateSequenceResponse` message.</span></span> <span data-ttu-id="cddfa-172">Wenn das zuverlässige Messaging-Ziel ermittelt, dass die Sequenz keine Inkonsistenzen aufweist, wartet das zuverlässige Messaging-Ziel so lange, wie vom Anwendungsziel angegeben, bevor es die Ressourcen zurückverlangt, um es dem Client zu ermöglichen, die letzte Bestätigung zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-172">If the Reliable Messaging destination determines that there are no inconsistencies in the sequence, the Reliable Messaging destination waits for an application destination-specified time before reclaiming resources, to allow the client the chance to receive the final acknowledgement.</span></span> <span data-ttu-id="cddfa-173">Anderenfalls fordert das zuverlässige Messaging-Ziel die Ressourcen unverzüglich zurück und teilt dem Anwendungsziel mit, dass die Sequenz nicht ordnungsgemäß beendet wurde, indem es das `Faulted`-Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="cddfa-173">Otherwise, the Reliable Messaging destination reclaims resources immediately and indicates to the application destination that the sequence ends with doubt by raising the `Faulted` event.</span></span>

<span data-ttu-id="cddfa-174">Ein Beispiel für eine `TerminateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cddfa-174">An example of a `TerminateSequence` message.</span></span>

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

<span data-ttu-id="cddfa-175">Beispiel `TerminateSequenceResponse` Meldung:</span><span class="sxs-lookup"><span data-stu-id="cddfa-175">Example `TerminateSequenceResponse` message:</span></span>

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

### <a name="sequences"></a><span data-ttu-id="cddfa-176">Sequenzen</span><span class="sxs-lookup"><span data-stu-id="cddfa-176">Sequences</span></span>

<span data-ttu-id="cddfa-177">Die folgende Liste enthält die Einschränkungen, die für Sequenzen gelten:</span><span class="sxs-lookup"><span data-stu-id="cddfa-177">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="cddfa-178">B1401: WCF generiert 9223372036854775807 die Sequenz `xs:long`Nummern und greift auf Sie zu</span><span class="sxs-lookup"><span data-stu-id="cddfa-178">B1401:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

<span data-ttu-id="cddfa-179">Ein Beispiel für einen `Sequence`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-179">An example of a `Sequence` header.</span></span>

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a><span data-ttu-id="cddfa-180">Anfordern einer Bestätigung</span><span class="sxs-lookup"><span data-stu-id="cddfa-180">Request Acknowledgement</span></span>

<span data-ttu-id="cddfa-181">WCF verwendet den `AckRequested`-Header als Keep-Alive-Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="cddfa-181">WCF uses the `AckRequested` header as a keep-alive mechanism.</span></span>

<span data-ttu-id="cddfa-182">Ein Beispiel für einen `AckRequested`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-182">An example of an `AckRequested` header.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a><span data-ttu-id="cddfa-183">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="cddfa-183">SequenceAcknowledgement</span></span>

<span data-ttu-id="cddfa-184">WCF verwendet einen "Piggy-back"-Mechanismus für Sequenz Bestätigungen, die im zuverlässigen WS-Messaging bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-184">WCF uses a "piggy-back" mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span> <span data-ttu-id="cddfa-185">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="cddfa-185">The following constraints apply:</span></span>

- <span data-ttu-id="cddfa-186">R1601: Wenn mithilfe des `Offer` Mechanismus zwei umgekehrte Sequenzen eingerichtet werden, kann der `SequenceAcknowledgement` Header in jeder Anwendungs Nachricht enthalten sein, die an den beabsichtigten Empfänger übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="cddfa-186">R1601: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span> <span data-ttu-id="cddfa-187">Der Remoteendpunkt muss in der Lage sein, auf einen per Piggyback-Verfahren gesendeten `SequenceAcknowledgement`-Header zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-187">The remote endpoint must be able to access a piggybacked `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="cddfa-188">B1602: WCF generiert keine `SequenceAcknowledgement` Header, die `Nack` Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="cddfa-188">B1602: WCF does not generate `SequenceAcknowledgement` headers that contain `Nack` elements.</span></span> <span data-ttu-id="cddfa-189">WCF überprüft, ob jedes `Nack` Element eine Sequenznummer enthält, ignoriert jedoch das `Nack` Element und den Wert.</span><span class="sxs-lookup"><span data-stu-id="cddfa-189">WCF validates that each `Nack` element contains a sequence number, but otherwise ignores the `Nack` element and value.</span></span>

 <span data-ttu-id="cddfa-190">Ein Beispiel für einen `SequenceAcknowledgement`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-190">An example of a `SequenceAcknowledgement` header.</span></span>

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="cddfa-191">WS-ReliableMessaging-Fehler</span><span class="sxs-lookup"><span data-stu-id="cddfa-191">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="cddfa-192">Im folgenden finden Sie eine Liste der Einschränkungen, die für die WCF-Implementierung von WS-ReliableMessaging-Fehlern gelten.</span><span class="sxs-lookup"><span data-stu-id="cddfa-192">The following is a list of constraints that apply to the WCF implementation of WS-ReliableMessaging faults.</span></span> <span data-ttu-id="cddfa-193">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="cddfa-193">The following constraints apply:</span></span>

- <span data-ttu-id="cddfa-194">B1701: WCF generiert keine `MessageNumberRollover` Fehler.</span><span class="sxs-lookup"><span data-stu-id="cddfa-194">B1701: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="cddfa-195">B1702: Wenn der Dienst Endpunkt über SOAP 1,2 das Verbindungs Limit erreicht und keine neuen Verbindungen verarbeiten kann, generiert WCF einen `CreateSequenceRefused` Fehlersubcode `netrm:ConnectionLimitReached`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cddfa-195">B1702: Over SOAP 1.2, when the service endpoint reaches its connection limit and cannot process new connections, WCF generates a nested `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

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

### <a name="ws-addressing-faults"></a><span data-ttu-id="cddfa-196">WS-Adressierungsfehler</span><span class="sxs-lookup"><span data-stu-id="cddfa-196">WS-Addressing Faults</span></span>

<span data-ttu-id="cddfa-197">Da WS-ReliableMessaging WS-Adressierung verwendet, kann die WCF WS-ReliableMessaging-Implementierung WS-Adressierungs Fehler generieren und übertragen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-197">Because WS-ReliableMessaging uses WS-Addressing, the WCF WS-ReliableMessaging implementation may generate and transmit WS-Addressing faults.</span></span> <span data-ttu-id="cddfa-198">In diesem Abschnitt werden die WS-Adressierungs Fehler behandelt, die von WCF explizit auf der WS-ReliableMessaging-Ebene generiert und übermittelt werden:</span><span class="sxs-lookup"><span data-stu-id="cddfa-198">This section covers the WS-Addressing faults that WCF explicitly generates and transmits at the WS-ReliableMessaging layer:</span></span>

- <span data-ttu-id="cddfa-199">B1801: WCF generiert und überträgt den `Message Addressing Header Required` Fault, wenn einer der folgenden Punkte zutrifft:</span><span class="sxs-lookup"><span data-stu-id="cddfa-199">B1801:WCF generates and transmits the `Message Addressing Header Required` fault when one of the following is true:</span></span>

  - <span data-ttu-id="cddfa-200">Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `MessageId`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-200">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="cddfa-201">Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `ReplyTo`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-201">A `CreateSequence`, `CloseSequence` or `TerminateSequence` message is missing a `ReplyTo` header.</span></span>

  - <span data-ttu-id="cddfa-202">Bei einer Nachricht vom Typ `CreateSequenceResponse`, `CloseSequenceResponse` oder `TerminateSequenceResponse` fehlt ein `RelatesTo`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-202">A `CreateSequenceResponse`, `CloseSequenceResponse`, or `TerminateSequenceResponse` message is missing a `RelatesTo` header.</span></span>

- <span data-ttu-id="cddfa-203">B1802: WCF generiert und überträgt den `Endpoint Unavailable` Fault, um anzugeben, dass kein Endpunkt lauscht, der die Sequenz auf der Grundlage der Untersuchung der Adressierungs Header in der `CreateSequence` Nachricht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="cddfa-203">B1802:WCF generates and transmits the `Endpoint Unavailable` fault to indicate there is no endpoint listening that can process the sequence based on examination of the addressing headers in the `CreateSequence` message.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="cddfa-204">Protokollkomposition</span><span class="sxs-lookup"><span data-stu-id="cddfa-204">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="cddfa-205">Komposition mit WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="cddfa-205">Composition with WS-Addressing</span></span>

<span data-ttu-id="cddfa-206">WCF unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung 2004/08 [ws-addr] und W3C WS-Adressierung 1,0 Empfehlungen [ws-addr-core] und [ws-addr-SOAP].</span><span class="sxs-lookup"><span data-stu-id="cddfa-206">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="cddfa-207">Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die Verwendung der WS-Adressierung nicht auf diese Version ein.</span><span class="sxs-lookup"><span data-stu-id="cddfa-207">While the WS-ReliableMessaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="cddfa-208">Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="cddfa-208">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="cddfa-209">R2101: Sowohl WS-Adressierung&#160;2004/08 als auch WS-Adressierung&#160;1.0 können mit zuverlässigem WS-Messaging verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-209">R2101: Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="cddfa-210">R2102: Für eine gegebene WS-ReliableMessaging-Sequenz oder ein Paar umgekehrter Sequenzen, die mithilfe des `Offer`-Mechanismus korreliert wurden, darf nur eine Version der WS-Adressierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-210">R2102: A single version of WS-Addressing must be used throughout a given WS-ReliableMessaging sequence or a pair of converse sequences correlated by using the `Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="cddfa-211">Komposition mit SOAP</span><span class="sxs-lookup"><span data-stu-id="cddfa-211">Composition with SOAP</span></span>

<span data-ttu-id="cddfa-212">WCF unterstützt die Verwendung von SOAP 1,1 und SOAP 1,2 mit zuverlässigem WS-Messaging.</span><span class="sxs-lookup"><span data-stu-id="cddfa-212">WCF supports the use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="cddfa-213">Komposition mit WS-Sicherheit und WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="cddfa-213">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="cddfa-214">WCF bietet Schutz für WS-ReliableMessaging-Sequenzen mithilfe von Secure Transport (HTTPS), Komposition mit WS-Sicherheit und Komposition mit WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="cddfa-214">WCF provides protection for WS-ReliableMessaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="cddfa-215">Das WS-ReliableMessaging&#160;1.1-Protokoll, das WS-Security&#160;1.1- und das WS-Secure Conversation&#160;1.3-Protokoll sollten zusammen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-215">The WS-ReliableMessaging 1.1 protocol, WS-Security 1.1 and WS-Secure Conversation 1.3 protocol should be used together.</span></span> <span data-ttu-id="cddfa-216">Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="cddfa-216">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="cddfa-217">R2301: um die Integrität einer WS-ReliableMessaging-Sequenz zusätzlich zur Integrität und Vertraulichkeit einzelner Nachrichten zu schützen, erfordert WCF, dass eine WS-Secure-Konversation verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="cddfa-217">R2301: To protect the integrity of a WS-ReliableMessaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="cddfa-218">R2302: Eine  WS-Secure Conversation-Sitzung muss vor der Erstellung von WS-ReliableMessaging-Sequenzen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-218">R2302:AWS-Secure Conversation session must be established prior to establishing WS-ReliableMessaging sequence(s).</span></span>

- <span data-ttu-id="cddfa-219">R2303: Wenn die Lebensdauer einer WS-ReliableMessaging-Sequenz die Lebensdauer der WS-SecureConversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-SecureConversationRenewal-Bindung erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-219">R2303: If the WS-ReliableMessaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="cddfa-220">B2304:Die WS-ReliableMessaging-Sequenz bzw. das Paar korrelierter umgekehrter Sequenzen ist immer an eine einzelne WS-SecureConversation-Sitzung gebunden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-220">B2304:WS-ReliableMessaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

- <span data-ttu-id="cddfa-221">R2305: Wenn die Zusammensetzung mit WS-Secure Conversation durchgeführt wird, erfordert der WCF-Beantworter, dass die `CreateSequence` Nachricht das `wsse:SecurityTokenReference`-Element und den `wsrm:UsesSequenceSTR`-Header enthält.</span><span class="sxs-lookup"><span data-stu-id="cddfa-221">R2305: When composed with WS-Secure Conversation, the WCF responder requires that the `CreateSequence` message contain the `wsse:SecurityTokenReference` element and the `wsrm:UsesSequenceSTR` header.</span></span>

 <span data-ttu-id="cddfa-222">Ein Beispiel für einen `UsesSequenceSTR`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-222">An example of a `UsesSequenceSTR` header.</span></span>

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a><span data-ttu-id="cddfa-223">Komposition mit SSL/TLS-Sitzungen</span><span class="sxs-lookup"><span data-stu-id="cddfa-223">Composition with SSL/TLS sessions</span></span>

<span data-ttu-id="cddfa-224">WCF unterstützt keine Komposition mit SSL/TLS-Sitzungen:</span><span class="sxs-lookup"><span data-stu-id="cddfa-224">WCF does not support composition with SSL/TLS sessions:</span></span>

- <span data-ttu-id="cddfa-225">B2401: WCF generiert nicht den `wsrm:UsesSequenceSSL`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-225">B2401: WCF does not generate the `wsrm:UsesSequenceSSL` header.</span></span>

- <span data-ttu-id="cddfa-226">R2402: ein zuverlässiger Messaging-Initiator darf keine `CreateSequence` Nachricht mit einem `wsrm:UsesSequenceSSL`-Header an einen WCF-Responder senden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-226">R2402: A Reliable Messaging Initiator must not send a `CreateSequence` message with a `wsrm:UsesSequenceSSL` header to a WCF Responder.</span></span>

### <a name="composition-with-ws-policy"></a><span data-ttu-id="cddfa-227">Komposition mit WS-Policy</span><span class="sxs-lookup"><span data-stu-id="cddfa-227">Composition with WS-Policy</span></span>

<span data-ttu-id="cddfa-228">WCF unterstützt zwei Versionen von WS-Policy: WS-Policy 1,2 und WS-Policy 1,5.</span><span class="sxs-lookup"><span data-stu-id="cddfa-228">WCF supports two versions of WS-Policy: WS-Policy 1.2 and WS-Policy 1.5.</span></span>

## <a name="ws-reliablemessaging-ws-policy-assertion"></a><span data-ttu-id="cddfa-229">WS-ReliableMessaging WS-Richtlinienassertion</span><span class="sxs-lookup"><span data-stu-id="cddfa-229">WS-ReliableMessaging WS-Policy Assertion</span></span>

<span data-ttu-id="cddfa-230">WCF verwendet WS-ReliableMessaging WS-Policy Assert `wsrm:RMAssertion`, um Endpunkte Funktionen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="cddfa-230">WCF uses WS-ReliableMessaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="cddfa-231">Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="cddfa-231">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="cddfa-232">B3001: WCF fügt `wsrmn:RMAssertion` WS-Policy-Assertionen an `wsdl:binding` Elemente an.</span><span class="sxs-lookup"><span data-stu-id="cddfa-232">B3001: WCF attaches `wsrmn:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="cddfa-233">WCF unterstützt sowohl Anhänge für `wsdl:binding`-als auch `wsdl:port`-Elemente.</span><span class="sxs-lookup"><span data-stu-id="cddfa-233">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="cddfa-234">B3002: WCF generiert niemals das `wsp:Optional`-Tag.</span><span class="sxs-lookup"><span data-stu-id="cddfa-234">B3002: WCF never generates the `wsp:Optional` tag.</span></span>

- <span data-ttu-id="cddfa-235">B3003: beim Zugriff auf die `wsrmp:RMAssertion` WS-Policy-Assertionen ignoriert WCF das `wsp:Optional`-Tag und behandelt die WS-RM-Richtlinie als obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="cddfa-235">B3003: When accessing the `wsrmp:RMAssertion` WS-Policy Assertion, WCF ignores the `wsp:Optional` tag and treats the WS-RM policy as mandatory.</span></span>

- <span data-ttu-id="cddfa-236">R3004: da WCF nicht mit SSL/TLS-Sitzungen verfasst wird, akzeptiert WCF keine Richtlinie, die `wsrmp:SequenceTransportSecurity`angibt.</span><span class="sxs-lookup"><span data-stu-id="cddfa-236">R3004: Because WCF does not compose with SSL/TLS sessions, WCF does not accept policy that specifies `wsrmp:SequenceTransportSecurity`.</span></span>

- <span data-ttu-id="cddfa-237">B3005: WCF generiert immer das `wsrmp:DeliveryAssurance` Element.</span><span class="sxs-lookup"><span data-stu-id="cddfa-237">B3005: WCF always generates the `wsrmp:DeliveryAssurance` element.</span></span>

- <span data-ttu-id="cddfa-238">B3006: WCF gibt immer die `wsrmp:ExactlyOnce` Zustellungs Assurance an.</span><span class="sxs-lookup"><span data-stu-id="cddfa-238">B3006: WCF always specifies the `wsrmp:ExactlyOnce` delivery assurance.</span></span>

- <span data-ttu-id="cddfa-239">B3007: WCF generiert und liest die folgenden Eigenschaften der WS-ReliableMessaging-Assertion und ermöglicht Ihnen die Steuerung über die WCF-`ReliableSessionBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="cddfa-239">B3007: WCF generates and reads the following properties of the WS-ReliableMessaging assertion and provides control over them on the WCF`ReliableSessionBindingElement`:</span></span>

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

  <span data-ttu-id="cddfa-240">Ein Beispiel für eine `RMAssertion`.</span><span class="sxs-lookup"><span data-stu-id="cddfa-240">An example of a `RMAssertion`.</span></span>

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

## <a name="flow-control-ws-reliablemessaging-extension"></a><span data-ttu-id="cddfa-241">WS-ReliableMessaging-Erweiterung zur Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="cddfa-241">Flow Control WS-ReliableMessaging Extension</span></span>

<span data-ttu-id="cddfa-242">WCF verwendet die WS-ReliableMessaging-Erweiterbarkeit, um eine optionale zusätzliche strengere Kontrolle über den Sequenz Nachrichtenfluss bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-242">WCF uses WS-ReliableMessaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="cddfa-243">Die Fluss Steuerung wird aktiviert, indem die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType>-Eigenschaft auf `true`festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="cddfa-243">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="cddfa-244">Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="cddfa-244">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="cddfa-245">B4001: Wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, generiert WCF in der Element Erweiterbarkeit des `SequenceAcknowledgement` Headers ein `netrm:BufferRemaining`-Element, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cddfa-245">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="cddfa-246">B4002: auch wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, erfordert WCF kein `netrm:BufferRemaining`-Element im `SequenceAcknowledgement`-Header.</span><span class="sxs-lookup"><span data-stu-id="cddfa-246">B4002: Even when Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element in the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="cddfa-247">B4003: das zuverlässige WCF-Messaging-Ziel verwendet `netrm:BufferRemaining`, um anzugeben, wie viele neue Nachrichten es Puffern kann.</span><span class="sxs-lookup"><span data-stu-id="cddfa-247">B4003: WCF Reliable Messaging Destination uses `netrm:BufferRemaining` to indicate how many new messages it can buffer.</span></span>

- <span data-ttu-id="cddfa-248">B4004: Wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, verwendet die zuverlässige WCF-Messaging Quelle den Wert von `netrm:BufferRemaining`, um die Nachrichtenübertragung zu drosseln.</span><span class="sxs-lookup"><span data-stu-id="cddfa-248">B4004:When Reliable Messaging Flow Control is enabled, the WCF Reliable Messaging Source uses the value of `netrm:BufferRemaining` to throttle message transmission.</span></span>

- <span data-ttu-id="cddfa-249">B4005: WCF generiert `netrm:BufferRemaining` ganzzahligen Werte zwischen 0 und 4096 einschließlich, und liest ganzzahlige Werte zwischen 0 und `xs:int`den `maxInclusive` Wert 214748364 einschließlich.</span><span class="sxs-lookup"><span data-stu-id="cddfa-249">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="cddfa-250">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="cddfa-250">Message Exchange Patterns</span></span>

<span data-ttu-id="cddfa-251">In diesem Abschnitt wird das Verhalten von WCF beschrieben, wenn WS-ReliableMessaging für verschiedene Nachrichtenaustausch Muster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cddfa-251">This section describes WCF's behavior when WS-ReliableMessaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="cddfa-252">Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:</span><span class="sxs-lookup"><span data-stu-id="cddfa-252">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="cddfa-253">Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall; der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-253">Non-Addressable Initiator: Initiator is behind a firewall; Responder can deliver messages to the Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="cddfa-254">Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-254">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="cddfa-255">Unidirektionaler, nicht adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="cddfa-255">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cddfa-256">Bindung</span><span class="sxs-lookup"><span data-stu-id="cddfa-256">Binding</span></span>

<span data-ttu-id="cddfa-257">WCF bietet ein unidirektionales Nachrichtenaustausch Muster unter Verwendung einer Sequenz über einen HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cddfa-257">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="cddfa-258">WCF verwendet HTTP-Anforderungen, um alle Nachrichten vom Initiator an den Beantworter zu übertragen, und HTTP-Antworten, um alle Nachrichten vom Responder an den Initiator zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-258">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cddfa-259">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-259">CreateSequence Exchange</span></span>

<span data-ttu-id="cddfa-260">Der WCF-Initiator überträgt eine `CreateSequence` Nachricht ohne `Offer`-Element in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-260">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="cddfa-261">Der WCF-Responder erstellt eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht ohne `Accept`-Element in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-261">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on the HTTP response.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="cddfa-262">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="cddfa-262">SequenceAcknowledgement</span></span>

<span data-ttu-id="cddfa-263">Der WCF-Initiator verarbeitet Bestätigungen für die Antwort aller Nachrichten mit Ausnahme der `CreateSequence` Nachricht und der Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-263">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="cddfa-264">Der WCF-Responder überträgt immer eine eigenständige Bestätigung der HTTP-Antwort an alle Sequenz-und `AckRequested` Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="cddfa-264">The WCF Responder always transmits a stand-alone acknowledgement on the HTTP response to all sequence and `AckRequested` messages.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="cddfa-265">CloseSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-265">CloseSequence Exchange</span></span>

<span data-ttu-id="cddfa-266">Der WCF-Initiator überträgt eine `CloseSequence` Nachricht in eine HTTP-Anforderung und erwartet die `CreateSequenceResponse` Meldung in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-266">The WCF Initiator transmits a `CloseSequence` message on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="cddfa-267">Der WCF-Responder überträgt die `CloseSequenceResponse` Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-267">The WCF Responder transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="cddfa-268">TerminateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-268">TerminateSequence Exchange</span></span>

<span data-ttu-id="cddfa-269">Der WCF-Initiator überträgt eine `TerminateSequence` Nachricht in eine HTTP-Anforderung und erwartet die `TerminateSequenceResponse` Meldung in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-269">The WCF Initiator transmits a `TerminateSequence` message on an HTTP request and expects the `TerminateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="cddfa-270">Der WCF-Responder überträgt die `TerminateSequenceResponse` Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-270">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="cddfa-271">Unidirektionaler, adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="cddfa-271">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cddfa-272">Bindung</span><span class="sxs-lookup"><span data-stu-id="cddfa-272">Binding</span></span>

<span data-ttu-id="cddfa-273">WCF bietet ein unidirektionales Nachrichtenaustausch Muster unter Verwendung einer Sequenz über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cddfa-273">WCF provides a one-way message exchange pattern using one sequence over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="cddfa-274">WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-274">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="cddfa-275">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="cddfa-275">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cddfa-276">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-276">CreateSequence Exchange</span></span>

<span data-ttu-id="cddfa-277">Der WCF-Initiator überträgt eine `CreateSequence` Nachricht ohne `Offer`-Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cddfa-277">The WCF Initiator transmits a `CreateSequence` message with no `Offer` element on an HTTP request.</span></span> <span data-ttu-id="cddfa-278">Der WCF-Responder erstellt eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht ohne `Accept`-Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cddfa-278">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with no `Accept` element on an HTTP request.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="cddfa-279">Adressierbarer Duplex-Initiator</span><span class="sxs-lookup"><span data-stu-id="cddfa-279">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cddfa-280">Bindung</span><span class="sxs-lookup"><span data-stu-id="cddfa-280">Binding</span></span>

<span data-ttu-id="cddfa-281">WCF bietet ein vollständig asynchrones bidirektionales Nachrichtenaustausch Muster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cddfa-281">WCF provides a fully-asynchronous, two-way message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="cddfa-282">Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Request/Reply`, `Addressable`-Initiator kombinieren.</span><span class="sxs-lookup"><span data-stu-id="cddfa-282">This message exchange pattern can be mixed with the `Request/Reply`, `Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="cddfa-283">WCF verwendet HTTP-Anforderungen, um alle Nachrichten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-283">WCF uses HTTP requests to transmit all messages.</span></span> <span data-ttu-id="cddfa-284">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="cddfa-284">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cddfa-285">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-285">CreateSequence Exchange</span></span>

<span data-ttu-id="cddfa-286">Der WCF-Initiator überträgt eine `CreateSequence` Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cddfa-286">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="cddfa-287">Der WCF-Responder stellt sicher, dass die `CreateSequence` über ein `Offer` Element verfügt, erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht mit einem `Accept` Element.</span><span class="sxs-lookup"><span data-stu-id="cddfa-287">The WCF Responder ensures that the `CreateSequence` has an `Offer` element, then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="cddfa-288">Sequenzlebensdauer</span><span class="sxs-lookup"><span data-stu-id="cddfa-288">Sequence Lifetime</span></span>

<span data-ttu-id="cddfa-289">WCF behandelt die beiden Sequenzen als eine Vollduplex Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cddfa-289">WCF treats the two sequences as one fully-duplex session.</span></span>

<span data-ttu-id="cddfa-290">Wenn Sie einen Fehler erzeugen, der eine Sequenz Fehler erzeugt, erwartet WCF, dass der Remote Endpunkt beide Sequenzen als fehlerhaft eingibt.</span><span class="sxs-lookup"><span data-stu-id="cddfa-290">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="cddfa-291">Beim Lesen eines Fehlers, bei dem ein Fehler auftritt, gibt WCF beide Sequenzen aus.</span><span class="sxs-lookup"><span data-stu-id="cddfa-291">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="cddfa-292">WCF kann seine ausgehende Sequenz schließen und die Verarbeitung von Nachrichten in der eingehenden Sequenz fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-292">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="cddfa-293">Umgekehrt kann WCF das Ende der eingehenden Sequenz verarbeiten und weiterhin Nachrichten in der ausgehenden Sequenz senden.</span><span class="sxs-lookup"><span data-stu-id="cddfa-293">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-and-one-way-non-addressable-initiator"></a><span data-ttu-id="cddfa-294">Anforderung-Antwort- und unidirektionaler, nicht adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="cddfa-294">Request-Reply and One-Way, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cddfa-295">Bindung</span><span class="sxs-lookup"><span data-stu-id="cddfa-295">Binding</span></span>

<span data-ttu-id="cddfa-296">WCF bietet ein unidirektionales Anforderungs-/Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cddfa-296">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="cddfa-297">WCF verwendet HTTP-Anforderungen, um alle Nachrichten vom Initiator an den Beantworter zu übertragen, und HTTP-Antworten, um alle Nachrichten vom Responder an den Initiator zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-297">WCF uses HTTP requests to transmit all messages from the Initiator to the Responder and HTTP responses to transmit all messages from the Responder to the Initiator.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cddfa-298">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-298">CreateSequence Exchange</span></span>

<span data-ttu-id="cddfa-299">Der WCF-Initiator überträgt eine `CreateSequence` Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-299">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request and expects the `CreateSequenceResponse` message on the HTTP response.</span></span> <span data-ttu-id="cddfa-300">Der WCF-Responder erstellt eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht mit einem `Accept`-Element in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-300">The WCF Responder creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element on the HTTP response.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="cddfa-301">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="cddfa-301">One-way Message</span></span>

<span data-ttu-id="cddfa-302">Um einen unidirektionalen Nachrichtenaustausch erfolgreich abzuschließen, überträgt der WCF-Initiator eine Anforderungs Sequenz Nachricht in der HTTP-Anforderung und empfängt eine eigenständige `SequenceAcknowledgement` Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-302">To complete a one-way message exchange successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="cddfa-303">Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-303">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="cddfa-304">Der WCF-Responder kann auf die Anforderung mit einer Bestätigung, einem Fehler oder einer Antwort mit leerem Text und HTTP 202-Statuscode Antworten.</span><span class="sxs-lookup"><span data-stu-id="cddfa-304">The WCF Responder may reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="cddfa-305">Bidirektionale Nachrichten</span><span class="sxs-lookup"><span data-stu-id="cddfa-305">Two Way Messages</span></span>

<span data-ttu-id="cddfa-306">Um ein bidirektionales Nachrichtenaustausch Protokoll erfolgreich abzuschließen, überträgt der WCF-Initiator eine Anforderungs Sequenz Nachricht in der HTTP-Anforderung und empfängt eine Antwort Sequenz Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-306">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="cddfa-307">Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.</span><span class="sxs-lookup"><span data-stu-id="cddfa-307">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="cddfa-308">Der WCF-Responder antwortet möglicherweise mit einer Anwendungs Antwort, einem Fehler oder einer Antwort mit leerem Text und HTTP 202-Statuscode auf die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cddfa-308">The WCF Responder may reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="cddfa-309">Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.</span><span class="sxs-lookup"><span data-stu-id="cddfa-309">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="cddfa-310">Wiederholen von Antworten</span><span class="sxs-lookup"><span data-stu-id="cddfa-310">Retrying Replies</span></span>

<span data-ttu-id="cddfa-311">WCF basiert auf einer HTTP-Anforderung-Antwort-Korrelation für die bidirektionale Nachrichtenaustausch-Protokoll Korrelation.</span><span class="sxs-lookup"><span data-stu-id="cddfa-311">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="cddfa-312">Aus diesem Grund beendet der WCF-Initiator den Wiederholungsversuch einer Anforderungs Sequenz Nachricht nicht, wenn die Anforderungs Sequenz Nachricht bestätigt wird, sondern wenn die HTTP-Antwort eine `SequenceAcknowledgement`, eine Anwendungs Antwort oder einen Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="cddfa-312">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries a `SequenceAcknowledgement`, application reply, or fault.</span></span> <span data-ttu-id="cddfa-313">Der WCF-Responder wiederholt Antworten auf die HTTP-Antwort der Anforderung, mit der die Antwort korreliert wird.</span><span class="sxs-lookup"><span data-stu-id="cddfa-313">The WCF Responder retries replies on the HTTP response of the request to which the reply is correlated.</span></span>

#### <a name="closesequence-exchange"></a><span data-ttu-id="cddfa-314">CloseSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-314">CloseSequence Exchange</span></span>

<span data-ttu-id="cddfa-315">Nachdem alle Antwort Sequenz Nachrichten und Bestätigungen für alle unidirektionalen Anforderungs Sequenz Nachrichten empfangen wurden, überträgt der WCF-Initiator eine `CloseSequence` Nachricht für die Anforderungs Sequenz in einer HTTP-Anforderung und erwartet die `CloseSequenceResponse` in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-315">After receiving all reply sequence messages and acknowledgements for all one way request sequence messages, the WCF Initiator transmits a `CloseSequence` message for the request sequence on an HTTP request and expects the `CloseSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="cddfa-316">Durch Schließen der Anforderungssequenz wird die Antwortsequenz implizit geschlossen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-316">Closing the request sequence implicitly closes the reply sequence.</span></span> <span data-ttu-id="cddfa-317">Dies bedeutet, dass der WCF-Initiator die endgültige `SequenceAcknowledgement` der Antwort Sequenz für die `CloseSequence` Nachricht enthält und dass die Antwort Sequenz keinen `CloseSequence` Exchange hat.</span><span class="sxs-lookup"><span data-stu-id="cddfa-317">This means the WCF Initiator includes the reply sequence’s Final `SequenceAcknowledgement` on the `CloseSequence` message and the reply sequence does not have a `CloseSequence` exchange.</span></span>

<span data-ttu-id="cddfa-318">Der WCF-Responder stellt sicher, dass alle Antworten bestätigt werden, und überträgt die `CloseSequenceResponse` Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-318">The WCF Responder ensures all replies are acknowledged and transmits the `CloseSequenceResponse` message on the HTTP response.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="cddfa-319">TerminateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-319">TerminateSequence Exchange</span></span>

<span data-ttu-id="cddfa-320">Nach dem Empfang der `CloseSequenceResponse` Nachricht überträgt der WCF-Initiator eine `TerminateSequence` Nachricht für die Anforderungs Sequenz in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse` in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-320">After receiving the `CloseSequenceResponse` message, the WCF Initiator transmits a `TerminateSequence` message for the request sequence on an HTTP request and expects the `TerminateSequenceResponse` on the HTTP response.</span></span>

<span data-ttu-id="cddfa-321">Wie beim `CloseSequence`-Austausch wird durch Beendigung der Anforderungssequenz die Antwortsequenz implizit beendet.</span><span class="sxs-lookup"><span data-stu-id="cddfa-321">Like the `CloseSequence` exchange, terminating the request sequence implicitly terminates the reply sequence.</span></span> <span data-ttu-id="cddfa-322">Dies bedeutet, dass der WCF-Initiator die endgültige `SequenceAcknowledgement` der Antwort Sequenz für die `TerminateSequence` Nachricht enthält und dass die Antwort Sequenz keinen `TerminateSequence` Exchange hat.</span><span class="sxs-lookup"><span data-stu-id="cddfa-322">This means the WCF Initiator includes the reply sequence’s final `SequenceAcknowledgement` on the `TerminateSequence` message and the reply sequence does not have a `TerminateSequence` exchange.</span></span>

<span data-ttu-id="cddfa-323">Der WCF-Responder überträgt die `TerminateSequenceResponse` Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cddfa-323">The WCF Responder transmits the `TerminateSequenceResponse` message on the HTTP response.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="cddfa-324">Adressierbarer Anforderung/Antwort-Initiator</span><span class="sxs-lookup"><span data-stu-id="cddfa-324">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cddfa-325">Bindung</span><span class="sxs-lookup"><span data-stu-id="cddfa-325">Binding</span></span>

<span data-ttu-id="cddfa-326">WCF bietet ein Anforderung-Antwort-Nachrichtenaustausch Muster mithilfe von zwei Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cddfa-326">WCF provides a request-reply message exchange pattern using two sequences over one inbound and one outbound HTTP channel.</span></span> <span data-ttu-id="cddfa-327">Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Duplex, Addressable`-Initiator kombinieren.</span><span class="sxs-lookup"><span data-stu-id="cddfa-327">This message exchange pattern can be mixed with the `Duplex, Addressable` Initiator message exchange pattern in a limited way.</span></span> <span data-ttu-id="cddfa-328">WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-328">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="cddfa-329">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="cddfa-329">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cddfa-330">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cddfa-330">CreateSequence Exchange</span></span>

<span data-ttu-id="cddfa-331">Der WCF-Initiator überträgt eine `CreateSequence` Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cddfa-331">The WCF Initiator transmits a `CreateSequence` message with an `Offer` element on an HTTP request.</span></span> <span data-ttu-id="cddfa-332">Der WCF-Responder stellt sicher, dass die `CreateSequence` über ein `Offer` Element verfügt, erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht mit einem `Accept` Element.</span><span class="sxs-lookup"><span data-stu-id="cddfa-332">The WCF Responder ensures that the `CreateSequence` has an `Offer` element then creates a sequence and transmits the `CreateSequenceResponse` message with an `Accept` element.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="cddfa-333">Anforderung/Antwort-Korrelation</span><span class="sxs-lookup"><span data-stu-id="cddfa-333">Request/Reply Correlation</span></span>

<span data-ttu-id="cddfa-334">Folgendes gilt für alle korrelierenden Anforderungen und Antworten:</span><span class="sxs-lookup"><span data-stu-id="cddfa-334">The following applies to all correlated requests and replies:</span></span>

- <span data-ttu-id="cddfa-335">WCF stellt sicher, dass alle Anwendungs Anforderungs Nachrichten einen `ReplyTo` Endpunkt Verweis und einen `MessageId`haben.</span><span class="sxs-lookup"><span data-stu-id="cddfa-335">WCF ensures all application request messages bear a `ReplyTo` endpoint reference and a `MessageId`.</span></span>

- <span data-ttu-id="cddfa-336">WCF wendet den lokalen Endpunkt Verweis an, wenn die `ReplyTo`der Anwendung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="cddfa-336">WCF applies the local endpoint reference as each application request message’s `ReplyTo`.</span></span> <span data-ttu-id="cddfa-337">Der lokale Endpunktverweis ist der `CreateSequence`-Verweis der `ReplyTo`-Nachricht für den Initiator und der `CreateSequence`-Verweis der `To`-Nachricht für den Beantworter.</span><span class="sxs-lookup"><span data-stu-id="cddfa-337">The local endpoint reference is the `CreateSequence` message’s `ReplyTo` for the Initiator and the `CreateSequence` message’s `To` for the Responder.</span></span>

- <span data-ttu-id="cddfa-338">WCF stellt sicher, dass eingehende Anforderungs Nachrichten eine `MessageId` und eine `ReplyTo`tragen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-338">WCF ensures that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span>

- <span data-ttu-id="cddfa-339">WCF stellt sicher, dass der URI des `ReplyTo` Endpunkt Verweises aller Anwendungs Anforderungs Nachrichten dem lokalen Endpunkt Verweis entspricht, wie zuvor definiert.</span><span class="sxs-lookup"><span data-stu-id="cddfa-339">WCF ensures the `ReplyTo` endpoint reference’s URI of all application request messages match the local endpoint reference as defined earlier.</span></span>

- <span data-ttu-id="cddfa-340">WCF stellt sicher, dass alle Antworten die richtigen `RelatesTo` und `To` Header nach `wsa` Anforderungs-/Antwort-Korrelations Regeln tragen.</span><span class="sxs-lookup"><span data-stu-id="cddfa-340">WCF ensures that all replies bear the correct `RelatesTo` and `To` headers following `wsa` request/reply correlation rules.</span></span>
