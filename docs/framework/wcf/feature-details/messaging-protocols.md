---
title: Messagingprotokolle
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: 3e56636e8364eec333f9585a0f62f6510561d1cc
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563277"
---
# <a name="messaging-protocols"></a>Messagingprotokolle
Der Windows Communication Foundation (WCF)-Kanalstapel wendet Codierungs- und Transportkanäle an interne nachrichtendarstellung in ihr kabelformat zu transformieren, und senden es mithilfe eines bestimmten Transports. Der am häufigsten verwendete Transport, der für die Interoperabilität bei Webdiensten verwendet wird, ist HTTP, und die am häufigsten von Webdiensten verwendeten Codierungen sind das XML-basierte SOAP 1.1, SOAP 1.2 und der Message Transmission Optimization Mechanism (MTOM).  
  
 Dieses Thema enthält Details zur WCF-Implementierung für die folgenden Protokolle, die vom Anwender verwendete <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.  
  
|Spezifikation/Dokument|Link|  
|-----------------------------|----------|  
|HTTP 1.1|http://www.ietf.org/rfc/rfc2616.txt|  
|SOAP 1.1 HTTP-Bindung|http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Abschnitt 7|  
|SOAP 1,2 HTTP-Bindung|http://www.w3.org/TR/soap12-part2/, Abschnitt 7|  
  
 Dieses Thema enthält Details zur WCF-Implementierung für die folgenden Protokolle <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> einsetzen.  
  
|Spezifikation/Dokument|Link|  
|-----------------------------|----------|  
|XML|http://www.w3.org/TR/REC-xml|  
|SOAP 1,1|http://www.w3.org/TR/2000/NOTE-SOAP-20000508/|  
|SOAP 1.2 Core|http://www.w3.org/TR/soap12-part1/|  
|WS-Adressierung 2004/08|http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/|  
|W3C Web Services Addressing 1.0 - Core|http://www.w3.org/TR/2006/REC-ws-addr-core-20060509|  
|W3C Web Services Addressing 1.0 - SOAP-Bindung|http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509|  
|W3C Web Services Addressing 1.0 - WSDL-Bindung|http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/|  
W3C Web Services Addressing 1.0 - Metadaten|http://www.w3.org/TR/ws-addr-metadata/|  
|WSDL SOAP1.1-Bindung|http://www.w3.org/TR/wsdl/|  
|WSDL SOAP1.2-Bindung|http://www.w3.org/Submission/wsdl11soap12/|  
  
 Dieses Thema enthält Details zur WCF-Implementierung für die folgenden Protokolle <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> verwendet.  
  
|Spezifikation/Dokument|Link|  
|-----------------------------|----------|  
|XOP|http://www.w3.org/TR/xop10/|  
|MTOM + SOAP 1.2-Bindung|http://www.w3.org/TR/soap12-mtom/|  
|MTOM SOAP 1.1-Bindung|http://www.w3.org/Submission/soap11mtom10/|  
|MTOM WS-Richtlinienassertion|http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/|  
  
 Die folgenden XML-Namespaces und zugeordneten Präfixe werden überall in diesem Thema verwendet.  
  
|Präfix|Namespace Uniform Resource Identifier (URI)|  
|------------|---------------------------------------------------|  
|s11|http://schemas.xmlsoap.org/soap/envelope|  
|s12|http://www.w3.org/2003/05/soap-envelope|  
|wsa|http://www.w3.org/2004/08/addressing|  
|wsam|http://www.w3.org/2007/05/addressing/metadata|  
|wsap|http://schemas.xmlsoap.org/ws/2004/09/policy/addressing|  
|wsa10|http://www.w3.org/2005/08/addressing|  
|wsaw10|http://www.w3.org/2006/05/addressing/wsdl|  
|xop|http://www.w3.org/2004/08/xop/include|  
|xmime|http://www.w3.org/2004/06/xmlmime<br /><br /> http://www.w3.org/2005/05/xmlmime|  
dp|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="soap-11-and-soap-12"></a>SOAP 1.1 und SOAP 1.2  
  
### <a name="envelope-and-processing-model"></a>Umschlag und Verarbeitungsmodell  
 WCF implementiert SOAP 1.1-umschlagsverarbeitung, die folgenden Basic Profile 1.1 (BP11) und Basic Profile 1.0 (SSBP10). SOAP 1.2-Umschlagsverarbeitung wird unter Befolgung von SOAP12-Part1 implementiert.  
  
 Dieser Abschnitt erklärt bestimmte, die von WCF im Hinblick auf BP11 und SOAP12-Part1.  
  
#### <a name="mandatory-header-processing"></a>Erforderliche Headerverarbeitung  
 WCF folgt den Regeln für die Verarbeitung von Headern markiert `mustUnderstand` in den SOAP 1.1- und SOAP 1.2-Spezifikationen, mit den folgenden Variationen beschrieben.  
  
 Eine Nachricht, die WCF-Kanalstapel eingibt, wird von einzelnen Kanälen, die durch zugeordnete Bindungselemente konfiguriert sind, z. B. Textnachrichtencodierung, Sicherheit, zuverlässiges Messaging und Transaktionen verarbeitet. Jeder Kanal erkennt Header des zugeordneten Namespace, und kennzeichnet sie als verstanden. Sobald eine Nachricht in den Verteiler eingeht, liest der Vorgangsformatierer Header, die vom entsprechenden Nachrichten-/Vorgangsvertrag erwartet werden, und kennzeichnet sie als verstanden. Der Verteiler überprüft, ob einige der verbleibenden Header nicht verstanden, aber als `mustUnderstand` gekennzeichnet sind, und löst eine Ausnahme aus. Nachrichten, die an den Empfänger gerichtete `mustUnderstand`-Header enthalten, werden nicht vom Empfängeranwendungscode verarbeitet.  
  
 Eine derartige schichtweise Verarbeitung lässt eine Trennung zwischen den Infrastrukturschichten und Anwendungsschichten auf dem SOAP-Knoten zu:  
  
-   B1111: Header, die nicht verstanden werden werden erkannt, nach der Verarbeitung der Nachricht durch die WCF-infrastrukturkanalstapel, aber bevor sie von der Anwendung verarbeitet wird  
  
     Der `mustUnderstand` Headerwert variiert zwischen SOAP 1.1 und SOAP 1.2. Basic Profile 1.1 erfordert, dass der `mustUnderstand`-Wert für SOAP 1.1-Nachrichten "0" (null) oder "1" sein muss. SOAP 1.2 lässt 0 (null), 1 `false` und `true` als Werte zu, empfiehlt aber die Ausgabe einer standardisierten Darstellung der `xs:boolean`-Werte (`false`, `true`).  
  
-   B1112: WCF gibt `mustUnderstand` Werte 0 und 1 für SOAP 1.1 und SOAP 1.2-Versionen des SOAP-Umschlags. WCF akzeptiert den gesamten Wertebereich `xs:boolean` für die `mustUnderstand` Header (0, 1, `false`, `true`)  
  
#### <a name="soap-faults"></a>SOAP-Fehler  
 Folgendes ist eine Liste der WCF-spezifische SOAP-Fehler-Implementierungen.  
  
-   B2121: WCF gibt die folgenden SOAP 1.1-Fehlercodes: `s11:mustUnderstand`, `s11:Client`, und `s11:Server`.  
  
-   B2122: WCF gibt die folgenden SOAP 1.2-Fehlercodes: `s12:MustUnderstand`, `s12:Sender`, und `s12:Receiver`.  
  
### <a name="http-binding"></a>HTTP-Bindung  
  
#### <a name="soap-11-http-binding"></a>SOAP 1.1 HTTP-Bindung  
 WCF implementiert die SOAP1. 1 HTTP-Bindung gemäß der Basic Profile 1.1-Spezifikation, Abschnitt 3.4 mit den folgenden Erklärungen:  
  
-   B2211: WCF-Dienst implementiert keine Umleitung von HTTP POST-Anforderungen.  
  
-   B2212: WCF-Clients unterstützen HTTP-Cookies in Übereinstimmung mit 3.4.8.  
  
#### <a name="soap-12-http-binding"></a>SOAP 1,2 HTTP-Bindung  
 WCF implementiert SOAP 1.2 HTTP-Bindung, wie in SOAP 1.2-Teil 2 (SOAP12Part2)-Spezifikation mit den folgenden Erklärungen beschrieben.  
  
 SOAP 1.2 hat einen optionalen Aktionsparameter für den `application/soap+xml`-Medientyp eingeführt. Dieser Parameter ist nützlich bei der Optimierung des Sendens von Nachrichten, ohne dass der Text der SOAP-Nachricht analysiert werden muss, wenn die WS-Adressierung nicht verwendet wird.  
  
-   R2221: Der `application/soap+xml`-Aktionsparameter muss, wenn er in einer SOAP 1.2-Anforderung vorliegt, dem Attribut `soapAction` auf dem Element `wsoap12:operation` in der dazugehörigen WSDL-Bindung entsprechen.  
  
-   R2222: Der `application/soap+xml`-Anwendungsparameter muss, wenn er in einer SOAP 1.2-Nachricht vorliegt, `wsa:Action` entsprechen, wenn die WS-Adressierung 2004/08 oder die WS-Adressierung 1.0 verwendet wird.  
  
 Wenn die WS-Adressierung deaktiviert ist und eine eingehende Anforderung keinen Aktionsparameter enthält, gilt die Nachrichten-`Action` als nicht angegeben.  
  
## <a name="ws-addressing"></a>WS-Adressierung  
 WCF implementiert 3 Versionen der WS-Adressierung:  
  
-   WS-Adressierung 2004/08  
  
-   W3C Web Services Addressing 1.0 Core (ADDR10-KERN) und SOAP-Bindung (ADDR10-SOAP)  
  
-   WS-Addressing 1.0 - Metadata  
  
### <a name="endpoint-references"></a>Endpunktverweise  
 Alle Versionen, die WCF implementiert WS-Adressierung verwenden zur Beschreibung von Endpunkten Endpunktverweise.  
  
#### <a name="endpoint-references-and-ws-addressing-versions"></a>Endpunktverweise und WS-Adressierungsversionen  
 WCF implementiert eine Reihe von infrastrukturprotokollen, die WS-Adressierung und insbesondere die `EndpointReference` Element und `W3C.WsAddressing.EndpointReferenceType` -Klasse (z. B. WS-ReliableMessaging, WS-SecureConversation und WS-Trust). WCF unterstützt die Verwendung beider Versionen der WS-Adressierung mit anderen infrastrukturprotokollen. WCF-Endpunkte unterstützen eine Version der WS-Adressierung pro Endpunkt.  
  
 Für R3111, den Namespace für die `EndpointReference` Element oder Nachrichtenaustausch mit WCF-Endpunkt verwendete Typ muss die Version der WS-Adressierung von diesem Endpunkt implementierten übereinstimmen.  
  
 Z. B., wenn ein WCF-Endpunkt WS-ReliableMessaging, implementiert die `AcksTo` Header innerhalb eines solchen Endpunkts zurückgegebenes `CreateSequenceResponse` verwendet die WS-Addressing-Version, die die `EncodingBinding` Element gibt an, für diesen Endpunkt.  
  
#### <a name="endpoint-references-and-metadata"></a>Endpunktverweise und Metadaten  
 Eine Anzahl von Szenarien erfordert kommunizierende Metadaten oder einen Verweis auf Metadaten für einen bestimmten Endpunkt.  
  
 B3121: WCF wendet Mechanismen, die in Abschnitt 6, um die Metadaten für Endpunktverweise nach Wert oder Verweis aufzunehmen der WS-MetadataExchange (MEX)-Spezifikation beschrieben.  
  
 Betrachten Sie ein Szenario, in denen ein WCF-Dienst erfordert Authentifizierung mit einem Security Assertions Markup Language (SAML)-Token ausgegeben wird, vom Tokenaussteller unter http://sts.fabrikam123.com. Der WCF-Endpunkt beschreibt diese Authentifizierungsanforderung mit `sp:IssuedToken` Assertion mit einer verschachtelten `sp:Issuer` Assertion, die auf den Aussteller des Tokens verweist. Clientanwendungen, die auf die `sp:Issuer`-Assertion zugreifen, müssen mit dem Tokenausstellerendpunkt kommunizieren können. Der Client muss Metadaten über den Tokenaussteller kennen. Verwenden die Erweiterungen in MEX definiert sind, bietet WCF einen Verweis auf die tokenausstellermetadaten.  
  
```xml  
<sp:IssuedToken>  
  <sp:Issuer>  
    <wsa10:Address>  
      http://sts.fabrikam123.com  
    </wsa10:Address>  
    <wsa10:Metadata>  
      <mex:Metadata>  
        <mex:MetadataSection>  
          <mex:MetadataReference>  
            <wsa10:Address>  
              http://sts.fabrikam123.com/mex  
            </wsa10:Address>  
          </mex:MetadataReference>  
        </mex:MetadataSection>  
      </mex:Metadata>  
    </wsa10:Metadata>  
  </sp:Issuer>  
</sp:IssuedToken>  
```  
  
### <a name="message-addressing-headers"></a>Nachrichtenadressierungsheader  
  
#### <a name="message-headers"></a>Nachrichtenheader  
 Für beide WS-adressierungsversionen verwendet WCF die folgenden Nachrichtenheader wie den Spezifikationen `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, und `wsa:RelatesTo`.  
  
 B3211: Für alle Versionen, die WS-Adressierung, WCF berücksichtigt, aber nicht standardmäßig WS-Adressierungs-Nachrichtenheader `wsa:FaultTo` und `wsa:From`.  
  
 Dienstanwendungen für die Interaktion mit WCF-Anwendungen können diese Nachrichtenheader und WCF diese entsprechend verarbeitet hinzufügen.  
  
#### <a name="reference-parameters-and-properties"></a>Verweisparameter und -eigenschaften  
 WCF implementiert die Verarbeitung von endpunktverweisparametern und Verweisparameter Endpunkt  
  
 Verweiseigenschaften in Übereinstimmung mit den jeweiligen Spezifikationen.  
  
 B3221: Wenn für die Verwendung von WS-Adressierung 2004/08 konfiguriert, WCF-Endpunkten keinen Unterschied zwischen der Verarbeitung von Verweiseigenschaften und Verweisparametern.  
  
### <a name="message-exchange-patterns"></a>Nachrichtenaustauschmuster  
 Die Reihenfolge der Meldungen, die die webdienstvorgangsaufruf beteiligt wird als bezeichnet die *Nachrichtenaustauschmuster*. WCF unterstützt unidirektionale, Anforderung / Antwort- und duplexnachrichten-austauschmuster. Dieser Abschnitt klärt die WS-Adressierungsanforderungen während der Nachrichtenverarbeitung, die vom verwendeten Nachrichtenaustauschmuster abhängig sind.  
  
 Überall in diesem Abschnitt sendet der Anforderungsdienst die erste Nachricht, und der Antwortdienst empfängt die erste Nachricht.  
  
#### <a name="one-way-message"></a>Unidirektionale Nachricht  
 Wenn ein WCF-Endpunkt konfiguriert ist, zur Unterstützung von Nachrichten mit einem bestimmten `Action` um ein unidirektionales Muster befolgen, befolgt der WCF-Endpunkt die folgenden Verhalten und Anforderungen. Sofern nicht anders angegeben, gelten Verhalten und Regeln für beide Versionen der WS-Adressierung in WCF unterstützt:  
  
-   R3311: Der Anforderungsdienst muss `wsa:To`, `wsa:Action` und Header für alle Verweisparameter, die vom Endpunktverweis angegeben werden, enthalten. Wenn die WS-Adressierung 2004/08 verwendet wird und [Verweiseigenschaften] vom Endpunktverweis angegeben werden, müssen auch die entsprechenden Header der Nachricht hinzugefügt werden.  
  
-   B3312: Der Anforderungsdienst kann `MessageID`-, `ReplyTo`- und `FaultTo`-Header enthalten. Die Empfängerinfrastruktur ignoriert sie, und sie werden an die Anwendung übergeben.  
  
-   R3313: Wenn HTTP verwendet wird und keine Nachricht an den HTTP-Antwortzweig gesendet wird, muss der Antwortdienst eine HTTP-Antwort ohne Text und mit einem HTTP 202-Statuscode senden.  
  
     Wenn die HTTP-Transportmethode verwendet wird und der Vorgangsvertrag eine Nachricht als unidirektional ausweist, kann die HTTP-Antwort immer noch zum Senden von Infrastrukturnachrichten verwendet werden – Reliable Messaging kann beispielsweise eine `SequenceAcknowledgement`-Nachricht in einer HTTP-Antwort senden.  
  
-   B3314: Der WCF-Beantworter sendet keine Fehlermeldung als Antwort auf eine unidirektionale Nachricht.  
  
#### <a name="request-reply"></a>Anforderung-Antwort  
 Wenn ein WCF-Endpunkt konfiguriert ist, für eine Nachricht mit einer angegebenen `Action` um das Anforderung-Antwort-Muster zu folgen, folgt der WCF-Endpunkt die Verhalten und Anforderungen, die unten. Sofern nicht anders angegeben, gelten Verhalten und Regeln für beide Versionen der WS-Adressierung in WCF unterstützt:  
  
-   R3321: Der anforderungsdienst muss in der Anforderung enthalten `wsa:To`, `wsa:Action`, `wsa:MessageID`, und Header für alle Verweisparameter oder Verweis Eigenschaften (oder beides) vom Endpunktverweis angegeben.  
  
-   R3322: Wenn die WS-Adressierung 2004/08 verwendet wird, muss `ReplyTo` auch in der Anforderung enthalten sein.  
  
-   R3323: Wenn WS-Adressierung 1.0 verwendet wird und `ReplyTo` ist nicht vorhanden ist, in der Anforderung, ein standardendpunktverweis, mit dem [Adresse]-Eigenschaft gleich "http://www.w3.org/2005/08/addressing/anonymous" wird verwendet.  
  
-   R3324: Der anforderungsdienst muss enthalten `wsa:To`, `wsa:Action`, und `wsa:RelatesTo` -Header in der Antwortnachricht als auch-Header für alle Verweisparameter oder Verweis Eigenschaften (oder beides) gemäß der `ReplyTo` -Endpunktverweis in der Anforderung.  
  
### <a name="web-services-addressing-faults"></a>Fehler bei Web Services Addressing  
 R3411: WCF erzeugt die folgenden von WS-Adressierung 2004/08 definierten Fehler.  
  
|Code|Ursache|  
|----------|-----------|  
|wsa:DestinationUnreachable|Die Nachricht ist mit `ReplyTo` angekommen, das sich von der Antwortadresse, die für diesen Kanal festgelegt ist, unterscheidet; für die in der To-Headerzeile angegebene Adresse gibt es kein Endpunkt-Listening.|  
|wsa:ActionNotSupported|Die Infrastrukturkanäle und -verteiler, die mit dem Endpunkt verbunden sind, erkennen die Aktion, die in der Headerzeile `Action` angegeben ist, nicht.|  
  
 R3412: WCF erzeugt die folgenden von WS-Adressierung 1.0 definierten Fehler.  
  
|Code|Ursache|  
|----------|-----------|  
|wsa10:InvalidAddressingHeader|Doppelte `wsa:To`, `wsa:ReplyTo`, `wsa:From` oder `wsa:MessageID`. Doppelte `wsa:RelatesTo` mit dem gleichen `RelationshipType`.|  
|wsa10:MessageAddressingHeaderRequired|Der erforderliche Adressierungsheader fehlt.|  
|wsa10:DestinationUnreachable|Die Nachricht ist mit `ReplyTo` angekommen, das sich von der Antwortadresse, die für diesen Kanal eingeführt wurde, unterscheidet. An der Adresse, die im To-Header angegeben ist, gibt es kein Endpunkt-Listening.|  
|wsa10:ActionNotSupported|Eine Aktion, die im `Action`-Header angegeben ist, wird von den Infrastrukturkanälen oder dem Verteiler, die/der mit dem Endpunkt verbunden sind/ist, nicht erkannt.|  
|wsa10:EndpointUnavailable|Der RM-Kanal schickt diesen Fehler zurück und gibt an, dass der Endpunkt die Sequenz basierend auf einer Untersuchung der Adressheader der Nachricht `CreateSequence` nicht verarbeiten wird.|  
  
 Code in den vorangehenden Tabellen wird auf `FaultCode` in SOAP 1.1 und `SubCode` (mit Code=Sender) in SOAP 1.2 abgebildet.  
  
### <a name="wsdl-11-binding-and-ws-policy-assertions"></a>WSDL 1.1-Bindung und WS-Richtlinienassertionen  
  
#### <a name="indicating-use-of-ws-addressing"></a>Angeben der Verwendung von WS-Adressierung  
 WCF verwendet Richtlinienassertionen, um endpunktunterstützung für eine bestimmte Version von WS-Adressierung anzugeben.  
  
 Die folgende Richtlinienassertion verfügt über das Endpoint Policy Subject [WS-PA] und gibt an, dass von diesem Endpunkt gesendete und empfangene Nachrichten WS-Adressierung 2004/08 verwenden müssen.  
  
```xml  
<wsap:UsingAddressing />  
```  
  
 Diese Richtlinienassertion erweitert die Spezifikation zur WS-Adressierung 2004/08.  
  
 Die folgende Richtlinienassertion gibt an, dass gesendete/empfangene Nachrichten die WS-Adressierung 1.0 verwenden müssen.  
  
```xml
<wsam:Addressing/>   
```  
  
 Die folgende Richtlinienassertion verfügt über ein Endpoint Policy Subject [WS-PA] und gibt an, dass von diesem Endpunkt gesendete und empfangene Nachrichten WS-Adressierung 2004/08 verwenden müssen.  
  
```xml  
<wsaw10:UsingAddressing />  
```  
  
 Das Element `wsaw10:UsingAddressing` wird aus der [WS-Addressing-WSDL] ausgeliehen und im Kontext von WS-Policy entsprechend der Spezifikation, Abschnitt 3.1.2, verwendet.  
  
 Die Nutzung von Adressing verwendet nicht die Semantik von WSDL 1.1-, SOAP 1.1- und SOAP 1.2 HTTP-Bindungen. Wenn beispielsweise eine Antwort auf eine Anfrage erwartet wird, die an einen Endpunkt gesendet wird, der Addressing und WSDL SOAP 1.x HTTP-Bindung verwendet, muss die Antwort unter Verwendung der HTTP-Antwort gesendet werden.  
  
 Die WS-AM-Assertion von Antworten, die über die HTTP-Antwort gesendet werden, ist Folgende:  
  
```xml  
<wsam:AnonymousResponses/>  
```  
  
 Die vollständige Richtlinienassertion kann wie folgt aussehen:  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
        <wsam:AnonymousResponses />   
    </wsp:Policy>  
</wsam:Addressing>  
```  
  
 Es gibt aber Nachrichtenaustauschmuster, die davon profitieren, zwei unabhängige, entgegengesetzte HTTP-Verbindungen zwischen dem Anforderungsdienst und dem Antwortdienst etabliert zu haben, z. B. unaufgeforderte unidirektionale Nachrichten, die vom Antwortdienst gesendet werden.  
  
 WCF bietet ein Feature, mit dem zwei zugrunde liegende Transportkanäle können einen Composite Duplex-Kanal bilden, bei dem ein Kanal für eingehende Nachrichten und der andere für ausgehende Nachrichten verwendet wird. Im Fall des HTTP-Transports stellt Composite Duplex zwei umgekehrte HTTP-Verbindungen bereit. Der Anforderungsdienst verwendet eine Verbindung, um Nachrichten an den Antwortdienst zu senden, und der Antwortdienst verwendet die andere, um Nachrichten zurück an den Anforderungsdienst zu senden.  
  
 Die WS-AM-Assertion von Antworten, die über separate HTTP-Anforderungen gesendet werden, ist Folgende:  
  
```xml  
<wsam:NonAnonymousResponses/>  
```  
  
 Die vollständige Richtlinienassertion kann wie folgt aussehen:  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
      <wsam:NonAnonymousResponses />   
   </wsp:Policy>  
  </wsam:Addressing>  
```  
  
 Die Verwendung der folgenden Assertion, die über Endpoint Policy Subject [WS-PA] an Endpunkten verfügt, die WSDL 1.1 SOAP 1.x HTTP-Bindungen verwenden, erfordert zwei einzelne entgegengesetzte HTTP-Verbindungen, die jeweils für den Nachrichtenfluss vom Anforderungsdienst an den Antwortdienst bzw. vom Antwortdienst an den Anforderungsdienst verwendet werden.  
  
```xml  
<cdp:CompositeDuplex/>  
```  
  
 Die vorherige Anweisung führt bei Anforderungsnachrichten zu den folgenden Anforderungen an den `wsa:ReplyTo`-Header:  
  
-   R3514: Anforderung an einen Endpunkt gesendete Anforderungsnachrichten müssen eine `ReplyTo` -Header mit der `[address]` -Eigenschaft nicht gleich "http://www.w3.org/2005/08/addressing/anonymous" Wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und verfügt über eine richtlinienalternative mit einer `wsap10:UsingAddressing` oder `wsap:UsingAddressing` Assertion gekoppelt `cdp:CompositeDuplex` angefügt.  
  
-   R3515: Anforderung an einen Endpunkt gesendete Anforderungsnachrichten müssen eine `ReplyTo` -Header mit der `[address]` -Eigenschaft gleich "http://www.w3.org/2005/08/addressing/anonymous", oder nicht über eine `ReplyTo` Header überhaupt, wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und verfügt über eine richtlinienalternative mit `wsap10:UsingAddressing` -Assertion und keiner `cdp:CompositeDuplex` -Assertion angehängt.  
  
-   R3516: Anforderung an einen Endpunkt gesendete Anforderungsnachrichten müssen eine `ReplyTo` -Header mit einem `[address]` -Eigenschaft gleich "http://www.w3.org/2005/08/addressing/anonymous" Wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und verfügt über eine richtlinienalternative mit `wsap:UsingAddressing` Assertion und keine `cdp:CompositeDuplex`-Assertion angehängt.  
  
 Die WS-Adressierung-WSDL-Spezifikation versucht, ähnliche Protokollbindungen zu beschreiben, indem sie ein `<wsaw:Anonymous/>`-Element mit drei Textwerten (erforderlich, optional und verboten) einführt, um die Anforderungen im `wsa:ReplyTo`-Header (Abschnitt 3.2) anzugeben. Leider ist eine derartige Elementdefinition im Kontext einer WS-Richtlinie als Assertion nicht besonders nützlich, da sie domänenspezifische Erweiterungen benötigt, um den Knotenpunkt von Alternativen zu unterstützen, die ein derartiges Element als Assertion verwenden. Eine derartige Elementdefinition gibt außerdem den Wert des `ReplyTo`-Headers als Gegenstück zum Endpunktverhalten auf dem Kabel an und macht ihn somit spezifisch für den HTTP-Transport.  
  
#### <a name="action-definition"></a>Aktionsdefinition  
 WS-Adressierung 2004/08 definiert ein `wsa:Action`-Attribut für die `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`-Elemente. WS-Adressierung 1.0 WSDL-Bindung (WS-ADDR10-WSDL) definiert ein ähnliches Attribut, `wsaw10:Action`.  
  
 Der einzige Unterschied zwischen den beiden ist die Standardaktionsmustersemantik, die in Abschnitt 3.3.2 von WS-ADDR bzw. Abschnitt 4.4.4 der 4.4.4 von WS-ADDR10-WSDL beschrieben wird.  
  
 Es ist sinnvoll, zwei Endpunkte verfügen, die denselben `portType` (oder der Vertrag, in der WCF-Terminologie), aber mit verschiedenen Versionen der WS-Adressierung. Da aber "Aktion" durch den `portType` definiert wird und sich nicht zwischen den Endpunkten, die den `portType` implementieren, ändern sollte, ist es unmöglich, beide Standardaktionsmuster zu unterstützen.  
  
 Um diese kontroverse zu beheben, WCF unterstützt eine einzelne Version der `Action` Attribut.  
  
 B3521: WCF verwendet die `wsaw10:Action` -Attribut `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` Elemente, die WS-ADDR10-WSDL, um zu bestimmen, gemäß der `Action` URI für die entsprechenden Nachrichten unabhängig von der WS-Addressing-Version, die vom Endpunkt verwendet wird.  
  
#### <a name="use-endpoint-reference-inside-wsdl-port"></a>Verwenden des Endpunktverweises im WSDL-Anschluss  
 Abschnitt 4.1 von WS-ADDR10-WSDL erweitert das `wsdl:port`-Element durch das untergeordnete `<wsa10:EndpointReference…/>`-Element, um den Endpunkt in WS-Adressierungsbegriffen zu beschreiben. WCF erweitert dieses Hilfsprogramm in der WS-Adressierung 2004/08, sodass `<wsa:EndpointReference…/>` erscheint als untergeordnetes Element des `wsdl:port`.  
  
-   R3531: Wenn einem Endpunkt eine Richtlinienalternative mit einer `<wsaw10:UsingAddressing/>`-Richtlinienassertion angehängt ist, kann das entsprechende`wsdl:port`-Element ein untergeordnetes Element`<wsa10:EndpointReference …/>` enthalten.  
  
-   R3532: Wenn ein `wsdl:port` enthält ein untergeordnetes Element `<wsa10:EndpointReference …/>`, `wsa10:EndpointReference/wsa10:Address` untergeordnete Element muss mit dem Wert übereinstimmen von der `@address` Attributs des gleichgeordneten `wsdl:port` / `wsdl:location` Element.  
  
-   R3533: Wenn einem Endpunkt eine Richtlinienalternative mit einer `<wsap:UsingAddressing/>`-Richtlinienassertion angehängt ist, kann das entsprechende`wsdl:port`-Element ein untergeordnetes Element`<wsa:EndpointReference …/>` enthalten.  
  
-   R3534: Wenn ein `wsdl:port` enthält ein untergeordnetes Element `<wsa:EndpointReference …/>`, `wsa:EndpointReference/wsa:Address` untergeordnete Element muss mit dem Wert übereinstimmen von der `@address` Attributs des gleichgeordneten `wsdl:port` / `wsdl:location` Element.  
  
### <a name="composition-with-ws-security"></a>Gestaltung mit WS-Sicherheit  
 Gemäß den Sicherheitsüberlegungsabschnitten in WS-ADDR und WS-ADDR10 wird empfohlen, dass alle adressierenden Header zusammen mit dem Nachrichtentext signiert werden, um sie zusammenzubinden.  
  
 Wenn WS-Sicherheit für den Nachrichtenintegritätsschutz verwendet wird, müssen die WS-Adressierungs-Nachrichtenheader genauso wie die Header, die aus Referenzparametern oder -eigenschaften (oder beidem) entstanden sind, zusammen mit dem Text der Nachricht signiert werden.  
  
### <a name="examples"></a>Beispiele  
  
#### <a name="one-way-message"></a>Unidirektionale Nachricht  
 In diesem Szenario sendet der Absender eine unidirektionale Nachricht zum Empfänger. SOAP 1.2, HTTP 1.1 und W3C WS-Adressierung 1.0 werden verwendet.  
  
 Die Anforderungsnachrichtenstruktur: Zu den Nachrichtenheadern gehören die Elemente `wsa10:To` und `wsa10:Action`. Der Nachrichtentext schließt ein bestimmtes `<app:Ping>`-Element vom Anwendungsnamespace ein.  
  
 HTTP-Header: Das Ziel in POST entspricht den URI in der `wsa10:To` Element.  
  
 Der Content-Type-Header entspricht dem Wert `application/soap+xml`, wie von SOAP 1.2 vorausgesetzt. Die Parameter `charset` und `action` sind eingeschlossen. Der Parameter `action` des Content-Type-Headers entspricht dem Wert des `wsa10:Action`-Nachrichtenheaders.  
  
```  
POST http://fabrikam123.com/Service HTTP/1.1  
Content-Type: application/soap+xml; charset=utf-8;    
              action="http://fabrikam123.com/Service/OneWay"  
Host: 131.107.72.15  
Content-Length: 1501  
Expect: 100-continue  
Proxy-Connection: Keep-Alive  
<s12:Envelope>  
  <s12:Header>  
    <wsa10:To s12:mustUnderstand="1">  
        http://fabrikam123.com/Service  
    </wsa10:To>  
    <wsa10:Action s12:mustUnderstand="1">  
        http://fabrikam123.com/Service/OneWay   
    </wsa10:Action>  
  </s12:Header>  
  <s12:Body>  
    <Ping xmlns="http://fabrikam123.com/Service/">  
      <Text>Hello World</Text>  
    </Ping>  
  </s12:Body>  
</s12:Envelope>  
```  
  
 Der Empfänger antwortet mit einer leeren HTTP-Antwort und dem Status 202. Ein Beispiel für die HTTP-Antwort:  
  
```  
HTTP/1.1 202 Accepted  
Date: Fri, 15 Jul 2005 08:56:07 GMT  
Server: Microsoft-IIS/6.0  
MicrosoftOfficeWebServer: 5.0_Pub  
X-Powered-By: ASP.NET  
X-AspNet-Version: 2.0.50215  
Cache-Control: private  
Content-Length: 0  
```  
  
## <a name="soap-message-transmission-optimization-mechanism"></a>SOAP-Nachrichten-Übertragungsoptimierungsmechanismus  
 Dieser Abschnitt beschreibt die Details der WCF-Implementierung für die HTTP-SOAP MTOM. MTOM-Technologie ist SOAP-nachrichtencodierungsmechanismus der gleichen Klasse wie traditionelle Text-/XML-Codierungs- oder WCF-binärcodierung. Zu MTOM gehören folgende Elemente:  
  
-   Ein XML-Codierungs- und Verpackungsmechanismus, der von [XOP] beschrieben wird, und XML-Informationselemente, die base64-codierte Binärdaten enthalten, die in einzelne Binärteile optimiert wurden.  
  
-   Eine MIME-Kapselung des XOP-Pakets, das das XML-Infoset und jeden Binärteil des XOP-Pakets in einen einzelnen MIME-Teil serialisiert.  
  
-   Eine MIME-XOP-Codierung, die auf SOAP 1.x Envelope angewendet wird.  
  
-   Eine HTTP-Transportbindung.  
  
 Es ist möglich, MTOM mit nicht-HTTP-Transporte mit WCF zu verwenden. In diesem Thema konzentrieren wir uns jedoch auf HTTP.  
  
 Das MTOM-Format setzt einen großen Satz von Spezifikationen ein, der MTOM selbst, XOP und MIME abdeckt. Die Modularität dieses Spezifikationssatzes macht es schwierig, die genauen Anforderungen an die Format- und Verarbeitungssemantik zu rekonstruieren. In diesem Abschnitt werden die Format- und Verarbeitungsanforderungen an MTOM-HTTP-Bindungen beschrieben.  
  
### <a name="mtom-message-encoding"></a>MTOM-Nachrichtencodierung  
  
#### <a name="generating-mtom-messages"></a>Generieren von MTOM-Nachrichten  
 [XOP] Abschnitt 3.1 beschreibt den Vorgang der Codierung von XML mit Elementinformationselementen, die base24-Werte enthalten, in ein abstrakt definiertes XOP-Paket.  
  
 Die folgende Sequenz von Schritten beschreibt den MTOM-spezifischen Codierungsprozess:  
  
1.  Stellen Sie sicher, dass der zu codierende SOAP-Umschlag kein elementinformationselement mit enthält eine `[namespace name]` von "http://www.w3.org/2004/08/xop/include" und ein `[local name]` von `Include`.  
  
2.  Erstellen Sie ein leeres MIME-Paket.  
  
3.  Identifizieren Sie die Elementinformationselemente, die optimiert werden sollten, innerhalb des Original XML Infoset. Für die Elemente optimiert werden, die Zeichen, die bilden die `[children]` des elementinformationselements-Element muss in kanonischer Form werden `xs:base64Binary` (Siehe XSD-2, 3.2.16 base64Binary) und darf Leerzeichen vor, oder nach dem nicht-Leerzeichen-Inhalt.  
  
4.  Erstellen Sie einen XOP SOAP-Umschlag, der eine Kopie des Original-SOAP-Umschlags ist, aber bei dem das untergeordnete Element jedes Elementinformationselements, das im vorherigen Schritt identifiziert wurde, durch ein `xop:Include`-Elementinformationselement ersetzt wurde, das wie folgt erstellt wird:  
  
    1.  Wandeln Sie die ersetzten Zeichen in Binärdaten um, indem Sie sie als base64-codierte Daten verarbeiten.  
  
    2.  Generieren Sie einen eindeutigen Content-ID-Headerwert, der die Anforderungen R3133 und R3134 zufriedenstellt.  
  
    3.  Generieren Sie einen Content-Transfer-Encoding-MIME-Header mit dem Wert "binär".  
  
    4.  Wenn das optimierte Elementinformationselement (das [übergeordnete Element] des neu eingefügten `xop:Include`-Elementinformationselements) ein `xmime:contentType`-Attributelement besitzt, generieren Sie einen Content-Type-MIME-Header mit dem Wert des `xmime:contentType`-Attributs.  
  
    5.  Generieren Sie ein neues MIME-Teil mit einem Inhalt aus Binärdaten, die aus den ersetzten Zeichen entschlüsselt wurden, die als base64, Content-ID-Header aus 4b, Content-Transfer-Encoding-Header und Content-Type-Header bei Generierung in Schritt 4d aus 4c verarbeitet wurden.  
  
    6.  Fügen Sie ein `href`-Attribut zum `xop:Include`-Element mit dem Wert "cid: uri" hinzu, der in Schritt 4b aus dem Content-ID-Headerwert erstellt wurde. Entfernen Sie die umschließenden "\<" und ">"-Zeichen, die URL-Escape-Zeichenfolge die verbleibenden, und fügen Sie das Präfix `cid:`. Der folgende minimale Zeichensatz ist erforderlich, um RFC1738 und RFC2396 mit einem Escapezeichen zu versehen. Andere Zeichen können mit Escapezeichen versehen werden.  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  Erstellen Sie ein Stamm-MIME-Teil mit dem XOP SOAP-Umschlag aus Schritt 4.  
  
6.  Schreiben Sie die HTTP-Header, einschließlich des HTTP Content-Type-Headers.  
  
7.  Schreiben Sie das MIME-Paket.  
  
#### <a name="processing-mtom-messages"></a>Verarbeiten von MTOM-Nachrichten  
 Die Verarbeitung einer MTOM-Nachricht ist das genaue Gegenteil des Vorgangs, der im vorangehenden Abschnitt "Generieren von MTOM-Nachrichten" beschrieben wurde:  
  
1.  Stellen Sie sicher, dass der Stamm-MIME-Teil den Content-Type `application/xop+xml` hat.  
  
2.  Erstellen Sie einen SOAP-Umschlag, indem Sie den Stamm-MIME-Teil des Pakets als XML-Dokument analysieren. Die Zeichencodierung wird vom Parameter `charset` des Content-Type des Stamm-MIME-Teils bestimmt.  
  
3.  Für jedes Elementinformationselement im erstellten SOAP-Umschlag, der, als einziges Mitglied seiner [untergeordneten] Eigenschaft, ein `xop:Include`-Elementinformationselement enthält:  
  
    1.  Löschen Sie das Präfix `cid:`, und entfernen Sie alle URI-Escape-Zeichensequenzen (RFC 2396) im Wert des `@href`-Attributs des Elements `xop:Include`. Schließen Sie die Ergebniszeichenfolge "\<", ">".  
  
    2.  Suchen Sie den MIME-Teil mit dem Content-ID-Headerwert, der mit der in Schritt 3a abgeleiteten Zeichenfolge übereinstimmt.  
  
    3.  Ersetzen Sie das Elementinformationselement `xop:Include`, das in der Eigenschaft `children` jedes Elements vorkommt, durch Zeicheninformationselemente, die die vorschriftsmäßige base64-Codierung (siehe XSD-2, 3.2.16 base64Binary) des Entitätstexts des in Schritt 3b identifizierten MIME-Teils repräsentieren (ersetzen Sie wirksam das Elementinformationselement `xop:Include` durch die Daten, die im Paketteil rekonstruiert wurden).  
  
#### <a name="http-content-type-header"></a>HTTP Content-Type Header  
 Im folgenden ist eine Liste von WCF-Klärungen des Formats des HTTP Content-Type-Headers, der eine SOAP 1.x MTOM-codierte Nachricht von Anforderungen, die in der MTOM-Spezifikation selbst abgeleitet und MTOM und RFC 2387 abgeleitet sind.  
  
-   R4131: Ein HTTP-Content-Type-Header muss den Wert mehrteilig/verwandt (Groß- und Kleinschreibung nicht beachtend) und seine Parameter besitzen. Bei den Parameternamen braucht die Groß- und Kleinschreibung nicht berücksichtigt werden. Die Parameterreihenfolge ist nicht wichtig.  
  
-   Das komplette Backus-Naur Form (BNF) des Content-Type-Headers für MIME-Nachrichten wird in RFC 2045, Abschnitt 5.1 aufgeführt.  
  
-   R4132: Ein HTTP Content-Type-Header muss über einen Typparameter mit dem Wert `application/xop+xml` verfügen, der von doppelten Anführungszeichen umschlossen ist.  
  
 Während die Anforderung, die doppelte Anführungszeichen verwenden, nicht in RFC 2387 explizit ist, der Text beobachtet, dass alle der mehrteiligen/verwandten medientypparameter in den meisten Fällen reservierte Zeichen wie enthalten "\@" oder "/" aus diesem Grund benötigen Sie doppelte Anführungszeichen markiert.  
  
-   R4133: Ein HTTP Content-Type-Header sollte einen Startparameter mit dem Wert des Content-ID-Headers des MIME-Teils, der den SOAP 1.x Envelope enthält, in doppelten Anführungszeichen besitzen. Wenn der Startparameter weggelassen wird, muss der erste MIME-Teil den SOAP 1.x Envelope enthalten.  
  
-   R4134: Zum HTTP Content-Type-Header für eine SOAP 1.1 MTOM-codierte Nachricht muss der Startinfo-Parameter, umgeben von doppelten Anführungszeichen, mit dem Wert von text/xml gehören.  
  
-   R4135: Zum HTTP Content-Type-Header für eine SOAP 1.2 MTOM-codierte Nachricht muss der Startinfo-Parameter mit dem Wert von `application/soap+xml`, umgeben von doppelten Anführungszeichen, gehören.  
  
-   R4136: Der HTTP Content-Type-Header für eine SOAP 1.x MTOM-codierte Nachricht muss den Grenzparameter mit dem Wert (umgeben von doppelten Anführungszeichen), der der MIME-Grenz-BNF entspricht, die in RFC 2046, Abschnitt 5.1.1 definiert wird, enthalten.  
  
    ```  
    boundary := 0*69<bchars> bcharsnospace   
    bchars := bcharsnospace / " "   
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"   
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"  
    ```  
  
     Beispiele:  
  
     RICHTIG  
  
    ```  
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"  
    ```  
  
     RICHTIG  
  
    ```  
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
    ```  
  
     FALSCH  
  
    ```  
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"   
    ```  
  
#### <a name="infoset-mime-part"></a>Infoset-MIME-Teil  
 SOAP 1.x Envelope ist als Stammteil des XOP MIME-Paket gekapselt und wird häufig der `infoset`-Teil genannt.  
  
-   R4141: SOAP 1.x Envelope muss als Stammteil des XOP MIME-Pakets, das als `infoset`-Teil bezeichnet wird und auf das vom HTTP Content-Type verwiesen wird, gekapselt werden.  
  
-   R4142: Der SOAP-`Infoset`-Teil muss die folgenden MIME-Köpfe einschließen: `Content-ID`, `Content-Transfer-Encoding` und `Content-Type`.  
  
 Das Format des Content-ID-Headers wird von RFC 2045 als  
  
```  
"Content-ID" ":" msg-id  
```  
  
 definiert, wobei `msg-id` in RFC 2822 (das RFC 822, auf das in RFC 2045 verwiesen wird, ablöst) als:  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 eingeschlossen ist, wird tatsächlich eine e-Mail-Adresse in "\<" und ">". Das `[CFWS]`-Präfix und -Suffix wurden in RFC 2822 hinzugefügt, um Kommentare auszuführen, und sollten nicht verwendet werden, um die Kompatibilität aufrechtzuerhalten.  
  
 R4143: Der Wert des Content-ID-Headers des Infoset MIME-Teils muss der Produktion `msg-id` von RFC 2822 folgen, wobei die Präfix- und Suffixteile des `[CFWS]` entfallen.  
  
 Eine Anzahl von MIME-Implementierungen gelockert, Anforderungen für den Wert eingefasst "\<" und ">" auf eine e-Mail-Adresse und verwendet `absoluteURI` eingeschlossen in "\<", ">" neben der e-Mail-Adresse. Diese Version von WCF verwendet die Werte von der Content-ID MIME Headers in der Form:  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 R4144: MTOM-Prozessoren sollten Content-ID-Headerwerte akzeptieren, die der folgenden entspannten `msg-id` entsprechen.  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 MIME (RFC 2045) stellt den Content-Transfer-Encoding-Header bereit, um die Codierung des Inhalts des MIME-Teils zu übermitteln. Der für das Content-Transfer-Encoding definierte Standard ist 7-Bit; da dies für die meisten SOAP-Nachrichten nicht geeignet ist, wird der Content-Transfer-Encoding-Header für eine bessere Interoperabilität benötigt:  
  
-   R4145: Der SOAP-Infosetteil muss den Content-Transfer-Encoding-Header enthalten.  
  
-   R4146: Wenn die SOAP-Umschlag-Zeichencodierung UTF-8 ist, muss der Wert des Content-Transfer-Encoding-Headers 8-Bit sein.  
  
-   R4147: Wenn die SOAP-Umschlag-Zeichencodierung UTF-16 ist, muss der Wert des Content-Transfer-Encoding-Headers binär sein.  
  
-   Gemäß [XOP] Abschnitt 5,  
  
-   R4148: Die SOAP1. 1 infosetteil muss eine enthalten Content-Type-Header mit der Media-Type Application/Xop + Xml und Parametertyp = "Text/Xml" und Charset  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   R4149: Der SOAP 1.2-infosetteil muss den Content-Type-Header mit Medientyp enthalten `application/xop+xml` und Parametertyp = "`application/soap+xml`" und `charset`.  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     Obwohl XOP den Parameter `charset` für `application/xop+xml` als optional definiert, wird er ähnlich der BP 1.1-Anforderung an den Parameter `charset` des Medientyps `text/xml` für die Interoperabilität benötigt.  
  
-   R4140: Die Parameter `type` und `charset` müssen im Content-Type-Header des SOAP 1.x-Infosetteils enthalten sein.  
  
#### <a name="wcf-endpoint-support-for-mtom"></a>WCF-Endpunkt-Unterstützung für MTOM  
 Der Zweck von MTOM ist es, eine SOAP-Nachricht zu codieren, um base64-codierte Daten zu optimieren. Die folgende Liste führt Einschränkungen auf:  
  
-   R4151: Jedes Elementinformationselement, das base64-codierte Daten enthält, kann optimiert werden.  
  
-   B4152: WCF optimiert elementinformationselemente, die base64-codierte Daten enthalten und Länge 1024 Bytes nicht überschreiten.  
  
 Ein WCF-Endpunkt konfiguriert werden, um MTOM zu verwenden, sendet immer MTOM-codierte Nachrichten. Selbst wenn kein Teil die erforderlichen Kriterien erfüllt, ist die Nachricht noch immer MTOM-codiert (als MIME-Paket mit einem einzelnen MIME-Teil serialisiert, der den SOAP-Umschlag enthält).  
  
### <a name="ws-policy-assertion-for-mtom"></a>WS-Policy-Assertion für MTOM  
 Die folgende Richtlinienassertion wird von WCF verwendet, um die MTOM-Verwendung durch den Endpunkt anzugeben:  
  
```xml  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   R4211: Die vorangehende Richtlinienassertion verfügt über ein Endpoint Policy Subject und gibt an, dass alle Nachrichten, die an den Endpunkt gesendet und von diesem empfangen werden, durch den Einsatz von MTOM optimiert werden.  
  
-   B4212: Bei der Verwendung von MTOM-Optimierung konfiguriert, ein WCF-Endpunkt Fügt eine MTOM-Richtlinienassertion, die in das entsprechende zugeordnete Richtlinie `wsdl:binding`.  
  
### <a name="composition-with-ws-security"></a>Gestaltung mit WS-Sicherheit  
 MTOM ist ein Codierungsmechanismus, der ähnlich wie `text/xml` und binäre WCF-XML. MTOM bietet eine natürliche Zusammensetzung aus WS-Sicherheit und anderen WS-*-Protokollen: eine über WS-Sicherheit gesicherte Nachricht kann durch den Einsatz von MTOM optimiert werden.  
  
### <a name="examples"></a>Beispiele  
  
#### <a name="wcf-soap-11-message-encoded-using-mtom"></a>WCF-SOAP 1.1-Nachricht, mit MTOM codiert  
  
```  
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1  
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"  
Content-Type: multipart/related;type="application/xop+xml";  
              start="<http://tempuri.org/0>";start-info="text/xml";  
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
Host: 131.107.72.15  
Content-Length: 1501  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Body>  
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">  
      <array>  
        <xop:Include   
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"   
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </array>  
    </EchoBinaryAsString>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/1/632618206521093670>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
…Binary Content..  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
```  
  
#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a>WCF Secure SOAP 1.2-Nachricht, mit MTOM codiert  
 In diesem Beispiel wird eine Nachricht mit MTOM und SOAP 1.2 codiert, die mit WS-Sicherheit geschützt wird. Die für die Codierung identifizierten Binärteile sind die Inhalte des `BinarySecurityToken`, `CipherValue` der `EncryptedData`, die zu der verschlüsselten Signatur und dem verschlüsselten Text gehören. Beachten Sie, dass die `CipherValue` von der `EncryptedKey` wurde nicht identifiziert, für die Optimierung von WCF, da seine Länge geringer als 1024 Bytes ist.  
  
```  
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1  
Content-Type: multipart/related; type="application/xop+xml";  
              start="<http://tempuri.org/0>";  
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";  
              start-info="application/soap+xml";   
              action="http://xmlsoap.org/echoBinaryAsString"  
Host: 131.107.72.15  
Content-Length: 1941  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
  <s:Header>  
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">  
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>  
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>  
      </u:Timestamp>  
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">  
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </o:BinarySecurityToken>  
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedKey>  
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">  
        <o:SecurityTokenReference>  
          <o:Reference URI="#_1"/>  
        </o:SecurityTokenReference>  
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>  
      </c:DerivedKeyToken>  
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:DataReference URI="#_3"/>  
        <e:DataReference URI="#_4"/>  
      </e:ReferenceList>  
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:Reference URI="#_2"/>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>  
          <e:CipherValue>  
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
          </e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedData>  
    </o:Security>  
  </s:Header>  
  <s:Body u:Id="_0">  
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
          <o:Reference URI="#_2"/>  
        </o:SecurityTokenReference>  
      </KeyInfo>  
      <e:CipherData>  
        <e:CipherValue>  
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
        </e:CipherValue>  
      </e:CipherData>  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/1/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary content of BinarySecurityToken - X509 Certificate...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/2/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted primary signature...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/3/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted Body...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--  
```
