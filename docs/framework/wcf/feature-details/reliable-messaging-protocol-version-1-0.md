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
ms.workload: dotnet
ms.openlocfilehash: a32c16067446459817e9943c2d729a67373a0333
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="reliable-messaging-protocol-version-10"></a>Zuverlässiges Messaging-Protokoll, Version 1.0
In diesem Thema werden [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Implementierungsdetails für das WS-Reliable Messaging-Protokoll in der Version 1.0 vom Februar 2005 beschrieben, die für die Interoperation mithilfe des HTTP-Transports erforderlich sind. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] orientiert sich an der WS-Reliable Messaging-Spezifikation mit den in diesem Thema erläuterten Einschränkungen und Klarstellungen. Beachten Sie, dass das zuverlässige WS-Messaging-Protokoll in der Version&#160;1.0 ab [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] implementiert ist.  
  
 Das WS-ReliableMessaging-Protokoll vom Februar&#160;2005 ist in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durch das <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> implementiert.  
  
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
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert `CreateSequence`- und `CreateSequenceResponse`-Nachrichten, um eine zuverlässige Nachrichtensequenz einzurichten. Es gelten die folgenden Einschränkungen:  
  
-   B1101: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert nicht das optionale Expires-Element in der `CreateSequence`-Nachricht oder, in den Fällen, in denen die `CreateSequence`-Nachricht ein `Offer`-Element enthält, das optionale `Expires`-Element im `Offer`-Element.  
  
-   B1102: Beim Zugriff auf die `CreateSequence` Nachricht, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `Responder` sendet und empfängt sowohl `Expires` Elemente, wenn vorhanden, aber ihre Werte nicht verwendet.  
  
 Zuverlässiges WS-Messaging führt den `Offer`-Mechanismus ein, um zwei umgekehrt korrelierende Sequenzen einzurichten, die eine Sitzung bilden.  
  
-   R1103: Wenn `CreateSequence` ein `Offer`-Element enthält, muss der zuverlässige Messaging-Beantworter entweder die Sequenz akzeptieren und mit `CreateSequenceResponse` antworten (enthält ein `wsrm:Accept`-Element), wodurch die zwei umgekehrt korrelierenden Sequenzen gebildet werden, oder er muss die `CreateSequence`-Anforderung zurückweisen.  
  
-   R1104: `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten müssen an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.  
  
-   R1105: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` müssen Adresswerte aufweisen, die sich oktettweise entsprechen.  
  
     Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter überprüft, ob die URI-Teile von `AcksTo`- und `ReplyTo`-EPRs identisch sind, bevor die Sequenz erstellt wird.  
  
-   R1106: `AcksTo`- und `ReplyTo`-Endpunktverweise in der `CreateSequence` sollten den gleichen Satz von Verweisparametern aufweisen.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] geht davon aus, dass die Verweisparameter von `AcksTo` und `ReplyTo` in `CreateSequence` identisch sind, erzwingt dies jedoch nicht, und verwendet die Verweisparameter von dem `ReplyTo`-Endpunktverweis für Bestätigungen und Nachrichten umgekehrter Sequenz.  
  
-   R1107: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen `SequenceAcknowledgement` und die in umgekehrter Sequenz fließenden Anwendungsnachrichten an den `ReplyTo`-Endpunktverweis der `CreateSequence` gesendet werden.  
  
-   R1108: Wenn mithilfe des Offer-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, muss die `[address]`-Eigenschaft des `wsrm:AcksTo`-Endpunktverweises, ein dem `wsrm:Accept`-Element von `CreateSequenceResponse` untergeordnetes Element, mit dem Ziel-URI von `CreateSequence` byteweise übereinstimmen.  
  
-   R1109: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen eingerichtet sind, müssen die vom Initiator gesendeten Nachrichten und die vom Beantworter gesendeten Bestätigungen der Nachrichten an den gleichen Endpunktverweis gesendet werden.  
  
     [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet zuverlässiges WS-Messaging, um zuverlässige Sitzungen zwischen dem Initiator und dem Beantworter einzurichten. Die Implementierung von zuverlässigem WS-Messaging in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet zuverlässige Sitzungen für unidirektionale, Anforderung-Antwort- und Vollduplex-Nachrichtenmuster. Die WS-Reliable Messaging `Offer` Mechanismus auf `CreateSequence` / `CreateSequenceResponse` können Sie die zwei umgekehrt korrelierte Sequenzen zu erstellen, und bietet ein, die für alle Endpunkte Nachricht geeignet ist. Da [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die Sicherheit solcher Sitzungen sowie den End-to-End-Schutz der Sitzungsintegrität garantiert, kann sichergestellt werden, dass alle an den gleichen Teilnehmer gerichteten Nachrichten am gleichen Ziel ankommen. Dies lässt auch Piggyback-Übertragung von Sequenzbestätigungen auf Anwendungsnachrichten zu. Deshalb gelten die Einschränkungen R1104, R1105 und R1108 für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
  
-   B1201:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert und greift auf die Sequenznummern, die nicht höher als `xs:long`des inklusive Maximalwert 9223372036854775807.  
  
-   B1202:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert immer eine ohne Text letzte Meldung mit der Aktions-URI des http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage.  
  
-   B1203: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] empfängt und sendet eine Nachricht mit einem Sequenzheader, der das `LastMessage`-Element enthält, sofern der Aktions-URI nicht "http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage" lautet.  
  
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
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet den `AckRequested`-Header als Keep-alive-Mechanismus. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert nicht das optionale `MessageNumber`-Element. Wird eine Nachricht mit einem `AckRequested`-Header empfangen, der das `MessageNumber`-Element enthält, ignoriert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] den Wert des `MessageNumber`-Elements, wie im folgenden Beispiel gezeigt:  
  
```xml  
<wsrm:AckRequested>  
  <wsrm:Identifier>  
    urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
  </wsrm:Identifier>  
</wsrm:AckRequested>  
```  
  
### <a name="sequenceacknowledgement-header"></a>SequenceAcknowledgement-Header  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet den Piggyback-Mechanismus für die im zuverlässigen WS-Messaging bereitgestellten Sequenzbestätigungen.  
  
-   R1401: Wenn mithilfe des `Offer`-Mechanismus zwei umgekehrte Sequenzen erstellt werden, kann der `SequenceAcknowledgement`-Header in jede an den vorgesehenen Empfänger gesendete Anwendungsnachricht aufgenommen werden.  
  
-   B1402: Wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine Bestätigung generieren muss (um beispielsweise auf eine `AckRequested`-Nachricht zu reagieren), bevor eine Sequenznachricht empfangen wurde, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen `SequenceAcknowledgement`-Header, der den Bereich "0-0" enthält, wie im folgenden Beispiel gezeigt:  
  
    ```xml  
    <wsrm:SequenceAcknowledgement>  
      <wsrm:Identifier>  
        urn:uuid:addabbbf-60cb-44d3-8c5b-9e0841629a36  
      </wsrm:Identifier>  
      <wsrm:AcknowledgementRange Upper="0" Lower="0"/>  
    </wsrm:SequenceAcknowledgement>  
    ```  
  
-   B1403: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert keine `SequenceAcknowledgement`-Header, die ein `Nack`-Element enthalten, unterstützt jedoch `Nack`-Elemente.  
  
### <a name="ws-reliablemessaging-faults"></a>WS-ReliableMessaging-Fehler  
 Die folgende Liste enthält die Einschränkungen, die für die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierung der Fehler des zuverlässigen WS-Messaging gelten:  
  
-   B1501: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert keine `MessageNumberRollover`-Fehler.  
  
-   B1502:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Endpunkt generiert möglicherweise `CreateSequenceRefused` Fehler auf, wie in der Spezifikation beschrieben.  
  
-   B1503:when den Dienstendpunkt seine Verbindungsgrenze erreicht und keine weiteren Verbindungen verarbeiten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert einen zusätzlichen `CreateSequenceRefused` -Fehlersubcode `netrm:ConnectionLimitReached`, wie im folgenden Beispiel gezeigt.  
  
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
 Da zuverlässiges WS-Messaging WS-Adressierung verwendet, kann die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierung von zuverlässigem WS-Messaging WS-Adressierungsfehler generieren. In diesem Abschnitt werden die WS-Adressierungsfehler erläutert, die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] explizit auf der Ebene des zuverlässigen WS-Messaging generiert.  
  
-   B1601:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert den Fehler, die Nachricht adressiert Header erforderlich, wenn eine der folgenden Aussagen zutrifft:  
  
    -   Eine Nachricht hat keinen `Sequence`-Header und keinen `Action`-Header.  
  
    -   Eine `CreateSequence`-Nachricht hat keinen `MessageId`-Header.  
  
    -   Eine `CreateSequence`-Nachricht hat keinen `ReplyTo`-Header.  
  
-   B1602:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert den Fehler, die Aktion nicht unterstützt, als Antwort auf eine Nachricht, die fehlen einer `Sequence` Header und verfügt über eine `Action` Header, der nicht erkannten in der WS-ReliableMessaging-Spezifikation ist.  
  
-   B1603:[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert den Fehler, der Endpunkt nicht verfügbar, um anzugeben, dass der Endpunkt die Sequenz basierend auf der Prüfung nicht verarbeitet werden die `CreateSequence` Nachricht Adressheader.  
  
## <a name="protocol-composition"></a>Protokollkomposition  
  
### <a name="composition-with-ws-addressing"></a>Komposition mit WS-Adressierung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt zwei Versionen der WS-Adressierung: WS-Adressierung&#160;2004/08 [WS-ADDR] und die Empfehlungen für W3C die WS-Addressierung&#160;1.0 [WS-WS-ADDR-CORE] und [WS-ADDR-SOAP].  
  
 Zwar erwähnt die WS-ReliableMessaging-Spezifikation nur die WS-Adressierung&#160;2004/08, schränkt jedoch die verwendete Version der WS-Adressierung nicht ein. Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:  
  
-   R2101: sowohl WS-Adressierung 2004/08 und WS-Adressierung 1.0 mit WS-Reliable Messaging verwendet werden kann.  
  
-   R2102:A einzelne Version der WS-Adressierung muss verwendet werden, in der gesamten einer angegebenen WS-Reliable Messaging-Sequenz oder ein Paar umgekehrter Sequenzen korreliert mit der `wsrm:Offer` Mechanismus.  
  
### <a name="composition-with-soap"></a>Komposition mit SOAP  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt die Verwendung sowohl von SOAP&#160;1.1 als auch von SOAP&#160;1.2 mit zuverlässigem WS-Messaging.  
  
### <a name="composition-with-ws-security-and-ws-secureconversation"></a>Komposition mit WS-Sicherheit und WS-SecureConversation  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet Schutz für die zuverlässigen WS-Messaging-Sequenzen durch die Verwendung einer sicheren Transportmethode (HTTPS), die Erstellung mit WS-Sicherheit und die Erstellung mit WS-Secure Conversation. Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:  
  
-   R2301: Schützen Sie die Integrität einer WS-Reliable Messaging-Sequenz neben der Integrität und Vertraulichkeit einzelner Nachrichten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfordert, dass WS-Secure Conversation verwendet werden muss.  
  
-   R2302:AWS-Secure Conversation-Sitzung muss vor dem Einrichten von WS-Reliable Messaging Sequence(s) eingerichtet werden.  
  
-   R2303: Wenn die Lebensdauer einer zuverlässigen WS-Messaging-Sequenz die Lebensdauer der WS-Secure Conversation-Sitzung überschreitet, muss das mithilfe von WS-Secure Conversation eingerichtete `SecurityContextToken` unter Verwendung der entsprechenden WS-Secure Conversation Renewal-Bindung erneuert werden.  
  
-   B2304:WS-Reliable Messaging-Sequenz oder ein paar umgekehrt korrelierte Sequenzen immer an eine einzelne WS-SecureConversation-Sitzung gebunden sind.  
  
     Die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Quelle generiert das `wsse:SecurityTokenReference`-Element im Abschnitt Elementerweiterbarkeit der `CreateSequence`-Nachricht.  
  
-   R2305:when mit WS-Secure Conversation verfasst eine `CreateSequence` Nachricht darf die `wsse:SecurityTokenReference` Element.  
  
## <a name="ws-reliable-messaging-ws-policy-assertion"></a>Zuverlässige WS-Messaging WS-Richtlinienassertion  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die WS-Richtlinienassertion `wsrm:RMAssertion` des zuverlässigen WS-Messaging, um die Fähigkeiten von Endpunkten zu beschreiben. Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:  
  
-   B3001: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] fügt die `wsrm:RMAssertion`-WS-Richtlinienassertion an `wsdl:binding`-Elemente an. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt sowohl das Anfügen an `wsdl:binding`-Elemente als auch an `wsdl:port`-Elemente.  
  
-   B3002: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt die folgenden optionalen Eigenschaften des WS-Reliable Messaging-Assertion und ermöglicht die Steuerung sie auf die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] `ReliableMessagingBindingElement`:  
  
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
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die Erweiterbarkeit des zuverlässigen WS-Messaging, um optional eine bessere Steuerung des Sequenznachrichtenflusses zu ermöglichen.  
  
 Flusssteuerung aktiviert ist, durch Festlegen der `ReliableSessionBindingElement`des `FlowControlEnabled``bool` Eigenschaft `true`. Die folgende Liste enthält die Einschränkungen, die für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gelten:  
  
-   B4001: Wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, generiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ein `netrm:BufferRemaining`-Element in der Elementerweiterbarkeit des `SequenceAcknowledgement`-Headers.  
  
-   B4002: Wenn die zuverlässige Messaging-Ablaufsteuerung aktiviert ist, erfordert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kein `netrm:BufferRemaining`-Element im `SequenceAcknowledgement`-Header, wie im folgenden Beispiel zu sehen:  
  
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
  
-   B4003: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet `netrm:BufferRemaining`, um anzugeben, wie viele neue Nachrichten das zuverlässige Messaging-Ziel puffern kann.  
  
-   B4004: die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zuverlässige Messaging-Dienst drosselt die Anzahl der Nachrichten, die übertragen werden, wenn die Anwendung für zuverlässiges Messaging-Ziel schnell Nachrichten empfangen kann. Das zuverlässige Messaging-Ziel puffert Nachrichten, und der Wert des Elements sinkt auf&#160;0.  
  
-   B4005: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] generiert `netrm:BufferRemaining`-Ganzzahlwerte zwischen&#160;0 und 4096 einschließlich und liest Ganzzahlwerte zwischen&#160;0 und dem `xs:int`-Wert von `maxInclusive` (214748364) einschließlich.  
  
## <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster  
 In diesem Abschnitt wird das Verhalten von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bei Verwendung von zuverlässigem WS-Messaging für verschiedene Nachrichtenaustauschmuster beschrieben. Für jedes Nachrichtenaustauschmuster werden die folgenden zwei Bereitstellungsszenarios erläutert:  
  
-   Nicht adressierbarer Initiator: Der Initiator befindet sich hinter einer Firewall, der Beantworter kann Nachrichten an den Initiator nur über HTTP-Antworten zustellen.  
  
-   Adressierbarer Initiator: Sowohl an den Initiator als auch den Beantworter können HTTP-Anforderungen gesendet werden, d.&#160;h., es können zwei entgegengesetzte HTTP-Verbindungen eingerichtet werden.  
  
### <a name="one-way-non-addressable-initiator"></a>Unidirektionaler, nicht adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt ein unidirektionales Nachrichtenaustauschmuster unter Verwendung einer Sequenz über einen HTTP-Kanal bereit. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die HTTP-Anforderungen, um alle Nachrichten vom RMS zum RMD zu übertragen, und die HTTP-Antworten, um alle Nachrichten vom RMD zum RMS zu übertragen.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht ohne Angebot. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht kein Angebot aufweist. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter antwortet mit einer `CreateSequence`-Nachricht auf die `CreateSequenceResponse`-Anforderung.  
  
#### <a name="sequenceacknowledgement"></a>SequenceAcknowledgement  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator erstellt Bestätigungen als Antwort auf alle Nachrichten mit Ausnahme von `CreateSequence`-Nachrichten und Fehlernachrichten. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter generiert eine eigenständige Bestätigung in der Antwort auf Sequenzen und auf `AckRequested`-Nachrichten.  
  
#### <a name="terminatesequence-message"></a>TerminateSequence-Nachricht  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behandelt `TerminateSequence` als unidirektionalen Vorgang, was bedeutet, dass die HTTP-Antwort einen leeren Textbereich und den HTTP-Statuscode&amp;#160;202 hat.  
  
### <a name="one-way-addressable-initiator"></a>Unidirektionaler, adressierbarer Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet ein unidirektionales Nachrichtenaustauschmuster unter Verwendung eines eingehenden und eines ausgehenden HTTP-Kanals. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht ohne Angebot. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht kein Angebot aufweist. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter sendet die `CreateSequenceResponse`-Nachricht über eine HTTP-Anforderung, die mit dem `ReplyTo`-Endpunktverweis adressiert wird.  
  
### <a name="duplex-addressable-initiator"></a>Adressierbarer Duplex-Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet ein vollständig asynchrones bidirektionales Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht mit einem Angebot. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht ein Angebot aufweist. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sendet die `CreateSequenceResponse` über eine HTTP-Anforderung, die an den `CreateSequence`-Endpunktverweis von `ReplyTo` adressiert wird.  
  
#### <a name="sequence-lifetime"></a>Sequenzlebensdauer  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] behandelt die beiden Sequenzen als eine Vollduplexsitzung.  
  
 Nach dem Generieren eines Fehlers für eine Sequenz erwartet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], dass der Remoteendpunkt einen Fehler für beide Sequenzen auslöst. Nach dem Lesen eines Fehlers, der zum Fehlschlagen einer Sequenz führt, löst [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen Fehler für beide Sequenzen aus.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] kann seine ausgehende Sequenz schließen und damit fortfahren, Nachrichten in seiner eingehenden Sequenz zu verarbeiten. Umgekehrt kann [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] auch das Schließen der eingehenden Sequenz durchführen und weiter Nachrichten in seiner ausgehenden Sequenz senden.  
  
### <a name="request-reply-non-addressable-initiator"></a>Nicht adressierbarer Anforderung-Antwort-Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet ein unidirektionales Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen HTTP-Kanal. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen, um Anforderungssequenznachrichten zu übertragen, und HTTP-Antworten, um Antwortsequenznachrichten zu übertragen.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht mit einem Angebot. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht ein Angebot aufweist. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter antwortet mit einer `CreateSequence`-Nachricht auf die `CreateSequenceResponse`-Anforderung.  
  
#### <a name="one-way-message"></a>Unidirektionale Nachricht  
 Um ein unidirektionales Nachrichtenaustauschprotokoll erfolgreich durchzuführen, überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine eigenständige `SequenceAcknowledgement`-Nachricht in der HTTP-Antwort. Die `SequenceAcknowledgement`-Nachricht muss die Nachrichtenübertragung bestätigen.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter kann mit einer Bestätigung, einem Fehler oder einer Antwort mit leerem Textbereich und dem HTTP-Statuscode&#160;202 auf die Anforderung reagieren.  
  
#### <a name="two-way-messages"></a>Bidirektionale Nachrichten  
 Um ein bidirektionales Nachrichtenaustauschprotokoll erfolgreich durchzuführen, überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht in der HTTP-Anforderung und empfängt eine Antwortsequenznachricht in der HTTP-Antwort. Die Antwort muss eine `SequenceAcknowledgement` enthalten, die die Übertragung der Anforderungssequenznachricht bestätigt.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter kann mit einer Anwendungsantwort, einem Fehler oder einer Antwort mit leerem Textbereich und dem HTTP-Statuscode "202" auf die Anforderung reagieren.  
  
 Aufgrund des Vorhandenseins unidirektionaler Nachrichten und des zeitlichen Ablaufs von Anwendungsantworten verfügen die Sequenznummern der Anforderungssequenznachricht und der Antwortsequenznachricht über keine Korrelation.  
  
#### <a name="retrying-replies"></a>Wiederholen von Antworten  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nutzt die HTTP-Anforderung-Antwort-Korrelation für das bidirektionale Nachrichtenaustauschprotokoll. Daher wiederholt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator eine Anforderungssequenznachricht auch dann weiter, wenn die Anforderungssequenznachricht bestätigt wird. Er hört erst dann auf, wenn die HTTP-Antwort eine Bestätigung, eine Benutzernachricht oder einen Fehler enthält. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter wiederholt die Antworten auf den HTTP-Anforderungsabschnitt der Anforderung, mit der die Antwort korreliert ist.  
  
#### <a name="lastmessage-exchange"></a>LastMessage-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert und überträgt eine letzte Nachricht ohne Text auf den HTTP-Anforderungsabschnitt. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfordert eine Antwort, ignoriert jedoch diese Antwortnachricht. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter reagiert auf die letzte Anforderungssequenznachricht ohne Text mit einer letzten Antwortsequenznachricht ohne Text.  
  
 Wenn der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter eine letzte Nachricht empfängt, in der der Aktions-URI nicht http://schemas.xmlsoap.org/ws/2005/02/rm/LastMessage lautet, antwortet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mit einer letzten Nachricht. Im Fall eines bidirektionalen Nachrichtenaustauschprotokolls enthält die letzte Nachricht die Anwendungsnachricht, im Falle eines unidirektionalen Nachrichtenaustauschprotokolls ist die letzte Nachricht leer.  
  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter benötigt keine Bestätigung für die letzte Antwortsequenznachricht ohne Text.  
  
#### <a name="terminatesequence-exchange"></a>TerminateSequence-Austausch  
 Wenn alle Anforderungen eine gültige Antwort erhalten haben, generiert und überträgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator die `TerminateSequence`-Nachricht der Anforderungssequenz auf den HTTP-Anforderungsabschnitt. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erfordert eine Antwort, ignoriert jedoch diese Antwortnachricht. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter reagiert auf die `TerminateSequence`-Nachricht der Anforderungssequenz mit einer `TerminateSequence`-Nachricht der Antwortsequenz.  
  
 In einer normalen Abschlusssequenz enthalten beide `TerminateSequence`-Nachrichten einen vollständigen Bereich von `SequenceAcknowledgement`.  
  
### <a name="requestreply-addressable-initiator"></a>Adressierbarer Anforderung/Antwort-Initiator  
  
#### <a name="binding"></a>Bindung  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet ein Anforderung-Antwort-Nachrichtenaustauschmuster unter Verwendung zweier Sequenzen über einen eingehenden und einen ausgehenden HTTP-Kanal. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet HTTP-Anforderungen zur Übertragung aller Nachrichten. Alle HTTP-Antworten haben einen leeren Textbereich und den HTTP-Statuscode&#160;202.  
  
#### <a name="createsequence-exchange"></a>CreateSequence-Austausch  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator generiert eine `CreateSequence`-Nachricht mit einem Angebot. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt vor dem Erstellen einer Sequenz sicher, dass die `CreateSequence`-Nachricht ein Angebot aufweist. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sendet die `CreateSequenceResponse` über eine HTTP-Anforderung, die an den `CreateSequence`-Endpunktverweis von `ReplyTo` adressiert wird.  
  
#### <a name="requestreply-correlation"></a>Anforderung/Antwort-Korrelation  
 Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator stellt sicher, dass alle Anwendungsanforderungsnachrichten eine `MessageId` und einen `ReplyTo`-Endpunktverweis enthalten. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Initiator wendet den `CreateSequence`-Endpunktverweis der `ReplyTo`-Nachricht für jede Anwendungsanforderungsnachricht an. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter erfordert, dass alle Anwendungsanforderungsnachrichten eine `MessageId` und einen `ReplyTo`-Endpunktverweis enthalten. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Beantworter stellt sicher, dass die URIs der Endpunktverweise der `CreateSequence`-Nachrichten und aller Anwendungsanforderungsnachrichten identisch sind.
