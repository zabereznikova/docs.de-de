---
title: "Structure Variables (Visual Basic) | Microsoft Docs"
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
  - "structures, variables"
  - "structures, structure variables"
  - "variables [Visual Basic], structure variables"
  - "structure variables"
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Structure Variables (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn Sie eine Struktur erstellt haben, können Sie für diesen Typ Variablen auf Prozedurebene und Variablen auf Modulebene deklarieren.  Zum Beispiel können Sie eine Struktur erstellen, in der Informationen über ein Computersystem aufgezeichnet werden.  Das folgende Beispiel veranschaulicht dies.  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 Nun können Sie Variablen dieses Typs deklarieren.  Dies wird aus der folgenden Deklaration ersichtlich.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  In Klassen und Modulen gilt für Strukturen, die mit einer [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) deklariert werden, standardmäßig der Public\-Zugriff.  Wenn Sie für eine Struktur den Private\-Zugriff festlegen möchten, deklarieren Sie sie mit dem Schlüsselwort [Private](../../../../visual-basic/language-reference/modifiers/private.md).  
  
## Zugriff auf Strukturwerte  
 Zum Zuweisen und Abrufen der Werte von den Elementen einer Strukturvariablen verwenden Sie dieselbe Syntax wie zum Festlegen und Abrufen von Eigenschaften für ein Objekt.  Sie fügen den Memberzugriffsoperator \(`.`\) zwischen den Strukturvariablennamen und den Elementnamen ein.  Im folgenden Beispiel wird auf Elemente der Variablen zugegriffen, die zuvor als `systemInfo`\-Typ deklariert wurden.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## Zuweisen von Strukturvariablen  
 Sie können auch eine Variable einer anderen zuordnen, wenn beide denselben Strukturtyp haben.  Damit werden alle Elemente einer Struktur in die entsprechenden Elemente der anderen Struktur kopiert.  Dies wird aus der folgenden Deklaration ersichtlich.  
  
```  
yourSystem = mySystem  
```  
  
 Wenn es sich bei einem Strukturelement um einen Verweistyp handelt \(z. B. `String`, `Object` oder Array\), wird der Zeiger auf die Daten kopiert.  Würde `systemInfo` im vorherigen Beispiel eine Objektvariable enthalten, wäre der Zeiger im vorigen Beispiel von `mySystem` nach `yourSystem` kopiert worden, und eine Änderung der Objektdaten durch eine Struktur wäre beim Zugriff über die andere Struktur wirksam geworden.  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)