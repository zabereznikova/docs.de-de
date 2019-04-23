---
title: <appDomainManagerAssembly>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4fe1dfbd62a6967ae51031fa12f80e9c5563dc44
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182350"
---
# <a name="appdomainmanagerassembly-element"></a>\<appDomainManagerAssembly> Element
Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.  
  
 \<configuration>  
\<runtime>  
\<appDomainManagerAssembly>  
  
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
 Um den Typ des Anwendungsdomänen-Managers angeben zu können, müssen Sie dieses Element angeben und die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) Element. Wenn eines der beiden Elemente nicht angegeben ist, wird das andere ignoriert.  
  
 Wenn die Standardanwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht mit den vom angegebenen Typ enthält die [ \<AppDomainManagerType >](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md) -Element; und der Prozess nicht gestartet. Wenn die Assembly gefunden wird, aber die Versionsinformationen nicht überein stimmt, ein <xref:System.IO.FileLoadException> ausgelöst.  
  
 Bei der Angabe des Anwendung Manager Domänentyp für die Standardanwendungsdomäne erben anderen Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt die Anwendungsdomänen-Managertyp. Verwenden der <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> und <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften an eine andere Anwendung Manager Domänentyp für eine neue Anwendungsdomäne.  
  
 Der Anwendungstyp für Domänen-Manager angeben, muss die Anwendung volle Vertrauenswürdigkeit. (Z. B. hat eine Anwendung ausgeführt wird, auf dem Desktop volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht mit voller Vertrauenswürdigkeit, verfügt eine <xref:System.TypeLoadException> ausgelöst.  
  
 Das Format des Anzeigenamens der Assembly finden Sie unter den <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Eigenschaft.  
  
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

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<AppDomainManagerType >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/appdomainmanagertype-element.md)
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [SetAppDomainManagerType-Methode](../../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
