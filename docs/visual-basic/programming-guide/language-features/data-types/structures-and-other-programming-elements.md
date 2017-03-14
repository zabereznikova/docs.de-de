---
title: "Structures and Other Programming Elements (Visual Basic) | Microsoft Docs"
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
  - "structures, arrays"
  - "procedures, structures as arguments to"
  - "objects [Visual Basic], structure elements"
  - "arrays [Visual Basic], structure elements"
  - "nested structures"
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Structures and Other Programming Elements (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können Strukturen gemeinsam mit Arrays, Objekten und Prozeduren sowie miteinander verwenden.  Die Interaktionen verwenden dieselbe Syntax, die diese Elemente einzeln verwenden.  
  
> [!NOTE]
>  Es ist nicht möglich, Strukturelemente in der Strukturdeklaration zu initialisieren.  Sie können nur denjenigen Elementen einer Variablen Werte zuweisen, die als Strukturtyp deklariert wurden.  
  
## Strukturen und Arrays  
 Ein Array kann innerhalb einer Struktur ein oder mehrere Elemente darstellen.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```vb#  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 Der Zugriff auf die Werte eines Arrays innerhalb einer Struktur erfolgt wie der Zugriff auf die Eigenschaft eines Objekts.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```vb#  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 Sie können auch ein Array von Strukturen deklarieren.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```vb#  
Dim allSystems(100) As systemInfo  
```  
  
 Für den Zugriff auf die Komponenten dieser Datenarchitektur gelten die gleichen Regeln.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```vb#  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## Strukturen und Objekte  
 Ein Objekt kann innerhalb einer Struktur ein oder mehrere Elemente darstellen.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```vb#  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 Anstelle von `Object` sollten Sie in einer solchen Deklaration ein bestimmtes Objekt verwenden.  
  
## Strukturen und Prozeduren  
 Sie können eine Struktur als Prozedurargument übergeben.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```vb#  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 Im vorangegangenen Beispiel wird die Struktur *durch einen Verweis* übergeben, wodurch die Prozedur deren Elemente so verändern kann, dass die Änderungen im Aufrufcode wirksam werden.  Wenn Sie eine Struktur vor solchen Änderungen schützen möchten, übergeben Sie sie durch einen Wert.  
  
 Sie können auch eine Struktur von einer `Function`\-Prozedur zurückgeben.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```vb#  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## Strukturen innerhalb von Strukturen  
 Strukturen können andere Strukturen enthalten.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
```vb#  
Public Structure driveInfo  
    Public type As String  
    Public size As Long  
End Structure  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As driveInfo  
    Public purchaseDate As Date  
End Structure  
```  
  
```vb#  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 Mit diesem Verfahren können Sie eine in einem Modul definierte Struktur in einer Struktur kapseln, die in einem anderen Modul definiert ist.  
  
 Strukturen können beliebig viele andere Strukturen enthalten.  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [How to: Declare a Structure](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Structure Variables](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)   
 [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)