---
title: "Zuverlässiges Messaging-Protokoll, Version 1.0"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5657b48a648603f24e89c0eebd1285ed9a505e54
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="reliable-messaging-protocol-version-10"></a><span data-ttu-id="a9774-102">Zuverlässiges Messaging-Protokoll, Version 1.0</span><span class="sxs-lookup"><span data-stu-id="a9774-102">Reliable Messaging Protocol version 1.0</span></span>
<span data-ttu-id="a9774-103">In diesem Thema werden [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Implementierungsdetails für das WS-Reliable Messaging-Protokoll in der Version 1.0 vom Februar 2005 beschrieben, die für die Interoperation mithilfe des HTTP-Transports erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a9774-103">This topic covers [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] implementation details for the WS-Reliable Messaging February 2005 (version 1.0) protocol necessary for interoperation using the HTTP transport.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-104"> orientiert sich an der WS-Reliable Messaging-Spezifikation mit den in diesem Thema erläuterten Einschränkungen und Klarstellungen.</span><span class="sxs-lookup"><span data-stu-id="a9774-104"> follows the WS-Reliable Messaging specification with the constraints and clarifications explained in this topic.</span></span> <span data-ttu-id="a9774-105">Beachten Sie, dass das zuverlässige WS-Messaging-Protokoll in der Version&#160;1.0 ab [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] implementiert ist.</span><span class="sxs-lookup"><span data-stu-id="a9774-105">Note that the WS-ReliableMessaging version 1.0 protocol is implemented starting with the [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)].</span></span>  
  
 <span data-ttu-id="a9774-106">Das WS-ReliableMessaging-Protokoll vom Februar&#160;2005 ist in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durch das <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> implementiert.</span><span class="sxs-lookup"><span data-stu-id="a9774-106">The WS-Reliable Messaging February 2005 protocol is implemented in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] by the <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.</span></span>  
  
 <span data-ttu-id="a9774-107">Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:</span><span class="sxs-lookup"><span data-stu-id="a9774-107">For convenience, the topic uses the following roles:</span></span>  
  
-   <span data-ttu-id="a9774-108">Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert</span><span class="sxs-lookup"><span data-stu-id="a9774-108">Initiator: the client that initiates WS-Reliable Message sequence creation</span></span>  
  
-   <span data-ttu-id="a9774-109">Beantworter: der Dienst, der die Anforderungen des Initiators empfängt</span><span class="sxs-lookup"><span data-stu-id="a9774-109">Responder: the service that receives the initiator's requests</span></span>  
  
 <span data-ttu-id="a9774-110">In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9774-110">This document uses the prefixes and namespaces in the following table.</span></span>  
  
|<span data-ttu-id="a9774-111">Präfix</span><span class="sxs-lookup"><span data-stu-id="a9774-111">Prefix</span></span>|<span data-ttu-id="a9774-112">Namespace</span><span class="sxs-lookup"><span data-stu-id="a9774-112">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="a9774-113">wsrm</span><span class="sxs-lookup"><span data-stu-id="a9774-113">wsrm</span></span>|<span data-ttu-id="a9774-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span><span class="sxs-lookup"><span data-stu-id="a9774-114">http://schemas.xmlsoap.org/ws/2005/02/rm</span></span>|  
|<span data-ttu-id="a9774-115">netrm</span><span class="sxs-lookup"><span data-stu-id="a9774-115">netrm</span></span>|<span data-ttu-id="a9774-116">http://schemas.microsoft.com/ws/2006/05/rm</span><span class="sxs-lookup"><span data-stu-id="a9774-116">http://schemas.microsoft.com/ws/2006/05/rm</span></span>|  
|<span data-ttu-id="a9774-117">s</span><span class="sxs-lookup"><span data-stu-id="a9774-117">s</span></span>|<span data-ttu-id="a9774-118">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="a9774-118">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="a9774-119">wsa</span><span class="sxs-lookup"><span data-stu-id="a9774-119">wsa</span></span>|<span data-ttu-id="a9774-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span><span class="sxs-lookup"><span data-stu-id="a9774-120">http://schemas.xmlsoap.org/ws/2005/08/addressing</span></span>|  
|<span data-ttu-id="a9774-121">wsse</span><span class="sxs-lookup"><span data-stu-id="a9774-121">wsse</span></span>|<span data-ttu-id="a9774-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="a9774-122">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd</span></span>|  
  
## <a name="messaging"></a><span data-ttu-id="a9774-123">Messaging</span><span class="sxs-lookup"><span data-stu-id="a9774-123">Messaging</span></span>  
  
### <a name="sequence-establishment-messages"></a><span data-ttu-id="a9774-124">Sequenzeinrichtungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="a9774-124">Sequence Establishment Messages</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-125"> implementiert `CreateSequence`- und `CreateSequenceResponse`-Nachrichten, um eine zuverlässige Nachrichtensequenz einzurichten.</span><span class="sxs-lookup"><span data-stu-id="a9774-125"> implements `CreateSequence` and `CreateSequenceResponse` messages to establish a reliable message sequence.</span></span> <span data-ttu-id="a9774-126">Es gelten die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="a9774-126">The following constraints apply:</span></span>  
  
-   <span data-ttu-id="a9774-127">B1101: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert nicht das optionale Expires-Element in der `CreateSequence`-Nachricht oder, in den Fällen, in denen die `CreateSequence`-Nachricht ein `Offer`-Element enthält, das optionale `Expires`-Element im `Offer`-Element.</span><span class="sxs-lookup"><span data-stu-id="a9774-127">B1101: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not generate the optional Expires element in the `CreateSequence` message or, in the cases when the `CreateSequence` message contains an `Offer` element, the optional `Expires` element in the `Offer` element.</span></span>  
  
-   <span data-ttu-id="a9774-128">B1102: Beim Zugreifen auf die `CreateSequence`-Nachricht sendet und empfängt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` beide `Expires`-Elemente, wenn sie vorhanden sind, verwendet ihre Werte jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="a9774-128">B1102: When accessing the `CreateSequence` message, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`Responder` sends and receives both `Expires` elements if they exist, but does not use their values.</span></span>  
  
 <span data-ttu-id="a9774-129">Zuverlässiges WS-Messaging führt den `Offer`-Mechanismus ein, um zwei umgekehrt korrelierende Sequenzen einzurichten, die eine Sitzung bilden.</span><span class="sxs-lookup"><span data-stu-id="a9774-129">WS-Reliable Messaging introduces the `Offer` mechanism to establish the two converse correlated sequences that form a session.</span></span>  
  
-   <span data-ttu-id="a9774-130">R1103: Wenn `CreateSequence` ein `Offer`-Element enthält, muss der zuverlässige Messaging-Beantworter entweder die Sequenz akzeptieren und mit `CreateSequenceResponse` antworten (enthält ein `wsrm:Accept`-Element), wodurch die zwei umgekehrt korrelierenden Sequenzen gebildet werden, oder er muss die `CreateSequence`-Anforderung zurückweisen.</span><span class="sxs-lookup"><span data-stu-id="a9774-130">R1103: If `CreateSequence` contains an `Offer` element, the Reliable Messaging Responder must either accept the sequence and respond with `CreateSequenceResponse` that contains a `wsrm:Accept` element, forming two correlated converse sequences or reject the `CreateSequence` request.</span></span>  
  
-   <span data-ttu-id="a9774-131">R1104: `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten müssen an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9774-131">R1104: `SequenceAcknowledgement` and application messages flowing on converse sequence must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="a9774-132">R1105: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` müssen Adresswerte aufweisen, die sich oktettweise entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a9774-132">R1105: `AcksTo` and `ReplyTo` endpoint references in the `CreateSequence` must have address values that match the octet-wise.</span></span>  
  
     <span data-ttu-id="a9774-133">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überprüft, ob die URI-Teile von `AcksTo`- und `ReplyTo`-EPRs identisch sind, bevor die Sequenz erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a9774-133">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder verifies that the URI portion of the `AcksTo` and `ReplyTo` EPRs are identical before creating a sequence.</span></span>  
  
-   <span data-ttu-id="a9774-134">R1106: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` sollten den gleichen Satz von Verweisparametern aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a9774-134">R1106: `AcksTo` and `ReplyTo` Endpoint References in the `CreateSequence` should have the same set of reference parameters.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-135"> geht davon aus, dass die Verweisparameter von `AcksTo` und `ReplyTo` in `CreateSequence` identisch sind, erzwingt dies jedoch nicht, und verwendet die Verweisparameter von dem `ReplyTo`-Endpunktverweis für Bestätigungen und Nachrichten umgekehrter Sequenz.</span><span class="sxs-lookup"><span data-stu-id="a9774-135"> does not enforce but assumes that [reference parameters] of `AcksTo` and `ReplyTo` on `CreateSequence` are identical and uses [reference parameters] from `ReplyTo` endpoint reference for acknowledgements and converse sequence messages.</span></span>  
  
-   <span data-ttu-id="a9774-136">R1107: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9774-136">R1107: When two converse sequences are established using the `Offer` mechanism, `SequenceAcknowledgement` and application messages flowing on converse sequences must be sent to the `ReplyTo` endpoint reference of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="a9774-137">R1108: Wenn mithilfe des Offer-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, muss die `[address]`-Eigenschaft des `wsrm:AcksTo`-Endpunktverweises, ein dem `wsrm:Accept`-Element von `CreateSequenceResponse` untergeordnetes Element, mit dem Ziel-URI von `CreateSequence` byteweise übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a9774-137">R1108: When two converse sequences are established using the Offer mechanism, the `[address]` property of the `wsrm:AcksTo` Endpoint Reference child element of the `wsrm:Accept` element of the `CreateSequenceResponse` must match byte-wise the destination URI of the `CreateSequence`.</span></span>  
  
-   <span data-ttu-id="a9774-138">R1109: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen die vom Initiator gesendeten Nachrichten und die vom Beantworter gesendeten Bestätigungen der Nachrichten an den gleichen Endpunktverweis gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9774-138">R1109: When two converse sequences are established using the `Offer` mechanism, messages sent by initiator and acknowledgements to messages by responder must be sent to the same Endpoint Reference.</span></span>  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-139"> verwendet zuverlässiges WS-Messaging, um zuverlässige Sitzungen zwischen dem Initiator und dem Beantworter einzurichten.</span><span class="sxs-lookup"><span data-stu-id="a9774-139"> uses WS-Reliable Messaging to establish reliable sessions between the Initiator and Responder.</span></span> <span data-ttu-id="a9774-140">Die Implementierung von zuverlässigem WS-Messaging in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet zuverlässige Sitzungen für unidirektionale, Anforderung-Antwort- und Vollduplex-Nachrichtenmuster.</span><span class="sxs-lookup"><span data-stu-id="a9774-140">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s WS-Reliable Messaging implementation provides reliable session for one-way, request-reply and full duplex messaging patterns.</span></span> <span data-ttu-id="a9774-141">Die WS-Reliable Messaging `Offer` Mechanismus auf `CreateSequence` / `CreateSequenceResponse` können Sie die zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein, die für alle Endpunkte Nachricht geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="a9774-141">The WS-Reliable Messaging `Offer` mechanism on `CreateSequence`/`CreateSequenceResponse` lets you establish two correlated converse sequences, and provides a session protocol that is suitable for all message endpoints.</span></span> <span data-ttu-id="a9774-142">Da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Sicherheit solcher Sitzungen sowie den End-to-End-Schutz der Sitzungsintegrität garantiert, kann sichergestellt werden, dass alle an den gleichen Teilnehmer gerichteten Nachrichten am gleichen Ziel ankommen.</span><span class="sxs-lookup"><span data-stu-id="a9774-142">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a security guarantee for such a session including end-to-end protection for session integrity, it is practical to ensure messages intended to the same party are arriving at the same destination.</span></span> <span data-ttu-id="a9774-143">Dies lässt auch Piggyback-Übertragung von Sequenzbestätigungen auf Anwendungsnachrichten zu.</span><span class="sxs-lookup"><span data-stu-id="a9774-143">This also allows piggy-backing of sequence acknowledgements on application messages.</span></span> <span data-ttu-id="a9774-144">Deshalb gelten die Einschränkungen R1104, R1105 und R1108 für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a9774-144">Therefore, constraints R1104, R1105, and R1108 apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="a9774-145">Ein Beispiel für eine `CreateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a9774-145">An example of a `CreateSequence` message.</span></span>  
  
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
  
 <span data-ttu-id="a9774-146">Ein Beispiel für eine `CreateSequenceResponse`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a9774-146">An example of a `CreateSequenceResponse` message.</span></span>  
  
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
  
### <a name="sequence"></a><span data-ttu-id="a9774-147">Sequenz</span><span class="sxs-lookup"><span data-stu-id="a9774-147">Sequence</span></span>  
 <span data-ttu-id="a9774-148">Die folgende Liste enthält die Einschränkungen, die für Sequenzen gelten:</span><span class="sxs-lookup"><span data-stu-id="a9774-148">The following is a list of constraints that apply to sequences:</span></span>  
  
-   <span data-ttu-id="a9774-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und greift auf die Sequenznummern, die nicht höher als `xs:long`des inklusive Maximalwert 9223372036854775807.</span><span class="sxs-lookup"><span data-stu-id="a9774-149">B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates and accesses sequence numbers no higher than `xs:long`’s maximum inclusive value, 9223372036854775807.</span></span>  
  
-   <span data-ttu-id="a9774-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert immer eine ohne Text letzte Meldung mit der Aktions-URI des http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span><span class="sxs-lookup"><span data-stu-id="a9774-150">B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] always generates an empty-bodied last message with the action URI of http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
-   <span data-ttu-id="a9774-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] empfängt und sendet eine Nachricht mit einem Sequenzheader, der das `LastMessage`-Element enthält, sofern der Aktions-URI nicht "http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage" lautet.</span><span class="sxs-lookup"><span data-stu-id="a9774-151">B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] receives and delivers a message with a Sequence header that contains a `LastMessage` element as long as the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.</span></span>  
  
 <span data-ttu-id="a9774-152">Ein Beispiel für einen Sequenzheader.</span><span class="sxs-lookup"><span data-stu-id="a9774-152">An example of a Sequence Header.</span></span>  
  
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
  
### <a name="ackrequested-header"></a><span data-ttu-id="a9774-153">AckRequested-Header</span><span class="sxs-lookup"><span data-stu-id="a9774-153">AckRequested Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-154"> verwendet den `AckRequested`-Header als Keep-alive-Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="a9774-154"> uses `AckRequested` Header as a keep-alive mechanism.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-155"> generiert nicht das optionale `MessageNumber`-Element.</span><span class="sxs-lookup"><span data-stu-id="a9774-155"> does not generate the optional `MessageNumber` element.</span></span> <span data-ttu-id="a9774-156">Wird eine Nachricht mit einem `AckRequested`-Header empfangen, der das `MessageNumber`-Element enthält, ignoriert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] den Wert des `MessageNumber`-Elements, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a9774-156">Upon receiving a message with an `AckRequested` header that contains the `MessageNumber` element, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ignores the `MessageNumber` element’s value, as shown in the following example.</span></span>  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a><span data-ttu-id="a9774-157">SequenceAcknowledgement-Header</span><span class="sxs-lookup"><span data-stu-id="a9774-157">SequenceAcknowledgement Header</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-158"> verwendet den Piggyback-Mechanismus für die im zuverlässigen WS-Messaging bereitgestellten Sequenzbestätigungen.</span><span class="sxs-lookup"><span data-stu-id="a9774-158"> uses piggy-back mechanism for sequence acknowledgements provided in WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="a9774-159">R1401: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, kann der `SequenceAcknowledgement`-Header in jede an den vorgesehenen Empfänger gesendete Anwendungsnachricht aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="a9774-159">R1401: When two converse sequences are established using the `Offer` mechanism, the `SequenceAcknowledgement` header may be included in any application message transmitted to the intended recipient.</span></span>  
  
-   <span data-ttu-id="a9774-160">B1402: Wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine Bestätigung generieren muss (um beispielsweise auf eine `AckRequested`-Nachricht zu reagieren), bevor eine Sequenznachricht empfangen wurde, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen `SequenceAcknowledgement`-Header, der den Bereich "0-0" enthält, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="a9774-160">B1402: When [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] must generate an acknowledgement prior to receiving any sequence messages (for example, to satisfy an `AckRequested` message), [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `SequenceAcknowledgement` header that contains the range 0-0, as shown in the following example.</span></span>  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   <span data-ttu-id="a9774-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert keine `SequenceAcknowledgement`-Header, die ein `Nack`-Element enthalten, unterstützt jedoch `Nack`-Elemente.</span><span class="sxs-lookup"><span data-stu-id="a9774-161">B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `SequenceAcknowledgement` headers that contain a `Nack` element but supports `Nack` elements.</span></span>  
  
### <a name="ws-reliablemessaging-faults"></a><span data-ttu-id="a9774-162">WS-ReliableMessaging-Fehler</span><span class="sxs-lookup"><span data-stu-id="a9774-162">WS-ReliableMessaging Faults</span></span>  
 <span data-ttu-id="a9774-163">Die folgende Liste enthält die Einschränkungen, die für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierung der Fehler des zuverlässigen WS-Messaging gelten:</span><span class="sxs-lookup"><span data-stu-id="a9774-163">The following is a list of constraints that apply to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation of WS-Reliable Messaging faults:</span></span>  
  
-   <span data-ttu-id="a9774-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert keine `MessageNumberRollover`-Fehler.</span><span class="sxs-lookup"><span data-stu-id="a9774-164">B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not generate `MessageNumberRollover` faults.</span></span>  
  
-   <span data-ttu-id="a9774-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Endpunkt generiert möglicherweise `CreateSequenceRefused` Fehler auf, wie in der Spezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9774-165">B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint may generate `CreateSequenceRefused` faults as described in the specification.</span></span>  
  
-   <span data-ttu-id="a9774-166">B1503:when den Dienstendpunkt seine Verbindungsgrenze erreicht und keine weiteren Verbindungen verarbeiten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert einen zusätzlichen `CreateSequenceRefused` -Fehlersubcode `netrm:ConnectionLimitReached`, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9774-166">B1503:When the service endpoint reaches its connection limit and cannot process new connections, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates an additional `CreateSequenceRefused` fault subcode, `netrm:ConnectionLimitReached`, as shown in the following example.</span></span>  
  
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
  
### <a name="ws-addressing-faults"></a><span data-ttu-id="a9774-167">WS-Adressierungsfehler</span><span class="sxs-lookup"><span data-stu-id="a9774-167">WS-Addressing Faults</span></span>  
 <span data-ttu-id="a9774-168">Da zuverlässiges WS-Messaging WS-Adressierung verwendet, kann die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierung von zuverlässigem WS-Messaging WS-Adressierungsfehler generieren.</span><span class="sxs-lookup"><span data-stu-id="a9774-168">Because WS-Reliable Messaging uses WS-Addressing, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-Reliable Messaging implementation may generate WS-Addressing faults.</span></span> <span data-ttu-id="a9774-169">In diesem Abschnitt werden die WS-Adressierungsfehler erläutert, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explizit auf der Ebene des zuverlässigen WS-Messaging generiert.</span><span class="sxs-lookup"><span data-stu-id="a9774-169">This section covers the WS-Addressing faults that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explicitly generates at the WS-Reliable Messaging layer:</span></span>  
  
-   <span data-ttu-id="a9774-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert den Fehler, die Nachricht adressiert Header erforderlich, wenn eine der folgenden Aussagen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="a9774-170">B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Message Addressing Header Required when one of the following is true:</span></span>  
  
    -   <span data-ttu-id="a9774-171">Eine Nachricht hat keinen `Sequence`-Header und keinen `Action`-Header.</span><span class="sxs-lookup"><span data-stu-id="a9774-171">A message is missing a `Sequence` header and an `Action` header.</span></span>  
  
    -   <span data-ttu-id="a9774-172">Eine `CreateSequence`-Nachricht hat keinen `MessageId`-Header.</span><span class="sxs-lookup"><span data-stu-id="a9774-172">A `CreateSequence` message is missing a `MessageId` header.</span></span>  
  
    -   <span data-ttu-id="a9774-173">Eine `CreateSequence`-Nachricht hat keinen `ReplyTo`-Header.</span><span class="sxs-lookup"><span data-stu-id="a9774-173">A `CreateSequence` message is missing a `ReplyTo` header.</span></span>  
  
-   <span data-ttu-id="a9774-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert den Fehler, die Aktion nicht unterstützt, als Antwort auf eine Nachricht, die fehlen einer `Sequence` Header und verfügt über eine `Action` Header, der nicht erkannten in der WS-ReliableMessaging-Spezifikation ist.</span><span class="sxs-lookup"><span data-stu-id="a9774-174">B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Action Not Supported in reply to a message that is missing a `Sequence` header and has an `Action` header that is not a recognized in the WS-Reliable Messaging specification.</span></span>  
  
-   <span data-ttu-id="a9774-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert den Fehler, der Endpunkt nicht verfügbar, um anzugeben, dass der Endpunkt die Sequenz basierend auf der Prüfung nicht verarbeitet werden die `CreateSequence` Nachricht Adressheader.</span><span class="sxs-lookup"><span data-stu-id="a9774-175">B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates the fault Endpoint Unavailable to indicate that the endpoint does not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>  
  
## <a name="protocol-composition"></a><span data-ttu-id="a9774-176">Protokollkomposition</span><span class="sxs-lookup"><span data-stu-id="a9774-176">Protocol Composition</span></span>  
  
### <a name="composition-with-ws-addressing"></a><span data-ttu-id="a9774-177">Komposition mit WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="a9774-177">Composition with WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-178"> unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung&#160;2004/08 [WS-ADDR] und die Empfehlungen für W3C die WS-Addressierung&#160;1.0 [WS-WS-ADDR-CORE] und [WS-ADDR-SOAP].</span><span class="sxs-lookup"><span data-stu-id="a9774-178"> supports two versions of WS-Addressing: WS-Addressing 2004/08 [WS-ADDR] and W3C WS-Addressing 1.0 Recommendations [WS-ADDR-CORE] and [WS-ADDR-SOAP].</span></span>  
  
 <span data-ttu-id="a9774-179">Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die verwendete Version der WS-Adressierung nicht ein.</span><span class="sxs-lookup"><span data-stu-id="a9774-179">While the WS-Reliable Messaging specification mentions only WS-Addressing 2004/08, it does not restrict the WS-Addressing version to be used.</span></span> <span data-ttu-id="a9774-180">Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:</span><span class="sxs-lookup"><span data-stu-id="a9774-180">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="a9774-181">R2101: sowohl WS-Adressierung 2004/08 und WS-Adressierung 1.0 mit WS-Reliable Messaging verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9774-181">R2101:Both WS-Addressing 2004/08 and WS-Addressing 1.0 can be used with WS-Reliable Messaging.</span></span>  
  
-   <span data-ttu-id="a9774-182">R2102:A einzelne Version der WS-Adressierung muss verwendet werden, in der gesamten einer angegebenen WS-Reliable Messaging-Sequenz oder ein Paar umgekehrter Sequenzen korreliert mit der `wsrm:Offer` Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="a9774-182">R2102:A single version of WS-Addressing must be used throughout a given WS-Reliable Messaging sequence or a pair of converse sequences correlated by using the `wsrm:Offer` mechanism.</span></span>  
  
### <a name="composition-with-soap"></a><span data-ttu-id="a9774-183">Komposition mit SOAP</span><span class="sxs-lookup"><span data-stu-id="a9774-183">Composition with SOAP</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-184"> unterstützt die Verwendung sowohl von SOAP&#160;1.1 als auch von SOAP&#160;1.2 mit zuverlässigem WS-Messaging.</span><span class="sxs-lookup"><span data-stu-id="a9774-184"> supports use of both SOAP 1.1 and SOAP 1.2 with WS-Reliable Messaging.</span></span>  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a><span data-ttu-id="a9774-185">Komposition mit WS-Sicherheit und WS-SecureConversation</span><span class="sxs-lookup"><span data-stu-id="a9774-185">Composition with WS-Security and WS-SecureConversation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-186"> bietet Schutz für die zuverlässigen WS-Messaging-Sequenzen durch die Verwendung einer sicheren Transportmethode (HTTPS), die Erstellung mit WS-Sicherheit und die Erstellung mit WS-Secure Conversation.</span><span class="sxs-lookup"><span data-stu-id="a9774-186"> provides protection for WS-Reliable Messaging sequences by using secure Transport (HTTPS), composition with WS-Security, and composition with WS-Secure Conversation.</span></span> <span data-ttu-id="a9774-187">Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:</span><span class="sxs-lookup"><span data-stu-id="a9774-187">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="a9774-188">R2301: Schützen Sie die Integrität einer WS-Reliable Messaging-Sequenz neben der Integrität und Vertraulichkeit einzelner Nachrichten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfordert, dass WS-Secure Conversation verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="a9774-188">R2301:To protect the integrity of a WS-Reliable Messaging sequence in addition to the integrity and confidentiality of individual messages, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] requires that WS-Secure Conversation must be used.</span></span>  
  
-   <span data-ttu-id="a9774-189">R2302:AWS-Secure Conversation-Sitzung muss vor dem Einrichten von WS-Reliable Messaging Sequence(s) eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="a9774-189">R2302:AWS-Secure Conversation session must be established prior to establishing WS-Reliable Messaging sequence(s).</span></span>  
  
-   <span data-ttu-id="a9774-190">R2303: Wenn die Lebensdauer einer zuverlässigen WS-Messaging-Sequenz die Lebensdauer der WS-Secure Conversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-Secure Conversation Renewal-Bindung erneuert werden.</span><span class="sxs-lookup"><span data-stu-id="a9774-190">R2303: If the WS-Reliable Messaging sequence lifetime exceeds the WS-Secure Conversation session’s lifetime, the `SecurityContextToken` established by using WS-Secure Conversation must be renewed by using the corresponding WS-Secure Conversation Renewal binding.</span></span>  
  
-   <span data-ttu-id="a9774-191">B2304:WS-Reliable Messaging-Sequenz oder ein paar umgekehrt korrelierte Sequenzen immer an eine einzelne WS-SecureConversation-Sitzung gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="a9774-191">B2304:WS-Reliable Messaging sequence or a pair of correlated converse sequences are always bound to a single WS-SecureConversation session.</span></span>  
  
     <span data-ttu-id="a9774-192">Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Quelle generiert das `wsse:SecurityTokenReference`-Element im Abschnitt Elementerweiterbarkeit der `CreateSequence`-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a9774-192">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] source generates the `wsse:SecurityTokenReference` element in the element extensibility section of the `CreateSequence` message.</span></span>  
  
-   <span data-ttu-id="a9774-193">R2305:when mit WS-Secure Conversation verfasst eine `CreateSequence` Nachricht darf die `wsse:SecurityTokenReference` Element.</span><span class="sxs-lookup"><span data-stu-id="a9774-193">R2305:When composed with WS-Secure Conversation, a `CreateSequence` message must contain the `wsse:SecurityTokenReference` element.</span></span>  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a><span data-ttu-id="a9774-194">Zuverlässige WS-Messaging WS-Richtlinienassertion</span><span class="sxs-lookup"><span data-stu-id="a9774-194">WS-Reliable Messaging WS-Policy Assertion</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-195"> verwendet die WS-Richtlinienassertion `wsrm:RMAssertion` des zuverlässigen WS-Messaging, um die Fähigkeiten von Endpunkten zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a9774-195"> uses WS-Reliable Messaging WS-Policy Assertion `wsrm:RMAssertion` to describe endpoints capabilities.</span></span> <span data-ttu-id="a9774-196">Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:</span><span class="sxs-lookup"><span data-stu-id="a9774-196">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="a9774-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fügt die `wsrm:RMAssertion`-WS-Richtlinienassertion an `wsdl:binding`-Elemente an.</span><span class="sxs-lookup"><span data-stu-id="a9774-197">B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attaches `wsrm:RMAssertion` WS-Policy Assertion to `wsdl:binding` elements.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-198"> unterstützt sowohl das Anfügen an `wsdl:binding`-Elemente als auch an `wsdl:port`-Elemente.</span><span class="sxs-lookup"><span data-stu-id="a9774-198"> supports both attachments to `wsdl:binding` and `wsdl:port` elements.</span></span>  
  
-   <span data-ttu-id="a9774-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt die folgenden optionalen Eigenschaften der zuverlässigen WS-Messaging-Assertion und ermöglicht ihre Steuerung über das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] von `ReliableMessagingBindingElement`:</span><span class="sxs-lookup"><span data-stu-id="a9774-199">B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports the following optional properties of WS-Reliable Messaging assertion and provides control over them on the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]`ReliableMessagingBindingElement`:</span></span>  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     <span data-ttu-id="a9774-200">Nachfolgend finden Sie ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a9774-200">The following is an example.</span></span>  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a><span data-ttu-id="a9774-201">Zuverlässige WS-Messaging-Erweiterung zur Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="a9774-201">Flow Control WS-Reliable Messaging Extension</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-202"> verwendet die Erweiterbarkeit des zuverlässigen WS-Messaging, um optional eine bessere Steuerung des Sequenznachrichtenflusses zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a9774-202"> uses WS-Reliable Messaging extensibility to provide optional additional tighter control over sequence message flow.</span></span>  
  
 <span data-ttu-id="a9774-203">Flusssteuerung aktiviert ist, durch Festlegen der `ReliableSessionBindingElement`des `FlowControlEnabled``bool` Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="a9774-203">Flow control is enabled by setting the `ReliableSessionBindingElement`’s `FlowControlEnabled``bool` property to `true`.</span></span> <span data-ttu-id="a9774-204">Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:</span><span class="sxs-lookup"><span data-stu-id="a9774-204">The following is a list of constraints that apply to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="a9774-205">B4001: Wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ein `netrm:BufferRemaining`-Element in der Elementerweiterbarkeit des `SequenceAcknowledgement`-Headers.</span><span class="sxs-lookup"><span data-stu-id="a9774-205">B4001: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates a `netrm:BufferRemaining` element in the element extensibility of the `SequenceAcknowledgement` header.</span></span>  
  
-   <span data-ttu-id="a9774-206">B4002: Wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, erfordert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kein `netrm:BufferRemaining`-Element im `SequenceAcknowledgement`-Header, wie im folgenden Beispiel zu sehen:</span><span class="sxs-lookup"><span data-stu-id="a9774-206">B4002: When Reliable Messaging Flow Control is enabled, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not require a `netrm:BufferRemaining` element to be present in `SequenceAcknowledgement` header, as shown in the following example.</span></span>  
  
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
  
-   <span data-ttu-id="a9774-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet `netrm:BufferRemaining`, um anzugeben, wie viele neue Nachrichten das zuverlässige Messaging-Ziel puffern kann.</span><span class="sxs-lookup"><span data-stu-id="a9774-207">B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses `netrm:BufferRemaining` to indicate how many new messages the Reliable Messaging Destination can buffer.</span></span>  
  
-   <span data-ttu-id="a9774-208">B4004: die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zuverlässige Messaging-Dienst drosselt die Anzahl der Nachrichten, die übertragen werden, wenn die Anwendung für zuverlässiges Messaging-Ziel schnell Nachrichten empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="a9774-208">B4004:The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging Service throttles the number of messages transmitted when the Reliable Messaging destination application cannot receive messages quickly.</span></span> <span data-ttu-id="a9774-209">Das zuverlässige Messaging-Ziel puffert Nachrichten, und der Wert des Elements sinkt auf&#160;0.</span><span class="sxs-lookup"><span data-stu-id="a9774-209">The Reliable Messaging destination buffers messages and the element’s value drops to 0.</span></span>  
  
-   <span data-ttu-id="a9774-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert `netrm:BufferRemaining`-Ganzzahlwerte zwischen&#160;0 und 4096 einschließlich und liest Ganzzahlwerte zwischen&#160;0 und dem `xs:int`-Wert von `maxInclusive` (214748364) einschließlich.</span><span class="sxs-lookup"><span data-stu-id="a9774-210">B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generates `netrm:BufferRemaining` integer values between 0 and 4096 inclusive, and reads integer values between 0 and `xs:int`’s `maxInclusive` value 214748364 inclusive.</span></span>  
  
## <a name="message-exchange-patterns"></a><span data-ttu-id="a9774-211">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="a9774-211">Message Exchange Patterns</span></span>  
 <span data-ttu-id="a9774-212">In diesem Abschnitt wird das Verhalten von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bei Verwendung von zuverlässigem WS-Messaging für verschiedene Nachrichtenaustauschmuster beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a9774-212">This section describes [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]'s behavior when WS-Reliable Messaging is used for different Message Exchange Patterns.</span></span> <span data-ttu-id="a9774-213">Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:</span><span class="sxs-lookup"><span data-stu-id="a9774-213">For each Message Exchange Pattern the following two deployments scenarios are considered:</span></span>  
  
-   <span data-ttu-id="a9774-214">Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall, der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.</span><span class="sxs-lookup"><span data-stu-id="a9774-214">Non-Addressable Initiator: Initiator is behind firewall; Responder can deliver messages to Initiator only on HTTP responses.</span></span>  
  
-   <span data-ttu-id="a9774-215">Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="a9774-215">Addressable Initiator: Initiator and Responder both can be sent HTTP requests; in other words, two converse HTTP connections can be established.</span></span>  
  
### <a name="one-way-non-addressable-initiator"></a><span data-ttu-id="a9774-216">Unidirektionaler, nicht adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="a9774-216">One-way, Non-addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a9774-217">Bindung</span><span class="sxs-lookup"><span data-stu-id="a9774-217">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-218"> stellt ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen HTTP-Kanal bereit.</span><span class="sxs-lookup"><span data-stu-id="a9774-218"> provides a one-way message exchange pattern using one sequence over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-219"> verwendet die HTTP-Anforderungen, um alle Nachrichten vom RMS zum RMD zu übertragen, und die HTTP-Antworten, um alle Nachrichten vom RMD zum RMS zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="a9774-219"> uses the HTTP requests to transmit all messages from the RMS to the RMD and the HTTP response to transmit all messages from the RMD to the RMS.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a9774-220">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="a9774-220">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a9774-221">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht ohne Angebot.</span><span class="sxs-lookup"><span data-stu-id="a9774-221">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="a9774-222">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht kein Angebot aufweist.</span><span class="sxs-lookup"><span data-stu-id="a9774-222">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="a9774-223">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter antwortet mit einer `CreateSequence`-Nachricht auf die `CreateSequenceResponse`-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a9774-223">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="sequenceacknowledgement"></a><span data-ttu-id="a9774-224">SequenceAcknowledgement</span><span class="sxs-lookup"><span data-stu-id="a9774-224">SequenceAcknowledgement</span></span>  
 <span data-ttu-id="a9774-225">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator erstellt Bestätigungen als Antwort auf alle Nachrichten mit Ausnahme von `CreateSequence`-Nachrichten und Fehlernachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9774-225">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator processes acknowledgements on the reply of all messages except the `CreateSequence` message and fault messages.</span></span> <span data-ttu-id="a9774-226">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter generiert eine eigenständige Bestätigung in der Antwort auf Sequenzen und auf `AckRequested`-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9774-226">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder always generates a stand-alone acknowledgement in the response to both sequence and `AckRequested` messages.</span></span>  
  
#### <a name="terminatesequence-message"></a><span data-ttu-id="a9774-227">TerminateSequence-Nachricht</span><span class="sxs-lookup"><span data-stu-id="a9774-227">TerminateSequence message</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-228"> behandelt `TerminateSequence` als unidirektionalen Vorgang, was bedeutet, dass die HTTP-Antwort einen leeren Textbereich und den HTTP-Statuscode&amp;#160;202 hat.</span><span class="sxs-lookup"><span data-stu-id="a9774-228"> treats `TerminateSequence` as a one-way operation, meaning the HTTP response has an empty body and HTTP 202 status code.</span></span>  
  
### <a name="one-way-addressable-initiator"></a><span data-ttu-id="a9774-229">Unidirektionaler, adressierbarer Initiator</span><span class="sxs-lookup"><span data-stu-id="a9774-229">One Way, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a9774-230">Bindung</span><span class="sxs-lookup"><span data-stu-id="a9774-230">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-231"> bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung eines eingehenden und eines ausgehenden HTTP-Kanals.</span><span class="sxs-lookup"><span data-stu-id="a9774-231"> provides a one-way message exchange pattern using one sequence over an inbound and an outbound Http channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-232"> verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9774-232"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a9774-233">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="a9774-233">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a9774-234">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="a9774-234">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a9774-235">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht ohne Angebot.</span><span class="sxs-lookup"><span data-stu-id="a9774-235">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with no offer.</span></span> <span data-ttu-id="a9774-236">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht kein Angebot aufweist.</span><span class="sxs-lookup"><span data-stu-id="a9774-236">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has no offer before creating a sequence.</span></span> <span data-ttu-id="a9774-237">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter sendet die `CreateSequenceResponse`-Nachricht über eine HTTP-Anforderung, die mit dem `ReplyTo`-Endpunktverweis adressiert wird.</span><span class="sxs-lookup"><span data-stu-id="a9774-237">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder transmits the `CreateSequenceResponse` message on an HTTP request addressed with the `ReplyTo` endpoint reference.</span></span>  
  
### <a name="duplex-addressable-initiator"></a><span data-ttu-id="a9774-238">Adressierbarer Duplex-Initiator</span><span class="sxs-lookup"><span data-stu-id="a9774-238">Duplex, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a9774-239">Bindung</span><span class="sxs-lookup"><span data-stu-id="a9774-239">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-240"> bietet ein vollständig asynchrones bidirektionales Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="a9774-240"> provides a fully asynchronous two-way message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-241"> verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9774-241"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a9774-242">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="a9774-242">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a9774-243">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="a9774-243">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a9774-244">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht mit einem Angebot.</span><span class="sxs-lookup"><span data-stu-id="a9774-244">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="a9774-245">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht ein Angebot aufweist.</span><span class="sxs-lookup"><span data-stu-id="a9774-245">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-246"> sendet die `CreateSequenceResponse` über eine HTTP-Anforderung, die an den `CreateSequence`-Endpunktverweis von `ReplyTo` adressiert wird.</span><span class="sxs-lookup"><span data-stu-id="a9774-246"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="sequence-lifetime"></a><span data-ttu-id="a9774-247">Sequenzlebensdauer</span><span class="sxs-lookup"><span data-stu-id="a9774-247">Sequence Lifetime</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-248"> behandelt die beiden Sequenzen als eine Vollduplexsitzung.</span><span class="sxs-lookup"><span data-stu-id="a9774-248"> treats the two sequences as one fully duplex session.</span></span>  
  
 <span data-ttu-id="a9774-249">Nach dem Generieren eines Fehlers für eine Sequenz erwartet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], dass der Remoteendpunkt einen Fehler für beide Sequenzen auslöst.</span><span class="sxs-lookup"><span data-stu-id="a9774-249">Upon generating a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] expects the remote endpoint to fault both sequences.</span></span> <span data-ttu-id="a9774-250">Nach dem Lesen eines Fehlers, der zum Fehlschlagen einer Sequenz führt, löst [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen Fehler für beide Sequenzen aus.</span><span class="sxs-lookup"><span data-stu-id="a9774-250">Upon reading a fault that faults one sequence, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] faults both sequences.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-251"> kann seine ausgehende Sequenz schließen und damit fortfahren, Nachrichten in seiner eingehenden Sequenz zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a9774-251"> can close its outbound sequence and continue to process messages on its inbound sequence.</span></span> <span data-ttu-id="a9774-252">Umgekehrt kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auch das Schließen der eingehenden Sequenz durchführen und weiter Nachrichten in seiner ausgehenden Sequenz senden.</span><span class="sxs-lookup"><span data-stu-id="a9774-252">Conversely, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] can process the close of the inbound sequence and continue to send messages on its outbound sequence.</span></span>  
  
### <a name="request-reply-non-addressable-initiator"></a><span data-ttu-id="a9774-253">Nicht adressierbarer Anforderung-Antwort-Initiator</span><span class="sxs-lookup"><span data-stu-id="a9774-253">Request-Reply, Non-Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a9774-254">Bindung</span><span class="sxs-lookup"><span data-stu-id="a9774-254">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-255"> bietet ein unidirektionales Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="a9774-255"> provides a one-way and request-reply message exchange pattern using two sequences over one HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-256"> verwendet HTTP-Anforderungen, um Anforderungssequenznachrichten zu übertragen, und HTTP-Antworten, um Antwortsequenznachrichten zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="a9774-256"> uses the HTTP requests to transmit the request sequence’s messages and uses the HTTP responses to transmit the reply sequence’s messages.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a9774-257">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="a9774-257">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a9774-258">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht mit einem Angebot.</span><span class="sxs-lookup"><span data-stu-id="a9774-258">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="a9774-259">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht ein Angebot aufweist.</span><span class="sxs-lookup"><span data-stu-id="a9774-259">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> <span data-ttu-id="a9774-260">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter antwortet mit einer `CreateSequence`-Nachricht auf die `CreateSequenceResponse`-Anforderung.</span><span class="sxs-lookup"><span data-stu-id="a9774-260">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the `CreateSequence` request with a `CreateSequenceResponse` message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="a9774-261">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="a9774-261">One-way Message</span></span>  
 <span data-ttu-id="a9774-262">Um ein unidirektionales Nachrichtenaustauschprotokoll erfolgreich durchzuführen, überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine eigenständige `SequenceAcknowledgement`-Nachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="a9774-262">To complete a one-way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a standalone `SequenceAcknowledgement` message on the HTTP response.</span></span> <span data-ttu-id="a9774-263">Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.</span><span class="sxs-lookup"><span data-stu-id="a9774-263">The `SequenceAcknowledgement` must acknowledge the message transmitted.</span></span>  
  
 <span data-ttu-id="a9774-264">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter kann mit einer Bestätigung, einem Fehler oder einer Antwort mit leerem Textbereich und dem HTTP-Statuscode&#160;202 auf die Anforderung reagieren.</span><span class="sxs-lookup"><span data-stu-id="a9774-264">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an acknowledgement, a fault, or a response with an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="two-way-messages"></a><span data-ttu-id="a9774-265">Bidirektionale Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a9774-265">Two Way Messages</span></span>  
 <span data-ttu-id="a9774-266">Um ein bidirektionales Nachrichtenaustauschprotokoll erfolgreich durchzuführen, überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine Antwortsequenznachricht in der HTTP-Antwort.</span><span class="sxs-lookup"><span data-stu-id="a9774-266">To complete a two way message exchange protocol successfully, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator transmits a request sequence message on the HTTP request and receives a reply sequence message on the HTTP response.</span></span> <span data-ttu-id="a9774-267">Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.</span><span class="sxs-lookup"><span data-stu-id="a9774-267">The response must carry a `SequenceAcknowledgement` acknowledging the request sequence message transmitted.</span></span>  
  
 <span data-ttu-id="a9774-268">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter kann mit einer Anwendungsantwort, einem Fehler oder einer Antwort mit leerem Textbereich und dem HTTP-Statuscode "202" auf die Anforderung reagieren.</span><span class="sxs-lookup"><span data-stu-id="a9774-268">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder can reply to the request with an application reply, a fault or a response with an empty body and HTTP 202 status code.</span></span>  
  
 <span data-ttu-id="a9774-269">Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.</span><span class="sxs-lookup"><span data-stu-id="a9774-269">Because of the presence of one-way messages and the timing of application replies, the request sequence message’s sequence number and the response message’s sequence number have no correlation.</span></span>  
  
#### <a name="retrying-replies"></a><span data-ttu-id="a9774-270">Wiederholen von Antworten</span><span class="sxs-lookup"><span data-stu-id="a9774-270">Retrying Replies</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-271"> nutzt die HTTP-Anforderung-Antwort-Korrelation für das bidirektionale Nachrichtenaustauschprotokoll.</span><span class="sxs-lookup"><span data-stu-id="a9774-271"> relies on HTTP request-reply correlation for two-way message exchange protocol correlation.</span></span> <span data-ttu-id="a9774-272">Daher wiederholt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht auch dann weiter, wenn die Anforderungssequenznachricht bestätigt wird. Er hört erst dann auf, wenn die HTTP-Antwort eine Bestätigung, eine Benutzernachricht oder einen Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="a9774-272">Because of this, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator does not stop retrying a request sequence message when the request sequence message is acknowledged but rather when the HTTP response carries an acknowledgement, user message, or fault.</span></span> <span data-ttu-id="a9774-273">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter wiederholt die Antworten auf den HTTP-Anforderungsabschnitt der Anforderung, mit der die Antwort korreliert ist.</span><span class="sxs-lookup"><span data-stu-id="a9774-273">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder retries replies on the HTTP request leg of the request to which the reply is correlated.</span></span>  
  
#### <a name="lastmessage-exchange"></a><span data-ttu-id="a9774-274">LastMessage-Austausch</span><span class="sxs-lookup"><span data-stu-id="a9774-274">LastMessage Exchange</span></span>  
 <span data-ttu-id="a9774-275">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert und überträgt eine letzte Nachricht ohne Text auf den HTTP-Anforderungsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="a9774-275">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits an empty bodied last message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-276"> erfordert eine Antwort, ignoriert jedoch diese Antwortnachricht.</span><span class="sxs-lookup"><span data-stu-id="a9774-276"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="a9774-277">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter reagiert auf die letzte Anforderungssequenznachricht ohne Text mit einer letzten Antwortsequenznachricht ohne Text.</span><span class="sxs-lookup"><span data-stu-id="a9774-277">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s empty-bodied last message with the reply sequence’s empty-bodied last message.</span></span>  
  
 <span data-ttu-id="a9774-278">Wenn der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter eine letzte Nachricht empfängt, in der der Aktions-URI nicht http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage lautet, antwortet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit einer letzten Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a9774-278">If the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder receives a last message in which the action URI is not http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] replies with a last message.</span></span> <span data-ttu-id="a9774-279">Im Fall eines bidirektionalen Nachrichtenaustauschprotokolls enthält die letzte Nachricht die Anwendungsnachricht, im Falle eines unidirektionalen Nachrichtenaustauschprotokolls ist die letzte Nachricht leer.</span><span class="sxs-lookup"><span data-stu-id="a9774-279">In the case of a two-way message exchange protocol, the last message carries the application message; in the case of a one-way message exchange protocol, the last message is empty.</span></span>  
  
 <span data-ttu-id="a9774-280">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter benötigt keine Bestätigung für die letzte Antwortsequenznachricht ohne Text.</span><span class="sxs-lookup"><span data-stu-id="a9774-280">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder does not require an acknowledgement for the reply sequence’s empty-bodied last message.</span></span>  
  
#### <a name="terminatesequence-exchange"></a><span data-ttu-id="a9774-281">TerminateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="a9774-281">TerminateSequence Exchange</span></span>  
 <span data-ttu-id="a9774-282">Wenn alle Anforderungen eine gültige Antwort erhalten haben, generiert und überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator die `TerminateSequence`-Nachricht der Anforderungssequenz auf den HTTP-Anforderungsabschnitt.</span><span class="sxs-lookup"><span data-stu-id="a9774-282">When all requests have received a valid reply, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates and transmits the request sequence’s `TerminateSequence` message on the HTTP request leg.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-283"> erfordert eine Antwort, ignoriert jedoch diese Antwortnachricht.</span><span class="sxs-lookup"><span data-stu-id="a9774-283"> requires a response but ignores the actual response message.</span></span> <span data-ttu-id="a9774-284">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter reagiert auf die `TerminateSequence`-Nachricht der Anforderungssequenz mit einer `TerminateSequence`-Nachricht der Antwortsequenz.</span><span class="sxs-lookup"><span data-stu-id="a9774-284">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder replies to the request sequence’s `TerminateSequence` message with the reply sequence’s `TerminateSequence` message.</span></span>  
  
 <span data-ttu-id="a9774-285">In einer normalen Abschlusssequenz enthalten beide `TerminateSequence`-Nachrichten einen vollständigen Bereich von `SequenceAcknowledgement`.</span><span class="sxs-lookup"><span data-stu-id="a9774-285">In a normal shutdown sequence, both `TerminateSequence` messages carry a full range `SequenceAcknowledgement`.</span></span>  
  
### <a name="requestreply-addressable-initiator"></a><span data-ttu-id="a9774-286">Adressierbarer Anforderung/Antwort-Initiator</span><span class="sxs-lookup"><span data-stu-id="a9774-286">Request/Reply, Addressable Initiator</span></span>  
  
#### <a name="binding"></a><span data-ttu-id="a9774-287">Bindung</span><span class="sxs-lookup"><span data-stu-id="a9774-287">Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-288"> bietet ein Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal.</span><span class="sxs-lookup"><span data-stu-id="a9774-288"> provides a request-reply message exchange pattern using two sequences over an inbound and an outbound HTTP channel.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-289"> verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a9774-289"> uses the HTTP requests to transmit all messages.</span></span> <span data-ttu-id="a9774-290">Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.</span><span class="sxs-lookup"><span data-stu-id="a9774-290">All HTTP responses have an empty body and HTTP 202 status code.</span></span>  
  
#### <a name="createsequence-exchange"></a><span data-ttu-id="a9774-291">CreateSequence-Austausch</span><span class="sxs-lookup"><span data-stu-id="a9774-291">CreateSequence Exchange</span></span>  
 <span data-ttu-id="a9774-292">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht mit einem Angebot.</span><span class="sxs-lookup"><span data-stu-id="a9774-292">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator generates a `CreateSequence` message with an offer.</span></span> <span data-ttu-id="a9774-293">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht ein Angebot aufweist.</span><span class="sxs-lookup"><span data-stu-id="a9774-293">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the `CreateSequence` has an offer before creating a sequence.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="a9774-294"> sendet die `CreateSequenceResponse` über eine HTTP-Anforderung, die an den `CreateSequence`-Endpunktverweis von `ReplyTo` adressiert wird.</span><span class="sxs-lookup"><span data-stu-id="a9774-294"> sends the `CreateSequenceResponse` on the HTTP request addressed to the `CreateSequence`’s `ReplyTo` endpoint reference.</span></span>  
  
#### <a name="requestreply-correlation"></a><span data-ttu-id="a9774-295">Anforderung/Antwort-Korrelation</span><span class="sxs-lookup"><span data-stu-id="a9774-295">Request/Reply Correlation</span></span>  
 <span data-ttu-id="a9774-296">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator stellt sicher, dass alle Anwendungsanforderungsnachrichten eine `MessageId` und einen `ReplyTo`-Endpunktverweis enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9774-296">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator ensures all application request messages bear a `MessageId` and a `ReplyTo` endpoint reference.</span></span> <span data-ttu-id="a9774-297">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator wendet den `CreateSequence`-Endpunktverweis der `ReplyTo`-Nachricht für jede Anwendungsanforderungsnachricht an.</span><span class="sxs-lookup"><span data-stu-id="a9774-297">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Initiator applies the `CreateSequence` message’s `ReplyTo` endpoint reference on each application request message.</span></span> <span data-ttu-id="a9774-298">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter erfordert, dass alle Anwendungsanforderungsnachrichten eine `MessageId` und einen `ReplyTo`-Endpunktverweis enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9774-298">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder requires that incoming request messages bear a `MessageId` and a `ReplyTo`.</span></span> <span data-ttu-id="a9774-299">Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt sicher, dass die URIs der Endpunktverweise der `CreateSequence`-Nachrichten und aller Anwendungsanforderungsnachrichten identisch sind.</span><span class="sxs-lookup"><span data-stu-id="a9774-299">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Responder ensures that the endpoint reference’s URI of both the `CreateSequence` and all application request messages are identical.</span></span>
