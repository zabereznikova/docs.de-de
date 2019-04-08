---
title: <NetFx40_LegacySecurityPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 20a0ca8560fcd5d7f9d171df3e3b4c3f42e78641
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075989"
---
# <a name="netfx40legacysecuritypolicy-element"></a>\<NetFx40_LegacySecurityPolicy >-Element
Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.  
  
 \<configuration>  
\<runtime>  
<NetFx40_LegacySecurityPolicy>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<NetFx40_LegacySecurityPolicy  
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Runtime die CAS-legacyrichtlinie verwendet.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Runtime verwendet nicht CAS-legacyrichtlinie. Dies ist die Standardeinstellung.|  
|`true`|Die Runtime verwendet die legacy-CAS-Richtlinie.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 CAS-Richtlinie ist in der .NET Framework, Version 3.5 und früheren Versionen immer wirksam. In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS-Richtlinie muss aktiviert sein.  
  
 CAS-Richtlinie ist versionsspezifisch. Benutzerdefinierte CAS-Richtlinien, die in früheren Versionen von .NET Framework vorhanden sein müssen erneut angegeben werden, der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Anwenden der `<NetFx40_LegacySecurityPolicy>` Element eine [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] Assembly hat keine Auswirkungen auf [Sicherheitstransparenter Code](../../../../../docs/framework/misc/security-transparent-code.md); die Transparenzregeln gelten weiterhin.  
  
> [!IMPORTANT]
>  Anwenden der `<NetFx40_LegacySecurityPolicy>` Elements kann dazu führen, Leistungseinbußen für Assemblys systemeigener Abbilder, die erstellt werden, indem der [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) nicht im installierten der [globalen Assemblycache ](../../../../../docs/framework/app-domains/gac.md). Die Leistungsminderung wird verursacht, wenn die Unmöglichkeit der Runtime, die die Assemblys als native Bilder geladen werden, wenn das Attribut angewendet wird, und ihre wird als just-in-Time-Assemblys geladen.  
  
> [!NOTE]
>  Wenn Sie eine .NET Framework-Zielversion angeben, die älter als die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in den projekteinstellungen für Visual Studio-Projekt, die CAS-Richtlinie aktiviert, einschließlich jeder benutzerdefinierten CAS-Richtlinien, die Sie für diese Version angegeben haben. Aber Sie ist nicht möglich, "new" verwenden [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Typen und Member. Sie können auch eine frühere Version von .NET Framework angeben, indem die [ \<SupportedRuntime >-Element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in das Schema für starteinstellungen in Ihrer [Konfigurationsdatei der Anwendung](../../../../../docs/framework/configure-apps/index.md).  
  
> [!NOTE]
>  Syntax von Konfigurationsdateien wird Groß-/Kleinschreibung beachtet. Sie sollten die Syntax verwenden, wie in den Abschnitten zu Syntax und Beispiel bereitgestellt.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die legacy-CAS-Richtlinie für eine Anwendung zu aktivieren.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
