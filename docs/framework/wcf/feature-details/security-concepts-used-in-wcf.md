---
title: In WCF verwendete Sicherheitsbegriffe
ms.date: 03/30/2017
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
ms.openlocfilehash: ce6dc6f5cb8680d6228e21206afdc3aa33085e7d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938120"
---
# <a name="security-concepts-used-in-wcf"></a>In WCF verwendete Sicherheitsbegriffe
Windows Communication Foundation (WCF)-Sicherheit basiert auf bereits verwendeten Konzepten und Bereitstellung in verschiedenen Sicherheitsinfrastrukturen.  
  
 WCF unterstützt einige dieser Infrastrukturen, wie z. b. Secure Sockets Layer (SSL) über HTTP (HTTPS). WCF geht aber über die Unterstützung vorhandener Sicherheitsinfrastrukturen hinaus, indem neuere, interoperable Sicherheitsstandards (z. b. WS-Sicherheit) über SOAP-codierte Nachrichten implementiert werden. Die zugrunde liegenden Sicherheitskonzepte sind identisch, unabhängig davon, ob Sie bestehende Mechanismen verwenden oder neue interoperable Standards. Das Verständnis der Konzepte, auf denen die bestehenden Infrastrukturen und neueren Standards beruhen, ist entscheidend für die Implementierung des besten Sicherheitsmodells für eine Anwendung.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Einführung in die Sicherheit für WCF Web Services  
 Die Microsoft Patterns and Practices-Gruppe hat ein ausführliches Whitepaper zu WCF-Sicherheits Anleitungen verfasst, das Sie hier herunterladen können: [WCF-Sicherheitshandbuch](https://go.microsoft.com/fwlink/?LinkId=210210). Dieses Whitepaper beschreibt die grundlegenden Sicherheitskonzepte im Zusammenhang mit Webdiensten, Key WCF-Sicherheitskonzepte, Szenarien für Intranetanwendungen und Internet Anwendungsszenarien.  
  
## <a name="industry-wide-security-specifications"></a>Branchenweite Sicherheitsspezifikationen  
  
### <a name="public-key-infrastructure"></a>Public Key-Infrastruktur  
 Die Public Key-Infrastruktur (PKI) ist ein System von digitalen Zertifikaten, Zertifizierungsstellen und anderen Registrierungsstellen, von dem jede an einer elektronischen Transaktion beteiligte Partei mittels Verschlüsselung mit öffentlichem Schlüssel überprüft und authentifiziert wird. Weitere Informationen finden Sie unter [Windows Server 2008 R2-Zertifikat Dienste](https://go.microsoft.com/fwlink/?LinkId=210211).  
  
### <a name="kerberos-protocol"></a>Kerberos-Protokoll  
 Das *Kerberos-Protokoll* ist eine Spezifikation zum Erstellen eines Sicherheitsmechanismus, mit dem Benutzer in einer Windows-Domäne authentifiziert werden. Es ermöglicht es einem Benutzer, in einer Domäne einen sicheren Kontext mit anderen Entitäten zu erstellen. Windows 2000-Plattformen und höher verwenden das Kerberos-Protokoll standardmäßig. Das Verständnis der Mechanismen dieses Systems ist bei der Erstellung eines Diensts hilfreich, der mit Intranetclients interagiert. Außerdem können Sie das Kerberos-Protokoll verwenden, um mit Internet Clients zu kommunizieren (d. h. das Kerberos-Protokoll ist interoperabel), da die *Webdienstesicherheit Kerberos-Bindung* weit verbreitet ist. Weitere Informationen zur Implementierung des Kerberos-Protokolls in Windows finden Sie unter [Microsoft Kerberos](https://go.microsoft.com/fwlink/?LinkId=210212).  
  
### <a name="x509-certificates"></a>X.509-Zertifikate  
 Bei X.509-Zertifikaten handelt es sich um ein primäres Anmeldeinformationsformular, das in Sicherheitsanwendungen verwendetet wird. Weitere Informationen zu x. 509-Zertifikaten finden Sie unter [Zertifikate für öffentliche x. 509-Schlüssel](https://go.microsoft.com/fwlink/?LinkId=210213). X.509-Zertifikate werden in einem Zertifikatspeicher gespeichert. Ein Computer mit Windows-Betriebssystem verfügt über diverse Zertifikatspeicher, die unterschiedliche Zwecke erfüllen. Weitere Informationen zu den unterschiedlichen speichern finden Sie unter [Zertifikat Speicher](https://go.microsoft.com/fwlink/?LinkID=87787).  
  
## <a name="web-services-security-specifications"></a>Sicherheitsspezifikationen für Webdienste  
 Die vom System definierten Bindungen unterstützen viele allgemein übliche Sicherheitsspezifikationen für Webdienste. Eine umfassende Liste der vom System bereitgestellten Bindungen und der von Ihnen unterstützten Webdienst Spezifikationen finden Sie unter: [Webdienst Protokolle, die von vom System bereitgestellten Interoperabilitäts Bindungen unterstützt](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## <a name="access-control-mechanisms"></a>Zugriffssteuerungsmechanismen  
 WCF bietet mehrere Möglichkeiten zum Steuern des Zugriffs auf einen Dienst oder Vorgang. Dazu zählen:  
  
1. <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2. ASP.NET-Mitgliedschaftsanbieter  
  
3. ASP.NET-Rollenanbieter  
  
4. Autorisierungs-Manager  
  
5. Identitätsmodell  
  
 Weitere Informationen zu diesen Themen finden Sie unter [Access Control Mechanismen](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Sicherheitsmodell für Windows Server-App-Fabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
