---
title: "In WCF verwendete Sicherheitsbegriffe | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
caps.latest.revision: 15
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 15
---
# In WCF verwendete Sicherheitsbegriffe
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Sicherheit baut auf Begriffen auf, die bereits in Gebrauch sind und in diversen Sicherheitsinfrastrukturen eingesetzt werden.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt einige jener Infrastrukturen, z. B. Secure Sockets Layer \(SSL\) über HTTP \(HTTPS\).[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet jedoch nicht nur Unterstützung für bestehende Sicherheitsinfrastrukturen, sondern implementiert auch neuere interoperable Sicherheitsstandards \(wie WS\-Sicherheit\) über SOAP\-codierte Nachrichten.Die zugrunde liegenden Sicherheitskonzepte sind identisch, unabhängig davon, ob Sie bestehende Mechanismen verwenden oder neue interoperable Standards.Das Verständnis der Konzepte, auf denen die bestehenden Infrastrukturen und neueren Standards beruhen, ist entscheidend für die Implementierung des besten Sicherheitsmodells für eine Anwendung.  
  
## Einführung in die Sicherheit für WCF Web Services  
 Die Microsoft Patterns and Practices\-Gruppe hat ein detailliertes Whitepaper zu WCF\-Sicherheitsempfehlungen geschrieben, das Ihnen unter [WCF\-Sicherheitshandbuch](http://go.microsoft.com/fwlink/?LinkId=210210) zum Download zur Verfügung steht.In diesem Whitepaper werden die grundlegenden Sicherheitskonzepte in Zusammenhang mit Webdiensten, die wichtigsten WCF\-Sicherheitskonzepte, Szenarien für Intranetanwendungen und Szenarien für Internetanwendungen beschrieben.  
  
## Branchenweite Sicherheitsspezifikationen  
  
### Public Key\-Infrastruktur  
 Die Public Key\-Infrastruktur \(PKI\) ist ein System von digitalen Zertifikaten, Zertifizierungsstellen und anderen Registrierungsstellen, von dem jede an einer elektronischen Transaktion beteiligte Partei mittels Verschlüsselung mit öffentlichem Schlüssel überprüft und authentifiziert wird.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] unter [Windows Server 2008 R2\-Zertifikatdienste](http://go.microsoft.com/fwlink/?LinkId=210211).  
  
### Kerberos\-Protokoll  
 Das *Kerberos\-Protokoll* ist eine Spezifikation für das Erstellen eines Sicherheitsmechanismus, durch den Benutzer in einer Windows\-Domäne authentifiziert werden.Es ermöglicht es einem Benutzer, in einer Domäne einen sicheren Kontext mit anderen Entitäten zu erstellen.Windows 2000\-Plattformen und höher verwenden das Kerberos\-Protokoll standardmäßig.Das Verständnis der Mechanismen dieses Systems ist bei der Erstellung eines Diensts hilfreich, der mit Intranetclients interagiert.Da die *Webdienstsicherheit\-Kerberos\-Bindung* weit verbreitet ist, können Sie das Kerberos\-Protokoll verwenden, um mit Internetclients zu kommunizieren \(d. h. das Kerberos\-Protokoll ist interoperabel\).[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zur Implementierung des Kerberos\-Protokolls in Windows findenSie unter [Microsoft Kerberos](http://go.microsoft.com/fwlink/?LinkId=210212).  
  
### X.509\-Zertifikate  
 Bei X.509\-Zertifikaten handelt es sich um ein primäres Anmeldeinformationsformular, das in Sicherheitsanwendungen verwendetet wird.Weitere Informationen zu X.509\-Zertifikaten finden Sie unter [X.509\-Zertifikate mit öffentlichem Schlüssel](http://go.microsoft.com/fwlink/?LinkId=210213).X.509\-Zertifikate werden in einem Zertifikatspeicher gespeichert.Ein Computer mit Windows\-Betriebssystem verfügt über diverse Zertifikatspeicher, die unterschiedliche Zwecke erfüllen.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] zu den verschiedenen Speichern finden Sie unter [Zertifikatspeicher](http://go.microsoft.com/fwlink/?LinkID=87787).  
  
## Sicherheitsspezifikationen für Webdienste  
 Die vom System definierten Bindungen unterstützen viele allgemein übliche Sicherheitsspezifikationen für Webdienste.Eine vollständige Liste der vom System definierten Bindungen und unterstützten Webdienstspezifikationen finden Sie unter [Durc vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
## Zugriffssteuerungsmechanismen  
 WCF bietet mehrere Möglichkeiten zum Steuern des Zugriffs auf einen Dienst oder Vorgang.Dazu zählen:  
  
1.  <xref:System.Security.Permissions.PrinciplePermissionAttribute>  
  
2.  ASP.NET\-Mitgliedschaftsanbieter  
  
3.  ASP.NET\-Rollenanbieter  
  
4.  Autorisierungs\-Manager  
  
5.  Identitätsmodell  
  
 Weitere Informationen zu diesen Themen finden Sie unter [Zugriffssteuerungsmechanismen](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md).  
  
## Siehe auch  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)