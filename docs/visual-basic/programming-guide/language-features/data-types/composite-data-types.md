---
title: "Composite Data Types (Visual Basic) | Microsoft Docs"
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
  - "classes [Visual Basic], composite types"
  - "types [Visual Basic], composite"
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Composite Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Zusätzlich zu den in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] verfügbaren elementaren Datentypen können Sie auch Elemente unterschiedlicher Typen zusammenstellen und so *zusammengesetzte Datentypen* wie Strukturen, Arrays und Klassen bilden.  Sie können zusammengesetzte Datentypen aus elementaren Typen und aus anderen zusammengesetzten Typen erstellen.  So können Sie z. B. ein Array von Strukturelementen oder eine Struktur mit Arraymembern erstellen.  
  
## Datentypen  
 Zusammengesetzte Typen unterscheiden sich vom Datentyp ihrer Komponenten.  So hat ein Array von `Integer`\-Elementen nicht den Datentyp `Integer`.  
  
 Der Datentyp eines Arrays wird normalerweise mithilfe des Elementtyps, runder Klammern und, falls erforderlich, Kommas dargestellt.  Beispielsweise wird ein eindimensionales Array von `String`\-Elementen in der Form `String()` dargestellt. Ein zweidimensionales Array von `Boolean`\-Elementen wird durch `Boolean(,)` angegeben.  
  
## Strukturtypen  
 Es gibt nicht einen einzelnen Datentyp, der alle Strukturen umfasst.  Stattdessen stellt jede Definition einer Struktur einen eindeutigen Datentyp dar, auch wenn in den Definitionen zweier Strukturen die gleichen Elemente in derselben Reihenfolge angegeben werden.  Wenn Sie jedoch zwei oder mehr Instanzen derselben Struktur erstellen, werden sie in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] als Strukturen desselben Typs behandelt.  
  
## Arraytypen  
 Es gibt keinen universellen Datentyp, der sich für alle Arrays eignet.  Der Datentyp einer bestimmten Instanz eines Arrays richtet sich nach den folgenden Faktoren:  
  
-   Der Tatsache, dass es sich hierbei um ein Array handelt  
  
-   Dem Rang \(Anzahl der Dimensionen\) des Arrays  
  
-   Dem Elementtyp des Arrays  
  
 Als Besonderheit ist anzumerken, dass die Länge einer gegebenen Dimension nicht Teil des Datentyps der Instanz ist.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 Im vorigen Beispiel wird davon ausgegangen, dass die Arrayvariablen `arrayA` und `arrayB` zum selben Datentyp gehören \(`Byte()`\), obwohl sie mit unterschiedlichen Längen initialisiert wurden.  Die Variablen `arrayB` und `arrayC` gehören nicht zum gleichen Typ, da ihre Elemente unterschiedlichen Typs sind.  Die Variablen `arrayC` und `arrayD` gehören nicht zum gleichen Typ, da ihre Ränge unterschiedlich sind.  Obwohl `arrayD` noch nicht initialisiert wurde, gehören die Variablen `arrayD` und `arrayE` zum gleichen Typ \(`Short(,)`\), weil ihr Rang und der Datentyp ihrer Elemente gleich sind.  
  
 Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Klassentypen  
 Es gibt keinen einzelnen Datentyp, der alle Klassen umfasst.  Obwohl eine Klasse von einer anderen Klasse erben kann, ist jede ein separater Datentyp.  Mehrere Instanzen der gleichen Klasse gehören zum gleichen Datentyp.  Wenn eine Klasseninstanzvariable einer anderen Klasseninstanzvariablen zugewiesen wird, gehören die Variablen nicht nur zum gleichen Datentyp, sondern verweisen auch auf dieselbe Klasseninstanz im Speicher.  
  
 Weitere Informationen zu Klassen finden Sie unter [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [How to: Hold More Than One Value in a Variable](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)