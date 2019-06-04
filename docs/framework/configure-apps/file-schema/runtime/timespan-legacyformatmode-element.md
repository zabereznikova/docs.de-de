---
title: <TimeSpan_LegacyFormatMode>-Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31e2a075f9202439cd62c81a06528b20c4971656
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489345"
---
# <a name="timespanlegacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode >-Element
Bestimmt, ob die Runtime Legacyverhalten bei Formatierungsvorgängen mit behält <xref:System.TimeSpan?displayProperty=nameWithType> Werte.  
  
 \<configuration>  
\<runtime>  
<TimeSpan_LegacyFormatMode>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Runtime Formatierung Legacyverhalten mit verwendet <xref:System.TimeSpan?displayProperty=nameWithType> Werte.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Laufzeit Legacyverhalten Formatierung nicht wiederhergestellt werden.|  
|`true`|Die Laufzeit wird die Formatierung Legacyverhalten wiederhergestellt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Ab .NET Framework 4, die <xref:System.TimeSpan?displayProperty=nameWithType> Struktur implementiert die <xref:System.IFormattable> Schnittstelle und Formatierungsvorgängen mit standardmäßigen und benutzerdefinierten Formatzeichenfolgen unterstützt. Wenn eine Analysemethode ein nicht unterstütztes Format Spezifizierer oder ein Formatzeichenfolge auftritt, löst eine <xref:System.FormatException>.  
  
 In früheren Versionen von .NET Framework die <xref:System.TimeSpan> Struktur wurde nicht implementiert. <xref:System.IFormattable> und Formatzeichenfolgen wurde nicht unterstützt. Allerdings viele Entwickler fälschlicherweise davon ausgegangen, dass <xref:System.TimeSpan> einen Satz von Formatzeichenfolgen unterstützt und verwendet Sie diese im [zur kombinierten Formatierung Vorgänge](../../../../../docs/standard/base-types/composite-formatting.md) mit Methoden, z. B. <xref:System.String.Format%2A?displayProperty=nameWithType>. Normalerweise, wenn ein Typ implementiert <xref:System.IFormattable> und Formatzeichenfolgen unterstützt, Aufrufe für die Formatierung von Methoden mit nicht unterstützten Zeichenfolgen in der Regel löst eine <xref:System.FormatException>. Aber da <xref:System.TimeSpan> wurde nicht implementiert <xref:System.IFormattable>, die Runtime die Formatzeichenfolge ignoriert und stattdessen aufgerufen der <xref:System.TimeSpan.ToString?displayProperty=nameWithType> Methode. Dies bedeutet, dass, obwohl die Formatzeichenfolgen keine Auswirkungen auf den Formatierungsvorgang hatte, ihre Anwesenheit nicht führt eine <xref:System.FormatException>.  
  
 Für Fälle, in der legacy-Code wird eine kombinierte Formatierungsmethode und eine ungültige Zeichenfolge übergeben, und diesen Code nicht neu kompiliert werden, können Sie die `<TimeSpan_LegacyFormatMode>` Element zum Wiederherstellen der Vorgängerversion <xref:System.TimeSpan> Verhalten. Beim Festlegen der `enabled` Attribut dieses Elements zu `true`, die kombinierte Formatierung Methodenergebnisse in einem Aufruf von <xref:System.TimeSpan.ToString?displayProperty=nameWithType> statt <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, und ein <xref:System.FormatException> wird nicht ausgelöst.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel instanziiert ein <xref:System.TimeSpan> Objekt und versucht, formatieren Sie sie mit der <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> -Methode mithilfe einer nicht unterstützten Standardformatzeichenfolge.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 Wenn Sie das Beispiel ausführen, auf die [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] oder eine frühere Version, die folgende Ausgabe angezeigt:  
  
```  
12:30:45  
```  
  
 Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel für die .NET Framework 4 oder höher ausführen:  
  
```  
Invalid Format  
```  
  
 Wenn Sie die folgende Konfigurationsdatei im Verzeichnis des Beispiels hinzufügen und dann das Beispiel für die .NET Framework 4 oder höher ausführen, die Ausgabe ist jedoch identisch, die durch das Beispiel erstellt wird, wenn er ausgeführt wird, [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
