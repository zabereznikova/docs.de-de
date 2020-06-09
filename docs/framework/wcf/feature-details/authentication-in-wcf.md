---
title: Authentifizierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: b513c9713bd2c04e125915d1a0a87c86ce249666
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597643"
---
# <a name="authentication-in-wcf"></a>Authentifizierung in WCF
In den folgenden Themen werden verschiedene Mechanismen in Windows Communication Foundation (WCF) gezeigt, die die Authentifizierung bereitstellen, z. b. die Windows-Authentifizierung, X. 509-Zertifikate sowie Benutzername und Kenn Wörter.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters](how-to-use-the-aspnet-membership-provider.md)  
 Zu den ASP.NET-Funktionen gehören eine Mitgliedschaft und ein Rollenanbieter, eine Datenbank, um Benutzernamen/Kennwort-Paare für die Authentifizierung zu speichern, sowie Benutzerrollen zur Autorisierung. In diesem Thema wird erläutert, wie WCF-Dienste dieselbe Datenbank verwenden können, um Benutzer zu authentifizieren und zu autorisieren.  
  
 [Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements](how-to-use-a-custom-user-name-and-password-validator.md)  
 Veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement integriert wird.  
  
 [Dienstidentität und Authentifizierung](service-identity-and-authentication.md)  
 Als zusätzliche Schutzmaßnahme kann ein Client den Dienst authentifizieren, indem er die erwartete *Identität* des Dienstanbieter angibt. Wenn die erwartete Identität und die vom Dienst zurückgegebene Identität nicht übereinstimmen, schlägt die Authentifizierung fehl.  
  
 [Sicherheitsaushandlung und Timeouts](security-negotiation-and-timeouts.md)  
 Beschreibt die Verwendung der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft in der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>-Klasse.  
  
 [Debuggen von Windows-Authentifizierungsfehlern](debugging-windows-authentication-errors.md)  
 Der Fokus liegt auf allgemeinen Problemen, die bei der Verwendung der Windows-Authentifizierung auftreten.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Häufige Sicherheitsszenarien](common-security-scenarios.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsübersicht](security-overview.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
