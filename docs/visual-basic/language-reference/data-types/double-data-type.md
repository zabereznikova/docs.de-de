---
title: "Double Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Double"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "identifier type characters, #"
  - "trailing zeros"
  - "real numbers"
  - "trailing 0 characters"
  - "0 characters, trailing"
  - "literal type characters, R"
  - "data types [Visual Basic], assigning"
  - "Double data type [Visual Basic]"
  - "# identifier type character"
  - "double-precision numbers"
  - "floating-point numbers, Double data type"
  - "R literal type character"
  - "zeros, trailing"
  - "Double data type"
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Double Data Type (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Speichert 64\-Bit\-\(8\-Byte\-\)Gleitkommazahlen mit Vorzeichen und doppelter Genauigkeit nach IEEE. Die Werte reichen von \-1,79769313486231570E\+308 bis \-4,94065645841246544E\-324 für negative Werte und von 4,94065645841246544E\-324 bis 1,79769313486231570E\+308 für positive Werte.  Zahlen mit doppelter Genauigkeit enthalten eine Näherung einer reellen Zahl.  
  
## Hinweise  
 Der `Double`\-Datentyp stellt die größten und kleinsten möglichen Werte für eine Zahl bereit.  
  
 Der Standardwert von `Double` ist 0 \(null\).  
  
## Programmiertipps  
  
-   **Genauigkeit.** Wenn Sie mit Gleitkommazahlen arbeiten, müssen Sie daran denken, dass die Zahlen im Speicher nicht immer präzise dargestellt werden.  Dies kann bei bestimmten Operationen zu unerwarteten Ergebnissen führen, z. B. beim Wertvergleich und beim Operator `Mod`.  Weitere Informationen finden Sie unter [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Nachgestellte Nullen.** Die Gleitkommadatentypen verfügen über keine interne Darstellung von nachgestellten Nullen.  Sie unterscheiden zum Beispiel nicht zwischen 4,2000 und 4,2.  Daher werden nachgestellte Nullen nicht dargestellt, wenn Sie Gleitkommawerte anzeigen oder drucken.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `R` an ein Literal wird der `Double`\-Datentyp erzwungen.  Wenn beispielsweise einem ganzzahligen Wert `R` folgt, wird der Wert in ein `Double` geändert.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     Durch Anhängen des Typkennzeichens `#` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Double`\-Datentyp erzwungen.  Im folgenden Beispiel wird die Variable `num` als `Double` behandelt:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Double?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.Double?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Decimal Data Type](../../../visual-basic/language-reference/data-types/decimal-data-type.md)   
 [Single Data Type](../../../visual-basic/language-reference/data-types/single-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)