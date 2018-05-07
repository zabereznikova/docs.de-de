---
title: Problematische Berechtigungen und Richtlinienverwaltung
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b89792f9579da2d72c0a7f90a983308b172093fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dangerous-permissions-and-policy-administration"></a>Problematische Berechtigungen und Richtlinienverwaltung
Verschiedene der geschützten Operationen, für die von .NET Framework Berechtigungen bereitgestellt werden, ermöglichen unter Umständen die Umgehung des Sicherheitssystems. Diese problematischen Berechtigungen sollten nur bei Bedarf für vertrauenswürdigen Code erteilt werden. Es gibt in der Regel keinen Schutz vor bösartigem Code, wenn dem Code diese Berechtigungen gewährt werden.  
  
> [!NOTE]
>  In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]wurden wichtige Änderungen am Sicherheitsmodell und an der Terminologie von .NET Framework vorgenommen. Weitere Informationen zu diesen Änderungen finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).  
  
 Die problematischen Berechtigungen werden in der folgenden Tabelle erläutert.  
  
|Berechtigung|Mögliches Risiko|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Ermöglicht es verwaltetem Code, Aufrufe in nicht verwaltetem Code auszuführen. Dies stellt häufig ein Risiko dar.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Ohne eine Überprüfung kann der Code beliebige Aktionen ausführen.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|Als ungültig erklärte Beweise können die Sicherheitsrichtlinien umgehen.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|Durch die Möglichkeit der Änderung von Sicherheitsrichtlinien kann die Sicherheit deaktiviert werden.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|Durch die Serialisierung können Zugriffsmechanismen umgangen werden. Weitere Informationen finden Sie unter [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|Durch die Fähigkeit zum Festlegen des aktuellen Prinzipals kann die rollenbasierte Sicherheit umgangen werden.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|Die Änderung von Threads ist aufgrund des mit Threads verbundenen Sicherheitszustands riskant.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Kann private Member zur Überwindung von Zugriffsmechanismen verwenden.|  
  
## <a name="see-also"></a>Siehe auch  
 [Richtlinien für das Schreiben von sicherem Code](../../../docs/standard/security/secure-coding-guidelines.md)
