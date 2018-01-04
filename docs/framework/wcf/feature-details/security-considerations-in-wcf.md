---
title: "Überlegungen zur Sicherheit in WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF]
- Windows Communication Foundation, security
- WCF, security
ms.assetid: 42055ee0-6d0c-443d-9d89-788dfc345d6d
caps.latest.revision: "49"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: f35bd56bdc69f8c57a7e46984778051b57b7a06a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-considerations-in-wcf"></a>Überlegungen zur Sicherheit in WCF
Die Themen in diesem Abschnitt verweisen auf verschiedene sicherheitsrelevante Punkte, die beim Entwurf einer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Anwendung in Betracht gezogen werden sollten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Offenlegung vertraulicher Informationen](../../../../docs/framework/wcf/feature-details/information-disclosure.md)  
 Erläutert, wie Informationen offengelegt und attackiert werden können und wie man diesen Gefahren begegnen kann.  
  
 [Erhöhen der Berechtigungen](../../../../docs/framework/wcf/feature-details/elevation-of-privilege.md)  
 Erläutert die Konsequenzen, mit denen zu rechnen ist, wenn einem Angreifer Autorisierungsberechtigungen erteilt werden, die über die ursprünglichen Berechtigungen hinausgehen, und stellt mögliche Gegenmaßnahmen vor.  
  
 [Denial-of-Service-Angriffe](../../../../docs/framework/wcf/feature-details/denial-of-service.md)  
 Erläutert, was geschieht, wenn ein System Nachrichten nicht angemessen verarbeiten kann, und stellt mögliche Gegenmaßnahmen vor.  
  
 [Manipulation](../../../../docs/framework/wcf/feature-details/tampering.md)  
 Erläutert die Manipulation von Nachrichten bzw. des Sendens von Nachrichten und stellt mögliche Gegenmaßnahmen vor.  
  
 [Replayangriffe](../../../../docs/framework/wcf/feature-details/replay-attacks.md)  
 Erläutert, was geschieht, wenn ein Angreifer einen Nachrichtenstrom zwischen zwei Parteien kopiert und den Strom für eine oder mehrere Parteien wiedergibt, und stellt mögliche Gegenmaßnahmen vor.  
  
 [Sicherheitsüberlegungen für sichere Sitzungen](../../../../docs/framework/wcf/feature-details/security-considerations-for-secure-sessions.md)  
 Erläutert die folgenden Punkte, die sich bei der Implementierung von Sicherheitssitzungen auf die Sicherheit auswirken.  
  
 [Nicht unterstützte Szenarien](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)  
 Führt verschiedene Szenarien auf, die einen bestimmten Sicherheitsaspekt nicht unterstützen und vermieden bzw. mit bestimmten Überlegungen angegangen werden sollten.  
  
## <a name="reference"></a>Verweis  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sicherheitsleitfaden und bewährte Methoden](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Sicherheit](../../../../docs/framework/wcf/feature-details/security.md)
