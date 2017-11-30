---
title: Strukturen und andere Programmierelemente (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: de343c06ec255d6cb68aa25d733e85385e884769
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>Strukturen und andere Programmierelemente (Visual Basic)
Sie können Strukturen in Verbindung mit Arrays, Objekten und Prozeduren sowie miteinander verwenden. Die Interaktionen verwenden dieselbe Syntax wie diese Elemente einzeln zu verwenden.  
  
> [!NOTE]
>  Sie können nicht der Struktur Elemente in der Strukturdeklaration initialisiert werden. Sie können nur auf Elemente in einer Variablen Werte zuweisen, die einen Strukturtyp deklariert wurde.  
  
## <a name="structures-and-arrays"></a>Strukturen und Arrays  
 Eine Struktur kann es sich um ein Array als eine oder mehrere Elemente enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 Sie greifen die Werte eines Arrays in einer Struktur genau wie Sie eine Eigenschaft für ein Objekt zuzugreifen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 Sie können auch ein Array von Strukturen deklarieren. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 Sie gelten dieselben Regeln für den Zugriff auf die Komponenten dieser Daten-Architektur. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>Strukturen und Objekte  
 Eine Struktur kann es sich um ein Objekt als ein oder mehrere Elemente enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 Verwenden Sie eine bestimmte Objektklasse in einer solchen Deklaration statt `Object`.  
  
## <a name="structures-and-procedures"></a>Strukturen und Prozeduren  
 Sie können eine Struktur wie eines Prozedurarguments übergeben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 Das obige Beispiel übergibt die Struktur *Verweisübergabe*, dadurch wird die Prozedur seine Elemente zu ändern, sodass die Änderungen im aufrufenden Code wirksam. Wenn Sie eine Struktur für eine solche Änderung schützen möchten, als Wert übergeben.  
  
 Sie können eine Struktur als auch Zurückgeben einer `Function` Prozedur. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim allSystems(100) As systemInfo  
Function findByDate(ByVal searchDate As Date) As systemInfo  
    Dim i As Integer  
    For i = 1 To 100  
        If allSystems(i).purchaseDate = searchDate Then Return allSystems(i)  
    Next i  
   ' Process error: system with desired purchase date not found.  
End Function  
```  
  
## <a name="structures-within-structures"></a>Strukturen innerhalb von Strukturen  
 Strukturen können andere Strukturen enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
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
  
```vb  
Dim allSystems(100) As systemInfo  
ReDim allSystems(1).diskDrives(3)  
allSystems(1).diskDrives(0).type = "Floppy"  
```  
  
 Diese Technik können auch um eine Struktur, die in einem Modul in einer Struktur in einem anderen Modul definierten definierte zu kapseln.  
  
 Strukturen können andere Strukturen in beliebiger Tiefe enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Strukturvariablen](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
