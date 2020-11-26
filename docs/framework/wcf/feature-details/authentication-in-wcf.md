---
title: Authentifizierung in WCF
description: Erfahren Sie mehr über verschiedene Mechanismen in WCF, die Authentifizierung bereitstellen, z. b. die Windows-Authentifizierung, X. 509-Zertifikate sowie Benutzername und Kennwort.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: e2334a8c024238f38e1c927a278a4e25e7dabd9d
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247537"
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
- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))
