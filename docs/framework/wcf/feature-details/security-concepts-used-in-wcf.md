---
title: In WCF verwendete Sicherheitsbegriffe
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
caps.latest.revision: 15
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 74b16698d40747937a89f84f0d958178b42d2e44
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="security-concepts-used-in-wcf"></a>In WCF verwendete Sicherheitsbegriffe
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Sicherheit baut auf Begriffen auf, die bereits in Gebrauch sind und in diversen Sicherheitsinfrastrukturen eingesetzt werden.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt einige jener Infrastrukturen, z. B. Secure Sockets Layer (SSL) über HTTP (HTTPS). [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] bietet jedoch nicht nur Unterstützung für bestehende Sicherheitsinfrastrukturen, sondern implementiert auch neuere interoperable Sicherheitsstandards (wie WS-Sicherheit) über SOAP-codierte Nachrichten. Die zugrunde liegenden Sicherheitskonzepte sind identisch, unabhängig davon, ob Sie bestehende Mechanismen verwenden oder neue interoperable Standards. Das Verständnis der Konzepte, auf denen die bestehenden Infrastrukturen und neueren Standards beruhen, ist entscheidend für die Implementierung des besten Sicherheitsmodells für eine Anwendung.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Einführung in die Sicherheit für WCF Web Services  
 Die Microsoft Patterns and Practices-Gruppe hat eine ausführliche Whitepaper über WCF-Sicherheitsleitfaden also zum Download zur Verfügung: [WCF-Sicherheitshandbuch](http://go.microsoft.com/fwlink/?LinkId=210210). In diesem Whitepaper werden die grundlegenden Sicherheitskonzepte in Zusammenhang mit Webdiensten, die wichtigsten WCF-Sicherheitskonzepte, Szenarien für Intranetanwendungen und Szenarien für Internetanwendungen beschrieben.  
  
## <a name="industry-wide-security-specifications"></a>Branchenweite Sicherheitsspezifikationen  
  
### <a name="public-key-infrastructure"></a>Public Key-Infrastruktur  
 Die Public Key-Infrastruktur (PKI) ist ein System von digitalen Zertifikaten, Zertifizierungsstellen und anderen Registrierungsstellen, von dem jede an einer elektronischen Transaktion beteiligte Partei mittels Verschlüsselung mit öffentlichem Schlüssel überprüft und authentifiziert wird. Weitere Informationen finden Sie unter [Windows Server 2008 R2-Zertifikatdienste](http://go.microsoft.com/fwlink/?LinkId=210211).  
  
### <a name="kerberos-protocol"></a>Kerberos-Protokoll  
 Die *Kerberos-Protokoll* ist eine Spezifikation für das Erstellen eines Sicherheitsmechanismus, die Benutzer in einer Windows-Domäne authentifiziert. Es ermöglicht es einem Benutzer, in einer Domäne einen sicheren Kontext mit anderen Entitäten zu erstellen. Windows 2000-Plattformen und höher verwenden das Kerberos-Protokoll standardmäßig. Das Verständnis der Mechanismen dieses Systems ist bei der Erstellung eines Diensts hilfreich, der mit Intranetclients interagiert. Da die *Web Services Security-Kerberos-Bindung* weit wird veröffentlicht, können Sie das Kerberos-Protokoll um mit Internetclients zu kommunizieren (d. h. das Kerberos-Protokoll ist interoperabel). Weitere Informationen zur Implementierung des Kerberos-Protokolls in Windows finden Sie unter [Microsoft Kerberos](http://go.microsoft.com/fwlink/?LinkId=210212).  
  
### <a name="x509-certificates"></a>X.509-Zertifikate  
 Bei X.509-Zertifikaten handelt es sich um ein primäres Anmeldeinformationsformular, das in Sicherheitsanwendungen verwendetet wird. Weitere Informationen zum x. 509-Zertifikate, finden Sie unter [x. 509-Zertifikate für öffentliche Schlüssel](http://go.microsoft.com/fwlink/?LinkId=210213). X.509-Zertifikate werden in einem Zertifikatspeicher gespeichert. Ein Computer mit Windows-Betriebssystem verfügt über diverse Zertifikatspeicher, die unterschiedliche Zwecke erfüllen. Weitere Informationen zu den verschiedenen speichern, finden Sie unter [Zertifikatspeichern](http://go.microsoft.com/fwlink/?LinkID=87787).  
  
## <a name="web-services-security-specifications"></a>Sicherheitsspezifikationen für Webdienste  
 Die vom System definierten Bindungen unterstützen viele allgemein übliche Sicherheitsspezifikationen für Webdienste. Eine vollständige Liste der vom System bereitgestellte Bindungen und die Webdienstspezifikationen, die sie unterstützen finden Sie unter: [unterstützte Webdienstprotokolle vom sicherheitsbindungsarten Interoperabilitätsbindungen](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## <a name="access-control-mechanisms"></a>Zugriffssteuerungsmechanismen  
 WCF bietet mehrere Möglichkeiten zum Steuern des Zugriffs auf einen Dienst oder Vorgang. Dazu zählen:  
  
1.  <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2.  ASP.NET-Mitgliedschaftsanbieter  
  
3.  ASP.NET-Rollenanbieter  
  
4.  Autorisierungs-Manager  
  
5.  Identitätsmodell  
  
 Weitere Informationen zu diesen Themen finden Sie unter [Zugriffssteuerungsmechanismen](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Sicherheitsmodell für Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
