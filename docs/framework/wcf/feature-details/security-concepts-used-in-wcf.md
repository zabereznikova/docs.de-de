---
title: In WCF verwendete Sicherheitsbegriffe
ms.date: 03/30/2017
ms.assetid: 3b9dfcf5-4bf1-4f35-9070-723171c823a1
ms.openlocfilehash: 3ef2b9c104fa15de17a769c9ca9354e5cef085bf
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295548"
---
# <a name="security-concepts-used-in-wcf"></a>In WCF verwendete Sicherheitsbegriffe
Windows Communication Foundation (WCF)-Sicherheit wird baut auf Begriffen bereits und in diversen Sicherheitsinfrastrukturen bereitgestellt.  
  
 WCF unterstützt einige jener Infrastrukturen, z. B. Secure Sockets Layer (SSL) über HTTP (HTTPS). Hingegen wird über SOAP-codierten Nachrichten WCF vorhandene Sicherheitsinfrastrukturen zu unterstützen, durch die Implementierung der neuere interoperable Sicherheitsstandards (z. B. WS-Security) ein. Die zugrunde liegenden Sicherheitskonzepte sind identisch, unabhängig davon, ob Sie bestehende Mechanismen verwenden oder neue interoperable Standards. Das Verständnis der Konzepte, auf denen die bestehenden Infrastrukturen und neueren Standards beruhen, ist entscheidend für die Implementierung des besten Sicherheitsmodells für eine Anwendung.  
  
## <a name="introduction-to-security-for-wcf-web-services"></a>Einführung in die Sicherheit für WCF Web Services  
 Der Microsoft Patterns and Practices-Gruppe habe eine detaillierte Whitepaper auf WCF-Sicherheitsleitfaden handelt es sich hier herunterladen: [WCF-Sicherheitshandbuch](https://go.microsoft.com/fwlink/?LinkId=210210). In diesem Whitepaper werden die grundlegenden Sicherheitskonzepte in Zusammenhang mit Webdiensten, die wichtigsten WCF-Sicherheitskonzepte, Szenarien für Intranetanwendungen und Szenarien für Internetanwendungen beschrieben.  
  
## <a name="industry-wide-security-specifications"></a>Branchenweite Sicherheitsspezifikationen  
  
### <a name="public-key-infrastructure"></a>Public Key-Infrastruktur  
 Die Public Key-Infrastruktur (PKI) ist ein System von digitalen Zertifikaten, Zertifizierungsstellen und anderen Registrierungsstellen, von dem jede an einer elektronischen Transaktion beteiligte Partei mittels Verschlüsselung mit öffentlichem Schlüssel überprüft und authentifiziert wird. Weitere Informationen finden Sie unter [Windows Server 2008 R2-Zertifikatdienste](https://go.microsoft.com/fwlink/?LinkId=210211).  
  
### <a name="kerberos-protocol"></a>Kerberos-Protokoll  
 Die *Kerberos-Protokoll* ist eine Spezifikation für das Erstellen eines Sicherheitsmechanismus, der Benutzern in einer Windows-Domäne authentifiziert. Es ermöglicht es einem Benutzer, in einer Domäne einen sicheren Kontext mit anderen Entitäten zu erstellen. Windows 2000-Plattformen und höher verwenden das Kerberos-Protokoll standardmäßig. Das Verständnis der Mechanismen dieses Systems ist bei der Erstellung eines Diensts hilfreich, der mit Intranetclients interagiert. Da die *Web Services Security-Kerberos-Bindung* weit veröffentlicht, können Sie das Kerberos-Protokoll um mit Internetclients zu kommunizieren (d. h. das Kerberos-Protokoll ist interoperabel). Weitere Informationen zur Implementierung des Kerberos-Protokolls in Windows finden Sie unter [Microsoft Kerberos](https://go.microsoft.com/fwlink/?LinkId=210212).  
  
### <a name="x509-certificates"></a>X.509-Zertifikate  
 Bei X.509-Zertifikaten handelt es sich um ein primäres Anmeldeinformationsformular, das in Sicherheitsanwendungen verwendetet wird. Weitere Informationen zu x. 509-Zertifikaten, finden Sie unter [x. 509-Zertifikate mit öffentlichem Schlüssel](https://go.microsoft.com/fwlink/?LinkId=210213). X.509-Zertifikate werden in einem Zertifikatspeicher gespeichert. Ein Computer mit Windows-Betriebssystem verfügt über diverse Zertifikatspeicher, die unterschiedliche Zwecke erfüllen. Weitere Informationen zu den verschiedenen speichern finden Sie unter [Zertifikatspeicher](https://go.microsoft.com/fwlink/?LinkID=87787).  
  
## <a name="web-services-security-specifications"></a>Sicherheitsspezifikationen für Webdienste  
 Die vom System definierten Bindungen unterstützen viele allgemein übliche Sicherheitsspezifikationen für Webdienste. Eine vollständige Liste der vom System bereitgestellten Bindungen und Webdienstspezifikationen support finden Sie unter: [Durch vom System bereitgestellte Interoperabilitätsbindungen unterstützte Webdienstprotokolle](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)  
  
## <a name="access-control-mechanisms"></a>Zugriffssteuerungsmechanismen  
 WCF bietet mehrere Möglichkeiten zum Steuern des Zugriffs auf einen Dienst oder Vorgang. Dazu zählen:  
  
1. <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
2. ASP.NET-Mitgliedschaftsanbieter  
  
3. ASP.NET-Rollenanbieter  
  
4. Autorisierungs-Manager  
  
5. Identitätsmodell  
  
 Weitere Informationen zu diesen Themen finden Sie unter [Mechanismen der Zugriffssteuerung](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
