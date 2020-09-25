---
title: <developmentMode>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
ms.openlocfilehash: ddcabb831193baee30016f663f32d8562283d936
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205021"
---
# <a name="developmentmode-element"></a>\<developmentMode>-Element

Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|**DeveloperInstallation**|Gibt an, ob die Runtime nach Assemblys in Verzeichnissen suchen soll, die durch die DEVPATH-Umgebungsvariable angegeben werden.|  
  
## <a name="developerinstallation-attribute"></a>DeveloperInstallation-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**true**|Sucht Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden.|  
|**false**|Sucht nicht nach Assemblys in Verzeichnissen, die durch die DEVPATH-Umgebungsvariable angegeben werden. Dies ist die Standardeinstellung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  

 Verwenden Sie diese Einstellung nur zur Entwicklungszeit. Die Laufzeit überprüft nicht die Versionen von Assemblys mit starkem Namen, die im DEVPATH gefunden werden. Es wird einfach die erste gefundene Assembly verwendet.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie Sie bewirken, dass die Laufzeit Assemblys in Verzeichnissen sucht, die durch die DEVPATH-Umgebungsvariable angegeben werden.  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Vorgehensweise: Suchen von Assemblys mit DEVPATH](../../how-to-locate-assemblies-by-using-devpath.md)
