---
title: <EnableAmPmParseAdjustment>-Element
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f132ce0a114a6fc904d86ca3ce893c447366523f
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252633"
---
# <a name="enableampmparseadjustment-element"></a>\<Enableampmparameseadjustment-> Element
Bestimmt, ob Datums-und Uhrzeit Analysemethoden einen angepassten Satz von Regeln zum Analysieren von Datums Zeichenfolgen verwenden, die einen Tag, einen Monat, eine Stunde und einen am/pm-Kenn Zeichner enthalten.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<Enableampmparameseanpassungs->**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob Datums-und Uhrzeit Analysemethoden einen angepassten Satz von Regeln zum Analysieren von Datums Zeichenfolgen verwenden, die nur einen Tag, einen Monat, eine Stunde und einen am/pm-Kenn Zeichner enthalten.|  
  
### <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Description|  
|-----------|-----------------|  
|0|Datums-und Uhrzeit-Analyse-Methoden verwenden keine angepassten Regeln für das Parsen von Datums Zeichenfolgen, die nur einen Tag, einen Monat, eine Stunde und am/pm-Kenn Zeichner enthalten.|  
|1|Datums-und Uhrzeit-Analyse-Methoden verwenden angepasste Regeln zum Parsen von Datums Zeichenfolgen, die nur einen Tag, einen Monat, eine Stunde und am/pm-Kenn Zeichner enthalten.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Das `<EnableAmPmParseAdjustment>` -Element steuert, wie die folgenden Methoden eine Datums Zeichenfolge analysieren, die einen numerischen Tag und Monat gefolgt von einer Stunde und einem am/pm-Kenn Zeichner (z. b. "4/10 6 am") enthält:  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 Es sind keine anderen Muster betroffen.  
  
 Das `<EnableAmPmParseAdjustment>` -Element hat keine Auswirkung auf <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>die <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>Methoden <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>,, <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> und.  
  
> [!IMPORTANT]
> In .net Core und .net Native sind die angepassten am/pm-Analyse-Regeln standardmäßig aktiviert.  
  
 Wenn die Verarbeitungs Anpassungs Regel nicht aktiviert ist, wird die erste Ziffer der Zeichenfolge als Stunde der 12-Stunden-Uhrzeit interpretiert, und der Rest der Zeichenfolge außer dem am/pm-Kenn Zeichner wird ignoriert. Das von der-Methode für die-Methode zurückgegebene Datum und die Uhrzeit bestehen aus dem aktuellen Datum und der Stunde des Tages, der aus der Datums Zeichenfolge extrahiert wird.  
  
 Wenn die Regel für die Verarbeitung von Regeln aktiviert ist, interpretiert die-Methode für den Tag und den Monat so, dass Sie zum aktuellen Jahr gehört, und interpretiert die Uhrzeit als Stunde der 12-Stunden-Uhr.  
  
 In der folgenden Tabelle wird der Unterschied <xref:System.DateTime> im-Wert <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> veranschaulicht, wenn die-Methode verwendet wird, um die Zeichenfolge "" `<EnableAmPmParseAdjustment>` 4/10 6 am `enabled` zu analysieren, wobei die-Eigenschaft des Elements auf "0" oder "1" festgelegt ist. Dabei wird davon ausgegangen, dass das heutige Datum der 5. Januar 2017 ist, und zeigt das Datum so an, als ob es mit der Format Zeichenfolge "G" der angegebenen Kultur formatiert wird.  
  
|Kulturname|enabled="0"|enabled="1"|  
|------------------|------------------|------------------|  
|en-US|1/5/2017 4:00:00 UHR|4/10/2017 6:00:00 UHR|  
|en-GB|5/1/2017 6:00:00|10/4/2017 6:00:00|  
  
## <a name="see-also"></a>Siehe auch

- [\<Runtime-> Element](runtime-element.md)
- [\<configuration> Element](../configuration-element.md)
