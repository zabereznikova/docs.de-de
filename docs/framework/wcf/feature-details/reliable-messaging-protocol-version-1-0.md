---
title: Zuverlässiges Messaging-Protokoll, Version 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: f45a0d5e50e9ab8a07a203d2c40ad36ef298a40d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33497051"
---
# <a name="reliable-messaging-protocol-version-10"></a>Zuverlässiges Messaging-Protokoll, Version 1.0
Dieses Thema enthält Details zur Implementierung der Windows Communication Foundation (WCF) für die WS-Reliable Messaging-Version von Februar 2005 (Version 1.0)-Protokoll für die Interoperation mithilfe des HTTP-Transports erforderlich. WCF folgt die WS-ReliableMessaging-Spezifikation mit den Einschränkungen und klarstellungen erläutert, die in diesem Thema. Beachten Sie, dass das zuverlässige WS-Messaging-Protokoll in der Version&#160;1.0 ab [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] implementiert ist.  
  
 Die WS-Reliable Messaging-Version von Februar 2005 Protokoll wird in WCF von implementiert die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:  
  
-   Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert  
  
-   Beantworter: der Dienst, der die Anforderungen des Initiators empfängt  
  
 In diesem Dokument werden die in der folgenden Tabelle aufgeführten Präfixe und Namespaces verwendet.  
  
|Präfix|Namespace|  
|------------|---------------|  
|wsrm|http://schemas.xmlsoap.org/ws/2005/02/rm|  
|netrm|http://schemas.microsoft.com/ws/2006/05/rm|  
|s|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://schemas.xmlsoap.org/ws/2005/08/addressing|  
|wsse|http://docs.oasis-open.org/wss/2004/01/oasis-200401-wssecurity-secext-1.0.xsd|  
  
## <a name="messaging"></a>Messaging  
  
### <a name="sequence-establishment-messages"></a>Sequenzeinrichtungsnachrichten  
 WCF implementiert `CreateSequence` und `CreateSequenceResponse` Nachrichten an eine zuverlässige nachrichtensequenz einzurichten. Es gelten die folgenden Einschränkungen:  
  
-   B1101: Der Initiator WCF generiert das optionale Expires-Element im nicht die `CreateSequence` Nachricht oder in den Fällen bei der `CreateSequence` Nachricht enthält eine `Offer` -Element, das optionale `Expires` Element in der `Offer` Element.  
  
-   B1102: Beim Zugriff auf die `CreateSequence` Meldung, die WCF`Responder` sendet und empfängt sowohl `Expires` Elemente, wenn vorhanden, aber ihre Werte nicht verwendet.  
  
 Zuverlässiges WS-Messaging führt den `Offer`-Mechanismus ein, um zwei umgekehrt korrelierende Sequenzen einzurichten, die eine Sitzung bilden.  
  
-   R1103: Wenn `CreateSequence` ein `Offer`-Element enthält, muss der zuverlässige Messaging-Beantworter entweder die Sequenz akzeptieren und mit `CreateSequenceResponse` antworten (enthält ein `wsrm:Accept`-Element), wodurch die zwei umgekehrt korrelierenden Sequenzen gebildet werden, oder er muss die `CreateSequence`-Anforderung zurückweisen.  
  
-   R1104: `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten müssen an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.  
  
-   R1105: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` müssen Adresswerte aufweisen, die sich oktettweise entsprechen.  
  
     Der WCF-Beantworter stellt sicher, dass der URI-Teil der `AcksTo` und `ReplyTo` EPRs identisch sind, vor dem Erstellen einer Sequenz.  
  
-   R1106: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` sollten den gleichen Satz von Verweisparametern aufweisen.  
  
     WCF wird nicht erzwungen, sondern setzt voraus, [Verweisparameter] `AcksTo` und `ReplyTo` auf `CreateSequence` identisch sind und verwendet [Verweisparameter] aus `ReplyTo` -Endpunktverweis für Bestätigungen und Nachrichten umgekehrter Sequenz.  
  
-   R1107: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.  
  
-   R1108: Wenn mithilfe des Offer-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, muss die `[address]`-Eigenschaft des `wsrm:AcksTo`-Endpunktverweises, ein dem `wsrm:Accept`-Element von `CreateSequenceResponse` untergeordnetes Element, mit dem Ziel-URI von `CreateSequence` byteweise übereinstimmen.  
  
-   R1109: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen die vom Initiator gesendeten Nachrichten und die vom Beantworter gesendeten Bestätigungen der Nachrichten an den gleichen Endpunktverweis gesendet werden.  
  
     WCF verwendet WS-Reliable Messaging, um zuverlässige Sitzungen zwischen dem Initiator und Beantworter einzurichten. WCF WS-ReliableMessaging-Implementierung bietet zuverlässige Sitzungen für unidirektionale, Anforderung-Antwort- und Vollduplex-Nachrichtenmuster. Die WS-Reliable Messaging `Offer` Mechanismus auf `CreateSequence` / `CreateSequenceResponse` können Sie die zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein, die für alle Endpunkte Nachricht geeignet ist. Da WCF eine Sicherheitsgarantie für solcher Sitzungen sowie End-to-End-Schutz bietet, ist es ratsam, um sicherzustellen, dass Nachrichten an den gleichen Teilnehmer am selben Ziel ankommen. Dies lässt auch Piggyback-Übertragung von Sequenzbestätigungen auf Anwendungsnachrichten zu. Daher gelten Einschränkungen R1104, R1105 und R1108 für WCF.  
  
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
  
-   B1201:WCF generiert und greift auf-Sequenznummern nicht höher als `xs:long`des inklusive Maximalwert 9223372036854775807.  
  
-   B1202:WCF generiert immer eine ohne Text letzte Meldung mit der Aktions-URI des http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
-   B1203: WCF empfängt und sendet eine Nachricht mit einem sequenzheader, der enthält einem `LastMessage` Element, sofern der Aktions-URI nicht besteht http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
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
 WCF verwendet `AckRequested` -Header als Keep-alive-Mechanismus. WCF generiert nicht das optionale `MessageNumber` Element. Nach dem Empfang einer Nachricht mit einer `AckRequested` Header, enthält die `MessageNumber` -Element WCF ignoriert den `MessageNumber` Wert des Elements, wie im folgenden Beispiel gezeigt.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>SequenceAcknowledgement-Header  
 WCF verwendet den Piggyback-Mechanismus für WS-Reliable Messaging bereitgestellten sequenzbestätigungen.  
  
-   R1401: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, kann der `SequenceAcknowledgement`-Header in jede an den vorgesehenen Empfänger gesendete Anwendungsnachricht aufgenommen werden.  
  
-   B1402: Wenn WCF eine Bestätigung vor dem Empfangen von sequenznachrichten generieren muss (z. B. erfüllen einer `AckRequested` Nachricht), WCF generiert eine `SequenceAcknowledgement` Header mit dem Bereich 0-0, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: WCF löst keine `SequenceAcknowledgement` -Headern, enthalten eine `Nack` -Element, unterstützt jedoch `Nack` Elemente.  
  
### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging-Fehler  
 Im folgenden finden eine Liste der Einschränkungen, die für die WCF-Implementierung des WS-ReliableMessaging-Fehler gelten:  
  
-   B1501: WCF löst keine `MessageNumberRollover` Fehler.  
  
-   B1502:WCF Endpunkt generiert möglicherweise `CreateSequenceRefused` Fehler auf, wie in der Spezifikation beschrieben.  
  
-   B1503:when den Dienstendpunkt seine Verbindungsgrenze erreicht und keine weiteren Verbindungen verarbeiten, WCF generiert einen zusätzlichen `CreateSequenceRefused` -Fehlersubcode `netrm:ConnectionLimitReached`, wie im folgenden Beispiel gezeigt.  
  
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
 Da WS-ReliableMessaging WS-Adressierung verwendet, kann WCF WS-Reliable Messaging Implementierung WS-Adressierungsfehler generieren. Dieser Abschnitt behandelt die WS-Adressierungsfehler, die WCF explizit auf der WS-ReliableMessaging-Schicht generiert:  
  
-   B1601:WCF generiert den Fehler, die Nachricht adressiert Header erforderlich, wenn eine der folgenden Aussagen zutrifft:  
  
    -   Eine Nachricht hat keinen `Sequence`-Header und keinen `Action`-Header.  
  
    -   Eine `CreateSequence`-Nachricht hat keinen `MessageId`-Header.  
  
    -   Eine `CreateSequence`-Nachricht hat keinen `ReplyTo`-Header.  
  
-   B1602:WCF generiert den Fehler, die Aktion nicht unterstützt, als Antwort auf eine Nachricht, die fehlen einer `Sequence` Header und verfügt über eine `Action` Header, der nicht erkannten in der WS-ReliableMessaging-Spezifikation ist.  
  
-   B1603:WCF generiert den Fehler, der Endpunkt nicht verfügbar, um anzugeben, dass der Endpunkt die Sequenz basierend auf der Prüfung nicht verarbeitet werden die `CreateSequence` Nachricht Adressheader.  
  
## <a name="protocol-composition"></a>Protokollkomposition  
  
### <a name="composition-with-ws-addressing"></a>Komposition mit WS-Adressierung  
 WCF unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung 2004/08 [WS-ADDR] und W3C WS-Adressierung 1.0 Empfehlungen [WS-ADDR-CORE] und [WS-ADDR-SOAP].  
  
 Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die verwendete Version der WS-Adressierung nicht ein. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
-   R2101: sowohl WS-Adressierung 2004/08 und WS-Adressierung 1.0 mit WS-Reliable Messaging verwendet werden kann.  
  
-   R2102:A einzelne Version der WS-Adressierung muss verwendet werden, in der gesamten einer angegebenen WS-Reliable Messaging-Sequenz oder ein Paar umgekehrter Sequenzen korreliert mit der `wsrm:Offer` Mechanismus.  
  
### <a name="composition-with-soap"></a>Komposition mit SOAP  
 WCF unterstützt die Verwendung von SOAP 1.1 und SOAP 1.2 mit zuverlässigem WS-Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Komposition mit WS-Sicherheit und WS-SecureConversation  
 WCF bietet Schutz für WS-Reliable Messaging-Sequenzen durch Verwenden von sicheren Transportmethode (HTTPS), Komposition mit WS-Security und Komposition mit WS-Secure Conversation. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
-   R2301: um die Integrität einer WS-Reliable Messaging-Sequenz neben der Integrität und Vertraulichkeit einzelner Nachrichten zu schützen, WCF erfordert, dass WS-Secure Conversation verwendet werden muss.  
  
-   R2302:AWS-Secure Conversation-Sitzung muss vor dem Einrichten von WS-Reliable Messaging Sequence(s) eingerichtet werden.  
  
-   R2303: Wenn die Lebensdauer einer zuverlässigen WS-Messaging-Sequenz die Lebensdauer der WS-Secure Conversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-Secure Conversation Renewal-Bindung erneuert werden.  
  
-   B2304:WS-Reliable Messaging-Sequenz oder ein paar umgekehrt korrelierte Sequenzen immer an eine einzelne WS-SecureConversation-Sitzung gebunden sind.  
  
     Die WCF-Quelle generiert die `wsse:SecurityTokenReference` Element im Abschnitt elementerweiterbarkeit der der `CreateSequence` Nachricht.  
  
-   R2305:when mit WS-Secure Conversation verfasst eine `CreateSequence` Nachricht darf die `wsse:SecurityTokenReference` Element.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Zuverlässige WS-Messaging WS-Richtlinienassertion  
 WCF verwendet die WS-Reliable Messaging WS-Policy-Assertion `wsrm:RMAssertion` Fähigkeiten von Endpunkten zu beschreiben. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
-   B3001: WCF fügt `wsrm:RMAssertion` WS-Richtlinienassertion an `wsdl:binding` Elemente. WCF unterstützt beide Anlagen `wsdl:binding` und `wsdl:port` Elemente.  
  
-   B3002: WCF unterstützt die folgenden optionalen Eigenschaften des WS-Reliable Messaging-Assertion und ermöglicht die Steuerung werden auf die WCF`ReliableMessagingBindingElement`:  
  
    -   `wsrm:InactivityTimeout`  
  
    -   `wsrm:AcknowledgementInterval`  
  
     Nachfolgend finden Sie ein Beispiel:  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a>Zuverlässige WS-Messaging-Erweiterung zur Ablaufsteuerung  
 WCF verwendet WS-ReliableMessaging-Erweiterbarkeit, um optionale Steuerung des sequenznachrichtenflusses Sequenz-Nachrichtenfluss zu ermöglichen.  
  
 Flusssteuerung aktiviert ist, durch Festlegen der `ReliableSessionBindingElement`des `FlowControlEnabled``bool` Eigenschaft `true`. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
-   B4001: Wenn zuverlässiges Messaging flusssteuerung aktiviert ist, WCF generiert eine `netrm:BufferRemaining` Element in der elementerweiterbarkeit des der `SequenceAcknowledgement` Header.  
  
-   B4002: Wenn zuverlässiges Messaging flusssteuerung aktiviert ist, WCF erfordert nicht, dass eine `netrm:BufferRemaining` Element vorhanden sein `SequenceAcknowledgement` -Header, wie im folgenden Beispiel gezeigt.  
  
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
  
-   B4003: WCF verwendet `netrm:BufferRemaining` , um anzugeben, wie viele der neue Nachrichten das zuverlässige Messaging-Ziel Puffern können.  
  
-   B4004: WCF zuverlässige Messaging-Dienst drosselt die Anzahl der Nachrichten, die übertragen werden, wenn die Anwendung für zuverlässiges Messaging-Ziel schnell Nachrichten empfangen kann. Das zuverlässige Messaging-Ziel puffert Nachrichten, und der Wert des Elements sinkt auf&#160;0.  
  
-   B4005: WCF generiert `netrm:BufferRemaining` -Ganzzahlwerte zwischen 0 und 4096 einschließlich und liest Ganzzahlwerte zwischen 0 und `xs:int`des `maxInclusive` Wert (214748364) einschließlich.  
  
## <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster  
 Dieser Abschnitt beschreibt die WCF Verhalten, wenn WS-Reliable Messaging für verschiedene Nachrichtenaustauschmuster verwendet wird. Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:  
  
-   Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall, der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.  
  
-   Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.  
  
### <a name="one-way-non-addressable-initiator"></a>Unidirektionaler, nicht adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen HTTP-Kanal. WCF verwendet die HTTP-Anforderungen, um alle Nachrichten vom RMS zum RMD zu übertragen und die HTTP-Antwort zur Übertragung aller Nachrichten vom RMD zum RMS zu übertragen.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` -Nachricht ohne Angebot. Der WCF-Beantworter wird sichergestellt, dass die `CreateSequence` kein Angebot vor dem Erstellen einer Sequenz aufweist. Der WCF-Beantworter reagiert auf die `CreateSequence` Anforderung mit einem `CreateSequenceResponse` Nachricht.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Der WCF--Initiator erstellt Bestätigungen als Antwort alle Nachrichten mit Ausnahme der `CreateSequence` -Nachrichten und Fehlernachrichten. Der WCF-Beantworter generiert eine eigenständige Bestätigung in der Antwort auf Sequenzen und `AckRequested` Nachrichten.  
  
#### <a name="terminatesequence-message"></a>TerminateSequence-Nachricht  
 WCF behandelt `TerminateSequence` als unidirektionalen Vorgang, d. h. die HTTP-Antwort einen leeren Textbereich und den HTTP-Statuscode 202 hat.  
  
### <a name="one-way-addressable-initiator"></a>Unidirektionaler, adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung eines eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` -Nachricht ohne Angebot. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` kein Angebot vor dem Erstellen einer Sequenz aufweist. Der WCF-Beantworter überträgt die `CreateSequenceResponse` Nachricht auf eine HTTP-Anforderung adressiert werden, mit der `ReplyTo` Endpunktverweis.  
  
### <a name="duplex-addressable-initiator"></a>Adressierbarer Duplex-Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein vollständig asynchrones bidirektionales Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` ein Angebot vor dem Erstellen einer Sequenz aufweist. WCF sendet die `CreateSequenceResponse` auf die HTTP-Anforderung adressiert werden, um die `CreateSequence`des `ReplyTo` Endpunktverweis.  
  
#### <a name="sequence-lifetime"></a>Sequenzlebensdauer  
 WCF behandelt die beiden Sequenzen als eine vollduplexsitzung.  
  
 Nach dem Generieren eines Fehlers, der einem Fehler in einer Sequenz, erwartet WCF Remoteendpunkt für beide Sequenzen auslöst. Nach dem Lesen eines Fehlers, der einem Fehler in einer Sequenz, Fehler WCF für beide Sequenzen.  
  
 WCF kann seine ausgehende Sequenz schließen und zum Verarbeiten von Nachrichten in seiner eingehenden Sequenz fortfahren. Im Gegensatz dazu kann WCF das Schließen der eingehenden Sequenz durchführen und weiter Nachrichten in seiner ausgehenden Sequenz senden.  
  
### <a name="request-reply-non-addressable-initiator"></a>Nicht adressierbarer Anforderung-Antwort-Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet einen unidirektionalen und Anforderung-Antwort-Nachrichtenaustauschmuster, die unter Verwendung zweier Sequenzen über einen HTTP-Kanal. WCF HTTP-Anforderungen verwendet, um die anforderungssequenznachrichten zu übertragen und die HTTP-Antworten verwendet, um die Antwortsequenznachrichten zu übertragen.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` ein Angebot vor dem Erstellen einer Sequenz aufweist. Der WCF-Beantworter reagiert auf die `CreateSequence` Anforderung mit einem `CreateSequenceResponse` Nachricht.  
  
#### <a name="one-way-message"></a>Unidirektionale Nachricht  
 Um ein unidirektionales Nachrichtenaustauschprotokoll erfolgreich abgeschlossen haben, den WCF-Initiator eine anforderungssequenznachricht in der HTTP-Anforderung sendet und empfängt eine eigenständige `SequenceAcknowledgement` -Nachricht in der HTTP-Antwort. Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.  
  
 Der WCF-Beantworter kann mit einer Bestätigung, einen Fehler oder eine Antwort mit leerem Textbereich und dem HTTP-Statuscode 202 auf die Anforderung antworten.  
  
#### <a name="two-way-messages"></a>Bidirektionale Nachrichten  
 Um eine zwei-Wege-Nachrichtenaustauschprotokoll erfolgreich abgeschlossen haben, den WCF-Initiator überträgt eine anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine antwortsequenznachricht in der HTTP-Antwort. Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.  
  
 Der WCF-Beantworter kann mit einer Anwendungsantwort, einem Fehler oder eine Antwort mit leerem Textbereich und dem HTTP-Statuscode 202 auf die Anforderung antworten.  
  
 Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.  
  
#### <a name="retrying-replies"></a>Wiederholen von Antworten  
 WCF basiert auf HTTP-Anforderung / Antwort-Korrelation für das bidirektionale Nachrichtenaustauschprotokoll. Aus diesem Grund wird der WCF-Initiator nicht beendet eine anforderungssequenznachricht wiederholen, wenn die anforderungssequenznachricht bestätigt wird, sondern wenn die HTTP-Antwort eine Bestätigung, die Meldung für den Benutzer oder den Fehler enthält. Der WCF-Beantworter wiederholt die Antworten auf die HTTP-Anforderungsabschnitt der Anforderung mit der die Antwort korreliert ist.  
  
#### <a name="lastmessage-exchange"></a>LastMessage-Austausch  
 Der WCF-Initiator generiert und überträgt eine leere letzte Nachricht ohne Text auf den HTTP-Anforderungsabschnitt. WCF erfordert eine Antwort ignoriert jedoch diese Antwortnachricht. Der WCF-Beantworter reagiert auf die anforderungssequenz ohne Text letzte Meldung mit der Antwortsequenz letzte Nachricht ohne Text.  
  
 Wenn der WCF-Beantworter eine letzte Nachricht empfängt, in der der Aktions-URI nicht ist http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage, WCF-antwortet mit einer letzten Nachricht. Im Fall eines bidirektionalen Nachrichtenaustauschprotokolls enthält die letzte Nachricht die Anwendungsnachricht, im Falle eines unidirektionalen Nachrichtenaustauschprotokolls ist die letzte Nachricht leer.  
  
 Der WCF-Beantworter erfordert keine Bestätigung für die Antwortsequenz letzte Nachricht ohne Text.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch  
 Wenn alle Anfragen eine gültige Antwort erhalten haben, wird der WCF-Initiator generiert und überträgt der anforderungssequenz `TerminateSequence` Nachricht auf den HTTP-Anforderungsabschnitt. WCF erfordert eine Antwort ignoriert jedoch diese Antwortnachricht. Der WCF-Beantworter reagiert auf der anforderungssequenz `TerminateSequence` -Meldung mit der Antwortsequenz `TerminateSequence` Nachricht.  
  
 In einer normalen Abschlusssequenz enthalten beide `TerminateSequence`-Nachrichten einen vollständigen Bereich von `SequenceAcknowledgement`.  
  
### <a name="requestreply-addressable-initiator"></a>Adressierbarer Anforderung/Antwort-Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein Anforderung-Antwort-Nachrichtenaustauschmuster Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` Nachricht mit einem Angebot. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` ein Angebot vor dem Erstellen einer Sequenz aufweist. WCF sendet die `CreateSequenceResponse` auf die HTTP-Anforderung adressiert werden, um die `CreateSequence`des `ReplyTo` Endpunktverweis.  
  
#### <a name="requestreply-correlation"></a>Anforderung/Antwort-Korrelation  
 Der WCF-Initiator wird sichergestellt, dass alle anwendungsanforderungsnachrichten eine `MessageId` und ein `ReplyTo` Endpunktverweis. Der WCF-Initiator gilt die `CreateSequence` Nachricht `ReplyTo` Endpunktverweis für jede anwendungsanforderungsnachricht an. Der WCF-Beantworter erfordert, dass eingehende Anforderungsnachrichten-Verweis besitzen eine `MessageId` und ein `ReplyTo`. Der WCF-Beantworter stellt sicher, dass der Endpunktverweis-URIS der Endpunktverweise der `CreateSequence` und aller anwendungsanforderungsnachrichten identisch sind.
