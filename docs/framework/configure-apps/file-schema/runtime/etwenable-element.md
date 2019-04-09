---
title: <etwEnable> Element
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ba411114bfb853e06c83adb42713d43f1452d9c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59135069"
---
# <a name="etwenable-element"></a>\<EtwEnable >-Element
Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.  
  
 \<Configuration >-Element  
\<Common Language Runtime >-Element  
\<etwEnabled>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob es sich bei ETW aktiviert werden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|true|Aktivieren Sie ETW. Dies ist die Standardeinstellung für Versionen von Windows ab Windows Vista und Windows Server 2008-Betriebssysteme.|  
|False|Deaktivieren Sie ETW. Dies ist die Standardeinstellung für frühere Versionen von Windows.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Ab Windows Vista ist ETW standardmäßig aktiviert. Verwenden Sie dieses Element, um ETW für eine Anwendung zu deaktivieren. Verwenden Sie dieses Element in früheren Versionen von Windows ETW für eine Anwendung zu aktivieren.  
  
> [!NOTE]
>  ETW kann aktiviert oder deaktiviert global auf einem Server mit einer registrierungseinstellung. Finden Sie unter [Steuern der Protokollierung in .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie die ETW-Ablaufverfolgung für eine Anwendung aktiviert wird.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Steuern der Protokollierung in .NET Framework](../../../../../docs/framework/performance/controlling-logging.md)
