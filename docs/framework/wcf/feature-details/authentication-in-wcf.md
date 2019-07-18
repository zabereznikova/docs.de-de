---
title: Authentifizierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: ebff66e185bdca75a0150b22a16392bfd08892d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61595958"
---
# <a name="authentication-in-wcf"></a>Authentifizierung in WCF
Die folgenden Themen zeigen eine Reihe von verschiedenen Mechanismen in Windows Communication Foundation (WCF), die Authentifizierung, z. B. bereitstellen, Windows-Authentifizierung, x. 509-Zertifikate und Benutzernamen und Kennwörter.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 Zu den ASP.NET-Funktionen gehören eine Mitgliedschaft und ein Rollenanbieter, eine Datenbank, um Benutzernamen/Kennwort-Paare für die Authentifizierung zu speichern, sowie Benutzerrollen zur Autorisierung. In diesem Thema wird erläutert, wie WCF-Dienste verwenden können die gleiche Datenbank zu authentifizieren und Autorisieren von Benutzern.  
  
 [Vorgehensweise: Verwenden Sie einen benutzerdefinierten Benutzernamen und das Kennwort-Validierungssteuerelement](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 Veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement integriert wird.  
  
 [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 Als zusätzliche Schutzvorrichtung, kann ein Client den Dienst authentifizieren, durch die Angabe der erwarteten *Identität* des Diensts. Wenn die erwartete Identität und die vom Dienst zurückgegebene Identität nicht übereinstimmen, schlägt die Authentifizierung fehl.  
  
 [Sicherheitsaushandlung und Timeouts](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 Beschreibt die Verwendung der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft in der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>-Klasse.  
  
 [Debuggen von Windows-Authentifizierungsfehlern](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 Der Fokus liegt auf allgemeinen Problemen, die bei der Verwendung der Windows-Authentifizierung auftreten.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Häufige Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
