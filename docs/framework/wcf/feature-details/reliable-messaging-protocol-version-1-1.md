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
# <a name="reliable-messaging-protocol-version-11"></a>Zuverlässiges Messaging-Protokoll, Version 1,1
In diesem Thema werden [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Implementierungsdetails für das WS-ReliableMessaging-Protokoll in der Version 1.1 vom Februar 2007 beschrieben, die für die Interoperation mithilfe des HTTP-Transports erforderlich sind. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] orientiert sich an der WS-ReliableMessaging-Spezifikation mit den in diesem Thema erläuterten Einschränkungen und Klarstellungen. Beachten Sie, dass das zuverlässige WS-Messaging-Protokoll in der Version&#160;1.1 ab [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] implementiert ist.  
  
 Das zuverlässige WS-Messaging-Protokoll vom Februar&#160;2007 ist in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durch das <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> implementiert.  
  
 Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:  
  
-   Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert  
  
-   Beantworter: der Dienst, der die Anforderungen des Initiators empfängt  
  
 In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.  
  
|Präfix|Namespace|  
|-|-|  
|wsrm|http://docs.oasis-open.org/ws-rx/wsrm/200702|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
|wsrmp|http://docs.oasis-open.org/ws-rx/wsrmp/200702|  
|netrmp|http://schemas.microsoft.com/ws-rx/wsrmp/200702|  
|wsp|(Entweder WS-Policy&#160;1.2 oder WS-Policy&#160;1.5)|  
  
## <a name="messaging"></a>Messaging  
  
### <a name="sequence-creation"></a>Sequenzerstellung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert `CreateSequence`- und `CreateSequenceResponse`-Nachrichten, um eine zuverlässige Messaging-Sequenz einzurichten. Es gelten die folgenden Einschränkungen:  
  
-   B1101: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator verwendet den gleichen Endpunktverweis wie `CreateSequence`, `ReplyTo` und `AcksTo` der `Offer/Endpoint`-Nachricht.  
  
-   R1102: Die `AcksTo`-, `ReplyTo`- und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen über Adresswerte mit identischen Zeichenfolgendarstellungen verfügen, die sich oktettweise entsprechen.  
  
    -   Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überprüft, ob der URI-Teil der `AcksTo`-, `ReplyTo`- und `Endpoint`-Endpunktreferenzen identisch ist, bevor die Sequenz erstellt wird.  
  
-   R1103: Die `AcksTo`- und `ReplyTo` und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen den gleichen Satz an Verweisparametern aufweisen.  
  
    -   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geht davon aus, dass die Verweisparameter der `AcksTo`-, `ReplyTo`- und `Offer/Endpoint`-Endpunktverweise für `CreateSequence` identisch sind, erzwingt dies jedoch nicht, und verwendet Verweisparameter vom `ReplyTo`-Endpunktverweis für Bestätigungen und Nachrichten umgekehrter Sequenz.  
  
-   B1104: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert das optionale `Expires`-Element oder `Offer/Expires`-Element in der `CreateSequence`-Nachricht nicht.  
  
-   B1105: Beim Zugriff auf die `CreateSequence`-Nachricht verwendet der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter den `Expires`-Wert im `CreateSequence`-Element als `Expires`-Wert im `CreateSequenceResponse`-Element. Andernfalls liest und ignoriert der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter die Werte für `Expires` und `Offer/Expires`.  
  
-   B1106: Bei Zugreifen auf die `CreateSequenceResponse`-Nachricht liest der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator den optionalen `Expires`-Wert, verwendet ihn aber nicht.  
  
-   B1107: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator und -Beantworter generieren immer das optionale `IncompleteSequenceBehavior`-Element im `CreateSequence/Offer`-Element und `CreateSequenceResponse`-Element.  
  
-   B1108: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet nur den `DiscardFollowingFirstGap`-Wert und den `NoDiscard`-Wert im `IncompleteSequenceBehavior`-Element.  
  
    -   Zuverlässiges WS-Messaging verwendet den `Offer`-Mechanismus, um die beiden umgekehrt korrelierten Sequenzen einzurichten, die eine Sitzung bilden.  
  
-   B1109: Wenn `CreateSequence` ein `Offer`-Element enthält, weist der unidirektionale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter die angebotene Sequenz ab, indem er mit einer `CreateSequenceResponse`-Nachricht ohne `Accept`-Element antwortet.  
  
-   B1110: Wenn ein zuverlässiger Messaging-Beantworter die angebotene Sequenz zurückweist, gibt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator einen Fehler für die neu erstellte Sequenz zurück.  
  
-   B1111: Wenn `CreateSequence` kein `Offer`-Element enthält, weist der bidirektionale [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter die angebotene Sequenz ab, indem er mit einem `CreateSequenceRefused`-Fehler antwortet.  
  
-   R1112: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, muss die `[address]`-Eigenschaft des `CreateSequenceResponse/Accept/AcksTo`-Endpunktverweises mit dem Ziel-URI der `CreateSequence`-Nachricht Byte für Byte übereinstimmen.  
  
-   R1113: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, müssen alle Nachrichten in beiden Sequenzen, die vom Initiator an den Beantworter übermittelt werden, an den gleichen Endpunktverweis gesendet werden.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet zuverlässiges WS-Messaging, um zuverlässige Sitzungen zwischen dem Initiator und dem Beantworter einzurichten. Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] WS-ReliableMessaging-Implementierung bietet eine zuverlässige Sitzung für unidirektionale, Anforderung-Antwort- und Vollduplex-Nachrichtenmuster. Der `Offer`-Mechanismus von zuverlässigem WS-Messaging für `CreateSequence` und `CreateSequenceResponse` ermöglicht es Ihnen, zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein für alle Nachrichtenendpunkte geeignetes Sitzungsprotokoll. Da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Sicherheit solcher Sitzungen sowie End-to-End-Schutz der Sitzungsintegrität garantiert, kann sichergestellt werden, dass alle an den gleichen Teilnehmer gerichteten Nachrichten am selben Ziel ankommen. Dadurch wird es zudem ermöglicht, Sequenzbestätigungen im Piggyback-Verfahren mit Anwendungsnachrichten zu übermitteln. Daher gelten die Einschränkungen R1102 R1112 und R1113 für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Ein Beispiel für eine `CreateSequence`-Nachricht.  
  
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
  
 Ein Beispiel für eine `CreateSequenceResponse`-Nachricht.  
  
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
  
### <a name="closing-a-sequence"></a>Schließen einer Sequenz  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die `CloseSequence`-Nachricht und die `CloseSequenceResponse`-Nachricht, um das von einer zuverlässigen Messaging-Quelle initiierte Schließen durchzuführen. Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging-Ziel initiiert das Schließen nicht, und die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable Messaging-Quelle unterstützt keinen Schließen-Vorgang, der von einem zuverlässigen Messaging-Ziel initiiert wird. Es gelten die folgenden Einschränkungen:  
  
-   B1201: Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable&#160;Messaging-Quelle sendet immer eine `CloseSequence`-Nachricht, um die Sequenz zu schließen.  
  
-   B1202: Die zuverlässige Messaging-Quelle wartet auf die Bestätigung aller Sequenznachrichten, bevor sie die `CloseSequence`-Nachricht sendet.  
  
-   B1203: Die zuverlässige Messaging-Quelle fügt immer das optionale `LastMsgNumber`-Element ein, es sei denn, die Sequenz enthält keine Nachrichten.  
  
-   R1204: Das zuverlässige Messaging-Ziel darf das Schließen nicht durch Senden einer `CloseSequence`-Nachricht initiieren.  
  
-   B1205: Bei Empfang einer `CloseSequence`-Nachricht betrachtet die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable&#160;Messaging-Quelle die Sequenz als unvollständig und sendet einen Fehler.  
  
 Ein Beispiel für eine `CloseSequence`-Nachricht.  
  
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
  
### <a name="sequence-termination"></a>Sequenzbeendigung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet hauptsächlich den `TerminateSequence/TerminateSequenceResponse`-Handshake, nachdem der `CloseSequence/CloseSequenceResponse`-Handshake abgeschlossen ist. Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable&#160;Messaging-Ziel initiiert die Beendigung nicht, und die zuverlässige Messaging-Quelle unterstützt keine Beendigung, die von einem zuverlässigen Messaging-Ziel initiiert wird. Es gelten die folgenden Einschränkungen:  
  
-   B1301: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator schickt die `TerminateSequence`-Nachricht erst nach dem erfolgreichen Abschluss des `CloseSequence/CloseSequenceResponse`-Handshake.  
  
-   R1302: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] überprüft, ob das `LastMsgNumber`-Element in allen `CloseSequence`-Nachrichten und `TerminateSequence`-Nachrichten für eine bestimmte Sequenz konsistent ist. Das bedeutet, dass `LastMsgNumber` entweder in keiner `CloseSequence`-Nachricht und keiner `TerminateSequence`-Nachricht vorhanden ist oder in allen `CloseSequence`-Nachrichten und `TerminateSequence`-Nachrichten vorhanden und identisch ist.  
  
-   B1303: Bei Empfang einer `TerminateSequence`-Nachricht nach dem `CloseSequence/CloseSequenceResponse`-Handshake antwortet das zuverlässige Messaging-Ziel mit einer `TerminateSequenceResponse`-Nachricht. Da die zuverlässige Messaging-Quelle die `TerminateSequence`-Nachricht erst nach Erhalt der letzten Bestätigung sendet, weiß das zuverlässige Messaging-Ziel mit Sicherheit, dass die Sequenz beendet ist, und fordert die Ressourcen unverzüglich zurück.  
  
-   B1304: Bei Empfang einer `TerminateSequence`-Nachricht vor dem `CloseSequence/CloseSequenceResponse`-Handshake antwortet das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Reliable&#160;Messaging-Ziel mit einer `TerminateSequenceResponse`-Nachricht. Wenn das zuverlässige Messaging-Ziel ermittelt, dass die Sequenz keine Inkonsistenzen aufweist, wartet das zuverlässige Messaging-Ziel so lange, wie vom Anwendungsziel angegeben, bevor es die Ressourcen zurückverlangt, um es dem Client zu ermöglichen, die letzte Bestätigung zu empfangen. Anderenfalls fordert das zuverlässige Messaging-Ziel die Ressourcen unverzüglich zurück und teilt dem Anwendungsziel mit, dass die Sequenz nicht ordnungsgemäß beendet wurde, indem es das `Faulted`-Ereignis auslöst.  
  
 Ein Beispiel für eine `TerminateSequence`-Nachricht.  
  
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
  
### <a name="sequences"></a>Sequenzen  
 Die folgende Liste enthält die Einschränkungen, die für Sequenzen gelten:  
  
-   B1401:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und greift auf die Sequenznummern, die nicht höher als `xs:long`des inklusive Maximalwert 9223372036854775807.  
  
 Ein Beispiel für einen `Sequence`-Header.  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a>Anfordern einer Bestätigung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet den `AckRequested`-Header als Keep-alive-Mechanismus.  
  
 Ein Beispiel für einen `AckRequested`-Header.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet den Piggyback-Mechanismus für die im zuverlässigen WS-Messaging bereitgestellten Sequenzbestätigungen. Es gelten die folgenden Einschränkungen:  
  
-   R1601: Wenn zwei umgekehrte Sequenzen eingerichtet sind mit den `Offer` Mechanismus, der `SequenceAcknowledgement` Header kann in jeder an den beabsichtigten Empfänger Anwendungsnachricht aufgenommen werden. Der Remoteendpunkt muss in der Lage sein, auf einen per Piggyback-Verfahren gesendeten `SequenceAcknowledgement`-Header zuzugreifen.  
  
-   B1602: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert keine `SequenceAcknowledgement`-Header, die `Nack`-Elemente enthalten. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] überprüft, ob jedes `Nack`-Element eine Sequenznummer enthält. Wenn dies nicht der Fall ist, werden das `Nack`-Element und sein Wert ignoriert.  
  
 Ein Beispiel für einen `SequenceAcknowledgement`-Header.  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging-Fehler  
 Die folgende Liste enthält die Einschränkungen, die für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierung der WS-ReliableMessaging-Fehler gelten. Es gelten die folgenden Einschränkungen:  
  
-   B1701: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert keine `MessageNumberRollover` Fehler.  
  
-   B1702: Wenn der Dienstendpunkt über SOAP&#160;1.2 seine Verbindungsgrenze erreicht und keine weiteren Verbindungen verarbeiten kann, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] den geschachtelten `CreateSequenceRefused`-Fehlersubcode `netrm:ConnectionLimitReached` (siehe folgendes Beispiel).  
  
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
  
### <a name="ws-addressing-faults"></a>WS-Adressierungsfehler  
 Da zuverlässiges WS-Messaging die WS-Adressierung verwendet, generiert und überträgt die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierung möglicherweise WS-Adressierungsfehler. In diesem Abschnitt werden die WS-Adressierungsfehler erläutert, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explizit auf der WS-ReliableMessaging-Schicht generiert und überträgt.  
  
-   B1801:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und überträgt die `Message Addressing Header Required` fehl, wenn eine der folgenden Aussagen zutrifft:  
  
    -   Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `MessageId`-Header.  
  
    -   Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `ReplyTo`-Header.  
  
    -   Bei einer Nachricht vom Typ `CreateSequenceResponse`, `CloseSequenceResponse` oder `TerminateSequenceResponse` fehlt ein `RelatesTo`-Header.  
  
-   B1802:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und überträgt die `Endpoint Unavailable` Fehler, um anzugeben, dass es kein Endpunkt gelauscht, die die Sequenz basierend auf der Prüfung der Adressierungsheader in verarbeiten kann die `CreateSequence` Nachricht.  
  
## <a name="protocol-composition"></a>Protokollkomposition  
  
### <a name="composition-with-ws-addressing"></a>Komposition mit WS-Adressierung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung&#160;2004/08 [WS-ADDR] und die Empfehlungen für W3C die WS-Addressierung&#160;1.0 [WS-WS-ADDR-CORE] und [WS-ADDR-SOAP].  
  
 Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die Verwendung der WS-Adressierung nicht auf diese Version ein. Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:  
  
-   R2101: Sowohl WS-Adressierung&#160;2004/08 als auch WS-Adressierung&#160;1.0 können mit zuverlässigem WS-Messaging verwendet werden.  
  
-   R2102: Für eine gegebene WS-ReliableMessaging-Sequenz oder ein Paar umgekehrter Sequenzen, die mithilfe des `Offer`-Mechanismus korreliert wurden, darf nur eine Version der WS-Adressierung verwendet werden.  
  
### <a name="composition-with-soap"></a>Komposition mit SOAP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt die Verwendung sowohl von SOAP&#160;1.1 als auch von SOAP&#160;1.2 mit zuverlässigem WS-Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Komposition mit WS-Sicherheit und WS-SecureConversation  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet Schutz für die WS-ReliableMessaging-Sequenzen durch die Verwendung einer sicheren Transportmethode (HTTPS), die Erstellung mit WS-Sicherheit und die Erstellung mit WS-Secure Conversation. Das WS-ReliableMessaging&#160;1.1-Protokoll, das WS-Security&#160;1.1- und das WS-Secure Conversation&#160;1.3-Protokoll sollten zusammen verwendet werden. Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:  
  
-   R2301: Damit die Integrität einer WS-ReliableMessaging-Sequenz sowie die Integrität und Vertraulichkeit einzelner Nachrichten sichergestellt ist, muss WS-Secure Conversation für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet werden.  
  
-   R2302:AWS-Secure Conversation-Sitzung muss vor dem Einrichten von WS-ReliableMessaging Sequence(s) eingerichtet werden.  
  
-   R2303: Wenn die Lebensdauer einer WS-ReliableMessaging-Sequenz die Lebensdauer der WS-SecureConversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-SecureConversationRenewal-Bindung erneuert werden.  
  
-   B2304:WS-ReliableMessaging-Sequenz oder ein paar umgekehrt korrelierte Sequenzen immer an eine einzelne WS-SecureConversation-Sitzung gebunden sind.  
  
-   R2305: Wenn WS-Secure Conversation zur Erstellung verwendet wird, erfordert es der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter, dass die `CreateSequence`-Nachricht das `wsse:SecurityTokenReference`-Element und den `wsrm:UsesSequenceSTR`-Header enthält.  
  
 Ein Beispiel für einen `UsesSequenceSTR`-Header.  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a>Komposition mit SSL/TLS-Sitzungen  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt keine Komposition mit SSL/TLS-Sitzungen:  
  
-   B2401: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert den `wsrm:UsesSequenceSSL`-Header nicht.  
  
-   R2402: Ein zuverlässiger Messaging-Initiator darf keine `CreateSequence`-Nachricht mit einem `wsrm:UsesSequenceSSL`-Header an einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter senden.  
  
### <a name="composition-with-ws-policy"></a>Komposition mit WS-Policy  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt zwei Versionen von WS-Policy: WS-Policy&#160;1.2 und WS-Policy&#160;1.5.  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a>WS-ReliableMessaging WS-Richtlinienassertion  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die WS-Richtlinienassertion von zuverlässigem WS-Messaging, `wsrm:RMAssertion`, um die Fähigkeiten von Endpunkten zu beschreiben. Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:  
  
-   B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fügt die `wsrmn:RMAssertion`-WS-Richtlinienassertion an `wsdl:binding`-Elemente an. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt sowohl das Anfügen an `wsdl:binding`-Elemente als auch an `wsdl:port`-Elemente.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert nie das `wsp:Optional`-Tag.  
  
-   B3003: Beim Zugreifen auf die `wsrmp:RMAssertion`-WS-Richtlinienassertion ignoriert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] das `wsp:Optional`-Tag und behandelt die WS-RM-Richtlinie als obligatorisch.  
  
-   R3004: Da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine Erstellung mit SSL/TLS-Sitzungen durchführt, akzeptiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] keine Richtlinie mit `wsrmp:SequenceTransportSecurity`.  
  
-   B3005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert immer das `wsrmp:DeliveryAssurance`-Element.  
  
-   B3006: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gibt immer die `wsrmp:ExactlyOnce`-Zustellungszusicherung an.  
  
-   B3007: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und liest die folgenden Eigenschaften der WS-ReliableMessaging-Assertion und ermöglicht die Steuerung sie auf die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `ReliableSessionBindingElement`:  
  
    -   `netrmp:InactivityTimeout`  
  
    -   `netrmp:AcknowledgementInterval`  
  
     Ein Beispiel für eine `RMAssertion`.  
  
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
  
## <a name="flow-control-ws-reliablemessaging-extension"></a>WS-ReliableMessaging-Erweiterung zur Ablaufsteuerung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die WS-ReliableMessaging-Erweiterbarkeit, um die optionale stärkere Kontrolle über den Sequenznachrichtenfluss zu ermöglichen.  
  
 Flusssteuerung aktiviert ist, durch Festlegen der `ReliableSessionBindingElement`des `FlowControlEnabled``boolean` Eigenschaft `true`. Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:  
  
-   B4001: Wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ein `netrm:BufferRemaining`-Element in der Elementerweiterbarkeit des `SequenceAcknowledgement`-Headers, wie im folgenden Beispiel zu sehen ist:  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4002: Selbst wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, erfordert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kein `netrm:BufferRemaining`-Element im `SequenceAcknowledgement`-Header.  
  
-   B4003: Das [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ReliableMessaging-Ziel verwendet `netrm:BufferRemaining`, um anzugeben, wie viele neue Nachrichten es puffern kann.  
  
-   B4004:when Reliable Messaging flusssteuerung aktiviert ist, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zuverlässige Messaging-Quelle verwendet den Wert der `netrm:BufferRemaining` zu drosseln nachrichtenübertragung.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert `netrm:BufferRemaining`-Ganzzahlwerte zwischen&#160;0 und 4096 einschließlich und liest Ganzzahlwerte zwischen&#160;0 und dem `xs:int`-Wert von `maxInclusive` (214748364) einschließlich.  
  
## <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster  
 In diesem Abschnitt wird das Verhalten von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bei Verwendung von WS-ReliableMessaging für verschiedene Nachrichtenaustauschmuster beschrieben. Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:  
  
-   Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall; der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.  
  
-   Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.  
  
### <a name="one-way-non-addressable-initiator"></a>Unidirektionaler, nicht adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen HTTP-Kanal bereit. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen, um Nachrichten vom Initiator an den Beantworter zu übertragen, und HTTP-Antworten, um Nachrichten vom Beantworter an den Initiator zu übertragen.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht ohne `Offer`-Element in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse`-Nachricht in der HTTP-Antwort. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht ohne `Accept`-Element in der HTTP-Antwort.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator erstellt Bestätigungen als Antwort auf alle Nachrichten mit Ausnahme von `CreateSequence`-Nachrichten und Fehlernachrichten. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überträgt stets eine eigenständige Bestätigung als HTTP-Antwort auf alle Sequenzen und `AckRequested`-Nachrichten.  
  
#### <a name="closesequence-exchange"></a>CloseSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CloseSequence`-Nachricht in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse`-Nachricht in der HTTP-Antwort. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überträgt die `CloseSequenceResponse`-Nachricht in der HTTP-Antwort.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `TerminateSequence`-Nachricht in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse`-Nachricht in der HTTP-Antwort. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überträgt die `TerminateSequenceResponse`-Nachricht in der HTTP-Antwort.  
  
### <a name="one-way-addressable-initiator"></a>Unidirektionaler, adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen eingehenden und einen ausgehenden HTTP-Kanal. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht ohne `Offer`-Element in einer HTTP-Anforderung. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht ohne `Accept`-Element in einer HTTP-Anforderung.  
  
### <a name="duplex-addressable-initiator"></a>Adressierbarer Duplex-Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet ein vollständig asynchrones bidirektionales Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Request/Reply`, `Addressable`-Initiator kombinieren. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt sicher, dass `CreateSequence` ein `Offer`-Element enthält, erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht mit einem `Accept`-Element.  
  
#### <a name="sequence-lifetime"></a>Sequenzlebensdauer  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behandelt die zwei Sequenzen als eine Vollduplexsitzung.  
  
 Nach dem Generieren eines Fehlers für eine Sequenz erwartet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], dass der Remoteendpunkt einen Fehler für beide Sequenzen auslöst. Nach dem Lesen eines Fehlers, der zum Fehlschlagen einer Sequenz führt, löst [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen Fehler für beide Sequenzen aus.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann seine ausgehende Sequenz schließen und damit fortfahren, Nachrichten in seiner eingehenden Sequenz zu verarbeiten. Umgekehrt kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auch das Schließen der eingehenden Sequenz durchführen und weiter Nachrichten in seiner ausgehenden Sequenz senden.  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Anforderung-Antwort- und unidirektionaler, nicht adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet ein unidirektionales Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen, um Nachrichten vom Initiator an den Beantworter zu übertragen, und HTTP-Antworten, um Nachrichten vom Beantworter an den Initiator zu übertragen.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse`-Nachricht in der HTTP-Antwort. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht mit einem `Accept`-Element in der HTTP-Antwort.  
  
#### <a name="one-way-message"></a>Unidirektionale Nachricht  
 Um einen unidirektionalen Nachrichtenaustausch erfolgreich durchzuführen, überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine eigenständige `SequenceAcknowledgement`-Nachricht in der HTTP-Antwort. Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter kann mit einer Bestätigung, einem Fehler oder einer Antwort mit leerem Textbereich und dem HTTP-Statuscode 202 auf die Anforderung reagieren.  
  
#### <a name="two-way-messages"></a>Bidirektionale Nachrichten  
 Um ein bidirektionales Nachrichtenaustauschprotokoll erfolgreich durchzuführen, überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine Antwortsequenznachricht in der HTTP-Antwort. Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter kann mit einer Anwendungsantwort, einem Fehler oder einer Antwort mit leerem Textbereich und dem HTTP-Statuscode&#160;202 auf die Anforderung reagieren.  
  
 Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.  
  
#### <a name="retrying-replies"></a>Wiederholen von Antworten  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nutzt die HTTP-Anforderung-Antwort-Korrelation für das bidirektionale Nachrichtenaustauschprotokoll. Daher wiederholt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht auch dann weiter, wenn die Anforderungssequenznachricht bestätigt wird. Er hört erst dann auf, wenn die HTTP-Antwort eine `SequenceAcknowledgement`, eine Anwendungsantwort oder einen Fehler enthält. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter wiederholt die Antworten in der HTTP-Antwort auf die Anforderung, mit der die Antwort korreliert ist.  
  
#### <a name="closesequence-exchange"></a>CloseSequence-Austausch  
 Nach dem Empfang aller Antwortsequenznachrichten und Bestätigungen für alle unidirektionalen Anforderungssequenznachrichten überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine `CloseSequence`-Nachricht für die Anforderungssequenz in einer HTTP-Anforderung und erwartet die `CloseSequenceResponse` in der HTTP-Antwort.  
  
 Durch Schließen der Anforderungssequenz wird die Antwortsequenz implizit geschlossen. Das bedeutet, der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator fügt die abschließende `SequenceAcknowledgement` der Antwortsequenz in die `CloseSequence`-Nachricht ein, und die Antwortsequenz verfügt über keinen `CloseSequence`-Austausch.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt sicher, dass alle Antworten bestätigt werden, und überträgt die `CloseSequenceResponse`-Nachricht in der HTTP-Antwort.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch  
 Nach Empfang der `CloseSequenceResponse`-Nachricht überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine `TerminateSequence`-Nachricht für die Anforderungssequenz in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse` in der HTTP-Antwort.  
  
 Wie beim `CloseSequence`-Austausch wird durch Beendigung der Anforderungssequenz die Antwortsequenz implizit beendet. Das bedeutet, der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator fügt die abschließende `SequenceAcknowledgement` der Antwortsequenz in die `TerminateSequence`-Nachricht ein, und die Antwortsequenz verfügt über keinen `TerminateSequence`-Austausch.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überträgt die `TerminateSequenceResponse`-Nachricht in der HTTP-Antwort.  
  
### <a name="requestreply-addressable-initiator"></a>Adressierbarer Anforderung/Antwort-Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet ein Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Duplex, Addressable`-Initiator kombinieren. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator überträgt eine `CreateSequence`-Nachricht mit einem `Offer`-Element in einer HTTP-Anforderung. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt sicher, dass `CreateSequence` ein `Offer`-Element enthält, erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse`-Nachricht mit einem `Accept`-Element.  
  
#### <a name="requestreply-correlation"></a>Anforderung/Antwort-Korrelation  
 Folgendes gilt für alle korrelierenden Anforderungen und Antworten:  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt sicher, dass alle Anwendungsanforderungsnachrichten einen `ReplyTo`-Endpunktverweis und eine `MessageId` enthalten.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wendet den lokalen Endpunktverweis als `ReplyTo` jeder einzelnen Anwendungsanforderungsnachricht an. Der lokale Endpunktverweis ist der `CreateSequence`-Verweis der `ReplyTo`-Nachricht für den Initiator und der `CreateSequence`-Verweis der `To`-Nachricht für den Beantworter.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt sicher, dass eingehende Anforderungsnachrichten eine `MessageId` und einen `ReplyTo`-Verweis besitzen.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt zudem sicher, dass der URI des `ReplyTo`-Endpunktverweises aller Anwendungsanforderungsnachrichten wie weiter oben definiert mit dem lokalen Endpunktverweis übereinstimmt.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt sicher, dass alle Antworten den richtigen `RelatesTo`-Header und `To`-Header gemäß den `wsa`-Anforderung-Antwort-Korrelationsregeln tragen.
