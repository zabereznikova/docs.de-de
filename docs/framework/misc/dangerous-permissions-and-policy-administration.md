---
title: "Dangerous Permissions and Policy Administration | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "permissions [.NET Framework], policy administration"
  - "security [.NET Framework], dangerous permissions"
  - "code security, dangerous permissions"
  - "secure coding, dangerous permissions"
  - "permissions [.NET Framework], dangerous"
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
caps.latest.revision: 11
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 11
---
# Dangerous Permissions and Policy Administration
Verschiedene der geschützten Operationen, für die von .NET Framework Berechtigungen bereitgestellt werden, ermöglichen unter Umständen die Umgehung des Sicherheitssystems. Diese problematischen Berechtigungen sollten nur bei Bedarf für vertrauenswürdigen Code erteilt werden. Es gibt in der Regel keinen Schutz vor bösartigem Code, wenn dem Code diese Berechtigungen gewährt werden.  
  
> [!NOTE]
>  In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] wurden wichtige Änderungen am Sicherheitsmodell und an der Terminologie von .NET Framework vorgenommen. Weitere Informationen zu diesen Änderungen finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).  
  
 Die problematischen Berechtigungen werden in der folgenden Tabelle erläutert.  
  
|Berechtigung|Mögliches Risiko|  
|------------------|----------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Ermöglicht es verwaltetem Code, Aufrufe in nicht verwaltetem Code auszuführen. Dies stellt häufig ein Risiko dar.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Ohne eine Überprüfung kann der Code beliebige Aktionen ausführen.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Als ungültig erklärte Beweise können die Sicherheitsrichtlinien umgehen.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Durch die Möglichkeit der Änderung von Sicherheitsrichtlinien kann die Sicherheit deaktiviert werden.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Durch die Serialisierung können Zugriffsmechanismen umgangen werden. Weitere Informationen finden Sie unter [Sicherheit und Serialisierung](../../../docs/framework/misc/security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Durch die Fähigkeit zum Festlegen des aktuellen Prinzipals kann die rollenbasierte Sicherheit umgangen werden.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag>|Die Änderung von Threads ist aufgrund des mit Threads verbundenen Sicherheitszustands riskant.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Kann private Member zur Überwindung von Zugriffsmechanismen verwenden.|  
  
## Siehe auch  
 [Secure Coding Guidelines](../../../docs/standard/security/secure-coding-guidelines.md)