---
title: <EnableAmPmParseAdjustment>-Element
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d1a14199debbb90827c1ea95347d485a636329
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59222509"
---
# <a name="enableampmparseadjustment-element"></a>\<EnableAmPmParseAdjustment >-Element
Bestimmt, ob Datum und Uhrzeit-Analysemethoden verwenden einen angepassten Satz von Regeln zum Analysieren von Datumszeichenfolgen, die ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.  
  
 \<configuration>  
 \<runtime>  
\<EnableAmPmParseAdjustment>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob Datum und Uhrzeit-Analysemethoden verwenden einen angepassten Satz von Regeln zum Analysieren von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.|  
  
### <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|0|Datum und Uhrzeit-Analysemethoden verwenden nicht angepasste Regeln zum Analysieren von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.|  
|1|Datum und Uhrzeit-Analysemethoden verwenden angepasste Regeln zum Analysieren von Datumszeichenfolgen, die nur ein Tag, Monat, Stunde und AM/PM-Kennzeichner enthalten.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<EnableAmPmParseAdjustment>` -Element steuert, wie die folgenden Methoden eine Datumszeichenfolge analysiert, die einen numerischen Tag und Monat, gefolgt von einer Stunde und einer AM/PM-Kennzeichner (z. B. "4/10 6 Uhr") enthält:  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Es sind keine anderen Mustern betroffen.  
  
 Die `<EnableAmPmParseAdjustment>` Element hat keine Auswirkungen auf die <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, und <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> Methoden.  
  
> [!IMPORTANT]
>  In .NET Core und .NET Native sind die angepassten AM/PM-Analyseregeln standardmäßig aktiviert.  
  
 Wenn die Analyse Anpassungsregel nicht aktiviert ist, wird die erste Ziffer der Zeichenfolge wird als der Stunde im 12-Stunden-Format interpretiert, und der Rest der Zeichenfolge, mit Ausnahme der AM/PM-Kennzeichner wird ignoriert. Datum und Uhrzeit, die von der Methode zurückgegebenen besteht aus dem aktuellen Datum und die Stunde des Tages aus der Datumszeichenfolge extrahiert.  
  
 Wenn die Analyse Anpassungsregel aktiviert ist, Analysemethode Tag und Monat als das aktuelle Jahr gehörend zu interpretieren und die Zeit als die Stunde im 12-Stunden-Format zu interpretieren.  
  
 Die folgende Tabelle zeigt den Unterschied in der <xref:System.DateTime> Wert fest, wenn die <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> Methode wird verwendet, um die Zeichenfolge analysiert "" 4/10 6 Uhr"mit der `<EnableAmPmParseAdjustment>` des Elements `enabled` -Eigenschaft auf"0"oder"1"festgelegt. Es wird davon ausgegangen, dass das heutige Datum ist 5. Januar 2017, und zeigt das Datum, als wäre es mit der angegebenen Kultur "G" Formatzeichenfolge formatiert ist.  
  
|Kulturname|enabled="0"|enabled="1"|  
|------------------|------------------|------------------|  
|en-US|1/5/2017 4:00:00 UHR|4/10/2017-06:00:00 UHR|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Siehe auch

- [\<Common Language Runtime >-Element](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)
- [\<configuration> Element](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
