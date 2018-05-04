---
title: '&lt;EtwEnable&gt; Element'
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 267a4a29282881d18201d0cb2062e91b4ff974a9
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltetwenablegt-element"></a>&lt;EtwEnable&gt; Element
Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.  
  
 \<Konfiguration >-Element  
\<Common Language Runtime >-Element  
\<EtwEnabled >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob ETW aktiviert werden soll.|  
  
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
 Ab Windows Vista wird ETW standardmäßig aktiviert. Verwenden Sie dieses Element, um ETW für eine Anwendung zu deaktivieren. Verwenden Sie in früheren Versionen von Windows dieses Element, um ETW für eine Anwendung zu aktivieren.  
  
> [!NOTE]
>  ETW kann aktiviert oder deaktiviert global auf einem Server mit einer Einstellung in der Registrierung. Finden Sie unter [Steuern der Protokollierung in .NET Framework](../../../../../docs/framework/performance/controlling-logging.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das ETW-Ablaufverfolgung für eine Anwendung zu aktivieren.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)](../../../../../docs/framework/performance/controlling-logging.md)
