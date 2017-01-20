---
title: "SByte Data Type (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.sbyte"
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
  - "SByte data type"
ms.assetid: 5c38374a-18a1-4cc2-b493-299e3dcaa60f
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# SByte Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Speichert 8\-Bit\-\(1\-Byte\-\)Ganzzahlen mit Vorzeichen, deren Werte sich im Bereich von \-128 bis einschließlich 127 bewegen.  
  
## Hinweise  
 Verwenden Sie den `SByte`\-Datentyp für Ganzzahlwerte, die nicht die gesamte Datenbreite von `Integer` oder nicht einmal die halbe Datenbreite von `Short` erfordern.  In bestimmten Fällen werden `SByte`\-Variablen von der Common Language Runtime eventuell platzsparend gepackt, damit weniger Arbeitsspeicher belegt wird.  
  
 Der Standardwert von `SByte` ist 0 \(null\).  
  
## Programmiertipps  
  
-   **CLS\-Kompatibilität.** Der `SByte`\-Datentyp ist nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), d. h. CLS\-kompatibler Code kann keine Komponente verwenden, die diesen Datentyp nutzt.  
  
-   **Erweiterung.** Der Datentyp `SByte` wird zu `Short`, `Integer`, `Long`, `Decimal`, `Single` und `Double` erweitert.  Dies bedeutet, dass Sie `SByte` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** `SByte` hat kein Literaltypzeichen oder Typkennzeichen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.SByte?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.SByte?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)