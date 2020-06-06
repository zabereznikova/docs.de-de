---
title: <appDomainManagerType>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154424"
---
# <a name="appdomainmanagertype-element"></a>\<appDomainManagerType>-Element
Gibt den Typ an, der als Anwendungsdomänen-Manager für die Standardanwendungsdomäne dient.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`value`|Erforderliches Attribut. Gibt den Namen des Typs einschließlich des Namespace an, der als Anwendungs Domänen-Manager für die Standard Anwendungsdomäne im Prozess dient.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  
 Um den Typ des Anwendungs Domänen-Managers anzugeben, müssen Sie sowohl dieses Element als auch das- [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) Element angeben. Wenn keines dieser Elemente angegeben ist, wird das andere ignoriert.  
  
 Wenn die Standard Anwendungsdomäne geladen wird, <xref:System.TypeLoadException> wird ausgelöst, wenn der angegebene Typ in der Assembly, die vom-Element angegeben ist, nicht vorhanden ist [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) . der Prozess kann nicht gestartet werden.  
  
 Wenn Sie den Anwendungs Domänen-Manager für die Standard Anwendungsdomäne angeben, erben andere Anwendungs Domänen, die aus der Standard Anwendungsdomäne erstellt wurden, den Typ des Anwendungs Domänen-Managers. Verwenden <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> Sie die <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> Eigenschaften und, um einen anderen Anwendungs Domänen-Manager-Typ für eine neue Anwendungsdomäne anzugeben.  
  
 Die Angabe des Anwendungs Domänen-Manager-Typs erfordert, dass die Anwendung volle Vertrauenswürdigkeit besitzt. (Eine Anwendung, die auf dem Desktop ausgeführt wird, hat beispielsweise volle Vertrauenswürdigkeit.) Wenn die Anwendung nicht über volle Vertrauenswürdigkeit verfügt, <xref:System.TypeLoadException> wird eine ausgelöst.  
  
 Das Format des Typs und Namespace entspricht dem Format, das für die Eigenschaft verwendet wird <xref:System.Type.FullName%2A?displayProperty=nameWithType> .  
  
 Dieses Konfigurationselement ist nur in den .NET Framework 4 und höher verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie angegeben wird, dass der Anwendungs Domänen-Manager für die Standard Anwendungsdomäne eines Prozesses der `MyMgr` Typ in der `AdMgrExample` Assembly ist.  
  
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
- [\<appDomainManagerAssembly>Gewisses](appdomainmanagerassembly-element.md)
- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [SetAppDomainManagerType-Methode](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
