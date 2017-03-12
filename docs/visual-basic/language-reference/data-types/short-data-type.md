---
title: "Short Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Short"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "numbers, whole"
  - "whole numbers"
  - "integral data types"
  - "integer numbers"
  - "numbers, integer"
  - "integers, data types"
  - "integers, types"
  - "data types [Visual Basic], integral"
  - "S literal type character"
  - "Short data type"
  - "literal type characters, S"
ms.assetid: 65fcbcf3-a841-400e-885e-301497729a8b
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Short Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Speichert 16\-Bit\-\(2\-Byte\-\)Ganzzahlen mit Vorzeichen, deren Werte sich im Bereich von \-32.768 bis einschließlich 32.767 bewegen.  
  
## Hinweise  
 Verwenden Sie den `Short`\-Datentyp für Ganzzahlwerte, die nicht die volle Datenbreite von `Integer` benötigen.  In bestimmten Fällen werden `Short`\-Variablen von der Common Language Runtime stark komprimiert, damit weniger Arbeitsspeicher belegt wird.  
  
 Der Standardwert von `Short` ist 0 \(null\).  
  
## Programmiertipps  
  
-   **Erweiterung.** Der `Short`\-Datentyp wird zu `Integer`, `Long`, `Decimal`, `Single` oder `Double` erweitert.  Dies bedeutet, dass Sie `Short` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `S` an ein Literal wird der `Short`\-Datentyp erzwungen.  `Short` hat kein Typkennzeichen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int16?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.Int16?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)