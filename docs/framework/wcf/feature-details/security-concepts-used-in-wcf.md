---
title: In WCF verwendete Sicherheitsbegriffe
ms.date: 03/30/2017
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
ms.openlocfilehash: f852ba4e1100103289bc5fd879b19ebd40443b8d
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595179"
---
# <a name="security-concepts-used-in-wcf"></a>In WCF verwendete Sicherheitsbegriffe
Windows Communication Foundation (WCF)-Sicherheit basiert auf bereits verwendeten Konzepten und Bereitstellung in verschiedenen Sicherheitsinfrastrukturen.  
  
 WCF unterstützt einige dieser Infrastrukturen, wie z. b. Secure Sockets Layer (SSL) über HTTP (HTTPS). WCF geht aber über die Unterstützung vorhandener Sicherheitsinfrastrukturen hinaus, indem neuere, interoperable Sicherheitsstandards (z. b. WS-Sicherheit) über SOAP-codierte Nachrichten implementiert werden. Die zugrunde liegenden Sicherheitskonzepte sind identisch, unabhängig davon, ob Sie bestehende Mechanismen verwenden oder neue interoperable Standards. Das Verständnis der Konzepte, auf denen die bestehenden Infrastrukturen und neueren Standards beruhen, ist entscheidend für die Implementierung des besten Sicherheitsmodells für eine Anwendung.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Einführung in die Sicherheit für WCF Web Services  

Die Microsoft Patterns and Practices-Gruppe schrieb ein detailliertes Whitepaper namens [WCF Security Guide](https://archive.codeplex.com/?p=wcfsecurityguide). Dieses Whitepaper beschreibt die grundlegenden Sicherheitskonzepte im Zusammenhang mit Webdiensten, Key WCF-Sicherheitskonzepte, Szenarien für Intranetanwendungen und Internet Anwendungsszenarien.  
  
## <a name="industry-wide-security-specifications"></a>Branchenweite Sicherheitsspezifikationen  
  
### <a name="public-key-infrastructure"></a>Public Key-Infrastruktur  

Die Public Key-Infrastruktur (PKI) ist ein System von digitalen Zertifikaten, Zertifizierungsstellen und anderen Registrierungsstellen, die jede an einer elektronischen Transaktion beteiligte Partei mittels Kryptografie mit öffentlichem Schlüssel überprüfen und authentifizieren.
  
### <a name="kerberos-protocol"></a>Kerberos-Protokoll  
 Das *Kerberos-Protokoll* ist eine Spezifikation zum Erstellen eines Sicherheitsmechanismus, mit dem Benutzer in einer Windows-Domäne authentifiziert werden. Es ermöglicht es einem Benutzer, in einer Domäne einen sicheren Kontext mit anderen Entitäten zu erstellen. Windows 2000-Plattformen und höher verwenden das Kerberos-Protokoll standardmäßig. Das Verständnis der Mechanismen dieses Systems ist bei der Erstellung eines Diensts hilfreich, der mit Intranetclients interagiert. Außerdem können Sie das Kerberos-Protokoll verwenden, um mit Internet Clients zu kommunizieren (d. h. das Kerberos-Protokoll ist interoperabel), da die *Webdienstesicherheit Kerberos-Bindung* weit verbreitet ist. Weitere Informationen zur Implementierung des Kerberos-Protokolls in Windows finden Sie unter [Microsoft Kerberos](/windows/win32/secauthn/microsoft-kerberos).  
  
### <a name="x509-certificates"></a>X.509-Zertifikate  
 Bei X.509-Zertifikaten handelt es sich um ein primäres Anmeldeinformationsformular, das in Sicherheitsanwendungen verwendetet wird. Weitere Informationen zu x. 509-Zertifikaten finden Sie unter [Zertifikate für öffentliche x. 509-Schlüssel](/windows/win32/seccertenroll/about-x-509-public-key-certificates). X.509-Zertifikate werden in einem Zertifikatspeicher gespeichert. Ein Computer mit Windows-Betriebssystem verfügt über diverse Zertifikatspeicher, die unterschiedliche Zwecke erfüllen. Weitere Informationen zu den unterschiedlichen speichern finden Sie unter [Zertifikat Speicher](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc757138(v=ws.10)).  
  
## <a name="web-services-security-specifications"></a>Sicherheitsspezifikationen für Webdienste  
 Die vom System definierten Bindungen unterstützen viele allgemein übliche Sicherheitsspezifikationen für Webdienste. Eine umfassende Liste der vom System bereitgestellten Bindungen und der von Ihnen unterstützten Webdienst Spezifikationen finden Sie unter: [Webdienst Protokolle, die von vom System bereitgestellten Interoperabilitäts Bindungen unterstützt](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## <a name="access-control-mechanisms"></a>Zugriffssteuerungsmechanismen  
 WCF bietet mehrere Möglichkeiten zum Steuern des Zugriffs auf einen Dienst oder Vorgang. Dazu zählen:  
  
1. <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2. ASP.NET-Mitgliedschaftsanbieter  
  
3. ASP.NET-Rollenanbieter  
  
4. Autorisierungs-Manager  
  
5. Identitätsmodell  
  
 Weitere Informationen zu diesen Themen finden Sie unter [Access Control Mechanismen](access-control-mechanisms.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsübersicht](security-overview.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
