---
title: <appDomainManagerType>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154424"
---
# <a name="appdomainmanagertype-element"></a>\<appDomainManagerType> Element
Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.  
  
[**\<Konfiguration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<Laufzeit>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attributes  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`value`|Erforderliches Attribut. Gibt den Namen des Typs an, einschließlich des Namespace, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne im Prozess dient.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine.  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Um den Typ des Anwendungsdomänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch das [ \<appDomainManagerAssembly->-Element](appdomainmanagerassembly-element.md) angeben. Wenn eines dieser Elemente nicht angegeben ist, wird das andere ignoriert.  
  
 Wenn die Standardanwendungsdomäne <xref:System.TypeLoadException> geladen wird, wird ausgelöst, wenn der angegebene Typ nicht in der Assembly vorhanden ist, die [ \<vom appDomainManagerAssembly->-Element](appdomainmanagerassembly-element.md) angegeben wird. und der Prozess kann nicht gestartet werden.  
  
 Wenn Sie den Anwendungsdomänen-Managertyp für die Standardanwendungsdomäne angeben, erben andere Anwendungsdomänen, die von der Standardanwendungsdomäne erstellt wurden, den Anwendungsdomänen-Managertyp. Verwenden <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Sie <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> die und Eigenschaften, um einen anderen Anwendungsdomänen-Managertyp für eine neue Anwendungsdomäne anzugeben.  
  
 Das Angeben des Anwendungsdomänen-Managertyps erfordert, dass die Anwendung voll vertrauenswürdig ist. (Eine Anwendung, die auf dem Desktop ausgeführt wird, hat z. B. volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über <xref:System.TypeLoadException> die volle Vertrauenswürdigkeit verfügt, wird eine ausgelöst.  
  
 Das Format des Typs und namespace ist das <xref:System.Type.FullName%2A?displayProperty=nameWithType> gleiche Format, das für die Eigenschaft verwendet wird.  
  
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
- [\<appDomainManagerAssembly> Element](appdomainmanagerassembly-element.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Schema der Konfigurationsdatei](../index.md)
- [SetAppDomainManagerType-Methode](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
