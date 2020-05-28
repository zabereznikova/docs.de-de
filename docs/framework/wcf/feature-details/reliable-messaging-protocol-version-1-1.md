---
title: Zuverlässiges Messaging-Protokoll, Version 1,1
ms.date: 03/30/2017
ms.assetid: 0da47b82-f8eb-42da-8bfe-e56ce7ba6f59
ms.openlocfilehash: ad0a77842c10965749eab4e76bb123938e07e9d5
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144720"
---
# <a name="reliable-messaging-protocol-version-11"></a>Zuverlässiges Messaging-Protokoll, Version 1,1

Dieses Thema behandelt Windows Communication Foundation (WCF)-Implementierungsdetails für das WS-ReliableMessaging-Protokoll vom Februar 2007 (Version 1,1), das für die Interoperation mithilfe des http-Transports erforderlich ist. WCF befolgt die WS-ReliableMessaging-Spezifikation mit den in diesem Thema erläuterten Einschränkungen und Erläuterungen. Beachten Sie, dass das WS-ReliableMessaging-Protokoll, Version 1,1, ab .NET Framework 3,5 implementiert wird.

Das WS-ReliableMessaging-Protokoll von Februar 2007 wird in WCF von implementiert <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .

Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:

- Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert

- Beantworter: der Dienst, der die Anforderungen des Initiators empfängt

 In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.

|Präfix|Namespace|
|-|-|
|wsrm|`http://docs.oasis-open.org/ws-rx/wsrm/200702`|
|netrm|`http://schemas.microsoft.com/ws/2006/05/rm`|
|s|`http://www.w3.org/2003/05/soap-envelope`|
|wsa|`http://schemas.xmlsoap.org/ws/2005/08/addressing`|
|wsse|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|
|wsrmp|`http://docs.oasis-open.org/ws-rx/wsrmp/200702`|
|netrmp|`http://schemas.microsoft.com/ws-rx/wsrmp/200702`|
|wsp|(Entweder WS-Policy&#160;1.2 oder WS-Policy&#160;1.5)|

## <a name="messaging"></a>Nachrichten

### <a name="sequence-creation"></a>Sequenzerstellung

WCF implementiert `CreateSequence` -und- `CreateSequenceResponse` Nachrichten, um eine zuverlässige Messaging Sequenz einzurichten. Es gelten die folgenden Einschränkungen:

- B1101: der WCF-Initiator verwendet denselben Endpunkt Verweis wie die der `CreateSequence` Nachricht `ReplyTo` , `AcksTo` und `Offer/Endpoint` .

- R1102: Die `AcksTo`-, `ReplyTo`- und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen über Adresswerte mit identischen Zeichenfolgendarstellungen verfügen, die sich oktettweise entsprechen.

  - Der WCF-Responder überprüft, ob der URI-Teil `AcksTo` der `ReplyTo` -,-und- `Endpoint` Endpunkt Verweise identisch sind, bevor eine Sequenz erstellt wird.

- R1103: Die `AcksTo`- und `ReplyTo` und `Offer/Endpoint`-Endpunktverweise in der `CreateSequence`-Nachricht müssen den gleichen Satz an Verweisparametern aufweisen.

  - WCF erzwingt nicht, sondern geht davon aus, dass die Verweis Parameter der `AcksTo` `ReplyTo` -,-und- `Offer/Endpoint` Endpunkt Verweise auf `CreateSequence` identisch sind, und verwendet Verweis Parameter aus dem `ReplyTo` Endpunkt Verweis für Bestätigungen und umgekehrte Sequenz Nachrichten.

- B1104: der WCF-Initiator generiert nicht das optionale- `Expires` oder- `Offer/Expires` Element in der `CreateSequence` Nachricht.

- B1105: beim Zugriff auf die `CreateSequence` Nachricht verwendet der WCF-Responder den `Expires` Wert im- `CreateSequence` Element als `Expires` Wert im- `CreateSequenceResponse` Element. Andernfalls liest und ignoriert der WCF-Responder den `Expires` -Wert und den- `Offer/Expires` Wert.

- B1106: beim Zugriff auf die `CreateSequenceResponse` Nachricht liest der WCF-Initiator den optionalen `Expires` Wert, verwendet ihn aber nicht.

- B1107: der WCF-Initiator und der-Responder generieren immer das optionale `IncompleteSequenceBehavior` -Element im `CreateSequence/Offer` -Element und im-Element `CreateSequenceResponse` .

- B1108: WCF verwendet nur den `DiscardFollowingFirstGap` -Wert und den- `NoDiscard` Wert im- `IncompleteSequenceBehavior` Element.

  - Zuverlässiges WS-Messaging verwendet den `Offer`-Mechanismus, um die beiden umgekehrt korrelierten Sequenzen einzurichten, die eine Sitzung bilden.

- B1109: Wenn `CreateSequence` ein Element enthält, lehnt der unidirektionale `Offer` WCF-Responder die angebotene Sequenz ab, indem er mit einem `CreateSequenceResponse` ohne ein `Accept` Element antwortet.

- B1110: Wenn ein zuverlässiger Messaging-Responder die angebotene Sequenz ablehnt, gibt der WCF-Initiator einen Fehler in der neu eingerichteten Sequenz aus.

- B1111: Wenn `CreateSequence` kein `Offer` -Element enthält, lehnt der bidirektionale WCF-Responder die angebotene Sequenz ab, indem er mit einem `CreateSequenceRefused` Fehler antwortet.

- R1112: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, muss die `[address]`-Eigenschaft des `CreateSequenceResponse/Accept/AcksTo`-Endpunktverweises mit dem Ziel-URI der `CreateSequence`-Nachricht Byte für Byte übereinstimmen.

- R1113: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, müssen alle Nachrichten in beiden Sequenzen, die vom Initiator an den Beantworter übermittelt werden, an den gleichen Endpunktverweis gesendet werden.

WCF verwendet WS-ReliableMessaging, um zuverlässige Sitzungen zwischen dem Initiator und dem Beantworter einzurichten. Die WCF WS-ReliableMessaging-Implementierung bietet eine zuverlässige Sitzung für unidirektionale, Anforderungs-Antwort-und vollständige Duplex Nachrichten Muster. Der `Offer`-Mechanismus von zuverlässigem WS-Messaging für `CreateSequence` und `CreateSequenceResponse` ermöglicht es Ihnen, zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein für alle Nachrichtenendpunkte geeignetes Sitzungsprotokoll. Da WCF eine Sicherheitsgarantie für eine solche Sitzung bietet, einschließlich End-to-End-Schutz für die Sitzungs Integrität, ist es praktisch sicherzustellen, dass die für dieselbe Partei vorgesehenen Nachrichten am gleichen Ziel ankommen. Dadurch wird es zudem ermöglicht, Sequenzbestätigungen im Piggyback-Verfahren mit Anwendungsnachrichten zu übermitteln. Daher gelten die Einschränkungen R1102, R1112 und R1113 für WCF.

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

WCF verwendet die `CloseSequence` -und- `CloseSequenceResponse` Meldungen für eine zuverlässige, von der Messaging Quelle initiierte Herunterfahren. Das zuverlässige WCF-Messaging-Ziel initiiert das Herunterfahren nicht, und die zuverlässige WCF-Messaging-Quelle unterstützt kein zuverlässiges, von einem Messaging Ziel initiiertes Herunterfahren. Es gelten die folgenden Einschränkungen:

- B1201: die Quelle für zuverlässiges WCF-Messaging sendet immer eine `CloseSequence` Nachricht, um die Sequenz zu schließen.

- B1202: Die zuverlässige Messaging-Quelle wartet auf die Bestätigung aller Sequenznachrichten, bevor sie die `CloseSequence`-Nachricht sendet.

- B1203: Die zuverlässige Messaging-Quelle fügt immer das optionale `LastMsgNumber`-Element ein, es sei denn, die Sequenz enthält keine Nachrichten.

- R1204: Das zuverlässige Messaging-Ziel darf das Schließen nicht durch Senden einer `CloseSequence`-Nachricht initiieren.

- B1205: nach dem Empfang einer `CloseSequence` Nachricht betrachtet die Quelle für zuverlässiges WCF-Messaging die Sequenz als unvollständig und sendet einen Fehler.

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
```

Beispiel `CloseSequenceResponse` Nachricht:

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

### <a name="sequence-termination"></a>Sequenzbeendigung

WCF verwendet in erster Linie den `TerminateSequence/TerminateSequenceResponse` Handshake, nachdem der Handshake abgeschlossen wurde `CloseSequence/CloseSequenceResponse` . Das zuverlässige WCF-Messaging-Ziel löst keine Beendigung aus, und die zuverlässige Messaging Quelle unterstützt keine zuverlässige, von einem Messaging Ziel initiierte Beendigung. Es gelten die folgenden Einschränkungen:

- B1301: der WCF-Initiator sendet die `TerminateSequence` Nachricht nur nach dem erfolgreichen Abschluss des `CloseSequence/CloseSequenceResponse` Handshakes.

- R1302: WCF überprüft, ob das `LastMsgNumber` Element in allen `CloseSequence` -und- `TerminateSequence` Nachrichten für eine bestimmte Sequenz konsistent ist. Das bedeutet, dass `LastMsgNumber` entweder in keiner `CloseSequence`-Nachricht und keiner `TerminateSequence`-Nachricht vorhanden ist oder in allen `CloseSequence`-Nachrichten und `TerminateSequence`-Nachrichten vorhanden und identisch ist.

- B1303: Bei Empfang einer `TerminateSequence`-Nachricht nach dem `CloseSequence/CloseSequenceResponse`-Handshake antwortet das zuverlässige Messaging-Ziel mit einer `TerminateSequenceResponse`-Nachricht. Da die zuverlässige Messaging-Quelle die `TerminateSequence`-Nachricht erst nach Erhalt der letzten Bestätigung sendet, weiß das zuverlässige Messaging-Ziel mit Sicherheit, dass die Sequenz beendet ist, und fordert die Ressourcen unverzüglich zurück.

- B1304: beim Empfangen einer `TerminateSequence` Nachricht vor dem `CloseSequence/CloseSequenceResponse` Hand Shake antwortet das zuverlässige WCF-Messaging-Ziel mit einer `TerminateSequenceResponse` Meldung. Wenn das zuverlässige Messaging-Ziel ermittelt, dass die Sequenz keine Inkonsistenzen aufweist, wartet das zuverlässige Messaging-Ziel so lange, wie vom Anwendungsziel angegeben, bevor es die Ressourcen zurückverlangt, um es dem Client zu ermöglichen, die letzte Bestätigung zu empfangen. Anderenfalls fordert das zuverlässige Messaging-Ziel die Ressourcen unverzüglich zurück und teilt dem Anwendungsziel mit, dass die Sequenz nicht ordnungsgemäß beendet wurde, indem es das `Faulted`-Ereignis auslöst.

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
```

Beispiel `TerminateSequenceResponse` Nachricht:

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

### <a name="sequences"></a>Sequenzen

Die folgende Liste enthält die Einschränkungen, die für Sequenzen gelten:

- B1401: WCF generiert und greift auf Sequenznummern zu `xs:long` , die nicht größer sind als der maximale inklusivwert, 9223372036854775807.

Ein Beispiel für einen `Sequence`-Header.

```xml
<wsrm:Sequence s:mustUnderstand="1">
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:MessageNumber>1</wsrm:MessageNumber>
</wsrm:Sequence>
```

### <a name="request-acknowledgement"></a>Anfordern einer Bestätigung

WCF verwendet den- `AckRequested` Header als Keep-Alive-Mechanismus.

Ein Beispiel für einen `AckRequested`-Header.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

WCF verwendet einen "Piggy-back"-Mechanismus für Sequenz Bestätigungen, die im zuverlässigen WS-Messaging bereitgestellt werden. Es gelten die folgenden Einschränkungen:

- R1601: Wenn mithilfe des-Mechanismus zwei umgekehrte Sequenzen eingerichtet werden `Offer` , `SequenceAcknowledgement` kann der-Header in jeder Anwendungs Nachricht enthalten sein, die an den beabsichtigten Empfänger übertragen wird. Der Remoteendpunkt muss in der Lage sein, auf einen per Piggyback-Verfahren gesendeten `SequenceAcknowledgement`-Header zuzugreifen.

- B1602: WCF generiert keine `SequenceAcknowledgement` Header, die `Nack` Elemente enthalten. WCF überprüft, ob jedes `Nack` Element eine Sequenznummer enthält, ignoriert jedoch das `Nack` Element und den Wert.

 Ein Beispiel für einen `SequenceAcknowledgement`-Header.

```xml
<wsrm:SequenceAcknowledgement>
  <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
  <wsrm:AcknowledgementRange Lower="1" Upper="1"></wsrm:AcknowledgementRange>
</wsrm:SequenceAcknowledgement>
```

### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging-Fehler

Im folgenden finden Sie eine Liste der Einschränkungen, die für die WCF-Implementierung von WS-ReliableMessaging-Fehlern gelten. Es gelten die folgenden Einschränkungen:

- B1701: WCF generiert keine `MessageNumberRollover` Fehler.

- B1702: Wenn der Dienst Endpunkt über SOAP 1,2 das Verbindungs Limit erreicht und keine neuen Verbindungen verarbeiten kann, generiert WCF einen untergeordneten `CreateSequenceRefused` Fehlersubcode, `netrm:ConnectionLimitReached` , wie im folgenden Beispiel gezeigt.

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

Da WS-ReliableMessaging WS-Adressierung verwendet, kann die WCF WS-ReliableMessaging-Implementierung WS-Adressierungs Fehler generieren und übertragen. In diesem Abschnitt werden die WS-Adressierungs Fehler behandelt, die von WCF explizit auf der WS-ReliableMessaging-Ebene generiert und übermittelt werden:

- B1801: WCF generiert und überträgt den `Message Addressing Header Required` Fehler, wenn eine der folgenden Punkte zutrifft:

  - Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `MessageId`-Header.

  - Bei einer Nachricht vom Typ `CreateSequence`, `CloseSequence` oder `TerminateSequence` fehlt ein `ReplyTo`-Header.

  - Bei einer Nachricht vom Typ `CreateSequenceResponse`, `CloseSequenceResponse` oder `TerminateSequenceResponse` fehlt ein `RelatesTo`-Header.

- B1802: WCF generiert und überträgt den `Endpoint Unavailable` Fehler, um anzugeben, dass kein Endpunkt lauscht, der die Sequenz auf der Grundlage der Untersuchung der Adressierungs Header in der Nachricht verarbeiten kann `CreateSequence` .

## <a name="protocol-composition"></a>Protokollkomposition

### <a name="composition-with-ws-addressing"></a>Komposition mit WS-Adressierung

WCF unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung 2004/08 [ws-addr] und W3C WS-Adressierung 1,0 Empfehlungen [ws-addr-core] und [ws-addr-SOAP].

Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die Verwendung der WS-Adressierung nicht auf diese Version ein. Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:

- R2101: Sowohl WS-Adressierung&#160;2004/08 als auch WS-Adressierung&#160;1.0 können mit zuverlässigem WS-Messaging verwendet werden.

- R2102: Für eine gegebene WS-ReliableMessaging-Sequenz oder ein Paar umgekehrter Sequenzen, die mithilfe des `Offer`-Mechanismus korreliert wurden, darf nur eine Version der WS-Adressierung verwendet werden.

### <a name="composition-with-soap"></a>Komposition mit SOAP

WCF unterstützt die Verwendung von SOAP 1,1 und SOAP 1,2 mit zuverlässigem WS-Messaging.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Komposition mit WS-Sicherheit und WS-SecureConversation

WCF bietet Schutz für WS-ReliableMessaging-Sequenzen mithilfe von Secure Transport (HTTPS), Komposition mit WS-Sicherheit und Komposition mit WS-Secure Conversation. Das WS-ReliableMessaging&#160;1.1-Protokoll, das WS-Security&#160;1.1- und das WS-Secure Conversation&#160;1.3-Protokoll sollten zusammen verwendet werden. Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:

- R2301: um die Integrität einer WS-ReliableMessaging-Sequenz zusätzlich zur Integrität und Vertraulichkeit einzelner Nachrichten zu schützen, erfordert WCF, dass eine WS-Secure-Konversation verwendet werden muss.

- R2302: Eine  WS-Secure Conversation-Sitzung muss vor der Erstellung von WS-ReliableMessaging-Sequenzen eingerichtet werden.

- R2303: Wenn die Lebensdauer einer WS-ReliableMessaging-Sequenz die Lebensdauer der WS-SecureConversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-SecureConversationRenewal-Bindung erneuert werden.

- B2304:Die WS-ReliableMessaging-Sequenz bzw. das Paar korrelierter umgekehrter Sequenzen ist immer an eine einzelne WS-SecureConversation-Sitzung gebunden.

- R2305: Wenn das zusammensetzen mit WS-Secure Conversation besteht, erfordert der WCF-Beantworter, dass die `CreateSequence` Nachricht das `wsse:SecurityTokenReference` -Element und den- `wsrm:UsesSequenceSTR` Header enthält.

 Ein Beispiel für einen `UsesSequenceSTR`-Header.

```xml
<wsrm:UsesSequenceSTR></wsrm:UsesSequenceSTR>
```

### <a name="composition-with-ssltls-sessions"></a>Komposition mit SSL/TLS-Sitzungen

WCF unterstützt keine Komposition mit SSL/TLS-Sitzungen:

- B2401: der-Header wird von WCF nicht generiert `wsrm:UsesSequenceSSL` .

- R2402: ein zuverlässiger Messaging-Initiator darf keine `CreateSequence` Nachricht mit einem- `wsrm:UsesSequenceSSL` Header an einen WCF-Responder senden.

### <a name="composition-with-ws-policy"></a>Komposition mit WS-Policy

WCF unterstützt zwei Versionen von WS-Policy: WS-Policy 1,2 und WS-Policy 1,5.

## <a name="ws-reliablemessaging-ws-policy-assertion"></a>WS-ReliableMessaging WS-Richtlinienassertion

WCF verwendet WS-ReliableMessaging WS-Policy Assert `wsrm:RMAssertion` , um Endpunkte Funktionen zu beschreiben. Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:

- B3001: WCF fügt `wsrmn:RMAssertion` die WS-Policy-Assertionen an `wsdl:binding` Elemente an. WCF unterstützt sowohl Anhänge für `wsdl:binding` -als auch- `wsdl:port` Elemente.

- B3002: WCF generiert das `wsp:Optional` Tag niemals.

- B3003: beim Zugriff auf die `wsrmp:RMAssertion` WS-Richtlinien Assertionen ignoriert WCF das `wsp:Optional` Tag und behandelt die WS-RM-Richtlinie als obligatorisch.

- R3004: da WCF nicht mit SSL/TLS-Sitzungen verfasst wird, akzeptiert WCF keine Richtlinie, die angibt `wsrmp:SequenceTransportSecurity` .

- B3005: WCF generiert immer das- `wsrmp:DeliveryAssurance` Element.

- B3006: WCF gibt die Übermittlungs Assurance immer an `wsrmp:ExactlyOnce` .

- B3007: WCF generiert und liest die folgenden Eigenschaften der WS-ReliableMessaging-Assertion und ermöglicht Ihnen die Kontrolle über diese auf dem WCF `ReliableSessionBindingElement` :

  - `netrmp:InactivityTimeout`

  - `netrmp:AcknowledgementInterval`

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

WCF verwendet die WS-ReliableMessaging-Erweiterbarkeit, um eine optionale zusätzliche strengere Kontrolle über den Sequenz Nachrichtenfluss bereitzustellen.

Die Fluss Steuerung wird aktiviert, indem die-Eigenschaft auf festgelegt wird <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> `true` . Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:

- B4001: Wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, generiert WCF ein- `netrm:BufferRemaining` Element in der Element Erweiterbarkeit des- `SequenceAcknowledgement` headers, wie im folgenden Beispiel gezeigt.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>urn:uuid:656652b8-9af2-4e94-9d07-2dc21c05ed27</wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="1" Lower="1"/>
    <netrm:BufferRemaining>8</netrm:BufferRemaining>
  </wsrm:SequenceAcknowledgement>
  ```

- B4002: auch wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, erfordert WCF kein- `netrm:BufferRemaining` Element im- `SequenceAcknowledgement` Header.

- B4003: das zuverlässige WCF-Messaging Ziel verwendet `netrm:BufferRemaining` , um anzugeben, wie viele neue Nachrichten Sie Puffern können.

- B4004: Wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, verwendet die zuverlässige WCF-Messaging Quelle den Wert von `netrm:BufferRemaining` , um die Nachrichtenübertragung zu drosseln.

- B4005: WCF generiert `netrm:BufferRemaining` ganzzahlige Werte zwischen 0 und 4096 einschließlich und liest ganzzahlige Werte zwischen 0 und `xs:int` dem `maxInclusive` Wert 214748364 einschließlich.

## <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster

In diesem Abschnitt wird das Verhalten von WCF beschrieben, wenn WS-ReliableMessaging für verschiedene Nachrichtenaustausch Muster verwendet wird. Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:

- Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall; der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.

- Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.

### <a name="one-way-non-addressable-initiator"></a>Unidirektionaler, nicht adressierbarer Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein unidirektionales Nachrichtenaustausch Muster unter Verwendung einer Sequenz über einen HTTP-Kanal. WCF verwendet HTTP-Anforderungen, um alle Nachrichten vom Initiator an den Beantworter zu übertragen, und HTTP-Antworten, um alle Nachrichten vom Responder an den Initiator zu übertragen.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator überträgt eine `CreateSequence` -Nachricht ohne `Offer` -Element in einer HTTP-Anforderung und erwartet die- `CreateSequenceResponse` Nachricht in der HTTP-Antwort. Der WCF-Responder erstellt eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht ohne- `Accept` Element in der HTTP-Antwort.

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

Der WCF-Initiator verarbeitet Bestätigungen für die Antwort aller Meldungen außer der `CreateSequence` Nachricht und den Fehlermeldungen. Der WCF-Responder überträgt immer eine eigenständige Bestätigung der HTTP-Antwort an alle Sequenzen und `AckRequested` Nachrichten.

#### <a name="closesequence-exchange"></a>CloseSequence-Austausch

Der WCF-Initiator überträgt eine `CloseSequence` Nachricht über eine HTTP-Anforderung und erwartet die `CreateSequenceResponse` Nachricht in der HTTP-Antwort. Der WCF-Responder überträgt die `CloseSequenceResponse` Nachricht in der HTTP-Antwort.

#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch

Der WCF-Initiator überträgt eine `TerminateSequence` Nachricht über eine HTTP-Anforderung und erwartet die `TerminateSequenceResponse` Nachricht in der HTTP-Antwort. Der WCF-Responder überträgt die `TerminateSequenceResponse` Nachricht in der HTTP-Antwort.

### <a name="one-way-addressable-initiator"></a>Unidirektionaler, adressierbarer Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein unidirektionales Nachrichtenaustausch Muster unter Verwendung einer Sequenz über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator überträgt eine- `CreateSequence` Nachricht ohne- `Offer` Element in einer HTTP-Anforderung. Der WCF-Responder erstellt eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht ohne- `Accept` Element in einer HTTP-Anforderung.

### <a name="duplex-addressable-initiator"></a>Adressierbarer Duplex-Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein vollständig asynchrones bidirektionales Nachrichtenaustausch Muster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Request/Reply`, `Addressable`-Initiator kombinieren. WCF verwendet HTTP-Anforderungen, um alle Nachrichten zu übertragen. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator überträgt eine- `CreateSequence` Nachricht mit einem- `Offer` Element in einer HTTP-Anforderung. Der WCF-Responder stellt sicher, dass `CreateSequence` ein- `Offer` Element aufweist, erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht mit einem- `Accept` Element.

#### <a name="sequence-lifetime"></a>Sequenzlebensdauer

WCF behandelt die beiden Sequenzen als eine Vollduplex Sitzung.

Wenn Sie einen Fehler erzeugen, der eine Sequenz Fehler erzeugt, erwartet WCF, dass der Remote Endpunkt beide Sequenzen als fehlerhaft eingibt. Beim Lesen eines Fehlers, bei dem ein Fehler auftritt, gibt WCF beide Sequenzen aus.

WCF kann seine ausgehende Sequenz schließen und die Verarbeitung von Nachrichten in der eingehenden Sequenz fortsetzen. Umgekehrt kann WCF das Ende der eingehenden Sequenz verarbeiten und weiterhin Nachrichten in der ausgehenden Sequenz senden.

### <a name="request-reply-and-one-way-non-addressable-initiator"></a>Anforderung-Antwort- und unidirektionaler, nicht adressierbarer Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein unidirektionales Anforderungs-/Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal. WCF verwendet HTTP-Anforderungen, um alle Nachrichten vom Initiator an den Beantworter zu übertragen, und HTTP-Antworten, um alle Nachrichten vom Responder an den Initiator zu übertragen.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator überträgt eine `CreateSequence` Nachricht mit einem `Offer` -Element in einer HTTP-Anforderung und erwartet die- `CreateSequenceResponse` Nachricht in der HTTP-Antwort. Der WCF-Responder erstellt eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht mit einem- `Accept` Element in der HTTP-Antwort.

#### <a name="one-way-message"></a>Unidirektionale Nachricht

Um einen unidirektionalen Nachrichtenaustausch erfolgreich abzuschließen, überträgt der WCF-Initiator eine Anforderungs Sequenz Nachricht in der HTTP-Anforderung und empfängt eine eigenständige `SequenceAcknowledgement` Nachricht in der HTTP-Antwort. Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.

Der WCF-Responder kann auf die Anforderung mit einer Bestätigung, einem Fehler oder einer Antwort mit leerem Text und HTTP 202-Statuscode Antworten.

#### <a name="two-way-messages"></a>Bidirektionale Nachrichten

Um ein bidirektionales Nachrichtenaustausch Protokoll erfolgreich abzuschließen, überträgt der WCF-Initiator eine Anforderungs Sequenz Nachricht in der HTTP-Anforderung und empfängt eine Antwort Sequenz Nachricht in der HTTP-Antwort. Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.

Der WCF-Responder antwortet möglicherweise mit einer Anwendungs Antwort, einem Fehler oder einer Antwort mit leerem Text und HTTP 202-Statuscode auf die Anforderung.

Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.

#### <a name="retrying-replies"></a>Wiederholen von Antworten

WCF basiert auf einer HTTP-Anforderung-Antwort-Korrelation für die bidirektionale Nachrichtenaustausch-Protokoll Korrelation. Aus diesem Grund beendet der WCF-Initiator den Wiederholungsversuch einer Anforderungs Sequenz Nachricht nicht, wenn die Anforderungs Sequenz Nachricht bestätigt wird, sondern wenn die HTTP-Antwort einen `SequenceAcknowledgement` , eine Anwendungs Antwort oder einen Fehler enthält. Der WCF-Responder wiederholt Antworten auf die HTTP-Antwort der Anforderung, mit der die Antwort korreliert wird.

#### <a name="closesequence-exchange"></a>CloseSequence-Austausch

Nachdem alle Antwort Sequenz Nachrichten und Bestätigungen für alle unidirektionalen Anforderungs Sequenz Nachrichten empfangen wurden, überträgt der WCF `CloseSequence` -Initiator eine Nachricht für die Anforderungs Sequenz in einer HTTP-Anforderung und erwartet die `CloseSequenceResponse` in der HTTP-Antwort.

Durch Schließen der Anforderungssequenz wird die Antwortsequenz implizit geschlossen. Dies bedeutet, dass der WCF-Initiator die endgültige Antwort Sequenz `SequenceAcknowledgement` in der `CloseSequence` Nachricht enthält und dass die Antwort Sequenz keinen `CloseSequence` Austausch hat.

Der WCF-Responder stellt sicher, dass alle Antworten bestätigt werden, und überträgt die `CloseSequenceResponse` Nachricht in der HTTP-Antwort.

#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch

Nach dem Empfang der `CloseSequenceResponse` Nachricht überträgt der WCF-Initiator eine `TerminateSequence` Nachricht für die Anforderungs Sequenz in einer HTTP-Anforderung und erwartet die `TerminateSequenceResponse` in der HTTP-Antwort.

Wie beim `CloseSequence`-Austausch wird durch Beendigung der Anforderungssequenz die Antwortsequenz implizit beendet. Dies bedeutet, dass der WCF-Initiator die endgültige Antwort Sequenz `SequenceAcknowledgement` in der `TerminateSequence` Nachricht enthält und dass die Antwort Sequenz keinen `TerminateSequence` Austausch hat.

Der WCF-Responder überträgt die `TerminateSequenceResponse` Nachricht in der HTTP-Antwort.

### <a name="requestreply-addressable-initiator"></a>Adressierbarer Anforderung/Antwort-Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein Anforderung-Antwort-Nachrichtenaustausch Muster mithilfe von zwei Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. Dieses Nachrichtenaustauschmuster lässt sich bis zu einem gewissen Grad mit dem Nachrichtenaustauschmuster für einen `Duplex, Addressable`-Initiator kombinieren. WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator überträgt eine- `CreateSequence` Nachricht mit einem- `Offer` Element in einer HTTP-Anforderung. Der WCF-Responder stellt sicher, dass der `CreateSequence` über ein `Offer` -Element verfügt, erstellt dann eine Sequenz und überträgt die `CreateSequenceResponse` Nachricht mit einem- `Accept` Element.

#### <a name="requestreply-correlation"></a>Anforderung/Antwort-Korrelation

Folgendes gilt für alle korrelierenden Anforderungen und Antworten:

- WCF stellt sicher, dass alle Anwendungs Anforderungs Nachrichten einen `ReplyTo` Endpunkt Verweis und einen haben `MessageId` .

- WCF wendet den lokalen Endpunkt Verweis auf die einzelnen Anwendungs Anforderungs Nachrichten an `ReplyTo` . Der lokale Endpunktverweis ist der `CreateSequence`-Verweis der `ReplyTo`-Nachricht für den Initiator und der `CreateSequence`-Verweis der `To`-Nachricht für den Beantworter.

- WCF stellt sicher, dass eingehende Anforderungs Nachrichten einen `MessageId` und einen tragen `ReplyTo` .

- WCF stellt sicher, dass der `ReplyTo` URI des Endpunkt Verweises für alle Anwendungs Anforderungs Nachrichten dem lokalen Endpunkt Verweis entspricht, wie zuvor definiert.

- WCF stellt sicher, dass alle Antworten die richtigen `RelatesTo` -und- `To` Header nach den `wsa` Anforderungs-/antwortkorrelations-Regeln
