---
title: Überlegungen zur Sicherheit in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
ms.openlocfilehash: 796098258601ec5fa208fd8a8060b28c3eeeb4d6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96276021"
---
# <a name="security-considerations-in-wcf"></a>Überlegungen zur Sicherheit in WCF

In den Themen in diesem Abschnitt werden verschiedene sicherheitsrelevante Aspekte aufgeführt, die beim Entwerfen einer Windows Communication Foundation (WCF)-Anwendung zu beachten sind.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Veröffentlichung von Informationen](information-disclosure.md)  
 Erläutert, wie Informationen offengelegt und attackiert werden können und wie man diesen Gefahren begegnen kann.  
  
 [Erhöhung von Rechten](elevation-of-privilege.md)  
 Erläutert die Konsequenzen, mit denen zu rechnen ist, wenn einem Angreifer Autorisierungsberechtigungen erteilt werden, die über die ursprünglichen Berechtigungen hinausgehen, und stellt mögliche Gegenmaßnahmen vor.  
  
 [Denial-of-Service](denial-of-service.md)  
 Erläutert, was geschieht, wenn ein System Nachrichten nicht angemessen verarbeiten kann, und stellt mögliche Gegenmaßnahmen vor.  
  
 [Manipulation](tampering.md)  
 Erläutert die Manipulation von Nachrichten bzw. des Sendens von Nachrichten und stellt mögliche Gegenmaßnahmen vor.  
  
 [Wiederholungsangriffe](replay-attacks.md)  
 Erläutert, was geschieht, wenn ein Angreifer einen Nachrichtenstrom zwischen zwei Parteien kopiert und den Strom für eine oder mehrere Parteien wiedergibt, und stellt mögliche Gegenmaßnahmen vor.  
  
 [Sicherheitsüberlegungen für Sicherheitssitzungen](security-considerations-for-secure-sessions.md)  
 Erläutert die folgenden Punkte, die sich bei der Implementierung von Sicherheitssitzungen auf die Sicherheit auswirken.  
  
 [Nicht unterstützte Szenarien](unsupported-scenarios.md)  
 Führt verschiedene Szenarien auf, die einen bestimmten Sicherheitsaspekt nicht unterstützen und vermieden bzw. mit bestimmten Überlegungen angegangen werden sollten.  
  
## <a name="reference"></a>Referenz  

 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  

 [Sicherheitsleitfaden und empfohlene Vorgehensweisen](security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>Siehe auch

- [Security](security.md)
