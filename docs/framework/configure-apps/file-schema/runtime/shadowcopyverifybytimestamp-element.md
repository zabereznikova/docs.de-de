---
title: '&lt;ShadowCopyVerifyByTimestamp&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bae98c91c8a9b68ec7c21b142bc9f004c7bc1394
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltshadowcopyverifybytimestampgt-element"></a>&lt;ShadowCopyVerifyByTimestamp&gt; Element
Gibt an, ob die Schattenkopiefunktion das in [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] eingeführte Standardstartverhalten verwendet oder auf das Startverhalten früherer Versionen von .NET Framework zurückgreift.  
  
 \<Konfiguration >-Element  
\<Common Language Runtime >-Element  
\<ShadowCopyVerifyByTimestamp >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob Anwendungsdomänen, die Schattenkopiefunktion verwenden Assembly Zeitstempel, beim Starten vergleichen zu bestimmen, ob eine Assembly aktualisiert wurde, bevor Sie die Assembly für die Schattenkopiefunktion.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|true|Beim Start kopiert wird nur für Assemblys, die aktualisiert wurden, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden. Dies ist die Standardeinstellung für die [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)].|  
|False|Wird auf das Startverhalten vorheriger Versionen von .NET Framework, dem wurde so kopieren Sie alle Dateien beim Start.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], Assemblys sind Schattenkopien nur, wenn ihre Zeitstempel angeben, dass sie geändert wurden, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden. Dies verbessert die Startzeiten für viele Anwendungen, die von Schattenkopien zu verwenden, wie in beschrieben [von Schattenkopien von Assemblys](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md). Anwendungen, die einen hohen Prozentsatz und die Häufigkeit der Assemblyaktualisierungen verfügen möglicherweise nicht von dieser Änderung im Verhalten profitieren. In diesem Fall können Sie dieses Element verwenden, um das Verhalten von früheren Versionen von .NET Framework wiederherzustellen.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie das standardmäßige Startverhalten der Schattenkopiefunktion Deaktivieren der [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], und kehren Sie zu das Startverhalten vorheriger Versionen von .NET Framework.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [Erstellen von Schattenkopien von Assemblys](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
