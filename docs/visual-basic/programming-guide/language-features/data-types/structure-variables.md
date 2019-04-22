---
title: Strukturvariablen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
ms.openlocfilehash: 9a6e542e297a17f44d929235530ae6058cf13a36
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816329"
---
# <a name="structure-variables-visual-basic"></a>Strukturvariablen (Visual Basic)
Nachdem Sie eine Struktur erstellt haben, können Sie Variablen auf Prozedurebene und auf Modulebene wie dieser Typ deklarieren. Beispielsweise können Sie eine Struktur, zeichnet Informationen zu einem Computersystem erstellen. Dies wird im folgenden Beispiel veranschaulicht:  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 Nun können Sie die Variablen dieses Typs deklarieren. Dies wird in die folgende Deklaration veranschaulicht.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  In Klassen und Modulen, Strukturen deklariert mit dem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) standardmäßig öffentlichen Zugriff auf. Wenn Sie eine Struktur privat festlegen möchten deklarieren Sie sie mithilfe, der [Private](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselwort.  
  
## <a name="access-to-structure-values"></a>Zugriff auf die Strukturwerte  
 Zum Zuweisen und Abrufen von Werten aus den Elementen einer Strukturvariablen, verwenden Sie die gleiche Syntax wie zum Festlegen und Abrufen von Eigenschaften für ein Objekt. Platzieren Sie den Memberzugriffsoperator (`.`) zwischen der Name der Struktur und der Elementname. Das folgende Beispiel greift auf die Elemente der zuvor als Typ deklarierten Variablen `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>Zuweisen von Strukturvariablen  
 Sie können auch eine Variable in einen anderen zuweisen, wenn vom selben Strukturtyp angehören. Dies kopiert alle Elemente einer Struktur in die entsprechenden Elemente im anderen. Dies wird in die folgende Deklaration veranschaulicht.  
  
```  
yourSystem = mySystem  
```  
  
 Wenn ein Strukturelement einen Referenztyp darstellt, z. B. eine `String`, `Object`, oder ein Array, das Zeiger auf die Daten werden kopiert. Im vorherigen Beispiel wenn `systemInfo` hatte eine Objektvariable enthalten, und klicken Sie dann im vorherigen Beispiel wird den Zeiger von kopiert haben, würden `mySystem` zu `yourSystem`, und eine Änderung an den Daten des Objekts durch eine Struktur wäre in Kraft, beim Zugriff auf über die andere Struktur.  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
