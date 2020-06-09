---
title: Autorisierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: d67d64dcf0003de28775ac947f8b5f72d7c2ba2a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597630"
---
# <a name="authorization-in-wcf"></a>Autorisierung in WCF
Autorisierung ist der Prozess, Zugriff und Rechte für Ressourcen zu steuern, z. B. Dienste oder Dateien. In den Themen in diesem Abschnitt wird erläutert, wie Sie diese grundlegende Aufgabe in Windows Communication Foundation (WCF) auf unterschiedlichste Weise ausführen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Zugriffssteuerungsmechanismen](access-control-mechanisms.md)  
 Bietet eine kurze Übersicht über die Autorisierungs Mechanismen in WCF und empfohlene Verwendungsmöglichkeiten.  
  
 [Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 Zeigt den Prozess zum Zugriff auf einen Dienst mit dem <xref:System.Security.Permissions.PrincipalPermissionAttribute> an.  
  
 [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 Führt Sie durch die Konfiguration eines Dienstanbieters, um die Verwendung der Rollen Anbieter Funktion von ASP.net zu ermöglichen.  
  
 [Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 ASP.net kann den Autorisierungs-Manager verwenden, um die Autorisierung für eine Website zu verwalten. WCF kann die Kombination von ASP.net/Authorization Manager auch für die Autorisierung von Clients nutzen.  
  
 [Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell](managing-claims-and-authorization-with-the-identity-model.md)  
 Erläutert die Grundlagen des Verwendens der Identitätsmodellinfrastruktur für auf Ansprüche basierende Autorisierung.  
  
 [Delegierung und Identitätswechsel](delegation-and-impersonation-with-wcf.md)  
 Erläutert den Unterschied zwischen Delegierung und Identitätswechsel.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Authentifizierung](authentication-in-wcf.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsübersicht](security-overview.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
