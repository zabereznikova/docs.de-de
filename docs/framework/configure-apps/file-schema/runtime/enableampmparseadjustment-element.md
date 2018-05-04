---
title: '&lt;EnableAmPmParseAdjustment&gt; Element'
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b17f521be31fa4082d9418c7dad734e37994bbb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ltenableampmparseadjustmentgt-element"></a>&lt;EnableAmPmParseAdjustment&gt; Element
Bestimmt, ob die Datums- und uhrzeitanalysemethoden verwenden einen angepassten Satz von Regeln analysiert Datumszeichenfolgen, die ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.  
  
 \<configuration>  
 \<Common Language Runtime >  
\<EnableAmPmParseAdjustment >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob Datums- und uhrzeitanalysemethoden einen angepassten Satz von Regeln analysiert Datumszeichenfolgen, die nur ein Tag, Monat, Stunde, und AM/PM-Kennzeichner enthalten.|  
  
### <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|0|Datums- und uhrzeitanalysemethoden verwenden nicht angepasste Regeln für die Analyse von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde, und AM/PM-Kennzeichner enthalten.|  
|1|Verwenden Sie angepasste Regeln für die Analyse von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde, und AM/PM-Kennzeichner enthalten, Datums- und uhrzeitanalysemethoden.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<EnableAmPmParseAdjustment>` -Element steuert, wie die folgenden Methoden eine Datumszeichenfolge analysiert, die einen numerischen Tag und Monat gefolgt von einer Stunde und einer AM/PM-Kennzeichner (z. B. "4/10 6 Uhr") enthält:  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Es sind keine anderen Mustern enthalten betroffen.  
  
 Die `<EnableAmPmParseAdjustment>` Element hat keinen Einfluss auf die <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, und <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> Methoden.  
  
> [!IMPORTANT]
>  Die angepassten AM/PM-Analyseregeln sind in .NET Core und .NET Native standardmäßig aktiviert.  
  
 Wenn die Analyse Anpassungsregel nicht aktiviert ist, wird die erste Ziffer der Zeichenfolge als der Stunde des 12-Stunden-Format interpretiert, und der Rest der Zeichenfolge mit Ausnahme der AM/PM-Kennzeichner wird ignoriert. Das Datum und die Uhrzeit der Rückgabe durch die Analysemethode besteht aus dem aktuellen Datum und der Stunde des Tages die Datumszeichenfolge extrahiert.  
  
 Wenn die Analyse Anpassungsregel aktiviert ist, Analysemethode interpretieren Sie, den Tag und Monat des aktuellen Jahres angehören und Interpretieren Sie die Zeit als der Stunde des 12-Stunden-Format.  
  
 Die folgende Tabelle zeigt den Unterschied in der <xref:System.DateTime> Wert der <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> Methode wird verwendet, um die Zeichenfolge analysiert "" 4/10 6 Uhr"mit der `<EnableAmPmParseAdjustment>` des Elements `enabled` -Eigenschaft auf"0"oder"1"festgelegt. Es wird davon ausgegangen, dass das heutige Datum ist 5 Januar 2017 und zeigt das Datum an, als wäre es mit der angegebenen Kultur "G" Formatzeichenfolge formatiert ist.  
  
|Kulturname|aktiviert = "0"|aktiviert = "1"|  
|------------------|------------------|------------------|  
|en-US|5/1/2017 4:00:00 UHR|4/10/2017 6:00:00 UHR|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Siehe auch  
 [\<Common Language Runtime >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
