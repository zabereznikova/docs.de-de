---
title: "Minderung: Standardm&#228;&#223;iger AuthorizationContext | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 3
---
# Minderung: Standardm&#228;&#223;iger AuthorizationContext
Die Implementierung von <xref:System.IdentityModel.Policy.AuthorizationContext>, was durch den Aufruf von <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> mit einem Argument für `null` `authorizationPolicies` zurückgegeben wird, hat die entsprechende Implementierung in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] geändert.  
  
## Auswirkungen  
 In seltenen Fällen liegen bei WCF\-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor.  
  
## Problemumgehung  
 Sie können das vorherige Verhalten auf zwei verschiedene Art und Weisen wiederherstellen:  
  
-   Kompilieren Sie Ihre App erneut, damit sie auf eine frühere Version als .NET Framework 4.6 abzielt.  Verwenden Sie für mithilfe von IIS gehosteten Diensten das `<httpRuntime targetFramework="x.x" />`\-Element, um auf eine frühere Version von .NET Framework abzuzielen.  
  
-   Fügen Sie dem Abschnitt `<appSettings>` Ihrer Datei „app.config“ die folgende Zeile hinzu:  
  
    ```  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)