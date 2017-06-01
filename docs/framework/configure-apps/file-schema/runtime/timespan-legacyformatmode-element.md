---
title: "&lt;TimeSpan_LegacyFormatMode&gt;-Element | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<TimeSpan_LegacyFormatMode>-Element"
  - "TimeSpan_LegacyFormatMode-Element"
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# &lt;TimeSpan_LegacyFormatMode&gt;-Element
Bestimmt, ob die Laufzeit Legacyverhalten bei Formatierungsvorgängen mit <xref:System.TimeSpan?displayProperty=fullName>\-Werten beibehält.  
  
## Syntax  
  
```  
<TimeSpan_LegacyFormatMode    
   enabled="true|false"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribute|**Beschreibung**|  
|---------------|----------------------|  
|`enabled`|Erforderliches Attribut.<br /><br /> Gibt an, ob die Laufzeit Legacyformatierungsverhalten mit <xref:System.TimeSpan?displayProperty=fullName>\-Werten verwendet.|  
  
## Enabled\-Attribut  
  
|Wert|**Beschreibung**|  
|----------|----------------------|  
|`false`|Die Laufzeit stellt das frühere Formatierungsverhalten nicht wieder her.|  
|`true`|Die Laufzeit stellt das Legacyformatierungsverhalten wieder her.|  
  
### Untergeordnete Elemente  
 Keine.  
  
### Übergeordnete Elemente  
  
|Element|**Beschreibung**|  
|-------------|----------------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime\- und .NET Framework\-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über Laufzeitinitialisierungsoptionen.|  
  
## Hinweise  
 Ab [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] implementiert die <xref:System.TimeSpan?displayProperty=fullName>\-Struktur die <xref:System.IFormattable>\-Schnittstelle und unterstützt Formatierungsvorgänge mit standardmäßigen und benutzerdefinierten Formatzeichenfolgen.  Wenn eine Analysemethode auf einen nicht unterstützten Formatbezeichner oder eine Formatzeichenfolge stößt, wird eine <xref:System.FormatException> ausgelöst.  
  
 In früheren Versionen von .NET Framework hat die <xref:System.TimeSpan>\-Struktur <xref:System.IFormattable> nicht implementiert und hat keine Formatzeichenfolgen unterstützt.  Viele Entwickler sind jedoch fälschlicherweise davon ausgegangen, dass <xref:System.TimeSpan> einen Satz von Formatzeichenfolgen unterstützt, und haben diese in [kombinierten Formatierungsoperationen](../../../../../docs/standard/base-types/composite-formatting.md) mit Methoden wie <xref:System.String.Format%2A?displayProperty=fullName> verwendet.  Wenn ein Typ <xref:System.IFormattable> implementiert und Formatzeichenfolgen unterstützt, lösen Aufrufe von Formatierungsmethoden mit nicht unterstützten Formatzeichenfolgen normalerweise eine <xref:System.FormatException> aus.  Da <xref:System.TimeSpan> jedoch <xref:System.IFormattable> nicht implementiert hat, hat die Laufzeit die Formatzeichenfolge ignoriert und stattdessen die <xref:System.TimeSpan.ToString?displayProperty=fullName>\-Methode aufgerufen.  Dies bedeutet, dass, obwohl die Formatzeichenfolgen keine Auswirkungen auf den Formatierungsvorgang hatten, ihr Vorhandensein zu keiner <xref:System.FormatException> geführt hat.  
  
 In Fällen, in denen in Legacycode eine kombinierte Formatierungsmethode und eine ungültige Formatzeichenfolge übergeben werden und in denen dieser Code nicht neu kompiliert werden kann, können Sie das <xref:System.TimeSpan>\-Legacyverhalten mit dem `<TimeSpan_LegacyFormatMode>`\-Element wiederherstellen.  Wenn Sie das `enabled`\-Attribut dieses Elements auf `true` festlegen, führt die kombinierte Formatierungsmethode zu einem Aufruf von <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=fullName> und nicht von <xref:System.TimeSpan.ToString?displayProperty=fullName>, und eine <xref:System.FormatException> wird nicht ausgelöst.  
  
## Beispiel  
 Im folgenden Beispiel wird ein <xref:System.TimeSpan>\-Objekt instanziiert und versucht, es mit der <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=fullName>\-Methode mit einer nicht unterstützten Standardformatzeichenfolge zu formatieren.  
  
 [!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
 [!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]  
  
 Wenn Sie das Beispiel für [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] oder eine frühere Version ausführen, wird die folgende Ausgabe angezeigt:  
  
```  
12:30:45  
```  
  
 Dies unterscheidet sich deutlich von der Ausgabe, wenn Sie das Beispiel unter [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] oder der höheren Version ausführen:  
  
```  
Invalid Format  
```  
  
 Wenn Sie jedoch die folgende Konfigurationsdatei das Verzeichnis des Beispiels hinzufügen und dann das Beispiel auf [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)] oder der höheren Version ausführen, lautet die Ausgabe zu der identisch, die durch das Beispiel erzeugt wird, die auf [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] ausgeführt wird.  
  
```  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <TimeSpan_LegacyFormatMode enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## Siehe auch  
 [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)   
 [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)