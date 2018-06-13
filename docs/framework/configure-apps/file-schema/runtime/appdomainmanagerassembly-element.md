---
title: '&lt;AppDomainManagerAssembly&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7656f4819e8ed6d8c1c87eabcbd5862929d47cdc
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32744849"
---
# <a name="ltappdomainmanagerassemblygt-element"></a>&lt;AppDomainManagerAssembly&gt; Element
Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.  
  
 \<configuration>  
\<Common Language Runtime >  
\<AppDomainManagerAssembly >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<appDomainManagerAssembly   
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`value`|Erforderliches Attribut. Gibt den Anzeigenamen der Assembly, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Um den Typ des Anwendungsdomänen-Managers anzugeben, müssen Sie dieses Element angeben und die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) Element. Wenn eines dieser Elemente nicht angegeben ist, wird die andere ignoriert.  
  
 Wenn die Standardanwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht mit den vom angegebenen Typ enthält die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) -Element ist; und der Prozess nicht gestartet. Wenn die Assembly gefunden wird, aber die Versionsinformationen nicht überein stimmt, eine <xref:System.IO.FileLoadException> ausgelöst wird.  
  
 Wenn Sie die Anwendung Manager Domänentyp für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt Managertyp die Anwendung an. Verwenden der <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> und <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften zur Angabe einer anderen Anwendung Manager Domänentyp für eine neue Anwendungsdomäne.  
  
 Die Anwendungsdomänen-Managertyp angeben, muss die Anwendung volle Vertrauenswürdigkeit. (Z. B. weist eine Anwendung, die auf dem Desktop ausgeführte volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über die volle Vertrauenswürdigkeit verfügt eine <xref:System.TypeLoadException> ausgelöst wird.  
  
 Das Format des Assemblyanzeigenamens, finden Sie unter der <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Eigenschaft.  
  
 Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] und höher.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie angeben, dass die Anwendungsdomänen-Manager für die Standardanwendungsdomäne eines Prozesses ist die `MyMgr` Geben Sie in der `AdMgrExample` Assembly.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly   
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>  
 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>  
 [\<AppDomainManagerType >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [SetAppDomainManagerType-Methode](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
