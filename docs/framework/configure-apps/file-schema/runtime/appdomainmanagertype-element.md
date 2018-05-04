---
title: '&lt;AppDomainManagerType&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fb771d58a99e42ad53a465008e8848cff0a87fd
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltappdomainmanagertypegt-element"></a>&lt;AppDomainManagerType&gt; Element
Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.  
  
 \<configuration>  
\<Common Language Runtime >  
\<AppDomainManagerType >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<appDomainManagerAssembly   
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`value`|Erforderliches Attribut. Gibt den Namen des Typs, einschließlich des Namespace, der als Anwendungsdomänen-Managers für die Standardanwendungsdomäne im Prozess dient.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Um den Typ des Anwendungsdomänen-Managers anzugeben, müssen Sie dieses Element angeben und die [ \<AppDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) Element. Wenn eines dieser Elemente nicht angegeben ist, wird die andere ignoriert.  
  
 Wenn die Standardanwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn der angegebene Typ nicht in der Assembly vorhanden ist, die von angegeben wird die [ \<AppDomainManagerAssembly >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md) Element und der Prozess kann nicht Starten.  
  
 Wenn Sie die Anwendung Manager Domänentyp für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt Managertyp die Anwendung an. Verwenden der <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> und <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften zur Angabe einer anderen Anwendung Manager Domänentyp für eine neue Anwendungsdomäne.  
  
 Die Anwendungsdomänen-Managertyp angeben, muss die Anwendung volle Vertrauenswürdigkeit. (Z. B. weist eine Anwendung, die auf dem Desktop ausgeführte volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über die volle Vertrauenswürdigkeit verfügt eine <xref:System.TypeLoadException> ausgelöst wird.  
  
 Das Format des Typs und des Namespace ist das gleiche Format für die verwendeten die <xref:System.Type.FullName%2A?displayProperty=nameWithType> Eigenschaft.  
  
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
 [\<AppDomainManagerAssembly >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagerassembly-element.md)  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [SetAppDomainManagerType-Methode](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
