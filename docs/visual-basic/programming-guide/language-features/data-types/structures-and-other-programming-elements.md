---
title: Strukturen und andere Programmierelemente
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: 309d0e5214897675e1758bd98b964392b379ca1b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346119"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>Strukturen und andere Programmierelemente (Visual Basic)
Sie können Strukturen in Verbindung mit Arrays, Objekten und Prozeduren sowie untereinander verwenden. Die Interaktionen verwenden die gleiche Syntax wie diese Elemente einzeln verwenden.  
  
> [!NOTE]
> Sie können keines der Structure-Elemente in der Struktur Deklaration initialisieren. Sie können Werte nur Elementen einer Variablen zuweisen, die als Strukturtyp deklariert wurde.  
  
## <a name="structures-and-arrays"></a>Strukturen und Arrays  
 Eine Struktur kann ein Array als ein oder mehrere Elemente enthalten. Das folgende Beispiel veranschaulicht dies.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 Sie greifen auf die Werte eines Arrays innerhalb einer Struktur auf die gleiche Weise zu, wie Sie auf eine Eigenschaft in einem Objekt zugreifen. Das folgende Beispiel veranschaulicht dies.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 Sie können auch ein Array von-Strukturen deklarieren. Das folgende Beispiel veranschaulicht dies.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 Sie befolgen die gleichen Regeln für den Zugriff auf die Komponenten dieser Datenarchitektur. Das folgende Beispiel veranschaulicht dies.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>Strukturen und Objekte  
 Eine Struktur kann ein Objekt als ein oder mehrere Elemente enthalten. Das folgende Beispiel veranschaulicht dies.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 Sie sollten eine bestimmte Objektklasse in einer solchen Deklaration anstelle von `Object`verwenden.  
  
## <a name="structures-and-procedures"></a>Strukturen und Prozeduren  
 Sie können eine Struktur als Prozedur Argument übergeben. Das folgende Beispiel veranschaulicht dies.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 Im vorangehenden Beispiel wird die Struktur als *Verweis*weitergeleitet, sodass die Prozedur die Elemente ändern kann, sodass die Änderungen im aufrufenden Code wirksam werden. Wenn Sie eine Struktur vor solchen Änderungen schützen möchten, übergeben Sie Sie als Wert.  
  
 Sie können auch eine Struktur aus einer `Function` Prozedur zurückgeben. Das folgende Beispiel veranschaulicht dies.  
  
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
 Strukturen können andere Strukturen enthalten. Das folgende Beispiel veranschaulicht dies.  
  
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
  
 Sie können dieses Verfahren auch verwenden, um eine Struktur zu kapseln, die in einem Modul innerhalb einer Struktur definiert ist, die in einem anderen Modul definiert ist.  
  
 Strukturen können andere Strukturen in beliebiger Tiefe enthalten.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Strukturvariablen](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
