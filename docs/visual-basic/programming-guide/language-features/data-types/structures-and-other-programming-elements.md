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
ms.openlocfilehash: 73d3f999e95c484dff3f5409f2cdb9032b64fe38
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266858"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>Strukturen und andere Programmierelemente (Visual Basic)
Sie können Strukturen in Verbindung mit Arrays, Objekten und Prozeduren sowie miteinander verwenden. Die Interaktionen verwenden die gleiche Syntax, die diese Elemente einzeln verwenden.  
  
> [!NOTE]
> Sie können keines der Strukturelemente in der Strukturdeklaration initialisieren. Sie können Werte nur Elementen einer Variablen zuweisen, die als Strukturtyp deklariert wurde.  
  
## <a name="structures-and-arrays"></a>Strukturen und Arrays  
 Eine Struktur kann ein Array als eines oder mehrere seiner Elemente enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure
```  
  
 Sie greifen auf die Werte eines Arrays innerhalb einer Struktur auf die gleiche Weise zu wie sie auf eine Eigenschaft für ein Objekt zugreifen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 Sie können auch ein Array von Strukturen deklarieren. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 Sie befolgen dieselben Regeln, um auf die Komponenten dieser Datenarchitektur zuzugreifen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>Strukturen und Objekte  
 Eine Struktur kann ein Objekt als eines oder mehrere seiner Elemente enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 Sie sollten eine bestimmte Objektklasse in einer `Object`solchen Deklaration anstelle von verwenden.  
  
## <a name="structures-and-procedures"></a>Strukturen und Verfahren  
 Sie können eine Struktur als Prozedurargument übergeben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 Im obigen Beispiel wird die Struktur *als Verweis*übergibt, wodurch die Prozedur ihre Elemente so ändern kann, dass die Änderungen im aufrufenden Code wirksam werden. Wenn Sie eine Struktur vor einer solchen Änderung schützen möchten, übergeben Sie sie an den Wert.  
  
 Sie können auch eine `Function` Struktur aus einer Prozedur zurückgeben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
  
 Sie können diese Technik auch verwenden, um eine Struktur zu kapseln, die in einem Modul innerhalb einer Struktur definiert ist, die in einem anderen Modul definiert ist.  
  
 Strukturen können andere Strukturen bis zu einer beliebigen Tiefe enthalten.  
  
## <a name="see-also"></a>Weitere Informationen

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementary Data Types (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Composite Data Types (Visual Basic)](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Strukturvariablen](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)
