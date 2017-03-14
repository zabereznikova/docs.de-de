---
title: "Array Conversions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arrays [Visual Basic], converting type"
  - "type conversion, arrays"
  - "conversions, type"
  - "arrays [Visual Basic], data types"
  - "conversions, data type"
  - "object arrays, converting type"
  - "data type conversion, array conversions"
  - "conversions, array types"
  - "object arrays"
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Array Conversions (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Ein Arraytyp kann in einen anderen Arraytyp konvertiert werden, wenn die folgenden Bedingungen zutreffen:  
  
-   **Gleicher Rang.** Die beiden Arrays müssen denselben Rang haben, d. h. die Anzahl der Dimensionen muss gleich sein.  Dabei kann die Länge der jeweiligen Dimensionen auch unterschiedlich sein.  
  
-   **Elementdatentyp.** Bei den Datentypen der Elemente beider Arrays muss es sich um Verweistypen handeln.  Sie können ein `Integer`\-Array nicht in ein `Long`\-Array oder gar in ein `Object`\-Array konvertieren, da mindestens ein Werttyp betroffen ist.  Weitere Informationen finden Sie unter [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
-   **Konvertierbarkeit.** Zwischen den Elementtypen der beiden Arrays muss eine Konvertierung \(erweiternde oder einschränkende Konvertierung\) möglich sein.  Ein Beispiel, das diese Anforderung nicht erfüllt, ist eine versuchte Konvertierung zwischen einem `String`\-Array und einem Array einer Klasse, die von <xref:System.Attribute?displayProperty=fullName> abgeleitet ist.  Diese beiden Typen haben keine Gemeinsamkeiten, sodass keinerlei Konvertierung möglich ist.  
  
 Je nachdem, ob die betreffenden Elemente erweitert oder eingeschränkt werden, wird die Konvertierung eines Arraytyps in einen anderen als erweiternde bzw. als eingrenzende Konvertierung bezeichnet.  Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## Konvertierung in ein Object\-Array  
 Wenn Sie ein `Object`\-Array deklarieren, ohne es zu initialisieren, lautet der Wert des dazugehörigen Elementtyps bis zur Initialisierung `Object`.  Wenn Sie es als Array einer bestimmten Klasse deklarieren, nimmt es den Typ dieser Klasse an.  Der zugrunde liegende Typ ist jedoch immer noch `Object`, und Sie können das Array nachfolgend als ein anderes Array einer nicht damit zusammenhängenden Klasse festlegen.  Da alle Klassen von `Object` abgeleitet werden, können Sie den Elementtyp des Arrays von einer beliebigen Klasse in eine beliebige andere Klasse ändern.  
  
 Im folgenden Beispiel findet zwischen den Typen `student` und `String` keine Konvertierung statt, aber beide werden von `Object` abgeleitet, sodass alle Zuweisungen gültig sind.  
  
```  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### Zugrunde liegender Typ eines Arrays  
 Wenn Sie ein Array ursprünglich mit einer bestimmten Klasse deklariert haben, hat sein zugrunde liegender Elementtyp diese Klasse.  Wenn Sie das Array nachfolgend als andere Klasse deklarieren muss eine Konvertierung zwischen den beiden Klassen erfolgen.  
  
 Im folgenden Beispiel ist `students` ein `student`\-Array.  Da zwischen `String` und `student` keine Konvertierung vorhanden ist, schlägt die letzte Anweisung fehl.  
  
```  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Conversions Between Strings and Other Types](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)   
 [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)