---
title: "Durc vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WS-protocols
- Web services protocols
- Windows Communication Foundation, Web service protocols
ms.assetid: 1f7fc4ff-30fe-4e46-adda-91caad3b06c6
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bfc4342435580796423056889b1c3bd22153740
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="web-services-protocols-supported-by-system-provided-interoperability-bindings"></a>Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist für die Interoperation mit Webdiensten konzipiert, die eine Reihe von Spezifikationen, die Webdienstspezifikationen, unterstützen. Um die Dienstkonfiguration für die empfohlene Vorgehensweise für Interoperabilität zu vereinfachen, führt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] drei interoperable, vom System bereitgestellte Bindungen ein: <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>, <xref:System.ServiceModel.WSHttpBinding?displayProperty=nameWithType> und <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>. Für Interoperabilität mit OASIS (Organization for the Advancement of Structured Information Standards)-Standards enthält [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine interoperable, vom System bereitgestellte Bindung: <xref:System.ServiceModel.WS2007HttpBinding?displayProperty=nameWithType>. Für die Veröffentlichung von Metadaten [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enthält zwei interoperable, vom System bereitgestellte Bindungen: [ \<MexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) und [ \<MexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md). Dieses Thema listet Spezifikationen auf, die von interoperablen, vom System bereitgestellten Bindungen unterstützt werden.  
  
## <a name="web-services-protocols-supported-by-basichttpbinding-wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding-bindings"></a>Von basicHttpBinding-, wsHttpBinding-, ws2007HttpBinding- und wsDualHttpBinding-Bindungen unterstützte Webdienstprotokolle  
  
### <a name="all-bindings"></a>Alle Bindungen  
 Die [ \<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), [ \<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), und [ \<ws2007HttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) Bindungen unterstützt die befolgen die Protokolle.  
  
> [!NOTE]
>  Weitere Informationen über Bindungen, die zur Veröffentlichung von Metadaten verwendet werden, finden Sie im Abschnitt „Vom System bereitgestellte Metadatenbindungen“ später in diesem Thema.  
  
|Kategorie|Protokoll|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> `BasicHttpBinding`, `WSHttpBinding` und `WS2007HttpBinding` nutzen die HTTP-HTTPS-Transporte.|  
|Messaging|MTOM|[MTOM](http://go.microsoft.com/fwlink/?LinkId=95326)<br /><br /> `basicHttpBinding`, `wsHttpBinding` und `ws2007HttpBinding` unterstützen MTOM (Message Transmission Optimization Mechanism). Standardmäßig nicht verwendet. Um MTOM zu verwenden, legen Sie das `messageEncoding`-Attribut auf `"Mtom"` fest.<br /><br /> Beispiel:<br /><br /> `<wsHttpBinding> <binding messageEncoding="Mtom"/> </wsHttpBinding>`|  
|Metadaten|WSDL 1.1|[WSDL 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet WSDL (Web Services Description Language), um Dienste zu beschreiben.|  
|Metadaten|WS-Richtlinie|[WS-Richtlinie](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die WS-Richtlinienspezifikation zusammen mit domänenspezifischen Assertionen zur Beschreibung von Dienstanforderungen und -funktionen.|  
|Metadaten|WS-Richtlinie 1.5|[WS-Policy 1.5](http://go.microsoft.com/fwlink/?LinkId=95327)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die WS-Richtlinienspezifikation zusammen mit domänenspezifischen Assertionen zur Beschreibung von Dienstanforderungen und -funktionen.|  
|Metadaten|WS-PolicyAttachment|[WS-PolicyAttachment](http://go.microsoft.com/fwlink/?LinkId=95328)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert WS-PolicyAttachment, um Richtlinienausdrücke bei verschiedenen Bereichen auf Web Services Description Language (WSDL) anzufügen.|  
|Metadaten|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und der WS-Richtlinie.|  
  
### <a name="basichttpbinding"></a>basicHttpBinding  
  
|Kategorie|Protokoll|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Messaging|SOAP 1,1|[SOAP 1.1](http://go.microsoft.com/fwlink/?LinkId=90520)<br /><br /> In Übereinstimmung mit Basic Profile 1.1 implementiert das `basicHttpBinding`-Element das SOAP 1.1-Nachrichtenprotokoll.|  
|Sicherheit|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> In Übereinstimmung mit dem Basic Security Profile implementiert das `basicHttpBinding`-Element Web Services Security (WSS) SOAP Message Security 1.0 für Benutzername/Kennwort und X.509-basierte Sicherheit.<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential &#124;                     "Message" .../> </binding> </basicHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security UsernameToken Profile 1.0|[WSS SOAP Message Security UsernameToken Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> `<basicHttpBinding> <binding name="Binding1"> <security mode="TransportWithMessageCredential"> <transport clientCredentialType="Basic"/> </security> </basicHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security x. 509-Zertifikatstokenprofil 1.0|[WSS SOAP Message Security x. 509-Zertifikatstokenprofil 1.0](http://go.microsoft.com/fwlink/?LinkId=95335)<br /><br /> `<basicHttpBinding>   <security mode="Message"> <message clientCredentialType="Certificate"/> </security> </basicHttpBinding>`|  
  
### <a name="wshttpbinding-ws2007httpbinding-and-wsdualhttpbinding"></a>wsHttpBinding, ws2007HttpBinding und wsDualHttpBinding  
  
|Kategorie|Protokoll|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Messaging|SOAP 1.2|[Einführung in](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Messaging-framework](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Zusätze (einschließlich HTTP-Bindung)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaging|WS-Adressierung 2005/08|[Web Services Addressing 1.0 – Core](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 – SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)<br /><br /> Die `wsHttpBinding`, `ws2007HttpBinding` und `wsDualHttpBinding` implementieren die WS-Adressierungsempfehlungen des World Wide Web Consortium (W3C), um asynchrones Messaging, Nachrichtenkorrelation und transportneutrale Adressierungsmechanismen zu ermöglichen.<br /><br /> WCF unterstützt keine Verschlüsselung von WS-Addressing-Headern, obwohl dies gemäß den WS-*-Spezifikationen zulässig ist.|  
|Messaging|WS-Addressing 1.0 - Metadata|[WS-Adressierung 1.0 Metadaten](http://www.w3.org/2007/05/addressing/metadata) Unterstützung für dieses Protokoll wird aktiviert, indem die Richtlinienversion im ServiceMetadata-Verhalten - mit Policyversion 1.2 (Standard) festgelegt, die Wsdl-Beschreibung ist kompatibel mit WS-Adressierung-Wsdl mit Policyversion 1.5 festgelegt, ist die Wsdl-Beschreibung, die mit ws-Adressierung Metadaten kompatibel.<br /><br /> WCF unterstützt keine Verschlüsselung von WS-Addressing-Headern, obwohl dies gemäß den WS-*-Spezifikationen zulässig ist.|  
|Sicherheit|WSS SOAP Message Security 1.0|[WSS SOAP Message Security 1.0](http://go.microsoft.com/fwlink/?LinkId=94684)<br /><br /> Zu verwenden, wenn das `securityMode`-Attribut auf "wsSecurityOverHttp" (Standard) festgelegt ist und die Parameter mithilfe des untergeordneten `wsSecurity`-Elements konfiguriert wurden.<br /><br /> `<wsHttpBinding>   <binding name="myBinding">      <security mode="Message" .../>   </binding> </wsHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security UsernameToken Profile 1.1|[WSS SOAP Message Security UsernameToken Profile 1.0](http://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> Zu verwenden, wenn das `wsSecurity`-Attribut des `authenticationMode`-Elements auf "Username" festgelegt ist.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="UserName        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security> </binding> </wsHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security X.509 Certificate Token Profile 1.1|[WSS SOAP Message Security x. 509-Zertifikatstokenprofil 1.1](http://go.microsoft.com/fwlink/?LinkId=95332)<br /><br /> Zu verwenden für Nachrichtenschutz, wenn das `wsSecurity`-Attribut des `authenticationMode`-Elements auf "Username", "Certificate" oder "None" festgelegt ist. Auch zu verwenden für die Clientauthentifizierung, wenn das `wsSecurity`-Attribut des `authenticationMode`-Elements auf "Certificate" festgelegt ist.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Certificate"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicherheit|WSS SOAP Message Security Kerberos Token Profile 1.1|[WSS SOAP Message Security Kerberos Token Profile 1.1](http://go.microsoft.com/fwlink/?LinkId=95333)<br /><br /> Zu verwenden für Authentifizierung und Nachrichtenschutz, wenn das `wsSecurity`-Attribut des `authenticationMode`-Elements auf "Windows" festgelegt ist.<br /><br /> `<wsHttpBinding>   <binding name="MyBinding">     <security mode="Message>       <message           clientCredentialType="Windows"        negotiateServiceCredential="false"        establishSecurityContext="false"/>     </security>   </binding> </wsHttpBinding>`|  
|Sicherheit|WS-SecureConversation|[WS-SecureConversation](http://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Zu verwenden für die Bereitstellung einer sicheren Sitzung, wenn das `security/@mode`-Attribut auf "Message" und das `message/@establishSecurityContext`-Attribut auf "true" (Standard) festgelegt sind.|  
|Sicherheit|WS-Trust|[WS-Trust](http://go.microsoft.com/fwlink/?LinkId=95318)<br /><br /> Wird von WS-SecureConversation verwendet (siehe oben).|  
|Zuverlässiges Messaging|WS-ReliableMessaging|[WS-ReliableMessaging](http://go.microsoft.com/fwlink/?LinkId=95322)<br /><br /> Zu verwenden, wenn die Bindung für die Verwendung von `reliableSession` konfiguriert ist.<br /><br /> `<wsHttpBinding>  <binding name="myBinding">    <reliableSession/>   </binding> </wsHttpBinding>`|  
|Transaktionen|WS-AtomicTransaction|[WS-AtomicTransaction](http://go.microsoft.com/fwlink/?LinkId=95323)<br /><br /> Wird für die Kommunikation zwischen Transaktions-Managern verwendet. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients und -Dienste verwenden immer lokale Transaktions-Manager.|  
|Transaktionen|WS-Coordination|[WS-Coordination](http://go.microsoft.com/fwlink/?LinkId=95324)<br /><br /> Zu verwenden für den Transaktionskontextfluss, wenn das `flowTransactions`-Attribut auf "Allowed" oder "Required" festgelegt ist.<br /><br /> `<wsHttpBinding>   <binding transactionFlow="true"/> </wsHttpBinding>`|  
  
## <a name="wsfederationhttpbinding-and-ws2007federationhttpbinding"></a>wsFederationHttpBinding und ws2007FederationHttpBinding  
 Die [ \<WsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md) und [ \<ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md) Elemente werden eingeführt, um Verbundszenarien, wobei eine dritte unterstützen Partei gibt ein Token zum Authentifizieren eines Clients verwendet. `wsHttpBinding` setzt zusätzlich zu den von der `wsFederationHttpBinding` verwendeten Protokollen ein:  
  
-   `WS-Trust` für die Tokenausgabe.  
  
-   WSS Security Assertions Markup Language (SAML) Token Profile 1.0 und 1.1 für das am häufigsten herausgegebene Tokenformat.  
  
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
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verbund](../../../../docs/framework/wcf/feature-details/federation.md) .  
  
## <a name="system-provided-metadata-bindings"></a>Vom System bereitgestellte Metadatenbindungen  
 Die folgende Tabelle beschreibt die Protokolle, die von den interoperablen Metadatenbindungen bereitgestellt und von der <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>-Klasse verfügbar gemacht werden.  
  
### <a name="mexhttpbinding"></a>mexHttpBinding  
 Die [ \<MexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md) Bindung unterstützt die folgenden Protokolle. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]mit dieser Bindung finden Sie unter [Veröffentlichungsmetadaten](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Kategorie|Protokoll|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)|  
|Messaging|SOAP 1.2|[Einführung in](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Messaging-framework](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Zusätze (einschließlich HTTP-Bindung)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaging|WS-Adressierung 2005/08|[Web Services Addressing 1.0 – Core](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 – SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadaten|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und der WS-Richtlinie.|  
  
### <a name="mexhttpsbinding"></a>mexHttpsBinding  
 [\<MexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md) unterstützt die folgenden Protokolle. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]mit dieser Bindung finden Sie unter [Veröffentlichungsmetadaten](../../../../docs/framework/wcf/feature-details/publishing-metadata.md).  
  
|Kategorie|Protokoll|Spezifikation und Verwendung|  
|--------------|--------------|-----------------------------|  
|Transport|HTTP 1.1|[HTTP 1.1](http://go.microsoft.com/fwlink/?LinkId=84048)<br /><br /> Transportsicherheit ist aktiviert.|  
|Messaging|SOAP 1.2|[Einführung in](http://go.microsoft.com/fwlink/?LinkId=48282)<br /><br /> [Messaging-framework](http://go.microsoft.com/fwlink/?LinkId=94664)<br /><br /> [Zusätze (einschließlich HTTP-Bindung)](http://go.microsoft.com/fwlink/?LinkId=95329)|  
|Messaging|WS-Adressierung 2005/08|[Web Services Addressing 1.0 – Core](http://go.microsoft.com/fwlink/?LinkId=90574)<br /><br /> [Web Services Addressing 1.0 – SOAP](http://go.microsoft.com/fwlink/?LinkId=95330)|  
|Metadaten|WS-MetadataExchange|[WS-MetadataExchange](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert WS-MetadataExchange zum Abrufen von XML-Schema, WSDL und der WS-Richtlinie.|  
  
## <a name="see-also"></a>Siehe auch  
 [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [\<BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)  
 [\<WsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)  
 [\<WsDualHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)  
 [\<MexHttpsBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpsbinding.md)  
 [\<MexHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/mexhttpbinding.md)
