---
title: "Single Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Single"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Single data type"
  - "F literal type character"
  - "trailing zeros"
  - "real numbers"
  - "literal type characters, F"
  - "trailing 0 characters"
  - "identifier type characters, !"
  - "single-precision numbers"
  - "! identifier type character"
  - "0 characters, trailing"
  - "data types [Visual Basic], assigning"
  - "floating-point numbers, Single data type"
  - "numbers, real"
  - "zeros, trailing"
  - "numbers, floating point"
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Single Data Type (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Enthält 32\-Bit\-\(4\-Byte\-\)Gleitkommazahlen mit Vorzeichen mit einfacher Genauigkeit nach IEEE. Die Werte reichen von –3,4028235E\+38 bis –1,401298E–45 für negative Werte und von 1,401298E–45 bis 3,4028235E\+38 für positive Werte.  Zahlen mit einfacher Genauigkeit enthalten eine Näherung einer reellen Zahl.  
  
## Hinweise  
 Verwenden Sie den `Single`\-Datentyp für Gleitkommawerte, die nicht die volle Datenbreite von `Double` benötigen.  In bestimmten Fällen werden `Single`\-Variablen von der Common Language Runtime eventuell platzsparend gepackt, damit weniger Arbeitsspeicher belegt wird.  
  
 Der Standardwert von `Single` ist 0.  
  
## Programmiertipps  
  
-   **Genauigkeit.** Wenn Sie mit Gleitkommazahlen arbeiten, sollten Sie beachten, dass sie im Arbeitsspeicher nicht immer präzise dargestellt werden.  Dies kann bei bestimmten Operationen zu unerwarteten Ergebnissen führen, z. B. beim Wertvergleich und beim Operator `Mod`.  Weitere Informationen finden Sie unter [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Erweiterung.** Der `Single`\-Datentyp wird zu `Double` erweitert.  Dies bedeutet, dass Sie `Single` in `Double` konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Nachgestellte Nullen.** Die Gleitkommadatentypen verfügen über keine interne Darstellung von nachgestellten Nullen.  Sie unterscheiden zum Beispiel nicht zwischen 4,2000 und 4,2.  Daher werden nachgestellte Nullen nicht dargestellt, wenn Sie Gleitkommawerte anzeigen oder drucken.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `F` an ein Literal wird der `Single`\-Datentyp erzwungen.  Durch Anhängen des Typkennzeichens `!` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Single`\-Datentyp erzwungen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Single?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.Single?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Decimal Data Type](../../../visual-basic/language-reference/data-types/decimal-data-type.md)   
 [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)