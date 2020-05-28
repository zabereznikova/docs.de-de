---
title: Zuverlässiges Messaging-Protokoll, Version 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: ef45df0f1cae1f20cf34d07d154baee2cad34b29
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "84143444"
---
# <a name="reliable-messaging-protocol-version-10"></a>Zuverlässiges Messaging-Protokoll, Version 1.0

Dieses Thema behandelt Windows Communication Foundation (WCF)-Implementierungsdetails für das WS-zuverlässige Messaging-Protokoll vom Februar 2005 (Version 1,0), das für die Interoperation mithilfe des http-Transports erforderlich ist. WCF befolgt die Spezifikation für zuverlässiges WS-Messaging mit den in diesem Thema erläuterten Einschränkungen und Erläuterungen. Beachten Sie, dass das WS-ReliableMessaging-Protokoll, Version 1,0, ab dem WinFX implementiert wird.

Das WS-zuverlässiges Messaging-Protokoll vom Februar 2005 wird in WCF vom implementiert <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> .

Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:

- Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert

- Beantworter: der Dienst, der die Anforderungen des Initiators empfängt

In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.

|Präfix|Namespace|
|------------|---------------|
|wsrm|`http://schemas.xmlsoap.org/ws/2005/02/rm`|
|netrm|`http://schemas.microsoft.com/ws/2006/05/rm`|
|s|`http://www.w3.org/2003/05/soap-envelope`|
|wsa|`http://schemas.xmlsoap.org/ws/2005/08/addressing|
|wsse|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd`|

## <a name="messaging"></a>Nachrichten

### <a name="sequence-establishment-messages"></a>Sequenzeinrichtungsnachrichten

WCF implementiert `CreateSequence` -und- `CreateSequenceResponse` Nachrichten, um eine zuverlässige Nachrichten Sequenz einzurichten. Es gelten die folgenden Einschränkungen:

- B1101: der WCF-Initiator generiert das optionale abläuft-Element nicht in der `CreateSequence` Nachricht oder, wenn die `CreateSequence` Nachricht ein-Element enthält `Offer` , das optionale- `Expires` Element im- `Offer` Element.

- B1102: Wenn Sie auf die `CreateSequence` Nachricht zugreifen, `Responder` sendet und empfängt der WCF beide `Expires` Elemente, wenn Sie vorhanden sind, verwendet jedoch ihre Werte nicht.

Zuverlässiges WS-Messaging führt den `Offer`-Mechanismus ein, um zwei umgekehrt korrelierende Sequenzen einzurichten, die eine Sitzung bilden.

- R1103: Wenn `CreateSequence` ein `Offer`-Element enthält, muss der zuverlässige Messaging-Beantworter entweder die Sequenz akzeptieren und mit `CreateSequenceResponse` antworten (enthält ein `wsrm:Accept`-Element), wodurch die zwei umgekehrt korrelierenden Sequenzen gebildet werden, oder er muss die `CreateSequence`-Anforderung zurückweisen.

- R1104: `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten müssen an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.

- R1105: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` müssen Adresswerte aufweisen, die sich oktettweise entsprechen.

  Der WCF-Responder überprüft, ob der URI-Teil des `AcksTo` -und des- `ReplyTo` EPRS vor dem Erstellen einer Sequenz identisch ist.

- R1106: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` sollten den gleichen Satz von Verweisparametern aufweisen.

  WCF erzwingt nicht, sondern geht davon aus, dass [Verweis Parameter] von `AcksTo` und `ReplyTo` auf `CreateSequence` identisch sind und [Verweis Parameter] aus dem `ReplyTo` Endpunkt Verweis für Bestätigungen und umgekehrte Sequenz Nachrichten verwendet.

- R1107: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.

- R1108: Wenn mithilfe des Offer-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, muss die `[address]`-Eigenschaft des `wsrm:AcksTo`-Endpunktverweises, ein dem `wsrm:Accept`-Element von `CreateSequenceResponse` untergeordnetes Element, mit dem Ziel-URI von `CreateSequence` byteweise übereinstimmen.

- R1109: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen die vom Initiator gesendeten Nachrichten und die vom Beantworter gesendeten Bestätigungen der Nachrichten an den gleichen Endpunktverweis gesendet werden.

  WCF verwendet zuverlässiges WS-Messaging, um zuverlässige Sitzungen zwischen dem Initiator und dem Beantworter einzurichten. Die WS-zuverlässige WS-Messaging-Implementierung von WCF bietet eine zuverlässige Sitzung für unidirektionale, Anforderungs-Antwort-und vollständige Duplex Nachrichten Muster. Der zuverlässige WS-Messaging- `Offer` Mechanismus `CreateSequence` / `CreateSequenceResponse` ermöglicht Ihnen das Einrichten von zwei korrelierten umgekehrten Sequenzen und stellt ein Sitzungsprotokoll bereit, das für alle Nachrichten Endpunkte geeignet ist. Da WCF eine Sicherheitsgarantie für eine solche Sitzung bietet, einschließlich End-to-End-Schutz für die Sitzungs Integrität, ist es praktisch, sicherzustellen, dass Nachrichten, die für dieselbe Partei vorgesehen sind, am gleichen Ziel ankommen. Dies lässt auch Piggyback-Übertragung von Sequenzbestätigungen auf Anwendungsnachrichten zu. Daher gelten die Einschränkungen R1104, R1105 und R1108 für WCF.

Ein Beispiel für eine `CreateSequence`-Nachricht.

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

 Ein Beispiel für eine `CreateSequenceResponse`-Nachricht.

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

### <a name="sequence"></a>Sequenz

Die folgende Liste enthält die Einschränkungen, die für Sequenzen gelten:

- B1201: WCF generiert und greift auf Sequenznummern zu `xs:long` , die nicht größer sind als der maximale inklusivwert, 9223372036854775807.

- B1202: WCF generiert immer eine letzte leere Nachricht mit dem Aktions-URI von `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .

- B1203: WCF empfängt und übermittelt eine Nachricht mit einem Sequenz Header, der ein-Element enthält, solange `LastMessage` der Aktions-URI nicht ist `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` .

Ein Beispiel für einen Sequenzheader.

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

### <a name="ackrequested-header"></a>AckRequested-Header

WCF verwendet den `AckRequested` -Header als Keep-Alive-Mechanismus. WCF generiert nicht das optionale- `MessageNumber` Element. Beim Empfang einer Nachricht mit einem- `AckRequested` Header, der das- `MessageNumber` Element enthält, ignoriert WCF den Wert des `MessageNumber` -Elements, wie im folgenden Beispiel gezeigt.

```xml
<wsrm:AckRequested>
  <wsrm:Identifier>
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
  </wsrm:Identifier>
</wsrm:AckRequested>
```

### <a name="sequenceacknowledgement-header"></a>SequenceAcknowledgement-Header

WCF verwendet den Piggy-back-Mechanismus für Sequenz Bestätigungen, die im zuverlässigen WS-Messaging bereitgestellt werden.

- R1401: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, kann der `SequenceAcknowledgement`-Header in jede an den vorgesehenen Empfänger gesendete Anwendungsnachricht aufgenommen werden.

- B1402: Wenn WCF vor dem empfangen von Sequenz Nachrichten eine Bestätigung generieren muss (z. b. um eine `AckRequested` Nachricht zu erfüllen), generiert WCF einen `SequenceAcknowledgement` Header, der den Bereich 0-0 enthält, wie im folgenden Beispiel gezeigt.

  ```xml
  <wsrm:SequenceAcknowledgement>
    <wsrm:Identifier>
      urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36
    </wsrm:Identifier>
    <wsrm:AcknowledgementRange Upper="0" Lower="0"/>
  </wsrm:SequenceAcknowledgement>
  ```

- B1403: WCF generiert keine `SequenceAcknowledgement` Header, die ein- `Nack` Element enthalten, aber-Elemente unterstützen `Nack` .

### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging-Fehler

Im folgenden finden Sie eine Liste der Einschränkungen, die für die WCF-Implementierung von WS-zuverlässigen Messaging Fehlern gelten:

- B1501: WCF generiert keine `MessageNumberRollover` Fehler.

- B1502: der WCF-Endpunkt generiert möglicherweise `CreateSequenceRefused` Fehler, wie in der Spezifikation beschrieben.

- B1503: Wenn der Dienst Endpunkt das Verbindungs Limit erreicht und keine neuen Verbindungen verarbeiten kann, generiert WCF einen zusätzlichen `CreateSequenceRefused` Fehlersubcode, `netrm:ConnectionLimitReached` , wie im folgenden Beispiel gezeigt.

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

### <a name="ws-addressing-faults"></a>WS-Adressierungsfehler

Da das zuverlässige WS-Messaging WS-Adressierung verwendet, kann die Implementierung der zuverlässigen WS-Messaging-Implementierung WS-Adressierungs Fehler generieren. In diesem Abschnitt werden die WS-Adressierungs Fehler erläutert, die von WCF explizit auf der zuverlässigen WS-Messaging-Schicht generiert werden:

- B1601: WCF generiert den Fehlermeldungs Adressierungs Header, der erforderlich ist, wenn einer der folgenden Punkte zutrifft:

  - Eine Nachricht hat keinen `Sequence`-Header und keinen `Action`-Header.

  - Eine `CreateSequence`-Nachricht hat keinen `MessageId`-Header.

  - Eine `CreateSequence`-Nachricht hat keinen `ReplyTo`-Header.

- B1602: WCF generiert die Fehler Aktion, die in der Antwort auf eine Nachricht, die keinen Header enthält, nicht unterstützt wird `Sequence` und über einen- `Action` Header verfügt, der in der WS-zuverlässigen Messaging Spezifikation nicht erkannt wird.

- B1603: WCF generiert den Fehler Endpunkt nicht verfügbar, um anzugeben, dass der Endpunkt die Sequenz nicht auf der Grundlage der Untersuchung der `CreateSequence` Adressierungs Header der Nachricht verarbeitet.

## <a name="protocol-composition"></a>Protokollkomposition

### <a name="composition-with-ws-addressing"></a>Komposition mit WS-Adressierung

WCF unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung 2004/08 [ws-addr] und W3C WS-Adressierung 1,0 Empfehlungen [ws-addr-core] und [ws-addr-SOAP].

Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die verwendete Version der WS-Adressierung nicht ein. Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:

- R2101:Sowohl WS-Adressierung&#160;2004/08 als auch WS-Adressierung&#160;1.0 können mit zuverlässigem WS-Messaging verwendet werden.

- R2102: für eine bestimmte zuverlässige WS-Messaging-Sequenz oder ein Paar umgekehrter Sequenzen, die mithilfe des-Mechanismus korreliert werden, muss eine einzelne Version der WS-Adressierung verwendet werden `wsrm:Offer` .

### <a name="composition-with-soap"></a>Komposition mit SOAP

WCF unterstützt die Verwendung von SOAP 1,1 und SOAP 1,2 mit zuverlässigem WS-Messaging.

### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Komposition mit WS-Sicherheit und WS-SecureConversation

WCF bietet Schutz für zuverlässige WS-Messaging-Sequenzen mithilfe von Secure Transport (HTTPS), Komposition mit WS-Sicherheit und Komposition mit WS-Secure Conversation. Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:

- R2301: um die Integrität einer zuverlässigen WS-Messaging-Sequenz zusätzlich zur Integrität und Vertraulichkeit einzelner Nachrichten zu schützen, erfordert WCF, dass eine WS-Secure-Konversation verwendet werden muss.

- R2302:EineWS-Secure Conversation-Sitzung muss vor der Erstellung von zuverlässigen WS-Messaging-Sequenzen eingerichtet werden.

- R2303: Wenn die Lebensdauer einer zuverlässigen WS-Messaging-Sequenz die Lebensdauer der WS-Secure Conversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-Secure Conversation Renewal-Bindung erneuert werden.

- B2304:Die zuverlässige WS-Messaging-Sequenz bzw. das Paar korrelierter umgekehrter Sequenzen ist immer an eine einzelne WS-SecureConversation-Sitzung gebunden.

  Die WCF-Quelle generiert das- `wsse:SecurityTokenReference` Element im Abschnitt Element Erweiterbarkeit der `CreateSequence` Nachricht.

- R2305: Wenn eine Nachricht mit WS-Secure Conversation zusammengesetzt wird, `CreateSequence` muss Sie das- `wsse:SecurityTokenReference` Element enthalten.

## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Zuverlässige WS-Messaging WS-Richtlinienassertion

WCF verwendet WS-zuverlässiges WS-Policy-Assertionen `wsrm:RMAssertion` zum Beschreiben von Endpunkten-Funktionen. Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:

- B3001: WCF fügt `wsrm:RMAssertion` die WS-Policy-Assertionen an `wsdl:binding` Elemente an. WCF unterstützt sowohl Anhänge für `wsdl:binding` -als auch- `wsdl:port` Elemente.

- B3002: WCF unterstützt die folgenden optionalen Eigenschaften der zuverlässigen WS-Messaging-Assertion und ermöglicht Ihnen die Kontrolle über die WCF `ReliableMessagingBindingElement` :

  - `wsrm:InactivityTimeout`

  - `wsrm:AcknowledgementInterval`

  Im Folgenden finden Sie ein Beispiel.

  ```xml
  <wsrm:RMAssertion>
    <wsrm:InactivityTimeout Milliseconds="600000" />
    <wsrm:AcknowledgementInterval Milliseconds="200" />
  </wsrm:RMAssertion>
  ```

## <a name="flow-control-ws-reliable-messaging-extension"></a>Zuverlässige WS-Messaging-Erweiterung zur Ablaufsteuerung

WCF verwendet die Erweiterbarkeit von zuverlässigem WS-Messaging, um eine optionale zusätzliche strengere Kontrolle über den Sequenz Nachrichtenfluss bereitzustellen.

Die Fluss Steuerung wird aktiviert, indem die-Eigenschaft auf festgelegt wird <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> `true` . Im folgenden finden Sie eine Liste der Einschränkungen, die für WCF gelten:

- B4001: Wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, generiert WCF ein- `netrm:BufferRemaining` Element in der Element Erweiterbarkeit des- `SequenceAcknowledgement` Headers.

- B4002: Wenn die zuverlässige Messaging-Ablauf Steuerung aktiviert ist, erfordert WCF nicht `netrm:BufferRemaining` , dass ein-Element im-Header vorhanden ist `SequenceAcknowledgement` , wie im folgenden Beispiel gezeigt.

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

- B4003: WCF verwendet `netrm:BufferRemaining` , um anzugeben, wie viele neue Nachrichten das zuverlässige Messaging Ziel Puffern kann.

- B4004: der WCF-Dienst für zuverlässiges Messaging schränkt die Anzahl der übermittelten Nachrichten ein, wenn die zuverlässige Messaging-Zielanwendung keine Nachrichten mehr schnell empfangen kann. Das zuverlässige Messaging-Ziel puffert Nachrichten, und der Wert des Elements sinkt auf&#160;0.

- B4005: WCF generiert `netrm:BufferRemaining` ganzzahlige Werte zwischen 0 und 4096 einschließlich und liest ganzzahlige Werte zwischen 0 und `xs:int` dem `maxInclusive` Wert 214748364 einschließlich.

## <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster

In diesem Abschnitt wird das Verhalten von WCF beschrieben, wenn das zuverlässige WS-Messaging für verschiedene Nachrichtenaustausch Muster verwendet wird. Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:

- Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall, der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.

- Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.

### <a name="one-way-non-addressable-initiator"></a>Unidirektionaler, nicht adressierbarer Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein unidirektionales Nachrichtenaustausch Muster unter Verwendung einer Sequenz über einen HTTP-Kanal. WCF verwendet die HTTP-Anforderungen, um alle Nachrichten vom RMS zum RMD zu übertragen, und die HTTP-Antwort, um alle Nachrichten vom RMD zum RMS zu übertragen.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator generiert eine `CreateSequence` Nachricht ohne Angebot. Der WCF-Responder stellt `CreateSequence` vor dem Erstellen einer Sequenz sicher, dass kein Angebot hat. Der WCF-Responder antwortet `CreateSequence` mit einer Meldung auf die Anforderung `CreateSequenceResponse` .

#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement

Der WCF-Initiator verarbeitet Bestätigungen für die Antwort aller Meldungen außer der `CreateSequence` Nachricht und den Fehlermeldungen. Der WCF-Responder generiert stets eine eigenständige Bestätigung in der Antwort auf die Sequenz und die `AckRequested` Nachrichten.

#### <a name="terminatesequence-message"></a>TerminateSequence-Nachricht

WCF behandelt als unidirektionalen `TerminateSequence` Vorgang, d. h. die HTTP-Antwort weist einen leeren Textkörper und HTTP 202-Statuscode auf.

### <a name="one-way-addressable-initiator"></a>Unidirektionaler, adressierbarer Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein unidirektionales Nachrichtenaustausch Muster unter Verwendung einer Sequenz über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator generiert eine `CreateSequence` Nachricht ohne Angebot. Der WCF-Beantworter stellt `CreateSequence` vor dem Erstellen einer Sequenz sicher, dass kein Angebot hat. Der WCF-Responder überträgt die `CreateSequenceResponse` Nachricht über eine HTTP-Anforderung, die mit dem Endpunkt Verweis adressiert wird `ReplyTo` .

### <a name="duplex-addressable-initiator"></a>Adressierbarer Duplex-Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein vollständig asynchrones bidirektionales Nachrichtenaustausch Muster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot. Der WCF- `CreateSequence` Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die über ein Angebot verfügt. WCF sendet den `CreateSequenceResponse` in der HTTP-Anforderung, die an den `CreateSequence` -Endpunkt Verweis adressiert ist `ReplyTo` .

#### <a name="sequence-lifetime"></a>Sequenzlebensdauer

WCF behandelt die beiden Sequenzen als eine Vollduplex Sitzung.

Wenn Sie einen Fehler erzeugen, der eine Sequenz Fehler erzeugt, erwartet WCF, dass der Remote Endpunkt beide Sequenzen als fehlerhaft eingibt. Beim Lesen eines Fehlers, bei dem ein Fehler auftritt, gibt WCF beide Sequenzen aus.

WCF kann seine ausgehende Sequenz schließen und die Verarbeitung von Nachrichten in der eingehenden Sequenz fortsetzen. Umgekehrt kann WCF das Ende der eingehenden Sequenz verarbeiten und weiterhin Nachrichten in der ausgehenden Sequenz senden.

### <a name="request-reply-non-addressable-initiator"></a>Nicht adressierbarer Anforderung-Antwort-Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein unidirektionales Anforderungs-/Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal. WCF verwendet die HTTP-Anforderungen zum Übertragen der Anforderungs Sequenz Nachrichten und verwendet die HTTP-Antworten, um die Nachrichten der Antwort Sequenz zu übertragen.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot. Der WCF- `CreateSequence` Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die über ein Angebot verfügt. Der WCF-Responder antwortet `CreateSequence` mit einer Meldung auf die Anforderung `CreateSequenceResponse` .

#### <a name="one-way-message"></a>Unidirektionale Nachricht

Zum erfolgreichen Abschluss eines unidirektionalen Nachrichtenaustausch Protokolls überträgt der WCF-Initiator eine Anforderungs Sequenz Nachricht in der HTTP-Anforderung und empfängt eine eigenständige `SequenceAcknowledgement` Nachricht in der HTTP-Antwort. Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.

Der WCF-Responder kann auf die Anforderung mit einer Bestätigung, einem Fehler oder einer Antwort mit einem leeren Text-und HTTP 202-Statuscode Antworten.

#### <a name="two-way-messages"></a>Bidirektionale Nachrichten

Um ein bidirektionales Nachrichtenaustausch Protokoll erfolgreich abzuschließen, überträgt der WCF-Initiator eine Anforderungs Sequenz Nachricht in der HTTP-Anforderung und empfängt eine Antwort Sequenz Nachricht in der HTTP-Antwort. Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.

Der WCF-Responder kann auf die Anforderung mit einer Anwendungs Antwort, einem Fehler oder einer Antwort mit leerem Text und HTTP 202-Statuscode Antworten.

Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.

#### <a name="retrying-replies"></a>Wiederholen von Antworten

WCF basiert auf einer HTTP-Anforderung-Antwort-Korrelation für die bidirektionale Nachrichtenaustausch-Protokoll Korrelation. Aus diesem Grund beendet der WCF-Initiator den Wiederholungsversuch einer Anforderungs Sequenz Nachricht nicht, wenn die Anforderungs Sequenz Nachricht bestätigt wird, sondern wenn die HTTP-Antwort eine Bestätigung, eine Benutzer Nachricht oder einen Fehler enthält. Der WCF-Responder wiederholt Antworten auf den HTTP-Anforderungs Abschnitt der Anforderung, mit der die Antwort korreliert wird.

#### <a name="lastmessage-exchange"></a>LastMessage-Austausch

Der WCF-Initiator generiert und überträgt eine leere Körper letzte Nachricht auf dem HTTP-Anforderungs Abschnitt. WCF erfordert eine Antwort, ignoriert jedoch die tatsächliche Antwortnachricht. Der WCF-Responder antwortet auf die letzte Nachricht mit dem leeren Körper der Anforderungs Sequenz mit der letzten Meldung der Antwort Sequenz.

Wenn der WCF-Responder eine letzte Nachricht empfängt, bei der der Aktions-URI nicht ist `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage` , antwortet WCF mit einer letzten Meldung. Im Fall eines bidirektionalen Nachrichtenaustauschprotokolls enthält die letzte Nachricht die Anwendungsnachricht, im Falle eines unidirektionalen Nachrichtenaustauschprotokolls ist die letzte Nachricht leer.

Der WCF-Responder erfordert keine Bestätigung für die letzte Nachricht der Antwort Sequenz.

#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch

Wenn alle Anforderungen eine gültige Antwort erhalten haben, generiert und überträgt der WCF-Initiator die Nachricht der Anforderungs Sequenz `TerminateSequence` auf den HTTP-Anforderungs Abschnitt. WCF erfordert eine Antwort, ignoriert jedoch die tatsächliche Antwortnachricht. Der WCF-Responder antwortet `TerminateSequence` mit der Meldung der Antwort Sequenz auf die Nachricht der Anforderungs Sequenz `TerminateSequence` .

In einer normalen Abschlusssequenz enthalten beide `TerminateSequence`-Nachrichten einen vollständigen Bereich von `SequenceAcknowledgement`.

### <a name="requestreply-addressable-initiator"></a>Adressierbarer Anforderung/Antwort-Initiator

#### <a name="binding"></a>Bindung

WCF bietet ein Anforderung-Antwort-Nachrichtenaustausch Muster mithilfe von zwei Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet die HTTP-Anforderungen, um alle Nachrichten zu übertragen. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.

#### <a name="createsequence-exchange"></a>CreateSequence-Austausch

Der WCF-Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot. Der WCF- `CreateSequence` Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die über ein Angebot verfügt. WCF sendet den `CreateSequenceResponse` in der HTTP-Anforderung, die an den `CreateSequence` -Endpunkt Verweis adressiert ist `ReplyTo` .

#### <a name="requestreply-correlation"></a>Anforderung/Antwort-Korrelation

Der WCF-Initiator stellt sicher, dass alle Anwendungs Anforderungs Nachrichten einen `MessageId` und einen `ReplyTo` Endpunkt Verweis tragen. Der WCF-Initiator wendet den `CreateSequence` `ReplyTo` Endpunkt Verweis der Nachricht auf jede Anwendungs Anforderungs Nachricht an. Der WCF-Responder erfordert, dass eingehende Anforderungs Nachrichten einen `MessageId` und einen tragen `ReplyTo` . Der WCF-Responder stellt sicher, dass der URI des Endpunkt Verweises sowohl von `CreateSequence` als auch von allen Anwendungs Anforderungs Nachrichten identisch ist.
