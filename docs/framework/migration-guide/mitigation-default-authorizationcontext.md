---
title: "Entschärfung: Standardmäßiger AuthorizationContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6cfeee63-b148-429a-a7e6-6fe9b0cb7610
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 48363d0f8e515b703e49761a763379566e217844
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-default-authorizationcontext"></a>Entschärfung: Standardmäßiger AuthorizationContext
In der Implementierung von <xref:System.IdentityModel.Policy.AuthorizationContext>, der durch den Aufruf von <xref:System.IdentityModel.Policy.AuthorizationContext.CreateDefaultAuthorizationContext%28System.Collections.Generic.IList%7BSystem.IdentityModel.Policy.IAuthorizationPolicy%7D%29> mit einem `null``authorizationPolicies`-Argument zurückgegeben wird, wurde die entsprechende Implementierung in [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] geändert.  
  
## <a name="impact"></a>Auswirkungen  
 In seltenen Fällen liegen bei WCF-Apps, die die benutzerdefinierte Authentifizierung verwenden, möglicherweise Verhaltensunterschiede vor.  
  
## <a name="mitigation"></a>Problemumgehung  
 Sie können das vorherige Verhalten auf zwei verschiedene Art und Weisen wiederherstellen:  
  
-   Kompilieren Sie Ihre App erneut, damit sie auf eine frühere Version als .NET Framework 4.6 abzielt. Verwenden Sie für mithilfe von IIS gehosteten Diensten das `<httpRuntime targetFramework="x.x" />`-Element, um auf eine frühere Version von .NET Framework abzuzielen.  
  
-   Fügen Sie dem Abschnitt `<appSettings>` Ihrer Datei „app.config“ die folgende Zeile hinzu:  
  
    ```xml  
    <add key="appContext.SetSwitch:Switch.System.IdentityModel.EnableCachedEmptyDefaultAuthorizationContext" value="true" />  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

