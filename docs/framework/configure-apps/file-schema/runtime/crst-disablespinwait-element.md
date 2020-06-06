---
title: <Crst_DisableSpinWait>-Element
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117639"
---
# <a name="crst_disablespinwait-element"></a>\<Crst_DisableSpinWait>-Element

Gibt an, ob das warten auf einen kritischen Abschnitt beim Konflikten deaktiviert werden soll.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|**wodurch**|Gibt an, ob das Drehfeld für kritische Abschnitte, bei denen ein Konflikt besteht, deaktiviert ist.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|1|Die Drehung wird deaktiviert, wenn ein kritischer Abschnitt nicht abgerufen werden kann.|  
|0|"Spin-warten" nicht deaktivieren, wenn ein kritischer Abschnitt nicht abgerufen werden kann. Dies ist der Standardwert.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen zu verschiedenen Lauf Zeit Konfigurationseinstellungen.|  
  
## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird die Drehung beim Konflikt in kritischen Abschnitten deaktiviert.  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
