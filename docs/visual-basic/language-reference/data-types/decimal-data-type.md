---
title: "Decimal Data Type (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Decimal"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "literal type characters, D"
  - "trailing zeros"
  - "real numbers"
  - "trailing 0 characters"
  - "Decimal data type"
  - "D literal type character"
  - "decimals, Decimal data type"
  - "0 characters, trailing"
  - "data types [Visual Basic], assigning"
  - "decimal keyword"
  - "numbers, real"
  - "variable-precision numbers"
  - "zeros, trailing"
  - "@ identifier type character"
  - "identifier type characters, @"
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Decimal Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Speichert 128\-Bit \(16\-Byte\)\-Werte mit Vorzeichen, die 96\-Bit \(12\-Bytes\)\-Ganzzahlnummern darstellen, deren Einteilung durch eine variable Zehnerpotenz erfolgt.  Der Skalierungsfaktor gibt die Anzahl der Ziffern rechts neben dem Dezimaltrennzeichen an. Sie reicht von 0 bis 28.  Bei einer Skala von 0 \(keine Dezimalstellen\) ist der größtmögliche Wert \+\/\-79,228,162,514,264,337,593,543,950,335 \(\+\/\-7.9228162514264337593543950335E\+28\).  Bei 28 Dezimalstellen ist der größte Wert \+\/\-7,9228162514264337593543950335, und der kleinste Wert ungleich 0 \(null\) ist \+\/\-0.0000000000000000000000000001 \(\+\/\-1E\-28\).  
  
## Hinweise  
 Der `Decimal`\-Datentyp stellt die größte Anzahl von signifikaten Stellen für eine Zahl bereit.  Er unterstützt bis zu 29 signifikante Stellen und kann Werte über 7.9228 x 10^28 darstellen.  Er eignet sich besonders für Berechnungen, die sehr viele Stellen erfordern und bei denen keine Rundungsfehler auftreten dürfen \(z. B. finanzielle Berechnungen\).  
  
 Der Standardwert von `Decimal` ist 0 \(null\).  
  
## Programmiertipps  
  
-   **Genauigkeit.** `Decimal` ist kein Gleitkommadatentyp.  Die `Decimal`\-Struktur enthält einen binären ganzzahligen Wert zusammen mit einem Vorzeichenbit und einem Skalierungsfaktor, der festlegt, welcher Teil des Werts ein Dezimalbruch ist.  Deswegen verfügen `Decimal`\-Zahlen über eine genauere Darstellung im Arbeitsspeicher als Gleitkommatypen \(`Single` und `Double`\).  
  
-   **Leistung.** Der `Decimal`\-Datentyp wird unter allen numerischen Typen am langsamsten verarbeitet.  Wägen Sie vor der Wahl eines Datentyps die Kriterien Genauigkeit und Leistung gegeneinander ab.  
  
-   **Erweiterung.** Der `Decimal`\-Datentyp wird zu `Single` oder `Double` erweitert.  Dies bedeutet, dass Sie `Decimal` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Nachgestellte Nullen.** Visual Basic speichert keine nacfolgenden Nullen in einem `Decimal`\-Literal.  Eine `Decimal`\-Variable behält jedoch alle nachgestellten Nullen bei, die aus Berechnungen resultieren.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
    ```  
    Dim d1, d2, d3, d4 As Decimal  
    d1 = 2.375D  
    d2 = 1.625D  
    d3 = d1 + d2  
    d4 = 4.000D  
    MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &  
          ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))  
    ```  
  
     Im vorausgehenden Beispiel lautet die Ausgabe von `MsgBox` wie folgt:  
  
     d1 \= 2.375, d2 \= 1.625, d3 \= 4.000, d4 \= 4  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `D` an ein Literal wird der `Decimal`\-Datentyp erzwungen.  Durch Anhängen des Typkennzeichens `@` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Decimal`\-Datentyp erzwungen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Decimal?displayProperty=fullName>\-Struktur.  
  
## Bereich  
 Sie müssen möglicherweise das `D`\-Typzeichen verwenden, um einer `Decimal`\-Variablen oder einer Konstanten einen großen Wert zuzuweisen.  Diese Anforderung ist, da der Compiler ein Literal als `Long`, es sei denn, ein Literalzeichen dem Literal folgt, wie im folgenden Beispiel gezeigt interpretiert.  
  
```  
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.  
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.  
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.  
```  
  
 Die Deklaration für `bigDec1` keinen Überlauf, da der Wert, der zugewiesen wird, innerhalb des Bereichs für `Long` fällt.  Der `Long`\-Wert kann zur `Decimal`\-Variablen zugewiesen werden.  
  
 Die Deklaration für `bigDec2` generiert einen Sammelfehler, da der Wert, der zugewiesen wird, für `Long` zu groß ist.  Da das numerische Literal nicht als `Long` zuerst interpretiert werden kann, kann es nicht zur `Decimal`\-Variablen zugewiesen werden.  
  
 Für `bigDec3` löst das Literaltypzeichen `D` das Problem, indem Sie den Compiler anweisen, die das Literal als `Decimal` statt als `Long` zu interpretieren.  
  
## Siehe auch  
 <xref:System.Decimal?displayProperty=fullName>   
 <xref:System.Decimal.%23ctor%2A?displayProperty=fullName>   
 <xref:System.Math.Round%2A?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Single Data Type](../../../visual-basic/language-reference/data-types/single-data-type.md)   
 [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)