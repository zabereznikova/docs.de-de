---
title: "Vorgehensweise: Erstellen einer Bindung mit Duplexverbund | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Vorgehensweise: Erstellen einer Bindung mit Duplexverbund
<xref:System.ServiceModel.WSFederationHttpBinding> unterstützt lediglich Datagramm\- sowie Anforderung\/Antwort\-Nachrichtenaustauschverträge.Für die Verwendung des Duplexnachrichtenaustauschvertrags muss eine benutzerdefinierte Bindung erstellt werden.In den folgenden Verfahren wird gezeigt, wie dies in der Konfiguration umgesetzt werden kann. Verwendet werden die Nachrichtenmodussicherheit bei HTTP und TCP sowie die Sicherheit im gemischten Modus bei TCP.Beispielcode mit allen drei Bindungen finden Sie am Ende dieses Themas.  
  
 Die Bindung kann auch im Code erstellt werden.Eine Beschreibung des zu erstellenden Stapels von Bindungselementen finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
### So erstellen Sie eine benutzerdefinierte Bindung mit HTTP und Duplexverbund  
  
1.  Erstellen Sie im [\<Bindungen\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)[\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)\-Element.  
  
2.  Erstellen Sie innerhalb des [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)[\<Bindung\>](../../../../docs/framework/misc/binding.md)`name``-Element, und legen Sie dessen FederationDuplexHttpMessageSecurityBinding`\-Attribut auf  fest.  
  
3.  Erstellen Sie innerhalb des [\<Bindung\>](../../../../docs/framework/misc/binding.md)[\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode``-Element, und legen Sie dessen SecureConversation`\-Attribut auf  fest.  
  
4.  Erstellen Sie innerhalb des [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode``-Element, und legen Sie dessen IssuedTokenForCertificate``-Attribut auf IssuedTokenForSslNegotiated` oder auf  fest.  
  
5.  Erstellen Sie nach dem [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<compositeDuplex\>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)\-Element.  
  
6.  Erstellen Sie nach dem [\<compositeDuplex\>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)\-Element.  
  
7.  Erstellen Sie nach dem [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)\-Element.  
  
### So erstellen Sie eine benutzerdefinierte Bindung mit TCP\-Nachrichtensicherheitsmodus und Duplexverbund  
  
1.  Erstellen Sie im [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)\-Element.  
  
2.  Erstellen Sie innerhalb des [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)`name``-Element, und legen Sie dessen FederationDuplexTcpMessageSecurityBinding`\-Attribut auf  fest.  
  
3.  Erstellen Sie innerhalb des [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode``-Element, und legen Sie dessen SecureConversation`\-Attribut auf  fest.  
  
4.  Erstellen Sie innerhalb des [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode``-Element, und legen Sie dessen IssuedTokenForCertificate``-Attribut auf IssuedTokenForSslNegotiated` oder auf  fest.  
  
5.  Erstellen Sie nach dem [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<tcpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)\-Element.  
  
### So erstellen Sie eine benutzerdefinierte Bindung mit gemischtem TCP\-Sicherheitsmodus und Duplexverbund  
  
1.  Erstellen Sie im [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)\-Element.  
  
2.  Erstellen Sie innerhalb des [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)`name``-Element, und legen Sie dessen FederationDuplexTcpTransportSecurityWithMessageCredentialBinding`\-Attribut auf  fest.  
  
3.  Erstellen Sie innerhalb des [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)`authenticationMode``-Element, und legen Sie dessen SecureConversation`\-Attribut auf  fest.  
  
4.  Erstellen Sie innerhalb des [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)`authenticationMode``-Element, und legen Sie dessen IssuedTokenForCertificate``-Attribut auf IssuedTokenForSslNegotiated` oder auf  fest.  
  
5.  Erstellen Sie nach dem [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)[\<sslStreamSecurity\>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)\-Element.  
  
6.  Erstellen Sie nach dem [\<sslStreamSecurity\>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)[\<tcpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md)\-Element.  
  
## Codebeispiel  
  
#### Beispiel mit drei Bindungen  
  
1.  Fügen Sie den folgenden Code in die Konfigurationsdatei ein:  
  
## Beispiel  
  
```  
  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
  
```