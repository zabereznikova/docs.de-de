---
title: "UShort Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ushort"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "numbers, whole"
  - "literal type characters, US"
  - "whole numbers"
  - "integral data types"
  - "integer numbers"
  - "numbers, integer"
  - "integers, data types"
  - "integers, types"
  - "data types [Visual Basic], integral"
  - "UShort data type"
  - "US literal type characters"
ms.assetid: 138db892-665d-4ba8-9cae-d8d91c4a8f39
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# UShort Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Enthält 16\-Bit\-\(2\-Byte\-\)Ganzzahlen ohne Vorzeichen im Wertebereich von 0 bis 65.535.  
  
## Hinweise  
 Verwenden Sie den `UShort`\-Datentyp für Binärdaten, die für `Byte` zu groß sind.  
  
 Der Standardwert von `UShort` ist 0 \(null\).  
  
## Programmiertipps  
  
-   **Negative Zahlen.** Da `UShort` ein Typ ohne Vorzeichen ist, kann er keine negativen Zahlen darstellen.  Wenn Sie den unären Minusoperator \(`-`\) in einem Ausdruck verwenden, der vom Typ `UShort` ist, wandelt Visual Basic den Ausdruck zunächst in den `Integer`\-Typ um.  
  
-   **CLS\-Kompatibilität.** Der `UShort`\-Datentyp ist nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), d. h. CLS\-kompatibler Code kann keine Komponente verwenden, die diesen Datentyp nutzt.  
  
-   **Erweiterung.** Der `UShort`\-Datentyp wird zu `Integer`, `UInteger`, `Long`, `ULong`, `Decimal`, `Single` und `Double` erweitert.  Dies bedeutet, dass Sie `UShort` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen der Literaltypzeichen `US` an ein Literal wird der `UShort`\-Datentyp erzwungen.  `UShort` hat kein Typkennzeichen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt16?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.UInt16>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)