---
title: "Entschärfung: ClaimsIdentity-Konstruktor"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 946903f1-0fbf-4f67-805b-1eb48352024d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a50cbd69aa1f2c72adc9fc4d10a070f5faa0cf54
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-claimsidentity-constructor"></a>Entschärfung: ClaimsIdentity-Konstruktor
Beginnend mit [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] gibt es eine Änderung in der Weise, wie der <xref:System.Security.Claims.ClaimsIdentity.%23ctor%28System.Security.Principal.IIdentity%29?displayProperty=fullName>-Konstruktor die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>-Eigenschaft festlegt. Wenn es sich bei dem <xref:System.Security.Principal.IIdentity>-Argument um ein <xref:System.Security.Claims.ClaimsIdentity>-Objekt handelt und die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>-Eigenschaft des <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht `null` ist, wird die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>-Eigenschaft mithilfe der <xref:System.Security.Claims.ClaimsIdentity.Clone%2A?displayProperty=fullName>-Methode angefügt. In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] wird die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A>-Eigenschaft als vorhandener Verweis angefügt.  
  
## <a name="impact"></a>Auswirkungen  
 Beginnend mit [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] ist die <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>-Eigenschaft des neuen <xref:System.Security.Claims.ClaimsIdentity>-Objekts nicht gleich der <xref:System.Security.Claims.ClaimsIdentity.Actor%2A?displayProperty=fullName>-Eigenschaft des <xref:System.Security.Principal.IIdentity>-Arguments des Konstruktors. In [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] und früheren Versionen ist sie gleich.  
  
## <a name="mitigation"></a>Problemumgehung  
 Wenn dieses Verhalten nicht erwünscht ist, können Sie das vorherige Verhalten wiederherstellen, indem Sie den `Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity`-Schalter in Ihrer Anwendungskonfigurationsdatei auf `true` festlegen. Dazu müssen Sie dem Abschnitt [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) Ihrer web.config-Datei Folgendes hinzufügen:  
  
```xml  
<configuration>  
   <runtime>  
      <AppContextSwitchOverrides value="Switch.System.Security.ClaimsIdentity.SetActorAsReferenceWhenCopyingClaimsIdentity=true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Neuausrichtungsänderungen](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

