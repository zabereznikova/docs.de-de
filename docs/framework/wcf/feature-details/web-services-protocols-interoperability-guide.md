---
title: Handbuch für die Interoperabilität von Webdienstprotokollen
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 37416a80c8b6f2ac086dbface1cda37609698bfc
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2018
ms.locfileid: "46490373"
---
# <a name="web-services-protocols-interoperability-guide"></a>Handbuch für die Interoperabilität von Webdienstprotokollen
Windows Communication Foundation (WCF) wird eine Zahl von Webdienstprotokollen implementiert. Viele dieser Protokolle verfügen über eine Reihe von Optionen und Erweiterungspunkten, deren Konfiguration im Ermessen der Implementierung liegt. Dieses Thema enthält eine Liste von Webdienstprotokollen, die von die WCF implementiert. In den weiteren Themen dieses Abschnitts finden Sie ausführlichere Informationen zur Implementierung der einzelnen unterstützten Protokolle.  
  
## <a name="web-services-protocols-implemented-by-wcf"></a>Von WCF implementierte Webdienstprotokolle  
 WCF bietet Unterstützung für Web Services (WS)-infrastrukturprotokollen über Kanäle und Anwendungsprotokolle mithilfe der Vertragsfunktion-Webdienste. Die Interoperabilität von Anwendungsprotokollen wird mithilfe von XML Schema Description Language 1.0 (XSD) und Web Services Description Language (WSDL) 1.1 erzielt.  
  
 Die Interoperabilität von Infrastrukturprotokollen wird mittels der WS-*-Spezifikationen bereitgestellt. WCF--Kanäle bieten Unterstützung für eine Reihe von WS -\* infrastrukturprotokollen. WCF-Kanäle werden mithilfe von Bindungselementen konfiguriert. Die folgenden Tabellen enthalten die vollständige Liste der WS-\* infrastrukturprotokollen, die von verschiedenen Elemente der WCF-Bindung implementiert.  
  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> unterstützt die in der folgenden Tabelle aufgeführten Spezifikationen:  
  
|Spezifikation/Dokument|Link|  
|-----------------------------|----------|  
|HTTP 1.1|[RFC 2616](https://go.microsoft.com/fwlink/?LinkId=90372)|  
|SOAP 1.1 HTTP-Bindung|[Simple Object Access Protocol (SOAP) 1.1](https://go.microsoft.com/fwlink/?LinkId=90520), Abschnitt 7|  
|SOAP 1,2 HTTP-Bindung|[SOAP-Version 1.2, Teil 2: Zusätze (zweite Ausgabe)](https://go.microsoft.com/fwlink/?LinkId=95329), Abschnitt 7|  
  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> unterstützen die in der folgenden Tabelle aufgeführten Spezifikationen:  
  
|Spezifikation/Dokument|Link|  
|-----------------------------|----------|  
|XML|[Extensible Markup Language (XML) 1.0 (Fourth Edition)](https://go.microsoft.com/fwlink/?LinkId=15139)|  
|SOAP 1,1|[Simple Object Access Protocol (SOAP) 1.1](https://go.microsoft.com/fwlink/?LinkId=96687)|  
|SOAP 1.2 Core|[SOAP Version 1.2, Teil 1: Messagingframework (zweite Ausgabe)](https://go.microsoft.com/fwlink/?LinkId=94664)|  
|WS-Adressierung 2004/08|[Web Services Addressing (WS-Adressierung)](https://go.microsoft.com/fwlink/?LinkId=81239)|  
|W3C Web Services Addressing 1.0 - Core|[Webdienste-Adressierung 1.0 - Core](https://go.microsoft.com/fwlink/?LinkId=96688)|  
|W3C Web Services Addressing 1.0 - SOAP-Bindung|[Web Services Addressing 1.0 – SOAP-Bindung](https://go.microsoft.com/fwlink/?LinkId=96689)|  
|W3C Web Services Addressing 1.0 - WSDL-Bindung*|[Web Services Addressing 1.0 – WSDL-Bindung](https://go.microsoft.com/fwlink/?LinkId=96690)|  
|W3C Web Services Addressing 1.0 – Metadaten|[Web Services Addressing 1.0 – Metadaten](http://www.w3.org/TR/ws-addr-metadata/)|  
|WSDL SOAP1.1-Bindung|[Web Services Description Language (WSDL) 1.1](https://go.microsoft.com/fwlink/?LinkId=96160)|  
|WSDL SOAP1.2-Bindung|[WSDL 1.1-Bindungserweiterung für SOAP 1.2](https://go.microsoft.com/fwlink/?LinkId=96691)|  
  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> unterstützt die in der folgenden Tabelle aufgeführten Spezifikationen:  
  
|Spezifikation/Dokument|Link|  
|-----------------------------|----------|  
|XOP|[XML-Binärdatei optimiert, Verpacken](https://go.microsoft.com/fwlink/?LinkId=96714)|  
|MTOM + SOAP1.2-Bindung|[SOAP-Nachrichten-Übertragungsoptimierungsmechanismus](https://go.microsoft.com/fwlink/?LinkId=96713)|  
|MTOM SOAP 1.1-Bindung|[SOAP 1.1-Bindung für MTOM 1.0](https://go.microsoft.com/fwlink/?LinkId=96712)|  
|MTOM WS-Richtlinienassertionen|Veröffentlichung steht noch aus|  
  
 <xref:System.ServiceModel.Channels.SecurityBindingElement> unterstützt die in der folgenden Tabelle aufgeführten Spezifikationen:  
  
|Spezifikation/Dokument|Link|  
|-----------------------------|----------|  
|WSS: SOAP-Nachrichtensicherheit 1,0|[Webdienstesicherheit: SOAP Message Security 1.0](https://go.microsoft.com/fwlink/?LinkId=94684)|  
|WSS: Username Token Profile 1.0|[Web Services Security UsernameToken Profile 1.0](https://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> erfordern Password/@Type= PasswordText zugewiesen (Standard)|  
|WSS: X.509 Token Profile 1.0|[Web Services Security x. 509-Zertifikatstokenprofil](https://go.microsoft.com/fwlink/?LinkId=95335)|  
|WSS: SAML 1.1 Token Profile 1,0|[Webdienstesicherheit: SAML-Tokenprofil](https://go.microsoft.com/fwlink/?LinkId=96693)|  
|WSS: SOAP-Nachrichtensicherheit 1.1|[Webdienstesicherheit: SOAP-Nachrichtensicherheit 1.1](https://go.microsoft.com/fwlink/?LinkId=91240)|  
|WSS: Username Token Profile 1.1|[Web Services Security-Tokenprofil 1.1](https://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> Implementieren Sie keine kennwortbasierte Schlüsselableitung;<br /><br /> erfordern Password/@Type= PasswordText zugewiesen (Standard)|  
|WSS: X509 Token Profile 1.1|[Web Services Security x. 509-Zertifikatstokenprofil 1.1](https://go.microsoft.com/fwlink/?LinkId=95332)|  
|WSS: Kerberos Token Profile 1.1|[Web Services Security Kerberos Token Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=95333)|  
|WSS: SAML 1.1 Token Profile 1.1|[Web Services Security SAML Token Profile 1,1](https://go.microsoft.com/fwlink/?LinkId=96694)|  
|WS-Secure Conversation|[Webdienste sichere Konversationssprache](https://go.microsoft.com/fwlink/?LinkId=95317)|  
|WS-Trust 1.4 (möglicherweise in englischer Sprache)|[Webdienste: Trust-Sprache](https://go.microsoft.com/fwlink/?LinkId=169514)|  
|WS-SecurityPolicy 2005/07|[Webdienste sichere Konversationssprache](https://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Wurde gemäß den an das OASIS WS-SX Technical Committee übermittelten Fehlerberichten geändert.<br /><br /> [WS-Sx-Nachricht](https://go.microsoft.com/fwlink/?LinkId=96700)|  
|WS-ReliableMessaging 1.1|[Protokoll für zuverlässiges Messaging, Version 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)|  
  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> unterstützt die in der folgenden Tabelle aufgeführten Spezifikationen:  
  
|Spezifikation/Dokument|Link|  
|-----------------------------|----------|  
|WS-Coordination|[Webdienste: Koordinierung](https://go.microsoft.com/fwlink/?LinkId=95324)|  
|WS-AtomicTransaction|[Webdienste: Atomic Transaction](https://go.microsoft.com/fwlink/?LinkId=95323)|  
  
 Die Klassen <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WsdlExporter>, <xref:System.ServiceModel.Description.WsdlImporter> und <xref:System.ServiceModel.Description.MetadataResolver> bieten Unterstützung für die folgenden Metadatenspezifikationen:  
  
-   [XML-Schemateil 1: Strukturen 2. Ausgabe](https://go.microsoft.com/fwlink/?LinkId=3536)  
  
-   [XML-Schemateil 2: Datatypes Second Edition](https://go.microsoft.com/fwlink/?LinkId=40138)  
  
-   [WSDL 1.1](https://go.microsoft.com/fwlink/?LinkId=96160)  
  
-   [WS-Richtlinie 1.2](https://go.microsoft.com/fwlink/?LinkId=96705)  
  
-   [WS-Richtlinie 1.5](https://go.microsoft.com/fwlink/?LinkId=96706)  
  
-   [WS-PolicyAttachment 1.2](https://go.microsoft.com/fwlink/?LinkId=96707)  
  
-   [WS-MetadataExchange-1.1](https://go.microsoft.com/fwlink/?LinkId=94868)  
  
-   [WS-Transfer Get zum Abrufen von Metadaten](https://go.microsoft.com/fwlink/?LinkId=96708)  
  
 Darüber hinaus werden die folgenden Interoperabilitätsprofile in WCF implementiert:  
  
-   [Basic Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=69313)  
  
-   [Einfache SOAP-Bindung von 1.0](https://go.microsoft.com/fwlink/?LinkId=96710)  
  
-   [Basic Security Profile 1.0 arbeiten Entwurf](https://go.microsoft.com/fwlink/?LinkId=96711)  
  
## <a name="see-also"></a>Siehe auch  
 [Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
 [Messagingprotokolle](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)  
 [Datenvertrags-Schemareferenz](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)  
 [WSDL und Richtlinie](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)  
 [Sicherheitsprotokolle](../../../../docs/framework/wcf/feature-details/security-protocols.md)  
 [Protokoll für zuverlässiges Messaging, Version 1.0](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-0.md)  
 [Protokoll für zuverlässiges Messaging, Version 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)  
 [Transaktionsprotokolle](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)  
 [Kontextaustauschprotokoll](../../../../docs/framework/wcf/feature-details/context-exchange-protocol.md)
