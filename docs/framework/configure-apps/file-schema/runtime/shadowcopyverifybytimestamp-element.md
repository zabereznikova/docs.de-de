---
title: <shadowCopyVerifyByTimestamp>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4187d266d82783ebb72073c1da92faff95352884
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489377"
---
# <a name="shadowcopyverifybytimestamp-element"></a>\<shadowCopyVerifyByTimestamp>-Element
Gibt an, ob die Schattenkopiefunktion das standardmäßige Startverhalten, die in .NET Framework 4 eingeführt wurde verwendet, oder setzt auf das Startverhalten früherer Versionen von .NET Framework.  
  
 \<Configuration >-Element  
\<Common Language Runtime >-Element  
\<shadowCopyVerifyByTimestamp>-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob die Anwendungsdomänen, die verwenden der Schattenkopiefunktion Assembly-Zeitstempel vergleichen, beim Starten zu bestimmen, ob eine Assembly aktualisiert wurde, bevor Sie die Assembly für die Schattenkopiefunktion.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|true|Beim Start kopiert wird nur Assemblys, die aktualisiert wurden, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden. Dies ist die Standardeinstellung für .NET Framework 4.|  
|False|Wird auf das Startverhalten früherer Versionen von .NET Framework, dem bestand darin, alle Dateien beim Start zu kopieren.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Ab .NET Framework 4 sind Assemblys Schattenkopien nur, wenn ihre Zeitstempel angeben, dass sie geändert wurden, seit sie zuletzt in das Schattenkopieverzeichnis kopiert wurden. Dies verbessert die Startzeiten für viele Anwendungen, die Schattenkopiefunktion, verwenden Sie, wie in beschrieben [Schattenkopien von Assemblys](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md). Anwendungen, die einen hohen Prozentsatz und Häufigkeit von Assembly-Updates verfügen möglicherweise nicht aufgrund der Änderung im Verhalten profitieren. In diesem Fall können Sie dieses Element, um das Verhalten früherer Versionen von .NET Framework wiederherzustellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie das standardmäßige Startverhalten der Schattenkopiefunktion in .NET Framework 4 zu deaktivieren, und machen Sie auf das Startverhalten vorheriger Versionen von .NET Framework.  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Erstellen von Schattenkopien von Assemblys](../../../../../docs/framework/app-domains/shadow-copy-assemblies.md)
