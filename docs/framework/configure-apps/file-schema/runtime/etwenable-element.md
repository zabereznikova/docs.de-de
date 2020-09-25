---
title: <etwEnable>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- etwEnable element
- <etwEnable> element
ms.assetid: 29dde982-6d8b-4099-8867-ad0d7733f6dc
ms.openlocfilehash: 1c3e42dfbc2c27841ed065e90bad24575e4fb2b1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91178267"
---
# <a name="etwenable-element"></a>\<etwEnable>-Element

Gibt an, ob die Ereignisablaufverfolgung für Windows (ETW) für Common Language Runtime-Ereignisse aktiviert wird.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<etwEnabled>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<etwEnable enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob etw aktiviert werden soll.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|true|Etw aktivieren. Dies ist die Standardeinstellung für Windows-Versionen, die mit den Betriebssystemen Windows Vista und Windows Server 2008 beginnen.|  
|false|Deaktivieren Sie etw. Dies ist die Standardeinstellung für frühere Versionen von Windows.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Bemerkungen  

 Ab Windows Vista ist etw standardmäßig aktiviert. Verwenden Sie dieses Element, um etw für eine Anwendung zu deaktivieren. In früheren Versionen von Windows verwenden Sie dieses Element, um etw für eine Anwendung zu aktivieren.  
  
> [!NOTE]
> Etw kann mithilfe einer Registrierungs Einstellung Global auf einem Server aktiviert oder deaktiviert werden. Siehe [Steuern der .NET Framework Protokollierung](../../../performance/controlling-logging.md).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie die ETW-Ablauf Verfolgung für eine Anwendung aktiviert wird.  
  
```xml  
<configuration>  
   <runtime>  
      <etwEnable enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [Steuern der Protokollierung in .NET Framework](../../../performance/controlling-logging.md)
