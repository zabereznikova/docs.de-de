---
title: '&lt;LegacyCorruptedStateExceptionsPolicy&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <legacyCorruptedStateExceptionsPolicy> element
- legacyCorruptedStateExceptionsPolicy element
ms.assetid: e0a55ddc-bfa8-4f3e-ac14-d1fc3330e4bb
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f09d6cf256e072d01f3cfc79987aa4d240f96235
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltlegacycorruptedstateexceptionspolicygt-element"></a>&lt;LegacyCorruptedStateExceptionsPolicy&gt; Element
Gibt an, ob die common Language Runtime verwalteten Codes zugriffsverletzungen und Beschädigung Ausnahmen abfangen kann.  
  
 \<configuration>  
\<Common Language Runtime >  
\<LegacyCorruptedStateExceptionsPolicy >  
  
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
|`false`|Die Anwendung wird nicht abfangen Fehler wie z. B. zugriffsverletzungen beschädigen. Dies ist die Standardeinstellung.|  
|`true`|Die Anwendung fängt Fehler wie z. B. zugriffsverletzungen beschädigen.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 In .NET Framework, Version 3.5 und früher zulässig die common Language Runtime verwalteten Code zum Abfangen von Ausnahmen, die nach beschädigten Prozess Status ausgelöst wurden. Eine zugriffsverletzung ist ein Beispiel für diese Art von Ausnahme.  
  
 Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], verwalteten Code nicht mehr fängt diese Arten von Ausnahmen in `catch` blockiert. Allerdings können außer Kraft setzen diese Änderung und die Handhabung von beschädigten Zustandsausnahmen auf zwei Arten verwalten:  
  
-   Legen Sie die `<legacyCorruptedStateExceptionsPolicy>` des Elements `enabled` -Attribut `true`. Diese Konfigurationseinstellung wird Processwide angewendet und wirkt sich auf alle Methoden.  
  
 - oder -   
  
-   Anwenden der <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=nameWithType> -Attribut auf die Methode, die Ausnahmen enthält `catch` Block.  
  
 Dieses Konfigurationselement steht nur in der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] und höher.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie angegeben, dass die Anwendung zurückgesetzt werden soll, um das Verhalten vor dem [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], und alle fehlt Fehler abgefangen.  
  
```xml  
<configuration>  
   <runtime>  
      <legacyCorruptedStateExceptionsPolicy enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute>  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
