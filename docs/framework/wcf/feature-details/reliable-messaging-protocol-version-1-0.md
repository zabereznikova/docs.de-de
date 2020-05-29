---
title: Zuverlässiges Messaging-Protokoll, Version 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: 8d192afcffca52136d6d71de49770c5a5ad13895
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202302"
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="cee08-102">Zuverlässiges Messaging-Protokoll, Version 1.0</span><span class="sxs-lookup"><span data-stu-id="cee08-102">Reliable Messaging Protocol version 1.0</span></span>

<span data-ttu-id="cee08-103">Dieses Thema behandelt Windows Communication Foundation (WCF)-Implementierungsdetails für das WS-zuverlässige Messaging-Protokoll vom Februar 2005 (Version 1,0), das für die Interoperation mithilfe des http-Transports erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="cee08-103">This topic covers Windows Communication Foundation (WCF) implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> <span data-ttu-id="cee08-104">WCF befolgt die Spezifikation für zuverlässiges WS-Messaging mit den in diesem Thema erläuterten Einschränkungen und Erläuterungen.</span><span class="sxs-lookup"><span data-stu-id="cee08-104">WCF follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="cee08-105">Beachten Sie, dass das WS-ReliableMessaging-Protokoll, Version 1,0, ab dem WinFX implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="cee08-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the WinFX.</span></span>

<span data-ttu-id="cee08-106">Das WS-zuverlässiges Messaging-Protokoll vom Februar 2005 wird in WCF vom implementiert <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .</span><span class="sxs-lookup"><span data-stu-id="cee08-106">The WS-Reliable Messaging February 2005 protocol is implemented in WCF by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>

<span data-ttu-id="cee08-107">Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="cee08-107">For convenience, the topic uses the following roles:</span></span>

- <span data-ttu-id="cee08-108">Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert</span><span class="sxs-lookup"><span data-stu-id="cee08-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>

- <span data-ttu-id="cee08-109">Beantworter: der Dienst, der die Anforderungen des Initiators empfängt</span><span class="sxs-lookup"><span data-stu-id="cee08-109">Responder: the service that receives the initiator's requests</span></span>

<span data-ttu-id="cee08-110">In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.</span><span class="sxs-lookup"><span data-stu-id="cee08-110">This document uses the prefixes and namespaces in the following table.</span></span>

|<span data-ttu-id="cee08-111">Präfix</span><span class="sxs-lookup"><span data-stu-id="cee08-111">Prefix</span></span>|<span data-ttu-id="cee08-112">Namespace</span><span class="sxs-lookup"><span data-stu-id="cee08-112">Namespace</span></span>|
|------------|---------------|
|<span data-ttu-id="cee08-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="cee08-113">wsrm</span></span>|`http://schemas.xmlsoap.org/ws/2005/02/rm`|
|<span data-ttu-id="cee08-114">netrm</span><span class="sxs-lookup"><span data-stu-id="cee08-114">netrm</span></span>|`http://schemas.microsoft.com/ws/2006/05/rm`|
|<span data-ttu-id="cee08-115">s</span><span class="sxs-lookup"><span data-stu-id="cee08-115">s</span></span>|`http://www.w3.org/2003/05/soap-envelope`|
|<span data-ttu-id="cee08-116">wsa</span><span class="sxs-lookup"><span data-stu-id="cee08-116">wsa</span></span>|`http://schemas.xmlsoap.org/ws/2005/08/addressing`|
|<span data-ttu-id="cee08-117">wsse</span><span class="sxs-lookup"><span data-stu-id="cee08-117">wsse</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|

## <a name="messaging"></a><span data-ttu-id="cee08-118">Nachrichten</span><span class="sxs-lookup"><span data-stu-id="cee08-118">Messaging</span></span>

### <a name="sequence-establishment-messages"></a><span data-ttu-id="cee08-119">Sequenzeinrichtungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="cee08-119">Sequence Establishment Messages</span></span>

<span data-ttu-id="cee08-120">WCF implementiert `CreateSequence` -und- `CreateSequenceResponse` Nachrichten, um eine zuverlässige Nachrichten Sequenz einzurichten.</span><span class="sxs-lookup"><span data-stu-id="cee08-120">WCF implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="cee08-121">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="cee08-121">The following constraints apply:</span></span>

- <span data-ttu-id="cee08-122">B1101: der WCF-Initiator generiert das optionale abläuft-Element nicht in der `CreateSequence` Nachricht oder, wenn die `CreateSequence` Nachricht ein-Element enthält `Offer` , das optionale- `Expires` Element im- `Offer` Element.</span><span class="sxs-lookup"><span data-stu-id="cee08-122">B1101: The WCF Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>

- <span data-ttu-id="cee08-123">B1102: Wenn Sie auf die `CreateSequence` Nachricht zugreifen, `Responder` sendet und empfängt der WCF beide `Expires` Elemente, wenn Sie vorhanden sind, verwendet jedoch ihre Werte nicht.</span><span class="sxs-lookup"><span data-stu-id="cee08-123">B1102: When accessing the `CreateSequence` message, the WCF`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>

<span data-ttu-id="cee08-124">Zuverlässiges WS-Messaging führt den `Offer`-Mechanismus ein, um zwei umgekehrt korrelierende Sequenzen einzurichten, die eine Sitzung bilden.</span><span class="sxs-lookup"><span data-stu-id="cee08-124">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>

- <span data-ttu-id="cee08-125">R1103: Wenn `CreateSequence` ein `Offer`-Element enthält, muss der zuverlässige Messaging-Beantworter entweder die Sequenz akzeptieren und mit `CreateSequenceResponse` antworten (enthält ein `wsrm:Accept`-Element), wodurch die zwei umgekehrt korrelierenden Sequenzen gebildet werden, oder er muss die `CreateSequence`-Anforderung zurückweisen.</span><span class="sxs-lookup"><span data-stu-id="cee08-125">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>

- <span data-ttu-id="cee08-126">R1104: `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten müssen an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-126">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>

- <span data-ttu-id="cee08-127">R1105: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` müssen Adresswerte aufweisen, die sich oktettweise entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cee08-127">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>

  <span data-ttu-id="cee08-128">Der WCF-Responder überprüft, ob der URI-Teil des `AcksTo` -und des- `ReplyTo` EPRS vor dem Erstellen einer Sequenz identisch ist.</span><span class="sxs-lookup"><span data-stu-id="cee08-128">The WCF Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>

- <span data-ttu-id="cee08-129">R1106: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` sollten den gleichen Satz von Verweisparametern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cee08-129">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>

  <span data-ttu-id="cee08-130">WCF erzwingt nicht, sondern geht davon aus, dass [Verweis Parameter] von `AcksTo` und `ReplyTo` auf `CreateSequence` identisch sind und [Verweis Parameter] aus dem `ReplyTo` Endpunkt Verweis für Bestätigungen und umgekehrte Sequenz Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="cee08-130">WCF does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>

- <span data-ttu-id="cee08-131">R1107: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-131">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>

- <span data-ttu-id="cee08-132">R1108: Wenn mithilfe des Offer-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, muss die `[address]`-Eigenschaft des `wsrm:AcksTo`-Endpunktverweises, ein dem `wsrm:Accept`-Element von `CreateSequenceResponse` untergeordnetes Element, mit dem Ziel-URI von `CreateSequence` byteweise übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="cee08-132">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>

- <span data-ttu-id="cee08-133">R1109: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen die vom Initiator gesendeten Nachrichten und die vom Beantworter gesendeten Bestätigungen der Nachrichten an den gleichen Endpunktverweis gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-133">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>

  <span data-ttu-id="cee08-134">WCF verwendet zuverlässiges WS-Messaging, um zuverlässige Sitzungen zwischen dem Initiator und dem Beantworter einzurichten.</span><span class="sxs-lookup"><span data-stu-id="cee08-134">WCF uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="cee08-135">Die WS-zuverlässige WS-Messaging-Implementierung von WCF bietet eine zuverlässige Sitzung für unidirektionale, Anforderungs-Antwort-und vollständige Duplex Nachrichten Muster.</span><span class="sxs-lookup"><span data-stu-id="cee08-135">WCF's WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="cee08-136">Der zuverlässige WS-Messaging- `Offer` Mechanismus `CreateSequence` / `CreateSequenceResponse` ermöglicht Ihnen das Einrichten von zwei korrelierten umgekehrten Sequenzen und stellt ein Sitzungsprotokoll bereit, das für alle Nachrichten Endpunkte geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="cee08-136">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="cee08-137">Da WCF eine Sicherheitsgarantie für eine solche Sitzung bietet, einschließlich End-to-End-Schutz für die Sitzungs Integrität, ist es praktisch, sicherzustellen, dass Nachrichten, die für dieselbe Partei vorgesehen sind, am gleichen Ziel ankommen.</span><span class="sxs-lookup"><span data-stu-id="cee08-137">Because WCF provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="cee08-138">Dies lässt auch Piggyback-Übertragung von Sequenzbestätigungen auf Anwendungsnachrichten zu.</span><span class="sxs-lookup"><span data-stu-id="cee08-138">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="cee08-139">Daher gelten die Einschränkungen R1104, R1105 und R1108 für WCF.</span><span class="sxs-lookup"><span data-stu-id="cee08-139">Therefore, constraints R1104, R1105, and R1108 apply to WCF.</span></span>

<span data-ttu-id="cee08-140">Ein Beispiel für eine `CreateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cee08-140">An example of a `CreateSequence` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequence
    </a:Action>
    <a:ReplyTo>
      <a:Address>
         http://Business456.com/clientA
      </a:Address>
    </a:ReplyTo>
    <a:MessageID>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </a:MessageID>
    <a:To s:mustUnderstand="1">
      http://Business456.com/clientA
    </a:To>
  </s:Header>
  <s:Body>
    <wsrm:CreateSequence>
      <wsrm:AcksTo>
       <wsa:Address>
         http://Business456.com/clientA
       </wsa:Address>
     </wsrm:AcksTo>
     <wsrm:Offer>
      <wsrm:Identifier>
        urn:uuid:0afb8d36-bf26-4776-b8cf-8c91fddb5496
      </wsrm:Identifier>
     </wsrm:Offer>
   </wsrm:CreateSequence>
  </s:Body>
</s:Envelope>
```

 <span data-ttu-id="cee08-141">Ein Beispiel für eine `CreateSequenceResponse`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cee08-141">An example of a `CreateSequenceResponse` message.</span></span>

```xml
<s:Envelope>
  <s:Header>
    <a:Action s:mustUnderstand="1">
      http://schemas.xmlsoap.org/ws/2005/02/rm/CreateSequenceResponse
    </a:Action>
    <a:RelatesTo>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </a:RelatesTo>
    <a:To s:mustUnderstand="1">
      http://Business456.com/clientA
    </a:To>
  </s:Header>
  <s:Body>
   <wsrm:CreateSequenceResponse>
    <Identifier>
     urn:uuid:eea0a36c-b38a-43e8-8c76-2fabe2d76386
    </Identifier>
    <Accept>
    <AcksTo>
      <a:Address>
        http://BusinessABC.com/serviceA
      </a:Address>
    </AcksTo>
    </Accept>
   </wsrm:CreateSequenceResponse>
  </s:Body>
</s:Envelope>
```

### <a name="sequence"></a><span data-ttu-id="cee08-142">Sequenz</span><span class="sxs-lookup"><span data-stu-id="cee08-142">Sequence</span></span>

<span data-ttu-id="cee08-143">Die folgende Liste enthält die Einschränkungen, die für Sequenzen gelten:</span><span class="sxs-lookup"><span data-stu-id="cee08-143">The following is a list of constraints that apply to sequences:</span></span>

- <span data-ttu-id="cee08-144">B1201: WCF generiert und greift auf Sequenznummern zu `xs:long` , die nicht größer sind als der maximale inklusivwert, 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="cee08-144">B1201:WCF generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>

- <span data-ttu-id="cee08-145">B1202: WCF generiert immer eine letzte leere Nachricht mit dem Aktions-URI von `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .</span><span class="sxs-lookup"><span data-stu-id="cee08-145">B1202:WCF always generates an empty-bodied last message with the action URI of `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>

- <span data-ttu-id="cee08-146">B1203: WCF empfängt und übermittelt eine Nachricht mit einem Sequenz Header, der ein-Element enthält, solange `LastMessage` der Aktions-URI nicht ist `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .</span><span class="sxs-lookup"><span data-stu-id="cee08-146">B1203: WCF receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.</span></span>

<span data-ttu-id="cee08-147">Ein Beispiel für einen Sequenzheader.</span><span class="sxs-lookup"><span data-stu-id="cee08-147">An example of a Sequence Header.</span></span>

```xml
<wsrm:Sequence>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
  <wsrm:MessageNumber>
    10
  </wsrm:MessageNumber>
  <wsrm:LastMessage/>
 </wsrm:Sequence>
```

### <a name="ackrequested-header"></a><span data-ttu-id="cee08-148">AckRequested-Header</span><span class="sxs-lookup"><span data-stu-id="cee08-148">AckRequested Header</span></span>

<span data-ttu-id="cee08-149">WCF verwendet den `AckRequested` -Header als Keep-Alive-Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="cee08-149">WCF uses `AckRequested` Header as a keep-alive mechanism.</span></span> <span data-ttu-id="cee08-150">WCF generiert nicht das optionale- `MessageNumber` Element.</span><span class="sxs-lookup"><span data-stu-id="cee08-150">WCF does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="cee08-151">Beim Empfang einer Nachricht mit einem- `AckRequested` Header, der das- `MessageNumber` Element enthält, ignoriert WCF den Wert des `MessageNumber` -Elements, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cee08-151">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, WCF ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="cee08-152">SequenceAcknowledgement-Header</span><span class="sxs-lookup"><span data-stu-id="cee08-152">SequenceAcknowledgement Header</span></span>

<span data-ttu-id="cee08-153">WCF verwendet den Piggy-back-Mechanismus für Sequenz Bestätigungen, die im zuverlässigen WS-Messaging bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-153">WCF uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>

- <span data-ttu-id="cee08-154">R1401: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, kann der `SequenceAcknowledgement`-Header in jede an den vorgesehenen Empfänger gesendete Anwendungsnachricht aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-154">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>

- <span data-ttu-id="cee08-155">B1402: Wenn WCF vor dem empfangen von Sequenz Nachrichten eine Bestätigung generieren muss (z. b. um eine `AckRequested` Nachricht zu erfüllen), generiert WCF einen `SequenceAcknowledgement` Header, der den Bereich 0-0 enthält, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cee08-155">B1402: When WCF must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), WCF generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="0" Lower="0"/>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="cee08-156">B1403: WCF generiert keine `SequenceAcknowledgement` Header, die ein- `Nack` Element enthalten, aber-Elemente unterstützen `Nack` .</span><span class="sxs-lookup"><span data-stu-id="cee08-156">B1403: WCF does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>

### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="cee08-157">WS-ReliableMessaging-Fehler</span><span class="sxs-lookup"><span data-stu-id="cee08-157">WS-ReliableMessaging Faults</span></span>

<span data-ttu-id="cee08-158">Im folgenden finden Sie eine Liste der Einschränkungen, die für die WCF-Implementierung von WS-zuverlässigen Messaging Fehlern gelten:</span><span class="sxs-lookup"><span data-stu-id="cee08-158">The following is a list of constraints that apply to the WCF implementation of WS-Reliable Messaging faults:</span></span>

- <span data-ttu-id="cee08-159">B1501: WCF generiert keine `MessageNumberRollover` Fehler.</span><span class="sxs-lookup"><span data-stu-id="cee08-159">B1501: WCF does not generate `MessageNumberRollover` faults.</span></span>

- <span data-ttu-id="cee08-160">B1502: der WCF-Endpunkt generiert möglicherweise `CreateSequenceRefused` Fehler, wie in der Spezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cee08-160">B1502:WCF endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>

- <span data-ttu-id="cee08-161">B1503: Wenn der Dienst Endpunkt das Verbindungs Limit erreicht und keine neuen Verbindungen verarbeiten kann, generiert WCF einen zusätzlichen `CreateSequenceRefused` Fehlersubcode, `netrm:ConnectionLimitReached` , wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cee08-161">B1503:When the service endpoint reaches its connection limit and cannot process new connections, WCF generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>

  ```xml
  <s:Envelope>
    <s:Header>
      <wsa:Action>
        http://schemas.xmlsoap.org/ws/2005/08/addressing/fault
      </wsa:Action>
    </s:Header>
    <s:Body>
      <s:Fault>
        <s:Code>
          <s:Value>
            s:Receiver
          </s:Value>
          <s:Subcode>
            <s:Value>
              wsrm:CreateSequenceRefused
            </s:Value>
            <s:Subcode>
              <s:Value>
                netrm:ConnectionLimitReached
              </s:Value>
            </s:Subcode>
          </s:Subcode>
        </s:Code>
        <s:Reason>
          <s:Text xml:lang="en">
            [Reason]
          </s:Text>
        </s:Reason>
      </s:Fault>
    </s:Body>
  </s:Envelope>
  ```

### <a name="ws-addressing-faults"></a><span data-ttu-id="cee08-162">WS-Adressierungsfehler</span><span class="sxs-lookup"><span data-stu-id="cee08-162">WS-Addressing Faults</span></span>

<span data-ttu-id="cee08-163">Da das zuverlässige WS-Messaging WS-Adressierung verwendet, kann die Implementierung der zuverlässigen WS-Messaging-Implementierung WS-Adressierungs Fehler generieren.</span><span class="sxs-lookup"><span data-stu-id="cee08-163">Because WS-Reliable Messaging uses WS-Addressing, WCF WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="cee08-164">In diesem Abschnitt werden die WS-Adressierungs Fehler erläutert, die von WCF explizit auf der zuverlässigen WS-Messaging-Schicht generiert werden:</span><span class="sxs-lookup"><span data-stu-id="cee08-164">This section covers the WS-Addressing faults that WCF explicitly generates at the WS-Reliable Messaging layer:</span></span>

- <span data-ttu-id="cee08-165">B1601: WCF generiert den Fehlermeldungs Adressierungs Header, der erforderlich ist, wenn einer der folgenden Punkte zutrifft:</span><span class="sxs-lookup"><span data-stu-id="cee08-165">B1601:WCF generates the fault Message Addressing Header Required when one of the following is true:</span></span>

  - <span data-ttu-id="cee08-166">Eine Nachricht hat keinen `Sequence`-Header und keinen `Action`-Header.</span><span class="sxs-lookup"><span data-stu-id="cee08-166">A message is missing a `Sequence` header and an `Action` header.</span></span>

  - <span data-ttu-id="cee08-167">Eine `CreateSequence`-Nachricht hat keinen `MessageId`-Header.</span><span class="sxs-lookup"><span data-stu-id="cee08-167">A `CreateSequence` message is missing a `MessageId` header.</span></span>

  - <span data-ttu-id="cee08-168">Eine `CreateSequence`-Nachricht hat keinen `ReplyTo`-Header.</span><span class="sxs-lookup"><span data-stu-id="cee08-168">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>

- <span data-ttu-id="cee08-169">B1602: WCF generiert die Fehler Aktion, die in der Antwort auf eine Nachricht, die keinen Header enthält, nicht unterstützt wird `Sequence` und über einen- `Action` Header verfügt, der in der WS-zuverlässigen Messaging Spezifikation nicht erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="cee08-169">B1602:WCF generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>

- <span data-ttu-id="cee08-170">B1603: WCF generiert den Fehler Endpunkt nicht verfügbar, um anzugeben, dass der Endpunkt die Sequenz nicht auf der Grundlage der Untersuchung der `CreateSequence` Adressierungs Header der Nachricht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cee08-170">B1603:WCF generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>

## <a name="protocol-composition"></a><span data-ttu-id="cee08-171">Protokollkomposition</span><span class="sxs-lookup"><span data-stu-id="cee08-171">Protocol Composition</span></span>

### <a name="composition-with-ws-addressing"></a><span data-ttu-id="cee08-172">Komposition mit WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="cee08-172">Composition with WS-Addressing</span></span>

<span data-ttu-id="cee08-173">WCF unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung 2004/08 [ws-addr] und W3C WS-Adressierung 1,0 Empfehlungen [ws-addr-core] und [ws-addr-SOAP].</span><span class="sxs-lookup"><span data-stu-id="cee08-173">WCF supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>

<span data-ttu-id="cee08-174">Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die verwendete Version der WS-Adressierung nicht ein.</span><span class="sxs-lookup"><span data-stu-id="cee08-174">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="cee08-175">Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="cee08-175">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="cee08-176">R2101:Sowohl WS-Adressierung&#160;2004/08 als auch WS-Adressierung&#160;1.0 können mit zuverlässigem WS-Messaging verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-176">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>

- <span data-ttu-id="cee08-177">R2102: für eine bestimmte zuverlässige WS-Messaging-Sequenz oder ein Paar umgekehrter Sequenzen, die mithilfe des-Mechanismus korreliert werden, muss eine einzelne Version der WS-Adressierung verwendet werden `wsrm:Offer` .</span><span class="sxs-lookup"><span data-stu-id="cee08-177">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>

### <a name="composition-with-soap"></a><span data-ttu-id="cee08-178">Komposition mit SOAP</span><span class="sxs-lookup"><span data-stu-id="cee08-178">Composition with SOAP</span></span>

<span data-ttu-id="cee08-179">WCF unterstützt die Verwendung von SOAP 1,1 und SOAP 1,2 mit zuverlässigem WS-Messaging.</span><span class="sxs-lookup"><span data-stu-id="cee08-179">WCF supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>

### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="cee08-180">Komposition mit WS-Sicherheit und WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="cee08-180">Composition with WS-Security and WS-SecureConversation</span></span>

<span data-ttu-id="cee08-181">WCF bietet Schutz für zuverlässige WS-Messaging-Sequenzen mithilfe von Secure Transport (HTTPS), Komposition mit WS-Sicherheit und Komposition mit WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="cee08-181">WCF provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="cee08-182">Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="cee08-182">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="cee08-183">R2301: um die Integrität einer zuverlässigen WS-Messaging-Sequenz zusätzlich zur Integrität und Vertraulichkeit einzelner Nachrichten zu schützen, erfordert WCF, dass eine WS-Secure-Konversation verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="cee08-183">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, WCF requires that WS-Secure Conversation must be used.</span></span>

- <span data-ttu-id="cee08-184">R2302:EineWS-Secure Conversation-Sitzung muss vor der Erstellung von zuverlässigen WS-Messaging-Sequenzen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-184">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>

- <span data-ttu-id="cee08-185">R2303: Wenn die Lebensdauer einer zuverlässigen WS-Messaging-Sequenz die Lebensdauer der WS-Secure Conversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-Secure Conversation Renewal-Bindung erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-185">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>

- <span data-ttu-id="cee08-186">B2304:Die zuverlässige WS-Messaging-Sequenz bzw. das Paar korrelierter umgekehrter Sequenzen ist immer an eine einzelne WS-SecureConversation-Sitzung gebunden.</span><span class="sxs-lookup"><span data-stu-id="cee08-186">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>

  <span data-ttu-id="cee08-187">Die WCF-Quelle generiert das- `wsse:SecurityTokenReference` Element im Abschnitt Element Erweiterbarkeit der `CreateSequence` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cee08-187">The WCF source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>

- <span data-ttu-id="cee08-188">R2305: Wenn eine Nachricht mit WS-Secure Conversation zusammengesetzt wird, `CreateSequence` muss Sie das- `wsse:SecurityTokenReference` Element enthalten.</span><span class="sxs-lookup"><span data-stu-id="cee08-188">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>

## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="cee08-189">Zuverlässige WS-Messaging WS-Richtlinienassertion</span><span class="sxs-lookup"><span data-stu-id="cee08-189">WS-Reliable Messaging WS-Policy Assertion</span></span>

<span data-ttu-id="cee08-190">WCF verwendet WS-zuverlässiges WS-Policy-Assertionen `wsrm:RMAssertion` zum Beschreiben von Endpunkten-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="cee08-190">WCF uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="cee08-191">Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="cee08-191">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="cee08-192">B3001: WCF fügt `wsrm:RMAssertion` die WS-Policy-Assertionen an `wsdl:binding` Elemente an.</span><span class="sxs-lookup"><span data-stu-id="cee08-192">B3001: WCF attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> <span data-ttu-id="cee08-193">WCF unterstützt sowohl Anhänge für `wsdl:binding` -als auch- `wsdl:port` Elemente.</span><span class="sxs-lookup"><span data-stu-id="cee08-193">WCF supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>

- <span data-ttu-id="cee08-194">B3002: WCF unterstützt die folgenden optionalen Eigenschaften der zuverlässigen WS-Messaging-Assertion und ermöglicht Ihnen die Kontrolle über die WCF `ReliableMessagingBindingElement` :</span><span class="sxs-lookup"><span data-stu-id="cee08-194">B3002: WCF supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the WCF`ReliableMessagingBindingElement`:</span></span>

  - `wsrm:InactivityTimeout`

  - `wsrm:AcknowledgementInterval`

  <span data-ttu-id="cee08-195">Im Folgenden finden Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cee08-195">The following is an example.</span></span>

  ```xml
  <wsrm:RMAssertion>
    <wsrm:InactivityTimeout Milliseconds="600000" />
    <wsrm:AcknowledgementInterval Milliseconds="200" />
  </wsrm:RMAssertion>
  ```

## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="cee08-196">Zuverlässige WS-Messaging-Erweiterung zur Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="cee08-196">Flow Control WS-Reliable Messaging Extension</span></span>

<span data-ttu-id="cee08-197">WCF verwendet die Erweiterbarkeit von zuverlässigem WS-Messaging, um eine optionale zusätzliche strengere Kontrolle über den Sequenz Nachrichtenfluss bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="cee08-197">WCF uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>

<span data-ttu-id="cee08-198">Die Fluss Steuerung wird aktiviert, indem die-Eigenschaft auf festgelegt wird <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> `true` .</span><span class="sxs-lookup"><span data-stu-id="cee08-198">Flow control is enabled by setting the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="cee08-199">Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:</span><span class="sxs-lookup"><span data-stu-id="cee08-199">The following is a list of constraints that apply to WCF:</span></span>

- <span data-ttu-id="cee08-200">B4001: Wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, generiert WCF ein- `netrm:BufferRemaining` Element in der Element Erweiterbarkeit des- `SequenceAcknowledgement` Headers.</span><span class="sxs-lookup"><span data-stu-id="cee08-200">B4001: When Reliable Messaging Flow Control is enabled, WCF generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>

- <span data-ttu-id="cee08-201">B4002: Wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, erfordert WCF nicht `netrm:BufferRemaining` , dass ein-Element im-Header vorhanden ist `SequenceAcknowledgement` , wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cee08-201">B4002: When Reliable Messaging Flow Control is enabled, WCF does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      http://fabrikam123.com/abc
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>
      8
    </netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- <span data-ttu-id="cee08-202">B4003: WCF verwendet `netrm:BufferRemaining` , um anzugeben, wie viele neue Nachrichten das zuverlässige Messaging Ziel Puffern kann.</span><span class="sxs-lookup"><span data-stu-id="cee08-202">B4003: WCF uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>

- <span data-ttu-id="cee08-203">B4004: der WCF-Dienst für zuverlässiges Messaging schränkt die Anzahl der übermittelten Nachrichten ein, wenn die zuverlässige Messaging-Zielanwendung keine Nachrichten mehr schnell empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="cee08-203">B4004:The WCF Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="cee08-204">Das zuverlässige Messaging-Ziel puffert Nachrichten, und der Wert des Elements sinkt auf&#160;0.</span><span class="sxs-lookup"><span data-stu-id="cee08-204">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>

- <span data-ttu-id="cee08-205">B4005: WCF generiert `netrm:BufferRemaining` ganzzahlige Werte zwischen 0 und 4096 einschließlich und liest ganzzahlige Werte zwischen 0 und `xs:int` dem `maxInclusive` Wert 214748364 einschließlich.</span><span class="sxs-lookup"><span data-stu-id="cee08-205">B4005: WCF generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>

## <a name="message-exchange-patterns"></a><span data-ttu-id="cee08-206">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="cee08-206">Message Exchange Patterns</span></span>

<span data-ttu-id="cee08-207">In diesem Abschnitt wird das Verhalten von WCF beschrieben, wenn das zuverlässige WS-Messaging für verschiedene Nachrichtenaustausch Muster verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cee08-207">This section describes WCF's behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="cee08-208">Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:</span><span class="sxs-lookup"><span data-stu-id="cee08-208">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>

- <span data-ttu-id="cee08-209">Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall, der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.</span><span class="sxs-lookup"><span data-stu-id="cee08-209">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>

- <span data-ttu-id="cee08-210">Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="cee08-210">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>

### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="cee08-211">Unidirektionaler, nicht adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="cee08-211">One-way, Non-addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cee08-212">Bindung</span><span class="sxs-lookup"><span data-stu-id="cee08-212">Binding</span></span>

<span data-ttu-id="cee08-213">WCF bietet ein unidirektionales Nachrichtenaustausch Muster unter Verwendung einer Sequenz über einen HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cee08-213">WCF provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> <span data-ttu-id="cee08-214">WCF verwendet die HTTP-Anforderungen, um alle Nachrichten vom RMS zum RMD zu übertragen, und die HTTP-Antwort, um alle Nachrichten vom RMD zum RMS zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cee08-214">WCF uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cee08-215">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cee08-215">CreateSequence Exchange</span></span>

<span data-ttu-id="cee08-216">Der WCF-Initiator generiert eine `CreateSequence` Nachricht ohne Angebot.</span><span class="sxs-lookup"><span data-stu-id="cee08-216">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="cee08-217">Der WCF-Responder stellt `CreateSequence` vor dem Erstellen einer Sequenz sicher, dass kein Angebot hat.</span><span class="sxs-lookup"><span data-stu-id="cee08-217">The WCF Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="cee08-218">Der WCF-Responder antwortet `CreateSequence` mit einer Meldung auf die Anforderung `CreateSequenceResponse` .</span><span class="sxs-lookup"><span data-stu-id="cee08-218">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>

#### <a name="sequenceacknowledgement"></a><span data-ttu-id="cee08-219">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="cee08-219">SequenceAcknowledgement</span></span>

<span data-ttu-id="cee08-220">Der WCF-Initiator verarbeitet Bestätigungen für die Antwort aller Meldungen außer der `CreateSequence` Nachricht und den Fehlermeldungen.</span><span class="sxs-lookup"><span data-stu-id="cee08-220">The WCF Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="cee08-221">Der WCF-Responder generiert stets eine eigenständige Bestätigung in der Antwort auf die Sequenz und die `AckRequested` Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="cee08-221">The WCF Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>

#### <a name="terminatesequence-message"></a><span data-ttu-id="cee08-222">TerminateSequence-Nachricht</span><span class="sxs-lookup"><span data-stu-id="cee08-222">TerminateSequence message</span></span>

<span data-ttu-id="cee08-223">WCF behandelt als unidirektionalen `TerminateSequence` Vorgang, d. h. die HTTP-Antwort weist einen leeren Textkörper und HTTP 202-Statuscode auf.</span><span class="sxs-lookup"><span data-stu-id="cee08-223">WCF treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>

### <a name="one-way-addressable-initiator"></a><span data-ttu-id="cee08-224">Unidirektionaler, adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="cee08-224">One Way, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cee08-225">Bindung</span><span class="sxs-lookup"><span data-stu-id="cee08-225">Binding</span></span>

<span data-ttu-id="cee08-226">WCF bietet ein unidirektionales Nachrichtenaustausch Muster unter Verwendung einer Sequenz über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cee08-226">WCF provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> <span data-ttu-id="cee08-227">WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cee08-227">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="cee08-228">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="cee08-228">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cee08-229">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cee08-229">CreateSequence Exchange</span></span>

<span data-ttu-id="cee08-230">Der WCF-Initiator generiert eine `CreateSequence` Nachricht ohne Angebot.</span><span class="sxs-lookup"><span data-stu-id="cee08-230">The WCF Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="cee08-231">Der WCF-Beantworter stellt `CreateSequence` vor dem Erstellen einer Sequenz sicher, dass kein Angebot hat.</span><span class="sxs-lookup"><span data-stu-id="cee08-231">The WCF Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="cee08-232">Der WCF-Responder überträgt die `CreateSequenceResponse` Nachricht über eine HTTP-Anforderung, die mit dem Endpunkt Verweis adressiert wird `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="cee08-232">The WCF Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>

### <a name="duplex-addressable-initiator"></a><span data-ttu-id="cee08-233">Adressierbarer Duplex-Initiator</span><span class="sxs-lookup"><span data-stu-id="cee08-233">Duplex, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cee08-234">Bindung</span><span class="sxs-lookup"><span data-stu-id="cee08-234">Binding</span></span>

<span data-ttu-id="cee08-235">WCF bietet ein vollständig asynchrones bidirektionales Nachrichtenaustausch Muster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cee08-235">WCF provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="cee08-236">WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cee08-236">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="cee08-237">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="cee08-237">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cee08-238">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cee08-238">CreateSequence Exchange</span></span>

<span data-ttu-id="cee08-239">Der WCF-Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot.</span><span class="sxs-lookup"><span data-stu-id="cee08-239">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="cee08-240">Der WCF- `CreateSequence` Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die über ein Angebot verfügt.</span><span class="sxs-lookup"><span data-stu-id="cee08-240">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="cee08-241">WCF sendet den `CreateSequenceResponse` in der HTTP-Anforderung, die an den `CreateSequence` -Endpunkt Verweis adressiert ist `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="cee08-241">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>

#### <a name="sequence-lifetime"></a><span data-ttu-id="cee08-242">Sequenzlebensdauer</span><span class="sxs-lookup"><span data-stu-id="cee08-242">Sequence Lifetime</span></span>

<span data-ttu-id="cee08-243">WCF behandelt die beiden Sequenzen als eine Vollduplex Sitzung.</span><span class="sxs-lookup"><span data-stu-id="cee08-243">WCF treats the two sequences as one fully duplex session.</span></span>

<span data-ttu-id="cee08-244">Wenn Sie einen Fehler erzeugen, der eine Sequenz Fehler erzeugt, erwartet WCF, dass der Remote Endpunkt beide Sequenzen als fehlerhaft eingibt.</span><span class="sxs-lookup"><span data-stu-id="cee08-244">Upon generating a fault that faults one sequence, WCF expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="cee08-245">Beim Lesen eines Fehlers, bei dem ein Fehler auftritt, gibt WCF beide Sequenzen aus.</span><span class="sxs-lookup"><span data-stu-id="cee08-245">Upon reading a fault that faults one sequence, WCF faults both sequences.</span></span>

<span data-ttu-id="cee08-246">WCF kann seine ausgehende Sequenz schließen und die Verarbeitung von Nachrichten in der eingehenden Sequenz fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="cee08-246">WCF can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="cee08-247">Umgekehrt kann WCF das Ende der eingehenden Sequenz verarbeiten und weiterhin Nachrichten in der ausgehenden Sequenz senden.</span><span class="sxs-lookup"><span data-stu-id="cee08-247">Conversely, WCF can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>

### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="cee08-248">Nicht adressierbarer Anforderung-Antwort-Initiator</span><span class="sxs-lookup"><span data-stu-id="cee08-248">Request-Reply, Non-Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cee08-249">Bindung</span><span class="sxs-lookup"><span data-stu-id="cee08-249">Binding</span></span>

<span data-ttu-id="cee08-250">WCF bietet ein unidirektionales Anforderungs-/Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cee08-250">WCF provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> <span data-ttu-id="cee08-251">WCF verwendet die HTTP-Anforderungen zum Übertragen der Anforderungs Sequenz Nachrichten und verwendet die HTTP-Antworten, um die Nachrichten der Antwort Sequenz zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cee08-251">WCF uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cee08-252">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cee08-252">CreateSequence Exchange</span></span>

<span data-ttu-id="cee08-253">Der WCF-Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot.</span><span class="sxs-lookup"><span data-stu-id="cee08-253">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="cee08-254">Der WCF- `CreateSequence` Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die über ein Angebot verfügt.</span><span class="sxs-lookup"><span data-stu-id="cee08-254">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="cee08-255">Der WCF-Responder antwortet `CreateSequence` mit einer Meldung auf die Anforderung `CreateSequenceResponse` .</span><span class="sxs-lookup"><span data-stu-id="cee08-255">The WCF Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>

#### <a name="one-way-message"></a><span data-ttu-id="cee08-256">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="cee08-256">One-way Message</span></span>

<span data-ttu-id="cee08-257">Zum erfolgreichen Abschluss eines unidirektionalen Nachrichtenaustausch Protokolls überträgt der WCF-Initiator eine Anforderungs Sequenz Nachricht in der HTTP-Anforderung und empfängt eine eigenständige `SequenceAcknowledgement` Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cee08-257">To complete a one-way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="cee08-258">Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.</span><span class="sxs-lookup"><span data-stu-id="cee08-258">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>

<span data-ttu-id="cee08-259">Der WCF-Responder kann auf die Anforderung mit einer Bestätigung, einem Fehler oder einer Antwort mit einem leeren Text-und HTTP 202-Statuscode Antworten.</span><span class="sxs-lookup"><span data-stu-id="cee08-259">The WCF Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>

#### <a name="two-way-messages"></a><span data-ttu-id="cee08-260">Bidirektionale Nachrichten</span><span class="sxs-lookup"><span data-stu-id="cee08-260">Two Way Messages</span></span>

<span data-ttu-id="cee08-261">Um ein bidirektionales Nachrichtenaustausch Protokoll erfolgreich abzuschließen, überträgt der WCF-Initiator eine Anforderungs Sequenz Nachricht in der HTTP-Anforderung und empfängt eine Antwort Sequenz Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="cee08-261">To complete a two way message exchange protocol successfully, the WCF Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="cee08-262">Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.</span><span class="sxs-lookup"><span data-stu-id="cee08-262">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>

<span data-ttu-id="cee08-263">Der WCF-Responder kann auf die Anforderung mit einer Anwendungs Antwort, einem Fehler oder einer Antwort mit leerem Text und HTTP 202-Statuscode Antworten.</span><span class="sxs-lookup"><span data-stu-id="cee08-263">The WCF Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>

<span data-ttu-id="cee08-264">Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.</span><span class="sxs-lookup"><span data-stu-id="cee08-264">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>

#### <a name="retrying-replies"></a><span data-ttu-id="cee08-265">Wiederholen von Antworten</span><span class="sxs-lookup"><span data-stu-id="cee08-265">Retrying Replies</span></span>

<span data-ttu-id="cee08-266">WCF basiert auf einer HTTP-Anforderung-Antwort-Korrelation für die bidirektionale Nachrichtenaustausch-Protokoll Korrelation.</span><span class="sxs-lookup"><span data-stu-id="cee08-266">WCF relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="cee08-267">Aus diesem Grund beendet der WCF-Initiator den Wiederholungsversuch einer Anforderungs Sequenz Nachricht nicht, wenn die Anforderungs Sequenz Nachricht bestätigt wird, sondern wenn die HTTP-Antwort eine Bestätigung, eine Benutzer Nachricht oder einen Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="cee08-267">Because of this, the WCF Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="cee08-268">Der WCF-Responder wiederholt Antworten auf den HTTP-Anforderungs Abschnitt der Anforderung, mit der die Antwort korreliert wird.</span><span class="sxs-lookup"><span data-stu-id="cee08-268">The WCF Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>

#### <a name="lastmessage-exchange"></a><span data-ttu-id="cee08-269">LastMessage-Austausch</span><span class="sxs-lookup"><span data-stu-id="cee08-269">LastMessage Exchange</span></span>

<span data-ttu-id="cee08-270">Der WCF-Initiator generiert und überträgt eine leere Körper letzte Nachricht auf dem HTTP-Anforderungs Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cee08-270">The WCF Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> <span data-ttu-id="cee08-271">WCF erfordert eine Antwort, ignoriert jedoch die tatsächliche Antwortnachricht.</span><span class="sxs-lookup"><span data-stu-id="cee08-271">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="cee08-272">Der WCF-Responder antwortet auf die letzte Nachricht mit dem leeren Körper der Anforderungs Sequenz mit der letzten Meldung der Antwort Sequenz.</span><span class="sxs-lookup"><span data-stu-id="cee08-272">The WCF Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>

<span data-ttu-id="cee08-273">Wenn der WCF-Responder eine letzte Nachricht empfängt, bei der der Aktions-URI nicht ist `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` , antwortet WCF mit einer letzten Meldung.</span><span class="sxs-lookup"><span data-stu-id="cee08-273">If the WCF Responder receives a last message in which the action URI is not `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF replies with a last message.</span></span> <span data-ttu-id="cee08-274">Im Fall eines bidirektionalen Nachrichtenaustauschprotokolls enthält die letzte Nachricht die Anwendungsnachricht, im Falle eines unidirektionalen Nachrichtenaustauschprotokolls ist die letzte Nachricht leer.</span><span class="sxs-lookup"><span data-stu-id="cee08-274">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>

<span data-ttu-id="cee08-275">Der WCF-Responder erfordert keine Bestätigung für die letzte Nachricht der Antwort Sequenz.</span><span class="sxs-lookup"><span data-stu-id="cee08-275">The WCF Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>

#### <a name="terminatesequence-exchange"></a><span data-ttu-id="cee08-276">TerminateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cee08-276">TerminateSequence Exchange</span></span>

<span data-ttu-id="cee08-277">Wenn alle Anforderungen eine gültige Antwort erhalten haben, generiert und überträgt der WCF-Initiator die Nachricht der Anforderungs Sequenz `TerminateSequence` auf den HTTP-Anforderungs Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cee08-277">When all requests have received a valid reply, the WCF Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> <span data-ttu-id="cee08-278">WCF erfordert eine Antwort, ignoriert jedoch die tatsächliche Antwortnachricht.</span><span class="sxs-lookup"><span data-stu-id="cee08-278">WCF requires a response but ignores the actual response message.</span></span> <span data-ttu-id="cee08-279">Der WCF-Responder antwortet `TerminateSequence` mit der Meldung der Antwort Sequenz auf die Nachricht der Anforderungs Sequenz `TerminateSequence` .</span><span class="sxs-lookup"><span data-stu-id="cee08-279">The WCF Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>

<span data-ttu-id="cee08-280">In einer normalen Abschlusssequenz enthalten beide `TerminateSequence`-Nachrichten einen vollständigen Bereich von `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="cee08-280">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>

### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="cee08-281">Adressierbarer Anforderung/Antwort-Initiator</span><span class="sxs-lookup"><span data-stu-id="cee08-281">Request/Reply, Addressable Initiator</span></span>

#### <a name="binding"></a><span data-ttu-id="cee08-282">Bindung</span><span class="sxs-lookup"><span data-stu-id="cee08-282">Binding</span></span>

<span data-ttu-id="cee08-283">WCF bietet ein Anforderung-Antwort-Nachrichtenaustausch Muster mithilfe von zwei Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="cee08-283">WCF provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> <span data-ttu-id="cee08-284">WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="cee08-284">WCF uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="cee08-285">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="cee08-285">All HTTP responses have an empty body and HTTP 202 status code.</span></span>

#### <a name="createsequence-exchange"></a><span data-ttu-id="cee08-286">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="cee08-286">CreateSequence Exchange</span></span>

<span data-ttu-id="cee08-287">Der WCF-Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot.</span><span class="sxs-lookup"><span data-stu-id="cee08-287">The WCF Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="cee08-288">Der WCF- `CreateSequence` Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die über ein Angebot verfügt.</span><span class="sxs-lookup"><span data-stu-id="cee08-288">The WCF Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="cee08-289">WCF sendet den `CreateSequenceResponse` in der HTTP-Anforderung, die an den `CreateSequence` -Endpunkt Verweis adressiert ist `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="cee08-289">WCF sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>

#### <a name="requestreply-correlation"></a><span data-ttu-id="cee08-290">Anforderung/Antwort-Korrelation</span><span class="sxs-lookup"><span data-stu-id="cee08-290">Request/Reply Correlation</span></span>

<span data-ttu-id="cee08-291">Der WCF-Initiator stellt sicher, dass alle Anwendungs Anforderungs Nachrichten einen `MessageId` und einen `ReplyTo` Endpunkt Verweis tragen.</span><span class="sxs-lookup"><span data-stu-id="cee08-291">The WCF Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="cee08-292">Der WCF-Initiator wendet den `CreateSequence` `ReplyTo` Endpunkt Verweis der Nachricht auf jede Anwendungs Anforderungs Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="cee08-292">The WCF Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="cee08-293">Der WCF-Responder erfordert, dass eingehende Anforderungs Nachrichten einen `MessageId` und einen tragen `ReplyTo` .</span><span class="sxs-lookup"><span data-stu-id="cee08-293">The WCF Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="cee08-294">Der WCF-Responder stellt sicher, dass der URI des Endpunkt Verweises sowohl von `CreateSequence` als auch von allen Anwendungs Anforderungs Nachrichten identisch ist.</span><span class="sxs-lookup"><span data-stu-id="cee08-294">The WCF Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
