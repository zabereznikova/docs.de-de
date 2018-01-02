---
title: '&lt;TimeSpan_LegacyFormatMode&gt; Element'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be4b26cdc79cef0854221172b8dea0bcc0f50981
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="lttimespanlegacyformatmodegt-element"></a>&lt;TimeSpan_LegacyFormatMode&gt; Element
Bestimmt, ob die Runtime Legacyverhalten bei Formatierungsvorgängen mit behält <xref:System.TimeSpan?displayProperty=nameWithType> Werte.  
  
 \<configuration>  
\<Common Language Runtime >  
< TimeSpan_LegacyFormatMode >  
  
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
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Common Language Runtime mit älteren Formatierungsverhalten verwendet <xref:System.TimeSpan?displayProperty=nameWithType> Werte.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`false`|Die Common Language Runtime Legacyverhalten Formatierung nicht wiederhergestellt werden.|  
|`true`|Die Common Language Runtime stellt Formatierung Legacyverhalten wieder her.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## <a name="remarks"></a>Hinweise  
 Beginnend mit der [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], <xref:System.TimeSpan?displayProperty=nameWithType> Struktur implementiert die <xref:System.IFormattable> Schnittstelle und Formatierungsvorgängen mit standardmäßigen und benutzerdefinierten Formatzeichenfolgen unterstützt. Wenn eine Analysemethode eine nicht unterstützte Formatbezeichner oder Formatzeichenfolge gefunden wird, löst sie eine <xref:System.FormatException>.  
  
 In früheren Versionen von .NET Framework die <xref:System.TimeSpan> Struktur wurde nicht implementiert <xref:System.IFormattable> und hat keine Formatzeichenfolgen unterstützt. Jedoch viele Entwickler fälschlicherweise davon ausgegangen, dass <xref:System.TimeSpan> hat einen Satz von Formatzeichenfolgen unterstützt, und verwendet diese in [zur kombinierten Formatierung Vorgänge](../../../../../docs/standard/base-types/composite-formatting.md) mit Methoden wie z. B. <xref:System.String.Format%2A?displayProperty=nameWithType>. In der Regel, wenn ein Typ implementiert <xref:System.IFormattable> und Formatzeichenfolgen unterstützt, Aufrufe von Formatierungsmethoden mit nicht unterstützten Format Zeichenfolgen in der Regel löst eine <xref:System.FormatException>. Aber da <xref:System.TimeSpan> wurde nicht implementiert <xref:System.IFormattable>, die Laufzeit die Formatzeichenfolge ignoriert und stattdessen aufgerufen die <xref:System.TimeSpan.ToString?displayProperty=nameWithType> Methode. Dies bedeutet, dass, obwohl die Formatzeichenfolgen keine Auswirkungen auf den Formatierungsvorgang hatte, deren Vorhandensein nicht ergeben hat eine <xref:System.FormatException>.  
  
 Für Fälle, in dem legacy-Code übergibt eine zur kombinierten Formatierung, Methode und eine ungültige Formatzeichenfolge und diesen Code nicht neu kompiliert werden, können Sie die `<TimeSpan_LegacyFormatMode>` Element zum Wiederherstellen der Vorgängerversion <xref:System.TimeSpan> Verhalten. Beim Festlegen der `enabled` Attribut dieses Elements in `true`, die zur kombinierten Formatierung Methodenergebnisse in einem Aufruf von <xref:System.TimeSpan.ToString?displayProperty=nameWithType> statt <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, und ein <xref:System.FormatException> wird nicht ausgelöst.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel instanziiert einen <xref:System.TimeSpan> -Objekt und formatieren Sie ihn mit dem Versuch, die <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> -Methode mithilfe einer nicht unterstützten Standardformatzeichenfolge.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 Wenn Sie das Beispiel ausführen, auf die [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] oder eine frühere Version zeigt es die folgende Ausgabe:  
  
```  
12:30:45  
```  
  
 Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel ausführen, auf die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] oder höher:  
  
```  
Invalid Format  
```  
  
 Wenn Sie das Beispiel die folgende Konfigurationsdatei hinzufügen jedoch dem Verzeichnis des, und führen Sie das Beispiel auf die [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] oder höher, die Ausgabe ist identisch mit der bei der Ausführung auf [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
