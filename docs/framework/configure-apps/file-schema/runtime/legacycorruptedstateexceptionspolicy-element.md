---
title: <legacyCorruptedStateExceptionsPolicy>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 777d496614435106b84b47b9aa3d35d964bc3e07
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704738"
---
# <a name="legacycorruptedstateexceptionspolicy-element"></a>\<legacyCorruptedStateExceptionsPolicy> Element
Gibt an, ob die common Language Runtime verwalteten Code zum Abfangen von zugriffsverletzungen und anderen Beschädigungen hervorgerufenen Ausnahmen zulässt.  
  
 \<configuration>  
\<runtime>  
\<legacyCorruptedStateExceptionsPolicy>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<legacyCorruptedStateExceptionsPolicy enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, dass die Anwendung abgefangen werden Fehler wie z. B. zugriffsverletzungen beschädigen.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Anwendung fängt keine Fehler z.B. zugriffsverletzungen beschädigen. Dies ist die Standardeinstellung.|  
|`true`|Die Anwendung fängt Fehler z.B. zugriffsverletzungen beschädigen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 In .NET Framework, Version 3.5 und früher darf die common Language Runtime verwalteten Code zum Abfangen von Ausnahmen, die vom Status der beschädigten Prozess ausgelöst wurden. Eine zugriffsverletzung ist ein Beispiel für diese Art von Ausnahme.  
  
 Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], verwalteten Code nicht mehr fängt diese Arten von Ausnahmen in `catch` Blöcke. Allerdings können außer Kraft setzen diese Änderung und verwaltet die Behandlung von Beschädigungen hervorgerufenen Ausnahmen gibt es zwei Möglichkeiten:  
  
- Legen Sie die `<legacyCorruptedStateExceptionsPolicy>` des Elements `enabled` Attribut `true`. Diese Konfigurationseinstellung wird angewendeten Processwide und wirkt sich auf alle Methoden.  
  
 - oder -   
  
- Anwenden der <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> -Attribut auf die Methode, die die Ausnahmen enthält `catch` Block.  
  
 Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie angegeben, dass die Anwendung das Verhalten vor zurückkehren soll die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], und alle Beschädigung Fehler abgefangen.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>
- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
