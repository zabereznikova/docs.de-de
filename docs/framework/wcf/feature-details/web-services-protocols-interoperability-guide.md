---
title: Interoperabilitäts Handbuch für Webdienst Protokolle
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 1b949880b3ebbaf121b79a958d17cf5708affcf3
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636145"
---
# <a name="web-services-protocols-interoperability-guide"></a>Interoperabilitäts Handbuch für Webdienst Protokolle

Windows Communication Foundation (WCF) implementiert eine Reihe von Webdienst Protokollen. Viele dieser Protokolle verfügen über eine Reihe von Optionen und Erweiterungspunkten, deren Konfiguration im Ermessen der Implementierung liegt. Dieses Thema enthält eine Liste der Webdienst Protokolle, die von WCF implementiert werden. In den weiteren Themen dieses Abschnitts finden Sie ausführlichere Informationen zur Implementierung der einzelnen unterstützten Protokolle.

## <a name="web-services-protocols-implemented-by-wcf"></a>Von WCF implementierte Webdienst Protokolle

WCF bietet Unterstützung für die Infrastruktur Protokolle von Webdiensten (WS) über Kanäle und Webdienst-Anwendungsprotokolle über das Vertrags Feature. Die Interoperabilität von Anwendungsprotokollen wird mithilfe von XML Schema Description Language 1.0 (XSD) und Web Services Description Language (WSDL) 1.1 erzielt.

Die Interoperabilität von Infrastrukturprotokollen wird mittels der WS-*-Spezifikationen bereitgestellt. WCF-Kanäle bieten Unterstützung für eine Reihe von WS-\*-Infrastruktur Protokollen. WCF-Kanäle werden mithilfe von Bindungs Elementen konfiguriert. Die folgenden Tabellen enthalten die vollständige Liste der WS-\*-Infrastruktur Protokolle, die von verschiedenen WCF-Bindungs Elementen implementiert werden.

<xref:System.ServiceModel.Channels.HttpTransportBindingElement> unterstützt die in der folgenden Tabelle aufgeführten Spezifikationen:

|Spezifikation/Dokument|Link|
|-----------------------------|----------|
|HTTP 1.1|[RFC 2616](https://www.rfc-editor.org/rfc/rfc2616.txt)|
|SOAP 1.1 HTTP-Bindung|[Simple Object Access Protocol (SOAP) 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), Abschnitt 7|
|SOAP 1,2 HTTP-Bindung|[SOAP-Version 1,2 Teil 2: Adjuncts (Second Edition)](https://www.w3.org/TR/soap12-part2/), Abschnitt 7|

<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> unterstützen die in der folgenden Tabelle aufgeführten Spezifikationen:

|Spezifikation/Dokument|Link|
|-----------------------------|----------|
|XML|[Extensible Markup Language (XML) 1,0 (vierte Ausgabe)](https://www.w3.org/TR/REC-xml/)|
|SOAP 1,1|[Simple Object Access Protocol (SOAP) 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)|
|SOAP 1.2 Core|[SOAP, Version 1,2, Teil 1: Messaging Framework (zweite Ausgabe)](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)|
|WS-Adressierung 2004/08|[Webdienst Adressierung (WS-Adressierung)](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)|
|W3C Web Services Addressing 1.0 - Core|[Webdienste Adressierung 1,0-Core](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509/)|
|W3C Web Services Addressing 1.0 - SOAP-Bindung|[Webdienst Adressierung 1,0-SOAP-Bindung](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509/)|
|W3C Web Services Addressing 1.0 - WSDL-Bindung*|[Webdienst Adressierung 1,0-WSDL-Bindung](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)|
|W3C Web Services Addressing 1.0 – Metadaten|[Webdienst Adressierung 1,0-Metadaten](https://www.w3.org/TR/ws-addr-metadata/)|
|WSDL SOAP1.1-Bindung|[Web Services Description Language (WSDL) 1,1](https://www.w3.org/TR/wsdl/)|
|WSDL SOAP1.2-Bindung|[WSDL 1,1-Bindungs Erweiterung für SOAP 1,2](https://www.w3.org/Submission/wsdl11soap12/)|

<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> unterstützt die in der folgenden Tabelle aufgeführten Spezifikationen:

|Spezifikation/Dokument|Link|
|-----------------------------|----------|
|XOP|[XML-Binär optimierte Paket Erstellung](https://www.w3.org/TR/xop10/)|
|MTOM + SOAP1.2-Bindung|[SOAP-Nachrichten Übertragungs Optimierungs Mechanismus](https://www.w3.org/TR/soap12-mtom/)|
|MTOM SOAP 1.1-Bindung|[SOAP 1,1-Bindung für MTOM 1,0](https://www.w3.org/Submission/soap11mtom10/)|
|MTOM WS-Richtlinienassertionen|[MTOM-serialisierungsrichtlinienassertion (WS-MTOMPolicy)](https://www.w3.org/Submission/WS-MTOMPolicy/)|

<xref:System.ServiceModel.Channels.SecurityBindingElement> unterstützt die in der folgenden Tabelle aufgeführten Spezifikationen:

|Spezifikation/Dokument|Link|
|-----------------------------|----------|
|WSS: SOAP-Nachrichtensicherheit 1,0|[Webdienstesicherheit: SOAP-Nachrichten Sicherheit 1,0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)|
|WSS: Username Token Profile 1.0|[Webdienstesicherheit UsernameToken-Profil 1,0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> Password/@Type= PasswordText erforderlich (Standard)|
|WSS: X.509 Token Profile 1.0|[Webdienstesicherheit X. 509-zertifikattokenprofil](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)|
|WSS: SAML 1.1 Token Profile 1,0|[Webdienstesicherheit: SAML-Tokenprofil](https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf)|
|WSS: SOAP-Nachrichtensicherheit 1.1|[Webdienstesicherheit: SOAP-Nachrichten Sicherheit 1,1](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf)|
|WSS: Username Token Profile 1.1|[Webdienstesicherheit UsernameToken-Profil 1,1](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> Implementieren Sie keine kennwortbasierte Schlüsselableitung;<br /><br /> Password/@Type= PasswordText erforderlich (Standard)|
|WSS: X509 Token Profile 1.1|[Webdienstesicherheit X. 509-zertifikattokenprofil 1,1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)|
|WSS: Kerberos Token Profile 1.1|[Webdienstesicherheit Kerberos-Tokenprofil 1,1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)|
|WSS: SAML 1.1 Token Profile 1.1|[Webdienstesicherheit SAML-Tokenprofil 1,1](https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf)|
|WS-Secure Conversation|[Webdienste, sichere Konversation Sprache](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)|
|WS-Trust 1.4 (möglicherweise in englischer Sprache)|[Webdienst-Vertrauensstellungs Sprache](https://docs.oasis-open.org/ws-sx/ws-trust/200802)|
|WS-SecurityPolicy 2005/07|[Webdienste, sichere Konversation Sprache](https://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> Wurde gemäß den an das OASIS WS-SX Technical Committee übermittelten Fehlerberichten geändert.<br /><br /> [WS-SX-Nachricht](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html)|
|WS-ReliableMessaging 1.1|[Protokoll für zuverlässiges Messaging, Version 1.1](reliable-messaging-protocol-version-1-1.md)|

<xref:System.ServiceModel.Channels.TransactionFlowBindingElement> unterstützt die in der folgenden Tabelle aufgeführten Spezifikationen:

|Spezifikation/Dokument|Link|
|-----------------------------|----------|
|WS-Coordination|[Koordination von Webdiensten](https://docs.microsoft.com/previous-versions/ms951231(v=msdn.10))|
|WS-AtomicTransaction|[Atomarische Webdienst Transaktion](https://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)|

Die Klassen <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WsdlExporter>, <xref:System.ServiceModel.Description.WsdlImporter> und <xref:System.ServiceModel.Description.MetadataResolver> bieten Unterstützung für die folgenden Metadatenspezifikationen:

- [XML-Schema Teil 1: Strukturen zweite Ausgabe](https://www.w3.org/TR/xmlschema-1/)

- [XML-Schema Teil 2: Datentypen Second Edition](https://www.w3.org/TR/xmlschema-2/)

- [WSDL 1,1](https://www.w3.org/TR/wsdl/)

- [WS-Richtlinie 1,2](https://www.w3.org/Submission/2006/SUBM-WS-Policy-20060425/)

- [WS-Richtlinie 1,5](https://www.w3.org/TR/ws-policy/)

- [WS-PolicyAttachment 1,2](https://www.w3.org/Submission/2006/SUBM-WS-PolicyAttachment-20060425/)

- [WS-MetadataExchange 1,1](https://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)

- [WS-Transfer Get für das Abrufen von Metadaten](https://www.w3.org/Submission/2006/SUBM-WS-Transfer-20060315/)

Außerdem werden die folgenden Interoperabilitäts Profile über WCF implementiert:

- [Basic-Profil 1,1](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html)

- [Einfache SOAP-Bindung 1,0](http://www.ws-i.org/Profiles/SimpleSoapBindingProfile-1.0-2004-08-24.html)

- [Basic Security Profile 1,0 Working Draft](http://www.ws-i.org/Profiles/BasicSecurityProfile-1.0-2006-03-29.html)

## <a name="see-also"></a>Siehe auch

- [Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [Messagingprotokolle](messaging-protocols.md)
- [Datenvertrags-Schemareferenz](data-contract-schema-reference.md)
- [WSDL und Richtlinie](wsdl-and-policy.md)
- [Sicherheitsprotokolle](security-protocols.md)
- [Protokoll für zuverlässiges Messaging, Version 1.0](reliable-messaging-protocol-version-1-0.md)
- [Protokoll für zuverlässiges Messaging, Version 1.1](reliable-messaging-protocol-version-1-1.md)
- [Transaktionsprotokolle](transaction-protocols.md)
- [Kontextaustauschprotokoll](context-exchange-protocol.md)
