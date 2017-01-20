---
title: "ULong Data Type (Visual Basic) | Microsoft Docs"
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
  - "vb.ulong"
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
  - "literal type characters, UL"
  - "ULong data type"
  - "UL literal type characters"
ms.assetid: 017e0702-774e-44ae-bedc-786b424ca84e
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ULong Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Speichert 64\-Bit\-\(8\-Byte\-\)Ganzzahlen ohne Vorzeichen mit Werten zwischen 0 und 18.446.744.073.709.551.615 \(mehr als 1,84 Mal 10 ^ 19\).  
  
## Hinweise  
 Verwenden Sie den `ULong`\-Datentyp, um Binärdaten zu speichern, die zu groß für `UInteger` sind, oder verwenden Sie die größtmöglichen vorzeichenlosen ganzzahligen Werte.  
  
 Der Standardwert von `ULong` ist 0 \(null\).  
  
## Programmiertipps  
  
-   **Negative Zahlen.** Da `ULong` ein Typ ohne Vorzeichen ist, kann er keine negativen Zahlen darstellen.  Wenn Sie den unären Minusoperator \(`-`\) in einem Ausdruck verwenden, der vom Typ `ULong` ist, wandelt Visual Basic den Ausdruck zunächst in den `Decimal`\-Typ um.  
  
-   **CLS\-Kompatibilität.** Der `ULong`\-Datentyp ist nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\), d. h. CLS\-kompatibler Code kann keine Komponente verwenden, die diesen Datentyp nutzt.  
  
-   **Interop\-Überlegungen.** Wenn eine Schnittstelle mit Komponenten vorhanden ist, die nicht für .NET Framework geschrieben wurden \(z. B. Automatisierungs\- oder COM\-Objekte\), ist zu beachten, dass Typen wie `ulong` in anderen Umgebungen eine andere Datenbreite \(32 Bit\) haben können.  Wenn Sie ein 32\-Bit\-Argument an eine solche Komponente übergeben, deklarieren Sie es im verwalteten Visual Basic\-Code als `UInteger` und nicht als `ULong`.  
  
     Darüber hinaus unterstützt die Automatisierung keine 64\-Bit\-Ganzzahlen unter Windows 95, Windows 98, Windows Me oder Windows 2000.  Sie können auf diesen Plattformen kein `ULong`\-Argument in Visual Basic an eine Automatisierungskomponente übergeben.  
  
-   **Erweiterung.** Der `ULong`\-Datentyp wird zu `Decimal`, `Single` und `Double` erweitert.  Dies bedeutet, dass Sie `ULong` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen der Literaltypzeichen `UL` an ein Literal wird der `ULong`\-Datentyp erzwungen.  `ULong` hat kein Typkennzeichen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.UInt64?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.UInt64>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)