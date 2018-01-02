---
title: '&lt;BypassTrustedAppStrongNames&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0343aef083076249325b9577f90964d066867f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltbypasstrustedappstrongnamesgt-element"></a>&lt;BypassTrustedAppStrongNames&gt; Element
Gibt an, ob die Überprüfung von starken Namen für vollständig vertrauenswürdige Assemblys zu umgehen, die in ein voll vertrauenswürdiges geladen werden <xref:System.AppDomain>.  
  
 \<configuration>  
\<Common Language Runtime >  
\<BypassTrustedAppStrongNames >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Bypass-Funktion, die Überprüfung starke Namen für vollständig vertrauenswürdige Assemblys aktiviert ist. Wenn diese Funktion aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft werden, wird beim Laden der Assembly. Die Standardeinstellung ist `true`.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`true`|Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden nicht überprüft werden, wenn die Assemblys in ein voll vertrauenswürdiges geladen werden <xref:System.AppDomain>. Dies ist die Standardeinstellung.|  
|`false`|Signaturen mit starkem Namen für vollständig vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in ein voll vertrauenswürdiges geladen werden <xref:System.AppDomain>. Die Signatur mit starkem Namen wird nur für Signatur Richtigkeit überprüft. Es wird nicht mit einem anderen starken Namen nach einer Übereinstimmung verglichen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Das strong Name-Bypass-Feature vermeidet den Aufwand der Überprüfung der Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys.  
  
 Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:  
  
-   Voll vertrauenswürdig ohne die <xref:System.Security.Policy.StrongName> Beweis (z. B. hat `MyComputer` Zonenbeweis).  
  
-   Geladen in eine voll vertrauenswürdige <xref:System.AppDomain>  
  
-   Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain>  
  
-   Nicht verzögert signiert  
  
> [!NOTE]
>  Wenn das Bypass-Feature für alle Anwendungen auf dem Computer deaktiviert wurde mithilfe eines Registrierungsschlüssels, wirkt sich diese Einstellung in der Konfigurationsdatei nicht. Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren des Strong-Name Bypass-Features](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie das Verhalten an, das die Signatur mit starkem Namen für vollständig vertrauenswürdige Assemblys überprüft wird.  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Gewusst wie: Deaktivieren der Strong-Name-Bypass-Funktion](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
