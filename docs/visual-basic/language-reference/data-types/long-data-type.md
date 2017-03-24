---
title: "Long Data Type (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Long"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "identifier type characters, &"
  - "numbers, whole"
  - "whole numbers"
  - "integral data types"
  - "& identifier type character"
  - "integer numbers"
  - "literal type characters, L"
  - "numbers, integer"
  - "integers, data types"
  - "L literal type character"
  - "integers, types"
  - "Long keyword"
  - "data types [Visual Basic], integral"
  - "data types [Visual Basic], assigning"
  - "Long data type"
ms.assetid: b4770c34-1804-4f8c-b512-c10b0893e516
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Long Data Type (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Speichert 64\-Bit\-\(8\-Byte\-\)Ganzzahlen mit Vorzeichen, deren Werte sich im Bereich von \-9.223.372.036.854.775.808 bis einschließlich 9.223.372.036.854.775.807 \(9,2... E\+18\) bewegen.  
  
## Hinweise  
 Verwenden Sie den `Long`\-Datentyp zum Speichern ganzer Zahlen, die für den `Integer`\-Datentyp zu groß sind.  
  
 Der Standardwert von `Long` ist 0 \(null\).  
  
## Programmiertipps  
  
-   **Interop\-Überlegungen.** Wenn Sie Komponenten anbinden, die nicht für .NET Framework geschrieben wurden \(z. B. Automatisierungs\- oder COM\-Objekte\), müssen Sie beachten, dass `Long` in anderen Umgebungen eine andere Datenbreite hat \(32 Bit\).  Wenn Sie ein 32\-Bit\-Argument an eine solche Komponente übergeben, deklarieren Sie es im neuen Visual Basic\-Code als `Integer` und nicht als `Long`.  
  
     Darüber hinaus unterstützt die Automatisierung keine 64\-Bit\-Ganzzahlen unter Windows 95, Windows 98, Windows Me oder Windows 2000.  Sie können unter diesen Betriebssystemen kein `Long`\-Argument in Visual Basic an eine Automatisierungskomponente übergeben.  
  
-   **Erweiterung.** Der `Long`\-Datentyp wird zu `Decimal`, `Single` oder `Double` erweitert.  Dies bedeutet, dass Sie `Long` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=fullName>\-Fehler auftritt.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `L` an ein Literal wird der `Long`\-Datentyp erzwungen.  Durch Anhängen des Typkennzeichens `&` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Long`\-Datentyp erzwungen.  
  
-   **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Int64?displayProperty=fullName>\-Struktur.  
  
## Siehe auch  
 <xref:System.Int64>   
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)