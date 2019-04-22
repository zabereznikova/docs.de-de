---
title: Strukturen und andere Programmierelemente (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], arrays
- procedures [Visual Basic], structures as arguments to
- objects [Visual Basic], structure elements
- arrays [Visual Basic], structure elements
- nested structures [Visual Basic]
ms.assetid: 0f849313-ccd2-4c9a-acb9-69de6751c088
ms.openlocfilehash: a943bbdec617ba6c95685df3a4fcdb36b52def22
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819108"
---
# <a name="structures-and-other-programming-elements-visual-basic"></a>Strukturen und andere Programmierelemente (Visual Basic)
Sie können die Strukturen in Verbindung mit Arrays, Objekte und Verfahren sowie anderen verwenden. Die Interaktionen verwenden dieselbe Syntax wie diese Elemente einzeln verwenden.  
  
> [!NOTE]
>  Alle Elemente der Struktur in der Strukturdeklaration kann nicht initialisiert werden. Sie können Werte nur für Elemente, die einer Variablen zuweisen, die auf einen Strukturtyp deklariert wurde.  
  
## <a name="structures-and-arrays"></a>Strukturen und Arrays  
 Eine Struktur kann es sich um ein Array als ein oder mehrere Elemente enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public diskDrives() As String  
    Public purchaseDate As Date  
End Structure   
```  
  
 Sie Zugriff auf die Werte eines Arrays innerhalb einer Struktur, die gleiche Weise, die Sie Zugriff auf eine Eigenschaft eines Objekts. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim mySystem As systemInfo  
ReDim mySystem.diskDrives(3)  
mySystem.diskDrives(0) = "1.44 MB"  
```  
  
 Sie können auch ein Array von Strukturen deklarieren. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim allSystems(100) As systemInfo  
```  
  
 Sie gelten dieselben Regeln für den Zugriff auf die Komponenten dieser Data-Architektur. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
ReDim allSystems(5).diskDrives(3)  
allSystems(5).CPU = "386SX"  
allSystems(5).diskDrives(2) = "100M SCSI"  
```  
  
## <a name="structures-and-objects"></a>Strukturen und Objekte  
 Eine Struktur kann es sich um ein Objekt als eine oder mehrere Elemente enthalten. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Protected Structure userInput  
    Public userName As String  
    Public inputForm As System.Windows.Forms.Form  
    Public userFileNumber As Integer  
End Structure  
```  
  
 Verwenden Sie eine bestimmte Objektklasse in einer solchen Deklaration statt `Object`.  
  
## <a name="structures-and-procedures"></a>Strukturen und Prozeduren  
 Sie können eine Struktur als ein Prozedurargument übergeben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Public currentCPUName As String = "700MHz Pentium compatible"  
Public currentMemorySize As Long = 256  
Public Sub fillSystem(ByRef someSystem As systemInfo)  
    someSystem.cPU = currentCPUName  
    someSystem.memory = currentMemorySize  
    someSystem.purchaseDate = Now  
End Sub  
```  
  
 Im vorherige Beispiel übergibt der Struktur *als Verweis*, dadurch, dass die Prozedur die Elemente zu ändern, sodass die Änderungen im aufrufenden Code wirksam. Wenn Sie eine Struktur vor solchen Änderungen schützen möchten, können übergeben sie als Wert.  
  
 Sie können auch eine Struktur von Zurückgeben einer `Function` Verfahren. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
  
 Sie können dieses Verfahren auch verwenden, zum Kapseln einer Struktur, die in einem Modul innerhalb einer Struktur, die definiert, die in einem anderen Modul definiert.  
  
 Strukturen können andere Strukturen in beliebiger Tiefe enthalten.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Strukturvariablen](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
