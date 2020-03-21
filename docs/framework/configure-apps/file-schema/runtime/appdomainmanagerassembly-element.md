---
title: <appDomainManagerAssembly>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <appDomainManagerAssembly> element
- appDomainManagerAssembly element
ms.assetid: c7c56e39-a700-44f5-b94e-411bfce339d9
ms.openlocfilehash: 4c4ea35bff17a0e5188f26884e93cf77173a7df8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154425"
---
# <a name="appdomainmanagerassembly-element"></a>\<appDomainManagerAssembly> Element
Gibt die Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerAssembly>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<appDomainManagerAssembly
   value="assembly display name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`value`|Erforderliches Attribut. Gibt den Anzeigenamen der Assembly an, die den Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess bereitstellt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Um den Typ des Anwendungsdomänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch [ \<dasDomainManagerType-element>](appdomainmanagertype-element.md) angeben. Wenn eines dieser Elemente nicht angegeben ist, wird das andere ignoriert.  
  
 Wenn die Standardanwendungsdomäne <xref:System.TypeLoadException> geladen wird, wird ausgelöst, wenn die angegebene Assembly nicht vorhanden ist oder wenn die Assembly nicht den vom [ \<appDomainManagerType>-Element](appdomainmanagertype-element.md) angegebenen Typ enthält. und der Prozess kann nicht gestartet werden. Wenn die Assembly gefunden wird, die Versionsinformationen jedoch nicht übereinstimmen, wird eine <xref:System.IO.FileLoadException> ausgelöst.  
  
 Wenn Sie den Anwendungsdomänen-Managertyp für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt wurden, den Anwendungsdomänen-Managertyp. Verwenden <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Sie <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> die und Eigenschaften, um einen anderen Anwendungsdomänen-Managertyp für eine neue Anwendungsdomäne anzugeben.  
  
 Das Angeben des Anwendungsdomänen-Managertyps erfordert, dass die Anwendung voll vertrauenswürdig ist. (Eine Anwendung, die auf dem Desktop ausgeführt wird, hat z. B. volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über <xref:System.TypeLoadException> die volle Vertrauenswürdigkeit verfügt, wird eine ausgelöst.  
  
 Das Format des Assemblyanzeigenamens finden <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> Sie in der Eigenschaft.  
  
 Dieses Konfigurationselement ist nur in .NET Framework 4 und höher verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie angeben, dass der `MyMgr` Anwendungsdomänen-Manager für die Standardanwendungsdomäne eines Prozesses der Typ in der `AdMgrExample` Assembly ist.  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [\<appDomainManagerType> Element](appdomainmanagertype-element.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
- [SetAppDomainManagerType-Methode](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
