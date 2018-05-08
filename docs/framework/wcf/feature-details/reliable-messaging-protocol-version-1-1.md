---
title: Zuverlässiges Messaging-Protokoll, Version 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: 8ff02bc6953ec1e5030dd0b592a352b7e23ab0d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="reliable-messaging-protocol-version-11"></a>Zuverlässiges Messaging-Protokoll, Version 1,1
Dieses Thema enthält Details zur Implementierung der Windows Communication Foundation (WCF) für die WS-ReliableMessaging-Version von Februar 2007 (Version 1.1)-Protokoll für die Interoperation mithilfe des HTTP-Transports erforderlich. WCF folgt die WS-ReliableMessaging-Spezifikation mit den Einschränkungen und klarstellungen erläutert, die in diesem Thema. Beachten Sie, dass das zuverlässige WS-Messaging-Protokoll in der Version&#160;1.1 ab [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] implementiert ist.  
  
 Die WS-ReliableMessaging-Version von Februar 2007 Protokoll wird in WCF von implementiert die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
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
 WCF implementiert `CreateSequence` und `CreateSequenceResponse` Sequenz von Nachrichten an ein zuverlässiges messaging herstellen. Es gelten die folgenden Einschränkungen:  
  
-   B1101: Der Initiator WCF verwendet den gleichen Endpunktverweis als die `CreateSequence` Nachricht `ReplyTo`, `AcksTo` und `Offer/Endpoint`.  
  
-   R1102: Die `AcksTo`-, `ReplyTo`- und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen über Adresswerte mit identischen Zeichenfolgendarstellungen verfügen, die sich oktettweise entsprechen.  
  
    -   Der WCF-Beantworter stellt sicher, dass der URI-Teil der `AcksTo`, `ReplyTo` und `Endpoint` Endpunktverweise identisch sind, vor dem Erstellen einer Sequenz.  
  
-   R1103: Die `AcksTo`- und `ReplyTo` und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen den gleichen Satz an Verweisparametern aufweisen.  
  
    -   WCF wird nicht erzwungen, sondern setzt voraus, die auf Parameter von der `AcksTo`, `ReplyTo` und `Offer/Endpoint` -Endpunktverweise für `CreateSequence` identisch sind und verwendet Verweisparameter vom die `ReplyTo` -Endpunktverweis für Bestätigungen und Nachrichten umgekehrter Sequenz.  
  
-   B1104: Der WCF-Initiator generiert nicht das optionale `Expires` oder `Offer/Expires` Element in der `CreateSequence` Nachricht.  
  
-   B1105: Beim Zugriff auf die `CreateSequence` Nachricht, die WCF-Antwortdienst verwendet die `Expires` Wert in der `CreateSequence` Element als der `Expires` Wert in der `CreateSequenceResponse` Element. Andernfalls der WCF-Beantworter liest und ignoriert die `Expires` und `Offer/Expires` Werte.  
  
-   B1106: Beim Zugriff auf die `CreateSequenceResponse` Nachricht, die WCF-Initiator liest das optionale `Expires` Wert aber nicht verwendet.  
  
-   B1107: Der WCF-Initiator und Beantworter generieren immer das optionale `IncompleteSequenceBehavior` Element in der `CreateSequence/Offer` und `CreateSequenceResponse` Elemente.  
  
-   B1108: WCF verwendet nur den `DiscardFollowingFirstGap` und `NoDiscard` Werte in der `IncompleteSequenceBehavior` Element.  
  
    -   Zuverlässiges WS-Messaging verwendet den `Offer`-Mechanismus, um die beiden umgekehrt korrelierten Sequenzen einzurichten, die eine Sitzung bilden.  
  
-   B1109: Wenn `CreateSequence` enthält ein `Offer` Element, lehnt die unidirektionalen WCF-Beantworter die angebotene Sequenz indem er mit einem `CreateSequenceResponse` ohne eine `Accept` Element.  
  
-   B1110: Wenn eine zuverlässige Messaging-Beantworter die angebotene Sequenz zurückweist, einem Fehler in der WCF-Initiator die neu eingerichtete Sequenz.  
  
-   B1111: Wenn `CreateSequence` enthält kein `Offer` Element, lehnt der bidirektionalen WCF-Beantworter die angebotene Sequenz indem er mit einem `CreateSequenceRefused` Fehler.  
  
-   R1112: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, muss die `[address]`-Eigenschaft des `CreateSequenceResponse/Accept/AcksTo`-Endpunktverweises mit dem Ziel-URI der `CreateSequence`-Nachricht Byte für Byte übereinstimmen.  
  
-   R1113: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, müssen alle Nachrichten in beiden Sequenzen, die vom Initiator an den Beantworter übermittelt werden, an den gleichen Endpunktverweis gesendet werden.  
  
 WS-ReliableMessaging wird von WCF verwendet, um zuverlässige Sitzungen zwischen dem Initiator und Beantworter einzurichten. Die WCF-WS-ReliableMessaging-Implementierung bietet eine zuverlässige Sitzung für unidirektionale, Anforderung-Antwort- und Vollduplex-Nachrichtenmuster. Der `Offer`-Mechanismus von zuverlässigem WS-Messaging für `CreateSequence` und `CreateSequenceResponse` ermöglicht es Ihnen, zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein für alle Nachrichtenendpunkte geeignetes Sitzungsprotokoll. Da WCF eine Sicherheitsgarantie für solcher Sitzungen sowie End-to-End-Schutz bietet, ist es ratsam, um sicherzustellen, dass Nachrichten für den gleichen Teilnehmer am selben Ziel ankommen. Dadurch wird es zudem ermöglicht, Sequenzbestätigungen im Piggyback-Verfahren mit Anwendungsnachrichten zu übermitteln. Daher gelten Einschränkungen R1102 R1112 und R1113 für WCF.  
  
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
 WCF verwendet die `CloseSequence` und `CloseSequenceResponse` Nachrichten für eine zuverlässige Messaging-Quelle initiierte schließen durchzuführen. Das WCF zuverlässige Messaging-Ziel initiiert das Schließen nicht, und der WCF Reliable Messaging-Quelle unterstützt keine zuverlässige Messaging-Ziel Herunterfahren durch einen. Es gelten die folgenden Einschränkungen:  
  
-   B1201: Die WCF Reliable Messaging-Quelle sendet immer eine `CloseSequence` Nachricht, um die Sequenz zu schließen.  
  
-   B1202: Die zuverlässige Messaging-Quelle wartet auf die Bestätigung aller Sequenznachrichten, bevor sie die `CloseSequence`-Nachricht sendet.  
  
-   B1203: Die zuverlässige Messaging-Quelle fügt immer das optionale `LastMsgNumber`-Element ein, es sei denn, die Sequenz enthält keine Nachrichten.  
  
-   R1204: Das zuverlässige Messaging-Ziel darf das Schließen nicht durch Senden einer `CloseSequence`-Nachricht initiieren.  
  
-   B1205: bei Empfang einer `CloseSequence` Nachricht, die WCF Reliable Messaging-Quelle die Sequenz als unvollständig und sendet einen Fehler.  
  
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
 WCF verwendet hauptsächlich die `TerminateSequence/TerminateSequenceResponse` Handshake nach Abschluss der `CloseSequence/CloseSequenceResponse` Handshake. Das WCF zuverlässige Messaging-Ziel initiiert die Beendigung nicht, und die zuverlässige Messaging-Quelle unterstützt keine zuverlässige Messaging-Ziel initiiert beenden. Es gelten die folgenden Einschränkungen:  
  
-   B1301: Der WCF--Initiator schickt die `TerminateSequence` Nachricht nach dem erfolgreichen Abschluss der `CloseSequence/CloseSequenceResponse` Handshake.  
  
-   R1302: WCF überprüft, ob die `LastMsgNumber` -Element ist konsistent in allen `CloseSequence` und `TerminateSequence` Nachrichten für eine bestimmte Sequenz. Das bedeutet, dass `LastMsgNumber` entweder in keiner `CloseSequence`-Nachricht und keiner `TerminateSequence`-Nachricht vorhanden ist oder in allen `CloseSequence`-Nachrichten und `TerminateSequence`-Nachrichten vorhanden und identisch ist.  
  
-   B1303: Bei Empfang einer `TerminateSequence`-Nachricht nach dem `CloseSequence/CloseSequenceResponse`-Handshake antwortet das zuverlässige Messaging-Ziel mit einer `TerminateSequenceResponse`-Nachricht. Da die zuverlässige Messaging-Quelle die `TerminateSequence`-Nachricht erst nach Erhalt der letzten Bestätigung sendet, weiß das zuverlässige Messaging-Ziel mit Sicherheit, dass die Sequenz beendet ist, und fordert die Ressourcen unverzüglich zurück.  
  
-   B1304: Beim Empfang von einer `TerminateSequence` -Nachricht vor der `CloseSequence/CloseSequenceResponse` -Handshakes stellt das WCF zuverlässige Messaging-Ziel antwortet mit einer `TerminateSequenceResponse` Nachricht. Wenn das zuverlässige Messaging-Ziel ermittelt, dass die Sequenz keine Inkonsistenzen aufweist, wartet das zuverlässige Messaging-Ziel so lange, wie vom Anwendungsziel angegeben, bevor es die Ressourcen zurückverlangt, um es dem Client zu ermöglichen, die letzte Bestätigung zu empfangen. Anderenfalls fordert das zuverlässige Messaging-Ziel die Ressourcen unverzüglich zurück und teilt dem Anwendungsziel mit, dass die Sequenz nicht ordnungsgemäß beendet wurde, indem es das `Faulted`-Ereignis auslöst.  
  
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
  
-   B1401:WCF generiert und greift auf-Sequenznummern nicht höher als `xs:long`des inklusive Maximalwert 9223372036854775807.  
  
 Ein Beispiel für einen `Sequence`-Header.  
  
```xml  
<wsrm:Sequence s:mustUnderstand="1">  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:MessageNumber>1</wsrm:MessageNumber>  
</wsrm:Sequence>  
```  
  
### <a name="request-acknowledgement"></a>Anfordern einer Bestätigung  
 WCF verwendet die `AckRequested` -Header als Keep-alive-Mechanismus.  
  
 Ein Beispiel für einen `AckRequested`-Header.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 WCF verwendet einen "Zusatz"-Mechanismus für die WS-Reliable Messaging bereitgestellten sequenzbestätigungen. Es gelten die folgenden Einschränkungen:  
  
-   R1601: Wenn zwei umgekehrte Sequenzen eingerichtet sind mit den `Offer` Mechanismus, der `SequenceAcknowledgement` Header kann in jeder an den beabsichtigten Empfänger Anwendungsnachricht aufgenommen werden. Der Remoteendpunkt muss in der Lage sein, auf einen per Piggyback-Verfahren gesendeten `SequenceAcknowledgement`-Header zuzugreifen.  
  
-   B1602: WCF löst keine `SequenceAcknowledgement` Header, die enthalten `Nack` Elemente. WCF überprüft, ob jedes `Nack` Element enthält eine Sequenznummer, jedoch andernfalls ignoriert die `Nack` Element und Wert.  
  
 Ein Beispiel für einen `SequenceAcknowledgement`-Header.  
  
```xml  
<wsrm:SequenceAcknowledgement>  
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>  
</wsrm:SequenceAcknowledgement>  
```  
  
### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging-Fehler  
 Im folgenden wird eine Liste der Einschränkungen, die für die WCF-Implementierung des WS-ReliableMessaging-Fehler gelten. Es gelten die folgenden Einschränkungen:  
  
-   B1701: WCF löst keine `MessageNumberRollover` Fehler.  
  
-   B1702: Über SOAP 1.2, wenn der Dienstendpunkt seine Verbindungsgrenze erreicht und keine weiteren Verbindungen verarbeiten WCF generiert eine geschachtelte `CreateSequenceRefused` -Fehlersubcode `netrm:ConnectionLimitReached`, wie im folgenden Beispiel gezeigt.  
  
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
 Da WS-ReliableMessaging WS-Adressierung verwendet wird, kann die WCF-WS-ReliableMessaging-Implementierung generieren und Übertragen von WS-Adressierungsfehler. Dieser Abschnitt behandelt die WS-Adressierungsfehler, die WCF explizit generiert und überträgt an der WS-ReliableMessaging-Schicht an:  
  
-   B1801:WCF generiert und überträgt die `Message Addressing Header Required` fehl, wenn eine der folgenden Aussagen zutrifft:  
  
    -   Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `MessageId`-Header.  
  
    -   Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `ReplyTo`-Header.  
  
    -   Bei einer Nachricht vom Typ `CreateSequenceResponse`, `CloseSequenceResponse` oder `TerminateSequenceResponse` fehlt ein `RelatesTo`-Header.  
  
-   B1802:WCF generiert und überträgt die `Endpoint Unavailable` Fehler, um anzugeben, dass es kein Endpunkt gelauscht, die die Sequenz basierend auf der Prüfung der Adressierungsheader in verarbeiten kann die `CreateSequence` Nachricht.  
  
## <a name="protocol-composition"></a>Protokollkomposition  
  
### <a name="composition-with-ws-addressing"></a>Komposition mit WS-Adressierung  
 WCF unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung 2004/08 [WS-ADDR] und W3C WS-Adressierung 1.0 Empfehlungen [WS-ADDR-CORE] und [WS-ADDR-SOAP].  
  
 Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die Verwendung der WS-Adressierung nicht auf diese Version ein. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
-   R2101: Sowohl WS-Adressierung&#160;2004/08 als auch WS-Adressierung&#160;1.0 können mit zuverlässigem WS-Messaging verwendet werden.  
  
-   R2102: Für eine gegebene WS-ReliableMessaging-Sequenz oder ein Paar umgekehrter Sequenzen, die mithilfe des `Offer`-Mechanismus korreliert wurden, darf nur eine Version der WS-Adressierung verwendet werden.  
  
### <a name="composition-with-soap"></a>Komposition mit SOAP  
 WCF unterstützt die Verwendung von SOAP 1.1 und SOAP 1.2 mit zuverlässigem WS-Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Komposition mit WS-Sicherheit und WS-SecureConversation  
 WCF bietet Schutz für WS-ReliableMessaging-Sequenzen durch Verwenden von sicheren Transportmethode (HTTPS), Komposition mit WS-Security und Komposition mit WS-Secure Conversation. Das WS-ReliableMessaging&#160;1.1-Protokoll, das WS-Security&#160;1.1- und das WS-Secure Conversation&#160;1.3-Protokoll sollten zusammen verwendet werden. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
-   R2301: Um die Integrität einer WS-ReliableMessaging-Sequenz neben der Integrität und Vertraulichkeit einzelner Nachrichten zu schützen, muss WCF WS-Secure Conversation verwendet werden muss.  
  
-   R2302:AWS-Secure Conversation-Sitzung muss vor dem Einrichten von WS-ReliableMessaging Sequence(s) eingerichtet werden.  
  
-   R2303: Wenn die Lebensdauer einer WS-ReliableMessaging-Sequenz die Lebensdauer der WS-SecureConversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-SecureConversationRenewal-Bindung erneuert werden.  
  
-   B2304:WS-ReliableMessaging-Sequenz oder ein paar umgekehrt korrelierte Sequenzen immer an eine einzelne WS-SecureConversation-Sitzung gebunden sind.  
  
-   R2305: Wenn mit WS-Secure Conversation ItemsControl-Element, das WCF-Beantworter erfordert, dass die `CreateSequence` Nachricht enthält die `wsse:SecurityTokenReference` Element und der `wsrm:UsesSequenceSTR` Header.  
  
 Ein Beispiel für einen `UsesSequenceSTR`-Header.  
  
```xml  
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>  
```  
  
### <a name="composition-with-ssltls-sessions"></a>Komposition mit SSL/TLS-Sitzungen  
 WCF unterstützt keine Komposition mit SSL/TLS-Sitzungen:  
  
-   B2401: WCF generiert nicht das `wsrm:UsesSequenceSSL` Header.  
  
-   R2402: Ein zuverlässiger Messaging-Initiator muss nicht senden eine `CreateSequence` -Nachricht mit einem `wsrm:UsesSequenceSSL` Header an einen WCF-Antwortdienst.  
  
### <a name="composition-with-ws-policy"></a>Komposition mit WS-Policy  
 WCF unterstützt zwei Versionen der WS-Policy: WS-Policy 1.2 und WS-Policy 1.5.  
  
## <a name="ws-reliablemessaging-ws-policy-assertion"></a>WS-ReliableMessaging WS-Richtlinienassertion  
 WCF verwendet die WS-ReliableMessaging WS-Richtlinienassertion `wsrm:RMAssertion` Fähigkeiten von Endpunkten zu beschreiben. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
-   B3001: WCF fügt `wsrmn:RMAssertion` WS-Richtlinienassertion an `wsdl:binding` Elemente. WCF unterstützt beide Anlagen `wsdl:binding` und `wsdl:port` Elemente.  
  
-   B3002: WCF generiert, die nie die `wsp:Optional` Tag.  
  
-   B3003: Beim Zugriff auf die `wsrmp:RMAssertion` WS-Policy-Assertion WCF ignoriert den `wsp:Optional` -Tag und behandelt die WS-RM-Richtlinie als obligatorisch.  
  
-   R3004: Da WCF nicht mit SSL/TLS-Sitzungen zu verfassen, WCF akzeptiert keine Richtlinie mit `wsrmp:SequenceTransportSecurity`.  
  
-   B3005: Immer WCF generiert das `wsrmp:DeliveryAssurance` Element.  
  
-   B3006: WCF immer gibt die `wsrmp:ExactlyOnce` übermittlungssicherung.  
  
-   B3007: WCF generiert und liest die folgenden Eigenschaften der WS-ReliableMessaging-Assertion und die Steuerung über die WCF`ReliableSessionBindingElement`:  
  
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
 WCF verwendet WS-ReliableMessaging-Erweiterbarkeit, um optionale Steuerung des sequenznachrichtenflusses Sequenz-Nachrichtenfluss zu ermöglichen.  
  
 Flusssteuerung aktiviert ist, durch Festlegen der `ReliableSessionBindingElement`des `FlowControlEnabled``boolean` Eigenschaft `true`. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
-   B4001: Wenn zuverlässiges Messaging flusssteuerung aktiviert ist, WCF generiert eine `netrm:BufferRemaining` Element in der elementerweiterbarkeit des der `SequenceAcknowledgement` -Header, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="1" Lower="1"/>             
      <netrm:BufferRemaining>8</netrm:BufferRemaining>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B4002: Selbst wenn zuverlässiges Messaging flusssteuerung aktiviert ist, WCF erfordert nicht, dass eine `netrm:BufferRemaining` Element in der `SequenceAcknowledgement` Header.  
  
-   B4003: WCF zuverlässige Messaging-Ziel verwendet `netrm:BufferRemaining` , um anzugeben, wie viele neue Nachrichten es Puffern können.  
  
-   B4004:when Reliable Messaging flusssteuerung aktiviert ist, die WCF zuverlässige Messaging-Quelle verwendet den Wert der `netrm:BufferRemaining` zu drosseln nachrichtenübertragung.  
  
-   B4005: WCF generiert `netrm:BufferRemaining` -Ganzzahlwerte zwischen 0 und 4096 einschließlich und liest Ganzzahlwerte zwischen 0 und `xs:int`des `maxInclusive` Wert (214748364) einschließlich.  
  
## <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster  
 Dieser Abschnitt beschreibt WCFs-Verhalten, wenn WS-ReliableMessaging für verschiedene Nachrichtenaustauschmuster verwendet wird. Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:  
  
-   Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall; der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.  
  
-   Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.  
  
### <a name="one-way-non-addressable-initiator"></a>Unidirektionaler, nicht adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen HTTP-Kanal. WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten vom Initiator an den Antwortdienst bzw. HTTP-Antworten zur Übertragung aller Nachrichten vom Beantworter an den Initiator.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht ohne `Offer` Element in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse` -Nachricht in der HTTP-Antwort. Der WCF-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht ohne `Accept` Element in der HTTP-Antwort.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Der WCF--Initiator erstellt Bestätigungen als Antwort alle Nachrichten mit Ausnahme der `CreateSequence` -Nachrichten und Fehlernachrichten. Der WCF-Beantworter überträgt stets eine eigenständige Bestätigung in der HTTP-Antwort auf alle Sequenzen und `AckRequested` Nachrichten.  
  
#### <a name="closesequence-exchange"></a>CloseSequence-Austausch  
 Der WCF--Initiator überträgt eine `CloseSequence` -Nachricht in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse` -Nachricht in der HTTP-Antwort. Der WCF-Beantworter überträgt die `CloseSequenceResponse` -Nachricht in der HTTP-Antwort.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch  
 Der WCF--Initiator überträgt eine `TerminateSequence` -Nachricht in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse` -Nachricht in der HTTP-Antwort. Der WCF-Beantworter überträgt die `TerminateSequenceResponse` -Nachricht in der HTTP-Antwort.  
  
### <a name="one-way-addressable-initiator"></a>Unidirektionaler, adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht ohne `Offer` -Element in einer HTTP-Anforderung. Der WCF-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht ohne `Accept` -Element in einer HTTP-Anforderung.  
  
### <a name="duplex-addressable-initiator"></a>Adressierbarer Duplex-Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein vollständig asynchrones bidirektionales Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Request/Reply`, `Addressable`-Initiator kombinieren. WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht mit einer `Offer` -Element in einer HTTP-Anforderung. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` hat eine `Offer` Element, dann erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht mit einer `Accept` Element.  
  
#### <a name="sequence-lifetime"></a>Sequenzlebensdauer  
 WCF behandelt die beiden Sequenzen als eine vollduplexsitzung.  
  
 Nach dem Generieren eines Fehlers, der einem Fehler in einer Sequenz, erwartet WCF Remoteendpunkt für beide Sequenzen auslöst. Nach dem Lesen eines Fehlers, der einem Fehler in einer Sequenz, Fehler WCF für beide Sequenzen.  
  
 WCF kann seine ausgehende Sequenz schließen und zum Verarbeiten von Nachrichten in seiner eingehenden Sequenz fortfahren. Im Gegensatz dazu kann WCF das Schließen der eingehenden Sequenz durchführen und weiter Nachrichten in seiner ausgehenden Sequenz senden.  
  
### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Anforderung-Antwort- und unidirektionaler, nicht adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet einen unidirektionalen und Anforderung-Antwort-Nachrichtenaustauschmuster, die unter Verwendung zweier Sequenzen über einen HTTP-Kanal. WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten vom Initiator an den Antwortdienst bzw. HTTP-Antworten zur Übertragung aller Nachrichten vom Beantworter an den Initiator.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht mit einer `Offer` Element in einer HTTP-Anforderung und erwartet die `CreateSequenceResponse` -Nachricht in der HTTP-Antwort. Der WCF-Beantworter erstellt eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht mit einem `Accept` Element in der HTTP-Antwort.  
  
#### <a name="one-way-message"></a>Unidirektionale Nachricht  
 Um einen unidirektionalen Nachrichtenaustausch erfolgreich abgeschlossen haben, den WCF-Initiator eine anforderungssequenznachricht in der HTTP-Anforderung sendet und empfängt eine eigenständige `SequenceAcknowledgement` -Nachricht in der HTTP-Antwort. Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.  
  
 Der WCF-Beantworter kann mit einer Bestätigung, einen Fehler oder eine Antwort mit leerem Textbereich und dem HTTP-Statuscode 202 auf die Anforderung antworten.  
  
#### <a name="two-way-messages"></a>Bidirektionale Nachrichten  
 Um eine zwei-Wege-Nachrichtenaustauschprotokoll erfolgreich abgeschlossen haben, den WCF-Initiator überträgt eine anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine antwortsequenznachricht in der HTTP-Antwort. Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.  
  
 Der WCF-Beantworter antwortet möglicherweise auf die Anforderung mit einer Anwendungsantwort, einem Fehler oder eine Antwort mit leerem Textbereich und dem HTTP-Statuscode 202.  
  
 Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.  
  
#### <a name="retrying-replies"></a>Wiederholen von Antworten  
 WCF basiert auf HTTP-Anforderung / Antwort-Korrelation für das bidirektionale Nachrichtenaustauschprotokoll. Aus diesem Grund der WCF-Initiator wird nicht beendet, und wiederholen Sie dann eine anforderungssequenznachricht, wenn die anforderungssequenznachricht bestätigt wird, sondern stattdessen bei die HTTP-Antwort enthält einen `SequenceAcknowledgement`, Anwendungsantwort oder einen Fehler. Der WCF-Beantworter wiederholt die Antworten auf die HTTP-Antwort der Anforderung mit der die Antwort korreliert ist.  
  
#### <a name="closesequence-exchange"></a>CloseSequence-Austausch  
 Nach dem Empfang aller Antwortsequenznachrichten und Bestätigungen für alle unidirektionalen anforderungssequenznachrichten, die WCF--Initiator überträgt eine `CloseSequence` -Nachricht für die anforderungssequenz in einer HTTP-Anforderung und erwartet die `CloseSequenceResponse` der HTTP-Antwort.  
  
 Durch Schließen der Anforderungssequenz wird die Antwortsequenz implizit geschlossen. Dies bedeutet, dass der Initiator WCF umfasst der Antwortsequenz endgültigen `SequenceAcknowledgement` auf die `CloseSequence` Nachricht und die Antwortsequenz verfügt nicht über eine `CloseSequence` Exchange.  
  
 Der WCF-Beantworter wird sichergestellt, dass alle Antworten bestätigt werden, und überträgt die `CloseSequenceResponse` -Nachricht in der HTTP-Antwort.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch  
 Nach dem Empfang der `CloseSequenceResponse` Nachricht, die WCF--Initiator überträgt eine `TerminateSequence` -Nachricht für die anforderungssequenz in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse` der HTTP-Antwort.  
  
 Wie beim `CloseSequence`-Austausch wird durch Beendigung der Anforderungssequenz die Antwortsequenz implizit beendet. Dies bedeutet, dass der Initiator WCF umfasst der Antwortsequenz endgültigen `SequenceAcknowledgement` auf die `TerminateSequence` Nachricht und die Antwortsequenz verfügt nicht über eine `TerminateSequence` Exchange.  
  
 Der WCF-Beantworter überträgt die `TerminateSequenceResponse` -Nachricht in der HTTP-Antwort.  
  
### <a name="requestreply-addressable-initiator"></a>Adressierbarer Anforderung/Antwort-Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Duplex, Addressable`-Initiator kombinieren. WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator überträgt eine `CreateSequence` -Nachricht mit einer `Offer` -Element in einer HTTP-Anforderung. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` verfügt über eine `Offer` Element erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse` -Nachricht mit einer `Accept` Element.  
  
#### <a name="requestreply-correlation"></a>Anforderung/Antwort-Korrelation  
 Folgendes gilt für alle korrelierenden Anforderungen und Antworten:  
  
-   WCF wird sichergestellt, dass alle anwendungsanforderungsnachrichten eine `ReplyTo` -Endpunktverweis und eine `MessageId`.  
  
-   WCF wendet den lokalen Endpunktverweis als einzelnen anwendungsanforderungsnachricht `ReplyTo`. Der lokale Endpunktverweis ist der `CreateSequence`-Verweis der `ReplyTo`-Nachricht für den Initiator und der `CreateSequence`-Verweis der `To`-Nachricht für den Beantworter.  
  
-   WCF wird sichergestellt, dass eingehende Anforderungsnachrichten-Verweis besitzen eine `MessageId` und ein `ReplyTo`.  
  
-   WCF wird sichergestellt, dass die `ReplyTo` URI-Endpunktverweises aller anwendungsanforderungsnachrichten entsprechen den lokalen Endpunktverweis wie weiter oben definiert.  
  
-   WCF wird sichergestellt, dass alle Antworten den richtigen tragen `RelatesTo` und `To` -Header gemäß `wsa` Anforderung/Antwort-Korrelationsregeln.
