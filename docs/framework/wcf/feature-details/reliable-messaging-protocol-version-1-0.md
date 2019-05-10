---
title: Zuverlässiges Messaging-Protokoll, Version 1.0
ms.date: 03/30/2017
ms.assetid: a5509a5c-de24-4bc2-9a48-19138055dcce
ms.openlocfilehash: 857bbbf9ffa1311c38cfc007e0cdc6bde06d6284
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64617579"
---
# <a name="reliable-messaging-protocol-version-10"></a>Zuverlässiges Messaging-Protokoll, Version 1.0
Dieses Thema enthält Details zur Implementierung von Windows Communication Foundation (WCF) für die WS-Reliable Messaging Februar-2005 (Version 1.0)-Protokoll für die Interoperation mithilfe des HTTP-Transports erforderlich sind. WCF folgt die WS-ReliableMessaging-Spezifikation mit den Einschränkungen und klarstellungen, die in diesem Thema erläutert. Beachten Sie, dass das zuverlässige WS-Messaging-Protokoll in der Version&amp;#160;1.0 ab [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] implementiert ist.  
  
 Die WS-Reliable Messaging Februar 2005 Protokoll wird in WCF von implementiert die <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>.  
  
 Der Einfachheit halber verwendet dieses Thema die folgenden Rollen:  
  
- Initiator: der Client, der die Erstellung der zuverlässigen WS-Messaging-Sequenz initiiert  
  
- Beantworter: der Dienst, der die Anforderungen des Initiators empfängt  
  
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
  
- B1101: Der WCF--Initiator generiert nicht das optionale Expires-Element in der `CreateSequence` Nachricht oder, in den Fällen bei der `CreateSequence` Nachricht enthält ein `Offer` -Element, das optionale `Expires` Element in der `Offer` Element.  
  
- B1102: Beim Zugriff auf die `CreateSequence` Nachricht, die WCF`Responder` sendet und empfängt sowohl `Expires` Elementen, wenn sie vorhanden sind, jedoch nicht deren Werte verwendet.  
  
 Zuverlässiges WS-Messaging führt den `Offer`-Mechanismus ein, um zwei umgekehrt korrelierende Sequenzen einzurichten, die eine Sitzung bilden.  
  
- R1103: Wenn `CreateSequence` enthält ein `Offer` -Element, das zuverlässige Messaging-Beantworter muss entweder die Sequenz akzeptieren und reagieren Sie mit `CreateSequenceResponse` , enthält eine `wsrm:Accept` -Element, erstellen zwei umgekehrte Sequenzen oder Ablehnen der `CreateSequence`Anforderung.  
  
- R1104: `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten müssen an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.  
  
- R1105: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` müssen Adresswerte aufweisen, die sich oktettweise entsprechen.  
  
     Der WCF-Beantworter überprüft, ob die URI-Teil der `AcksTo` und `ReplyTo` EPRs identisch sind, bevor die Sequenz.  
  
- R1106: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` sollten den gleichen Satz von Verweisparametern aufweisen.  
  
     WCF wird nicht erzwungen, sondern setzt voraus, [Verweisparameter] `AcksTo` und `ReplyTo` auf `CreateSequence` identisch sind und verwendet [Verweisparameter] aus `ReplyTo` -Endpunktverweis für Bestätigungen und Nachrichten umgekehrter Sequenz.  
  
- R1107: Bei zwei umgekehrte Sequenzen eingerichtet werden, mithilfe der `Offer` Mechanismus `SequenceAcknowledgement` und in umgekehrter fließenden Anwendungsnachrichten müssen an der `ReplyTo` -Endpunktverweis der `CreateSequence`.  
  
- R1108: Wenn zwei umgekehrte Sequenzen eingerichtet werden, mithilfe des Offer-Mechanismus, der `[address]` Eigenschaft der `wsrm:AcksTo` Endpunktverweis untergeordnetes Element des der `wsrm:Accept` Element der `CreateSequenceResponse` müssen byteweise das Ziel-URI von der übereinstimmen`CreateSequence`.  
  
- R1109: Wenn zwei umgekehrte Sequenzen eingerichtet werden, mithilfe der `Offer` Mechanismus, der vom Initiator und Bestätigungen der Nachrichten vom Beantworter gesendeten Nachrichten müssen an den gleichen Endpunktverweis gesendet werden.  
  
     WCF verwendet WS-Reliable Messaging, um zuverlässige Sitzungen zwischen dem Initiator und Beantworter einzurichten. WS-Reliable Messaging von WCF-Implementierung bietet zuverlässige Sitzungen für unidirektionale, Anforderung-Antwort- und Vollduplex-Nachrichtenmuster. Das WS-Reliable Messaging `Offer` Mechanismus auf `CreateSequence` / `CreateSequenceResponse` können Sie die zwei korrelierter umgekehrter Sequenzen einzurichten, und bietet ein, die für alle nachrichtenendpunkte geeignet ist. Da WCF eine Sicherheitsgarantie für solcher Sitzungen sowie End-to-End-Schutz bietet, ist es ratsam, um sicherzustellen, dass Nachrichten, die den gleichen Teilnehmer sollen auf dem gleichen Ziel eintreffen. Dies lässt auch Piggyback-Übertragung von Sequenzbestätigungen auf Anwendungsnachrichten zu. Daher gelten die Einschränkungen R1104, R1105 und R1108 für WCF.  
  
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
  
- B1201:WCF generiert und Zugriffe Sequenznummern nicht höher als `xs:long`des inklusive Maximalwert 9223372036854775807.  
  
- B1202:WCF generiert immer eine leere letzte Nachricht mit der Aktions-URI des `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.  
  
- B1203: WCF empfängt und sendet eine Nachricht mit einem sequenzheader, der enthält eine `LastMessage` Element, sofern der Aktions-URI nicht ist `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`.  
  
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
 WCF verwendet `AckRequested` -Header als Keep-alive-Mechanismus. WCF generiert nicht das optionale `MessageNumber` Element. Nach Erhalt einer Nachricht mit einer `AckRequested` Header, enthält die `MessageNumber` -Element WCF ignoriert den `MessageNumber` der Wert des Elements, wie im folgenden Beispiel gezeigt.  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>SequenceAcknowledgement-Header  
 WCF verwendet den Piggyback-Mechanismus für die im zuverlässigen WS-Messaging bereitgestellten sequenzbestätigungen.  
  
- R1401: Wenn zwei umgekehrte Sequenzen eingerichtet werden, mithilfe der `Offer` Mechanismus, der `SequenceAcknowledgement` Header kann in jede Anwendungsnachricht mit dem beabsichtigten Empfänger enthalten sein.  
  
- B1402: Wenn WCF eine Bestätigung empfangen von sequenznachrichten generieren muss (beispielsweise erfüllt ein `AckRequested` Nachricht), WCF generiert eine `SequenceAcknowledgement` Header, der den Bereich 0-0, enthält, wie im folgenden Beispiel gezeigt.  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
- B1403: WCF generiert keine `SequenceAcknowledgement` -Header mit einem `Nack` unterstützt jedoch Element `Nack` Elemente.  
  
### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging-Fehler  
 Im folgenden finden eine Liste der Einschränkungen, die für die WCF-Implementierung des WS-ReliableMessaging-Fehler gelten:  
  
- B1501: WCF generiert keine `MessageNumberRollover` Fehler.  
  
- B1502:WCF-Endpunkt generiert möglicherweise `CreateSequenceRefused` wie in der Spezifikation beschrieben.  
  
- B1503:when der Dienstendpunkt seine Verbindungsgrenze erreicht und keine weiteren Verbindungen verarbeiten, WCF generiert einen zusätzlichen `CreateSequenceRefused` -Fehlersubcode `netrm:ConnectionLimitReached`, wie im folgenden Beispiel gezeigt.  
  
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
 Da zuverlässiges WS-Messaging WS-Adressierung verwendet, kann WCF WS-Reliable-Messaging-Implementierung mit WS-Adressierungsfehler generieren. Dieser Abschnitt behandelt die WS-Adressierungsfehler, die von WCF explizit auf der WS-Reliable Messaging-Schicht generiert:  
  
- B1601:WCF generiert den Fehler, die Nachrichtenadressierungs-Header erforderlich, wenn eine der folgenden Bedingungen zutrifft:  
  
    - Eine Nachricht hat keinen `Sequence`-Header und keinen `Action`-Header.  
  
    - Eine `CreateSequence`-Nachricht hat keinen `MessageId`-Header.  
  
    - Eine `CreateSequence`-Nachricht hat keinen `ReplyTo`-Header.  
  
- B1602:WCF generiert den Fehler, die Aktion nicht unterstützt, als Antwort auf eine Nachricht, die nicht vorhanden ist eine `Sequence` Header und verfügt über eine `Action` Header, der nicht erkannten in der WS-ReliableMessaging-Spezifikation ist.  
  
- B1603:WCF generiert den Fehler, der Endpunkt nicht verfügbar, um anzugeben, dass der Endpunkt die Sequenz basierend auf einer Untersuchung der keine verarbeitet die `CreateSequence` Nachricht Adressheader.  
  
## <a name="protocol-composition"></a>Protokollkomposition  
  
### <a name="composition-with-ws-addressing"></a>Komposition mit WS-Adressierung  
 WCF unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung 2004/08 [WS-ADDR] und W3C WS-Adressierung 1.0 Empfehlungen [WS-ADDR-CORE] und [WS-ADDR-SOAP].  
  
 Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&amp;#160;2004/08, schränkt jedoch die verwendete Version der WS-Adressierung nicht ein. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
- R2101: sowohl WS-Adressierung 2004/08 und WS-Adressierung 1.0 können mit zuverlässigem WS-Messaging verwendet werden.  
  
- Einzelne R2102:A-Version der WS-Adressierung muss verwendet werden, während des gesamten eine gegebene WS-ReliableMessaging-Sequenz oder ein Paar umgekehrter Sequenzen korreliert mit der `wsrm:Offer` Mechanismus.  
  
### <a name="composition-with-soap"></a>Komposition mit SOAP  
 WCF unterstützt die Verwendung von SOAP 1.1 und SOAP 1.2 mit zuverlässigem WS-Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Komposition mit WS-Sicherheit und WS-SecureConversation  
 WCF bietet Schutz für die WS-ReliableMessaging-Sequenzen unter Verwendung von sicheren Transportmethode (HTTPS), Komposition mit WS-Security und Komposition mit WS-Secure Conversation. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
- R2301: um die Integrität einer WS-ReliableMessaging-Sequenz sowie die Integrität und Vertraulichkeit einzelner Nachrichten zu schützen, WCF erfordert, dass WS-Secure Conversation verwendet werden muss.  
  
- R2302:AWS-Secure Conversation-Sitzung muss vor der Erstellung von WS-ReliableMessaging-Sequenzen eingerichtet werden.  
  
- R2303: Wenn die WS-Reliable Messaging-Sequenz-Lebensdauer der WS-Secure Conversation Sitzung überschreitet die `SecurityContextToken` hergestellt, indem Sie mithilfe von WS-Secure Conversation muss mithilfe der entsprechenden WS-Secure Conversation Renewal-Bindung erneuert werden.  
  
- B2304:WS-Reliable Messaging-Sequenz bzw. das Paar korrelierter umgekehrter Sequenzen ist immer an eine einzelne WS-SecureConversation-Sitzung gebunden.  
  
     Die WCF-Quelle generiert die `wsse:SecurityTokenReference` Element im Abschnitt elementerweiterbarkeit der der `CreateSequence` Nachricht.  
  
- R2305:when mit WS-Secure Conversation verfasst eine `CreateSequence` Nachricht darf die `wsse:SecurityTokenReference` Element.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Zuverlässige WS-Messaging WS-Richtlinienassertion  
 WCF verwendet die WS-Reliable-Messaging WS-Richtlinienassertion `wsrm:RMAssertion` Fähigkeiten von Endpunkten zu beschreiben. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
- B3001: Fügt WCF `wsrm:RMAssertion` WS-Richtlinienassertion `wsdl:binding` Elemente. WCF unterstützt sowohl Anlagen in `wsdl:binding` und `wsdl:port` Elemente.  
  
- B3002: WCF unterstützt die folgenden optionalen Eigenschaften der WS-ReliableMessaging-Assertion und unter der Kontrolle bietet, auf die WCF`ReliableMessagingBindingElement`:  
  
    - `wsrm:InactivityTimeout`  
  
    - `wsrm:AcknowledgementInterval`  
  
     Nachfolgend finden Sie ein Beispiel:  
  
    ```xml  
    <wsrm:RMAssertion>  
      <wsrm:InactivityTimeout Milliseconds="600000" />  
      <wsrm:AcknowledgementInterval Milliseconds="200" />  
    </wsrm:RMAssertion>  
    ```  
  
## <a name="flow-control-ws-reliable-messaging-extension"></a>Zuverlässige WS-Messaging-Erweiterung zur Ablaufsteuerung  
 WCF verwendet die WS-ReliableMessaging-Erweiterbarkeit optionales Steuerung des sequenznachrichtenflusses Nachrichtenfluss Sequenz bereitstellen.  
  
 Flusssteuerung aktiviert ist, durch Festlegen der <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.FlowControlEnabled?displayProperty=nameWithType> Eigenschaft `true`. Im folgenden finden eine Liste der Einschränkungen, die für WCF gelten:  
  
- B4001: WCF wird generiert, wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, eine `netrm:BufferRemaining` Element in der elementerweiterbarkeit des der `SequenceAcknowledgement` Header.  
  
- B4002: Wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, WCF erfordert keine `netrm:BufferRemaining` Element vorhanden sein `SequenceAcknowledgement` -Header, wie im folgenden Beispiel gezeigt.  
  
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
  
- B4003: WCF verwendet `netrm:BufferRemaining` um anzugeben, wie viele der neue Nachrichten das zuverlässige Messaging-Ziel Puffern kann.  
  
- B4004: WCF Reliable Messaging-Dienst drosselt die Anzahl der Nachrichten, die übertragen werden, wenn die zuverlässige Messaging-Zielanwendung schnell keine Nachrichten empfangen kann. Das zuverlässige Messaging-Ziel puffert Nachrichten, und der Wert des Elements sinkt auf&amp;#160;0.  
  
- B4005: WCF generiert `netrm:BufferRemaining` ganzzahlige Werte zwischen 0 und 4096 einschließlich und liest Ganzzahlwerte zwischen 0 und `xs:int`des `maxInclusive` Wert (214748364) einschließlich.  
  
## <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster  
 Dieser Abschnitt beschreibt WCFs-Verhalten, wenn WS-Reliable Messaging für verschiedene Nachrichtenaustauschmuster verwendet wird. Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:  
  
- Nicht Adressierbarer Initiator: Initiator befindet sich hinter der Firewall; Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.  
  
- Adressierbarer Initiator: Initiator und Beantworter können HTTP-Anforderungen gesendet werden. Anders gesagt können zwei entgegengesetzte HTTP-Verbindungen hergestellt werden.  
  
### <a name="one-way-non-addressable-initiator"></a>Unidirektionaler, nicht adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen HTTP-Kanal. WCF verwendet die HTTP-Anforderungen zur Übertragung aller Nachrichten vom RMS zum RMD und die HTTP-Antwort zur Übertragung aller Nachrichten vom RMD zum RMS.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` -Nachricht ohne Angebot. Der WCF-Beantworter stellt sicher die `CreateSequence` kein Angebot vor dem Erstellen einer Sequenz aufweist. Der WCF-Beantworter reagiert auf die `CreateSequence` Anforderungen, bei denen eine `CreateSequenceResponse` Nachricht.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Der WCF-Initiator erstellt Bestätigungen als Antwort alle Nachrichten mit Ausnahme der `CreateSequence` -Nachrichten und Fehlernachrichten. Der WCF-Beantworter generiert eine eigenständige Bestätigung in der Antwort auf Sequenzen und `AckRequested` Nachrichten.  
  
#### <a name="terminatesequence-message"></a>TerminateSequence-Nachricht  
 WCF behandelt `TerminateSequence` als einen unidirektionalen Vorgang, was bedeutet der HTTP-Antwort hat, leerem Textbereich und dem HTTP 202-Statuscode.  
  
### <a name="one-way-addressable-initiator"></a>Unidirektionaler, adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein unidirektionales Nachrichtenaustauschmuster, die mit einer einzigen Sequenz über einen eingehenden und einen ausgehenden Http-Kanal. WCF verwendet die HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&amp;#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` -Nachricht ohne Angebot. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` kein Angebot vor dem Erstellen einer Sequenz aufweist. Der WCF-Beantworter überträgt die `CreateSequenceResponse` Nachricht in einer HTTP-Anforderung adressiert wird, mit der `ReplyTo` Endpunktverweis.  
  
### <a name="duplex-addressable-initiator"></a>Adressierbarer Duplex-Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein vollständig asynchrones bidirektionales Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet die HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&amp;#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` -Nachricht mit einem Angebot. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` ein Angebot vor dem Erstellen einer Sequenz aufweist. WCF sendet die `CreateSequenceResponse` behoben die HTTP-Anforderung die `CreateSequence`des `ReplyTo` Endpunktverweis.  
  
#### <a name="sequence-lifetime"></a>Sequenzlebensdauer  
 WCF behandelt die beiden Sequenzen als eine vollduplexsitzung.  
  
 Nach dem Generieren eines Fehlers, der eine Sequenz einen Fehler an, erwartet, dass WCF den Remoteendpunkt für beide Sequenzen auslöst. Nach dem Lesen eines Fehlers, der eine Sequenz einen Fehler, Fehler WCF für beide Sequenzen.  
  
 WCF kann seine ausgehende Sequenz schließen und zum Verarbeiten von Nachrichten in seiner eingehenden Sequenz fortsetzen. Im Gegensatz dazu kann WCF das Schließen der eingehenden Sequenz und weiter Nachrichten in seiner ausgehenden Sequenz senden.  
  
### <a name="request-reply-non-addressable-initiator"></a>Nicht adressierbarer Anforderung-Antwort-Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF stellt einen unidirektionalen und Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal. WCF HTTP-Anforderungen verwendet, um die anforderungssequenznachrichten zu übertragen und die HTTP-Antworten verwendet, um die Antwortsequenznachrichten zu übertragen.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` -Nachricht mit einem Angebot. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` ein Angebot vor dem Erstellen einer Sequenz aufweist. Der WCF-Beantworter reagiert auf die `CreateSequence` Anforderungen, bei denen eine `CreateSequenceResponse` Nachricht.  
  
#### <a name="one-way-message"></a>Unidirektionale Nachricht  
 Um ein unidirektionales Nachrichtenaustauschprotokoll erfolgreich abgeschlossen haben, den WCF-Initiator eine anforderungssequenznachricht in der HTTP-Anforderung sendet und empfängt eine eigenständige `SequenceAcknowledgement` -Nachricht in der HTTP-Antwort. Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.  
  
 Der WCF-Beantworter kann mit einer Bestätigung, einem Fehler oder eine Antwort mit leerem Textbereich und dem HTTP 202-Statuscode auf die Anforderung antworten.  
  
#### <a name="two-way-messages"></a>Bidirektionale Nachrichten  
 Um eine zwei-Wege-Nachrichtenaustauschprotokoll erfolgreich abgeschlossen haben, den WCF-Initiator eine anforderungssequenznachricht in der HTTP-Anforderung sendet und empfängt eine antwortsequenznachricht in der HTTP-Antwort. Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.  
  
 Der WCF-Beantworter kann mit einer Anwendungsantwort, einem Fehler oder eine Antwort mit leerem Textbereich und dem HTTP 202-Statuscode auf die Anforderung antworten.  
  
 Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.  
  
#### <a name="retrying-replies"></a>Wiederholen von Antworten  
 WCF basiert auf HTTP-Anforderung-Antwort-Korrelation für bidirektionale Nachrichtenaustauschprotokoll. Aus diesem Grund wird der WCF-Initiator nicht beendet eine anforderungssequenznachricht wiederholen, wenn die anforderungssequenznachricht bestätigt wird, sondern wenn die HTTP-Antwort eine Bestätigung, die Meldung für den Benutzer oder den Fehler enthält. Der WCF-Beantworter wiederholt die Antworten auf den HTTP-Anforderungsabschnitt der Anforderung mit der die Antwort korreliert ist.  
  
#### <a name="lastmessage-exchange"></a>LastMessage-Austausch  
 Der WCF-Initiator generiert und überträgt eine letzte Nachricht ohne Text auf den HTTP-Anforderungsabschnitt. WCF erfordert eine Antwort ignoriert jedoch diese Antwortnachricht. Der WCF-Beantworter reagiert auf die anforderungssequenz leere letzte Nachricht mit der Antwortsequenz leere letzte Nachricht.  
  
 Wenn der WCF-Beantworter eine letzte Nachricht empfängt, in dem der Aktions-URI nicht ist `http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage`, WCF-Antworten mit einer letzten Nachricht. Im Fall eines bidirektionalen Nachrichtenaustauschprotokolls enthält die letzte Nachricht die Anwendungsnachricht, im Falle eines unidirektionalen Nachrichtenaustauschprotokolls ist die letzte Nachricht leer.  
  
 Der WCF-Beantworter erfordert keine Bestätigung für die Antwortsequenz leere letzte Nachricht.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch  
 Wenn alle Anforderungen eine gültige Antwort erhalten haben, wird der WCF-Initiator generiert und überträgt der anforderungssequenz `TerminateSequence` Nachricht auf den HTTP-Anforderungsabschnitt. WCF erfordert eine Antwort ignoriert jedoch diese Antwortnachricht. Der WCF-Beantworter reagiert auf der anforderungssequenz `TerminateSequence` Nachricht mit der Antwortsequenz `TerminateSequence` Nachricht.  
  
 In einer normalen Abschlusssequenz enthalten beide `TerminateSequence`-Nachrichten einen vollständigen Bereich von `SequenceAcknowledgement`.  
  
### <a name="requestreply-addressable-initiator"></a>Adressierbarer Anforderung/Antwort-Initiator  
  
#### <a name="binding"></a>Bindung  
 WCF bietet ein Anforderung-Antwort-Nachrichtenaustauschmuster, die Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. WCF verwendet die HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&amp;#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der WCF--Initiator generiert eine `CreateSequence` -Nachricht mit einem Angebot. Der WCF-Beantworter stellt sicher, dass die `CreateSequence` ein Angebot vor dem Erstellen einer Sequenz aufweist. WCF sendet die `CreateSequenceResponse` behoben die HTTP-Anforderung die `CreateSequence`des `ReplyTo` Endpunktverweis.  
  
#### <a name="requestreply-correlation"></a>Anforderung/Antwort-Korrelation  
 Der WCF-Initiator wird sichergestellt, alle anwendungsanforderungsnachrichten eine `MessageId` und `ReplyTo` Endpunktverweis. Der WCF--Initiator wendet den `CreateSequence` Nachricht `ReplyTo` Endpunktverweis für jede anwendungsanforderungsnachricht an. Der WCF-Beantworter erfordert, dass eingehende Anforderungsnachrichten beachten einer `MessageId` und `ReplyTo`. Der WCF-Beantworter stellt sicher, dass der Endpunktverweis-URIS der Endpunktverweise der `CreateSequence` und aller anwendungsanforderungsnachrichten identisch sind.
