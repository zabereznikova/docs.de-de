---
title: "How to: Hold More Than One Value in a Variable (Visual Basic) | Microsoft Docs"
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
  - "classes [Visual Basic], composite data types"
  - "composite types"
  - "composite data types"
  - "data types [Visual Basic], composite"
  - "arrays [Visual Basic], composite data types"
  - "structures, composite data types"
  - "arrays [Visual Basic], compilation errors"
  - "types [Visual Basic], composite"
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Hold More Than One Value in a Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Einer Variablen können mehrere Werte übergeben werden, wenn sie mit einem *zusammengesetzten Datentyp* deklariert wird.  
  
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) umfassen Strukturen, Arrays und Klassen.  In einer Variablen eines zusammengesetzten Datentyps kann eine Kombination von elementaren Datentypen und anderen zusammengesetzten Typen abgelegt werden.  Strukturen und Klassen können sowohl Code als auch Daten aufnehmen.  
  
### So legen Sie mehrere Werte in einer Variablen ab  
  
1.  Legen Sie fest, welchen zusammengesetzten Datentyp Sie für die Variable verwenden möchten.  
  
2.  Wenn der zusammengesetzte Datentyp noch nicht definiert ist, definieren Sie ihn, damit er für die Variable zur Verfügung steht.  
  
    -   Definieren Sie mit einer [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md) eine Struktur.  
  
    -   Definieren Sie mit einer [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) ein Array.  
  
    -   Definieren Sie mit einer [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md) eine Klasse.  
  
3.  Deklarieren Sie mit einer `Dim`\-Anweisung die Variable.  
  
4.  Geben Sie unmittelbar nach dem Variablennamen eine `As`\-Klausel an.  
  
5.  Geben Sie unmittelbar nach dem `As`\-Schlüsselwort den Namen des entsprechenden zusammengesetzten Datentyps an.  
  
## Siehe auch  
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Type Characters](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)