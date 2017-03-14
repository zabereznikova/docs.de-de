---
title: "Integer Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Integer"
  - "Integer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "numbers, whole"
  - "enumerated values"
  - "whole numbers"
  - "integral data types"
  - "integer numbers"
  - "numbers, integer"
  - "integers, data types"
  - "literal type characters, I"
  - "integers, types"
  - "data types [Visual Basic], integral"
  - "% identifier type character"
  - "data types [Visual Basic], assigning"
  - "identifier type characters, %"
  - "I literal type character"
  - "Integer data type"
ms.assetid: a8f233b4-4be3-455c-861b-05af2fbb6c60
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Integer Data Type (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Speichert 32\-Bit\-\(4\-Byte\-\)Ganzzahlen mit Vorzeichen, deren Werte sich im Bereich von \-2.147.483.648 bis einschließlich 2.147.483.647 bewegen.  
  
## Hinweise  
 Der `Integer`\-Datentyp bietet in Verbindung mit einem 32\-Bit\-Prozessor eine optimale Leistung.  Die anderen ganzzahligen Typen werden langsamer in den Arbeitsspeicher geladen und im Arbeitsspeicher gespeichert bzw. langsamer aus dem Arbeitsspeicher geladen.  
  
 Der Standardwert von `Integer` lautet 0.  
  
## Programmiertipps  
  
-   **Interop\-Überlegungen.** Wenn Sie Komponenten anbinden, die nicht für .NET Framework geschrieben wurden \(z. B. Automatisierungs\- oder COM\-Objekte\), müssen Sie beachten, dass `Integer` in anderen Umgebungen eine andere Datenbreite hat \(16 Bit\).  Wenn Sie ein 16\-Bit\-Argument an eine solche Komponente übergeben, deklarieren Sie es im neuen Visual Basic\-Code als `Short` und nicht als `Integer`.  
  
-   **Erweiterung.** Der `Integer`\-Datentyp wird zu `Long`, `Decimal`, `Single` oder `Double` erweitert.  Dies bedeutet, dass Sie `Integer` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `I` an ein Literal wird der `Integer`\-Datentyp erzwungen.  Durch Anhängen des Typkennzeichens `%` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Integer`\-Datentyp erzwungen.  
  
-   **Framework\-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int32?displayProperty=fullName>\-Struktur.  
  
## Bereich  
 Wenn Sie für eine Variable mit Ganzzahltyp eine Zahl festlegen, die außerhalb des Bereichs für diesen Typ liegt, tritt ein Fehler auf.  Wenn Sie versuchen, sie auf einen Bruch festzulegen, wird die Zahl auf den nächsten ganzzahligen Wert auf\- oder abgerundet.  Wenn die Zahl zwei Ganzzahlwerten gleichermaßen nahe ist, wird der Wert auf die nächste gerade ganze Zahl gerundet.  So werden Rundungsfehler reduziert, die sich beim einheitlichen Runden von in der Mitte liegenden Werten in nur eine Richtung ergeben.  Der folgende Code zeigt Beispiele für eine Rundung.  
  
```  
' The valid range of an Integer variable is -2147483648 through +2147483647.  
Dim k As Integer  
' The following statement causes an error because the value is too large.  
k = 2147483648  
' The following statement sets k to 6.  
k = 5.9  
' The following statement sets k to 4  
k = 4.5  
' The following statement sets k to 6  
' Note, Visual Basic uses banker’s rounding (toward nearest even number)  
k = 5.5  
```  
  
## Siehe auch  
 <xref:System.Int32?displayProperty=fullName>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md)   
 [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)