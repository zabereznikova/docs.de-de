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
ms.openlocfilehash: 15d28ff7d11b5d15ce44d9ab1f56548256850ff8
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645759"
---
# <a name="dangerous-permissions-and-policy-administration"></a>Problematische Berechtigungen und Richtlinienverwaltung
Verschiedene der geschützten Operationen, für die von .NET Framework Berechtigungen bereitgestellt werden, ermöglichen unter Umständen die Umgehung des Sicherheitssystems. Diese problematischen Berechtigungen sollten nur bei Bedarf für vertrauenswürdigen Code erteilt werden. Es gibt in der Regel keinen Schutz vor bösartigem Code, wenn dem Code diese Berechtigungen gewährt werden.  
  
> [!NOTE]
> In .NET Framework 4 wurden wichtige Änderungen am .NET Framework-Sicherheitsmodell und der Terminologie vorgenommen. Weitere Informationen zu diesen Änderungen finden Sie unter [Sicherheitsänderungen](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).  
  
 Die problematischen Berechtigungen werden in der folgenden Tabelle erläutert.  
  
|Berechtigung|Mögliches Risiko|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Ermöglicht es verwaltetem Code, Aufrufe in nicht verwaltetem Code auszuführen. Dies stellt häufig ein Risiko dar.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Ohne eine Überprüfung kann der Code beliebige Aktionen ausführen.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|Als ungültig erklärte Beweise können die Sicherheitsrichtlinien umgehen.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|Durch die Möglichkeit der Änderung von Sicherheitsrichtlinien kann die Sicherheit deaktiviert werden.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|Durch die Serialisierung können Zugriffsmechanismen umgangen werden. Weitere Informationen finden Sie unter [Sicherheit und Serialisierung](security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|Durch die Fähigkeit zum Festlegen des aktuellen Prinzipals kann die rollenbasierte Sicherheit umgangen werden.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|Die Änderung von Threads ist aufgrund des mit Threads verbundenen Sicherheitszustands riskant.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Kann private Member zur Überwindung von Zugriffsmechanismen verwenden.|  
  
## <a name="see-also"></a>Siehe auch

- [Richtlinien für das Schreiben von sicherem Code](../../standard/security/secure-coding-guidelines.md)
