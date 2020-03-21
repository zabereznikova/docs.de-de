---
title: Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle
ms.date: 03/30/2017
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
ms.openlocfilehash: a1e67401a09370a46bc7a3e8546c95467bc18b67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184145"
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle
Windows Communication Foundation (WCF) wurde für die Zusammenarbeit mit Webdiensten entwickelt, die eine Reihe von Spezifikationen unterstützen, die als Webdienstspezifikationen bezeichnet werden. Um die Dienstkonfiguration für Best Practices für die Interoperabilität zu vereinfachen, <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType>führt <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>WCF drei interoperable Systembindungen ein: <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>, und . Für die Interoperabilität mit DEN OASIS-Standards (Organization for the Advancement of Structured Information <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>Standards) enthält WCF eine interoperable systemfähige Bindung: . Für die Metadatenpublikation enthält WCF zwei interoperable, vom System bereitgestellte Bindungen: [ \<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) und [ \<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). Dieses Thema listet Spezifikationen auf, die von interoperablen, vom System bereitgestellten Bindungen unterstützt werden.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Von basicHttpBinding-, wsHttpBinding-, ws2007HttpBinding- und wsDualHttpBinding-Bindungen unterstützte Webdienstprotokolle  
  
### <a name="all-bindings"></a>Alle Bindungen  
 Die [ \<grundlegenden bindungen für httpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)und [ \<ws2007HttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) unterstützen die folgenden Protokolle.  
  
> [!NOTE]
> Weitere Informationen über Bindungen, die zur Veröffentlichung von Metadaten verwendet werden, finden Sie im Abschnitt „Vom System bereitgestellte Metadatenbindungen“ später in diesem Thema.  
  
|Category|Protocol|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> `BasicHttpBinding`, `WSHttpBinding` und `WS2007HttpBinding` nutzen die HTTP-HTTPS-Transporte.|  
|Nachrichten|MTOM|[MTOM](https://www.w3.org/TR/soap12-mtom/)<br /><br /> `basicHttpBinding`, `wsHttpBinding` und `ws2007HttpBinding` unterstützen MTOM (Message Transmission Optimization Mechanism). Standardmäßig nicht verwendet. Um MTOM zu verwenden, legen Sie das `messageEncoding`-Attribut auf `"Mtom"` fest.<br /><br /> Beispiel:<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Metadaten|WSDL 1.1|[WSDL 1.1](https://www.w3.org/TR/wsdl/)<br /><br /> WCF verwendet Web Services Description Language (WSDL), um Dienste zu beschreiben.|  
|Metadaten|WS-Richtlinie|[WS-Richtlinie](https://www.w3.org/Submission/WS-Policy/)<br /><br /> WCF verwendet die WS-Policy-Spezifikation zusammen mit domänenspezifischen Assertionen, um Dienstanforderungen und -funktionen zu beschreiben.|  
|Metadaten|WS-Richtlinie 1.5|[WS-Richtlinie 1.5](https://www.w3.org/TR/2007/CR-ws-policy-20070605/)<br /><br /> WCF verwendet die WS-Policy-Spezifikation zusammen mit domänenspezifischen Assertionen, um Dienstanforderungen und -funktionen zu beschreiben.|  
|Metadaten|WS-PolicyAttachment|[WS-PolicyAttachment](http://specs.xmlsoap.org/ws/2004/09/policy/ws-policyattachment.pdf)<br /><br /> WCF implementiert WS-PolicyAttachment zum Anfügen von Richtlinienausdrücken an verschiedene Bereiche in Web Services Description Language (WSDL).|  
|Metadaten|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und WS-Policy.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Category|Protocol|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Nachrichten|SOAP 1,1|[SOAP 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)<br /><br /> In Übereinstimmung mit Basic Profile 1.1 implementiert das `basicHttpBinding`-Element das SOAP 1.1-Nachrichtenprotokoll.|  
|Sicherheit|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> In Übereinstimmung mit dem Basic Security Profile implementiert das `basicHttpBinding`-Element Web Services Security (WSS) SOAP Message Security 1.0 für Benutzername/Kennwort und X.509-basierte Sicherheit.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security UsernameToken Profile 1.0|[WSS SOAP Message Security UsernameToken Profile 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security X.509 Zertifikattokenprofil 1.0|[WSS SOAP Message Security X.509 Zertifikattokenprofil 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding und wsDualHttpBinding  
  
|Category|Protocol|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Nachrichten|SOAP 1.2|[Einführung](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Messagingframework](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuncts (einschließlich HTTP-Bindung)](https://www.w3.org/TR/soap12-part2/)|  
|Nachrichten|WS-Adressierung 2005/08|[Webdienste-Adressierung 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)<br /><br /> Die `wsHttpBinding`, `ws2007HttpBinding` und `wsDualHttpBinding` implementieren die WS-Adressierungsempfehlungen des World Wide Web Consortium (W3C), um asynchrones Messaging, Nachrichtenkorrelation und transportneutrale Adressierungsmechanismen zu ermöglichen.<br /><br /> WCF unterstützt keine Verschlüsselung von WS-Addressing-Headern, obwohl dies gemäß den WS-*-Spezifikationen zulässig ist.|  
|Nachrichten|WS-Addressing 1.0 - Metadata|[WS-Adressierung 1.0-Metadaten](https://www.w3.org/2007/05/addressing/metadata/) Die Unterstützung für dieses Protokoll wird aktiviert, indem die Richtlinienversion im ServiceMetadata-Verhalten festgelegt wird – mit einer Richtlinienversion, die auf 1.2 (Standard) festgelegt ist, entspricht die wsdl-Beschreibung WS-Adressierungwsdl, wobei die Richtlinienversion auf 1.5 festgelegt ist, die wsdl-Beschreibung mit ws-Adressierungsmetadaten kompatibel ist.<br /><br /> WCF unterstützt keine Verschlüsselung von WS-Addressing-Headern, obwohl dies gemäß den WS-*-Spezifikationen zulässig ist.|  
|Sicherheit|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)<br /><br /> Zu verwenden, wenn das `securityMode`-Attribut auf "wsSecurityOverHttp" (Standard) festgelegt ist und die Parameter mithilfe des untergeordneten `wsSecurity`-Elements konfiguriert wurden.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security UsernameToken Profil 1.1|[WSS SOAP Message Security UsernameToken Profile 1.0](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> Zu verwenden, wenn das `wsSecurity`-Attribut des `authenticationMode`-Elements auf "Username" festgelegt ist.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP Message Security X.509 Certificate Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)<br /><br /> Zu verwenden für Nachrichtenschutz, wenn das `wsSecurity`-Attribut des `authenticationMode`-Elements auf "Username", "Certificate" oder "None" festgelegt ist. Auch zu verwenden für die Clientauthentifizierung, wenn das `wsSecurity`-Attribut des `authenticationMode`-Elements auf "Certificate" festgelegt ist.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security Kerberos Token Profile 1.1|[WSS SOAP Message Security Kerberos Tokenprofil 1.1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)<br /><br /> Zu verwenden für Authentifizierung und Nachrichtenschutz, wenn das `wsSecurity`-Attribut des `authenticationMode`-Elements auf "Windows" festgelegt ist.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicherheit|WS-SecureConversation|[WS-SecureConversation](http://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> Zu verwenden für die Bereitstellung einer sicheren Sitzung, wenn das `security/@mode`-Attribut auf "Message" und das `message/@establishSecurityContext`-Attribut auf "true" (Standard) festgelegt sind.|  
|Sicherheit|WS-Trust|[WS-Vertrauen](http://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf)<br /><br /> Wird von WS-SecureConversation verwendet (siehe oben).|  
|Zuverlässiges Messaging|WS-ReliableMessaging|[WS-ReliableMessaging](http://specs.xmlsoap.org/ws/2005/02/rm/ws-reliablemessaging.pdf)<br /><br /> Zu verwenden, wenn die Bindung für die Verwendung von `reliableSession` konfiguriert ist.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Transaktionen|WS-AtomicTransaction|[WS-AtomicTransaction](http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)<br /><br /> Wird für die Kommunikation zwischen Transaktions-Managern verwendet. WCF-Clients und -Dienste verwenden immer lokale Transaktionsmanager.|  
|Transaktionen|WS-Coordination|[WS-Coordination](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))<br /><br /> Zu verwenden für den Transaktionskontextfluss, wenn das `flowTransactions`-Attribut auf „Allowed“ oder „Required“ festgelegt ist.<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding und ws2007FederationHttpBinding  
 [ \<DieFederationHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) und [ \<ws2007FederationHttpBinding>-Elemente](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) werden eingeführt, um Unterstützung für Verbundszenarien bereitzustellen, in denen ein Drittanbieter ein Token ausgibt, das zum Authentifizieren eines Clients verwendet wird. `wsHttpBinding` setzt zusätzlich zu den von der `wsFederationHttpBinding` verwendeten Protokollen ein:  
  
- `WS-Trust` für die Tokenausgabe.  
  
- WSS Security Assertions Markup Language (SAML) Token Profile 1.0 und 1.1 für das am häufigsten herausgegebene Tokenformat.  
  
 Beispiel:  
  
```xml  
<wsFederationHttpBinding>  
  <binding name="myBinding">  
     <security mode="Message">  
       <message issuedKeyType="Symmetric"
                issuedTokenType="http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.1#SAMLV1.1">  
         <issuerMetadata address =
         'http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex'>  
       </message>  
     </security>  
  </binding>  
</wsFederationHttpBinding>  
```  
  
 Weitere Informationen finden Sie unter [Föderation](../../../../docs/framework/wcf/feature-details/federation.md) .  
  
## <a name="system-provided-metadata-bindings"></a>Vom System bereitgestellte Metadatenbindungen  
 Die folgende Tabelle beschreibt die Protokolle, die von den interoperablen Metadatenbindungen bereitgestellt und von der <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>-Klasse verfügbar gemacht werden.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 Die [ \<mexHttpBinding>-Bindung](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) unterstützt die folgenden Protokolle. Weitere Informationen zur Verwendung dieser Bindung finden Sie unter [Veröffentlichen von Metadaten](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocol|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)|  
|Nachrichten|SOAP 1.2|[Einführung](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Messagingframework](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuncts (einschließlich HTTP-Bindung)](https://www.w3.org/TR/soap12-part2/)|  
|Nachrichten|WS-Adressierung 2005/08|[Webdienste-Adressierung 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|Metadaten|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und WS-Policy.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 mexHttpsBinding>unterstützt die folgenden Protokolle. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) Weitere Informationen zur Verwendung dieser Bindung finden Sie unter [Veröffentlichen von Metadaten](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Category|Protocol|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](https://www.ietf.org/rfc/rfc2616.txt)<br /><br /> Transportsicherheit ist aktiviert.|  
|Nachrichten|SOAP 1.2|[Einführung](https://www.w3.org/TR/soap12-part0/)<br /><br /> [Messagingframework](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)<br /><br /> [Adjuncts (einschließlich HTTP-Bindung)](https://www.w3.org/TR/soap12-part2/)|  
|Nachrichten|WS-Adressierung 2005/08|[Webdienste-Adressierung 1.0 - Core](https://www.w3.org/TR/ws-addr-core/)<br /><br /> [Web Services Addressing 1.0 - SOAP](https://www.w3.org/TR/ws-addr-soap/)|  
|Metadaten|WS-MetadataExchange|[WS-MetadataExchange](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)<br /><br /> WCF implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und WS-Policy.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)
- [\<grundlegendehttpBinding->](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)
- [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)
- [\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)
- [\<mexHttpsBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)
- [\<mexHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
