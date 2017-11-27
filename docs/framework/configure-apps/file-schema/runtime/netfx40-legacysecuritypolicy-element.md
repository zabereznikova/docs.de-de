---
title: '&lt;NetFx40_LegacySecurityPolicy&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <NetFx40_LegacySecurityPolicy> element
- NetFx40_LegacySecurityPolicy element
ms.assetid: 07132b9c-4a72-4710-99d7-e702405e02d4
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cb59eb6e2a5e831f603747b3e0f9435bd076fbf8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltnetfx40legacysecuritypolicygt-element"></a>&lt;NetFx40_LegacySecurityPolicy&gt; Element
Gibt an, ob die Runtime die Legacyrichtlinie für Code Access Security (CAS) verwendet.  
  
 \<configuration>  
\<Common Language Runtime >  
< NetFx40_LegacySecurityPolicy >  
  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Common Language Runtime CAS-legacyrichtlinie verwendet.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Legacy-CAS-Richtlinie wird von die Laufzeit nicht verwendet. Dies ist die Standardeinstellung.|  
|`true`|Die Laufzeit verwendet die legacy-CAS-Richtlinie.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Die CAS-Richtlinie ist in .NET Framework, Version 3.5 und frühere Versionen müssen immer wirksam. In der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], CAS-Richtlinie muss aktiviert sein.  
  
 Die CAS-Richtlinie ist versionsspezifisch. Benutzerdefinierte CAS-Richtlinien, die in früheren Versionen von .NET Framework vorhanden sein müssen erneut angegeben werden, der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].  
  
 Anwenden der `<NetFx40_LegacySecurityPolicy>` Element um eine [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] Assembly hat keinen Einfluss auf [Sicherheitstransparenter Code](../../../../../docs/framework/misc/security-transparent-code.md); die Transparenzregeln gelten weiterhin.  
  
> [!IMPORTANT]
>  Anwenden der `<NetFx40_LegacySecurityPolicy>` Element kann bedeutenden Leistungseinbußen führen, für die Assemblys von systemeigenen Images erstellt, indem die [Native Image Generator (Ngen.exe)](../../../../../docs/framework/tools/ngen-exe-native-image-generator.md) , die nicht installiert sind die [globaler Assemblycache ](../../../../../docs/framework/app-domains/gac.md). Leistungsabfälle wird verursacht, wenn die Unfähigkeit der Laufzeit, Assemblys als systemeigene Images zu laden, wenn das Attribut angewendet wird, wodurch ihre wird als just-in-Time-Assemblys geladen.  
  
> [!NOTE]
>  Wenn Sie eine .NET Framework-Zielversion angeben, die älter ist als die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] in den projekteinstellungen für Visual Studio-Projekts, die CAS-Richtlinie aktiviert, einschließlich alle benutzerdefinierten CAS-Richtlinien, die Sie für die jeweilige Version angegeben. Sie werden jedoch neue verwenden [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] Typen und Member. Sie können auch eine frühere Version von .NET Framework angeben, mit der [ \<SupportedRuntime >-Element](../../../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) in das Schema für starteinstellungen in Ihre [Anwendungskonfigurationsdatei](../../../../../docs/framework/configure-apps/index.md).  
  
> [!NOTE]
>  Syntax von Konfigurationsdateien wird Groß-/Kleinschreibung beachtet. Sie sollten die Syntax verwenden, wie in den Abschnitten Syntax und ein Beispiel bereitgestellt.  
  
## <a name="configuration-file"></a>Konfigurationsdatei  
 Dieses Element kann nur in der Anwendungskonfigurationsdatei verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die legacy-CAS-Richtlinie für eine Anwendung zu aktivieren.  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
