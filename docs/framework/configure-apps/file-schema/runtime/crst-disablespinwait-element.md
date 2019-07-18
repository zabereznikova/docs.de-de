---
title: < Crst_DisableSpinWait >-element
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f89f0558c11e229fef2ca3cd619e3c033f12c858
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754678"
---
# <a name="crstdisablespinwait-element"></a>\<Crst_DisableSpinWait >-Element

Gibt an, ob die Spin-warten auf einen kritischen Abschnitt bei Konflikten deaktiviert.  
  
 \<configuration>  
\<runtime>  
\<Crst_DisableSpinWait>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|**enabled**|Gibt an, ob Spin-warten auf kritische Abschnitte, wenn diese Anzahl von Konflikten vorliegt deaktiviert ist.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|1|Deaktivieren Sie Spin-Waiting aus, wenn ein Kritischer Abschnitt kann nicht abgerufen werden.|  
|0|Drehfeld-Waiting kann nicht deaktiviert werden, wenn ein Kritischer Abschnitt kann nicht abgerufen werden. Dies ist der Standardwert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über verschiedene Konfigurationseinstellungen für die Common Language Runtime.|  
  
## <a name="example"></a>Beispiel  

Das folgende Beispiel deaktiviert die Spin-Waiting in kritischen Abschnitten bei Konflikten.  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
