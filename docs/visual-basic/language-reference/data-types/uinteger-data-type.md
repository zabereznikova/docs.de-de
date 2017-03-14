---
title: "UInteger Data Type | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.uinteger"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "numbers, whole"
  - "UInteger data type"
  - "literal type characters, UI"
  - "whole numbers"
  - "integral data types"
  - "integer numbers"
  - "numbers, integer"
  - "integers, data types"
  - "integers, types"
  - "UI literal type characters"
  - "data types [Visual Basic], integral"
ms.assetid: db7ddd34-4f23-46f5-84dd-8b0f83bb8729
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# UInteger Data Type
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Speichert 32\-Bit\-\(4\-Byte\-\)Ganzzahlen ohne Vorzeichen mit einem Wert zwischen 0 und 4.294.967.295.  
  
## Hinweise  
 Der `UInteger`\-Datentyp stellt den größten Wert ohne Vorzeichen in der rationellsten Datenbreite bereit.  
  
 Der Standardwert von `UInteger` ist 0 \(null\).  
  
## Programmiertipps  
 Der `UInteger`\-Datentyp und der `Integer`\-Datentyp bieten auf einem 32\-Bit\-Prozessor optimale Leistung, weil das Laden, Speichern und Abrufen der kleineren ganzzahligen Typen \(`UShort`, `Short`, `Byte` und `SByte`\) länger dauert, obwohl bei diesen Typen weniger Bits verwendet werden.  
  
-   **Negative Zahlen.** Da `UInteger` ein Typ ohne Vorzeichen ist, kann er keine negativen Zahlen darstellen.  Wenn Sie den unären Minusoperator \(`-`\) in einem Ausdruck verwenden, der vom Typ `UInteger` ist, wandelt Visual Basic den Ausdruck zunächst in den `Long`\-Typ um.  
  
-   **CLS\-Kompatibilität.** Der `UInteger`\-Datentyp ist nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), d. h. CLS\-kompatibler Code kann keine Komponente verwenden, die diesen Datentyp nutzt.  
  
-   **Interop\-Überlegungen.** Wenn eine Schnittstelle mit Komponenten vorhanden ist, die nicht für .NET Framework geschrieben wurden \(z. B. Automatisierungs\- oder COM\-Objekte\), ist zu beachten, dass Typen wie `uint` in anderen Umgebungen eine andere Datenbreite \(16 Bit\) haben können.  Wenn Sie ein 16\-Bit\-Argument an eine solche Komponente übergeben, deklarieren Sie es im verwalteten Visual Basic\-Code als `UShort` und nicht als `UInteger`.  
  
-   **Erweiterung.** Der Datentyp `UInteger` wird zu `Long`, `ULong`, `Decimal`, `Single` und `Double` erweitert.  Dies bedeutet, dass Sie `UInteger` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen der Literaltypzeichen `UI` an ein Literal wird der `UInteger`\-Datentyp erzwungen.  `UInteger` hat kein Typkennzeichen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt32?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.UInt32>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)