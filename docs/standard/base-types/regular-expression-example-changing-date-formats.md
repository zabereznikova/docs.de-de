---
title: "Beispiel f&#252;r regul&#228;re Ausdr&#252;cke: &#196;ndern von Datumsformaten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Suchen mit regulären Ausdrücken, Beispiele"
  - "Analysieren von Text mit regulären Ausdrücken, Beispiele"
  - "Reguläre Ausdrücke, Beispiele"
  - "Reguläre Ausdrücke von .NET Framework, Beispiele"
  - "Reguläre Ausdrücke [.NET Framework], Beispiele"
  - "Musterabgleich mit regulären Ausdrücken, Beispiele"
ms.assetid: 5fcc75a5-09d7-45ae-a4c0-9ad6085ac83d
caps.latest.revision: 19
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 19
---
# Beispiel f&#252;r regul&#228;re Ausdr&#252;cke: &#196;ndern von Datumsformaten
Im folgenden Codebeispiel wird die <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=fullName>\-Methode, um Datumsangaben zu ersetzen, die das Formular *mm*\/*dd*\/*yy* mit Datumsangaben verfügen, die das Formular *dd*\-*mm*\-*yy*.  
  
## Beispiel  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#1)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#1)]  
  
 Im folgenden Code wird gezeigt, wie die `MDYToDMY`\-Methode in einer Anwendung aufgerufen werden kann.  
  
 [!code-csharp[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/csharp/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/cs/Example_ChangeDateFormats1.cs#2)]
 [!code-vb[RegularExpressions.Examples.ChangeDateFormats#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/RegularExpressions.Examples.ChangeDateFormats/vb/Example_ChangeDateFormats1.vb#2)]  
  
## Kommentare  
 Das Muster für reguläre Ausdrücke `\b(?<month>\d{1,2})/(?<day>\d{1,2})/(?<year>\d{2,4})\b` wird entsprechend der folgenden Tabelle interpretiert:  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(?<month>\d{1,2})`|Entsprechung für eine oder zwei Dezimalstellen finden.  Dies ist die Erfassungsgruppe `month`.|  
|`/`|Entsprechung für den Schrägstrich finden.|  
|`(?<day>\d{1,2})`|Entsprechung für eine oder zwei Dezimalstellen finden.  Dies ist die Erfassungsgruppe `day`.|  
|`/`|Entsprechung für den Schrägstrich finden.|  
|`(?<year>\d{2,4})`|Vergleich von zwei bis vier Dezimalstellen.  Dies ist die Erfassungsgruppe `year`.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
 Mit dem Muster `${day}-${month}-${year}` wird die Ersetzungszeichenfolge gemäß der Darstellung in der folgenden Tabelle definiert.  
  
|Muster|**Beschreibung**|  
|------------|----------------------|  
|`$(day)`|Fügen Sie die von der Erfassungsgruppe `day` erfasste Zeichenfolge hinzu.|  
|`-`|Fügen Sie einen Bindestrich hinzu.|  
|`$(month)`|Fügen Sie die von der Erfassungsgruppe `month` erfasste Zeichenfolge hinzu.|  
|`-`|Fügen Sie einen Bindestrich hinzu.|  
|`$(year)`|Fügen Sie die von der Erfassungsgruppe `year` erfasste Zeichenfolge hinzu.|  
  
## Siehe auch  
 [Reguläre Ausdrücke von .NET Framework](../../../docs/standard/base-types/regular-expressions.md)