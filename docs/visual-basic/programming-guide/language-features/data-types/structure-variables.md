---
title: Strukturvariablen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- structures [Visual Basic], variables
- structures [Visual Basic], structure variables
- variables [Visual Basic], structure variables
- structure variables [Visual Basic]
ms.assetid: 156872f8-aabc-4454-8e2d-f2253c3c13c9
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef42c44de84caffde909eb2b3e9361016a6abb97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="structure-variables-visual-basic"></a>Strukturvariablen (Visual Basic)
Nachdem Sie eine Struktur erstellt haben, können Sie Variablen auf Prozedurebene und auf Modulebene als diesen Typ deklarieren. Beispielsweise können Sie eine Struktur, zeichnet Informationen zu einem Computersystem erstellen. Dies wird im folgenden Beispiel veranschaulicht:  
  
```  
Public Structure systemInfo  
    Public cPU As String  
    Public memory As Long  
    Public purchaseDate As Date  
End Structure  
```  
  
 Nun können Sie Variablen dieses Typs deklarieren. Dies wird anhand die folgende Deklaration veranschaulicht.  
  
```  
Dim mySystem, yourSystem As systemInfo  
```  
  
> [!NOTE]
>  In Klassen und Module mit Strukturen deklariert die [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) standardmäßig öffentlichen Zugriff auf. Wenn Sie beabsichtigen die eine Struktur, die privat sein, sicher deklarieren Sie sie mit der [Private](../../../../visual-basic/language-reference/modifiers/private.md) Schlüsselwort.  
  
## <a name="access-to-structure-values"></a>Zugriff auf die Strukturwerte  
 Um zuzuweisen, und rufen Werte aus den Elementen einer Strukturvariablen, verwenden Sie die gleiche Syntax wie zum Festlegen und Abrufen von Eigenschaften für ein Objekt. Platzieren Sie den Memberzugriffsoperator (`.`) zwischen den Struktur-Variablennamen und den Elementnamen. Das folgende Beispiel greift auf die Elemente der zuvor als Typ deklarierten Variablen `systemInfo`.  
  
```  
mySystem.cPU = "486"  
Dim tooOld As Boolean  
If yourSystem.purchaseDate < #1/1/1992# Then tooOld = True  
```  
  
## <a name="assigning-structure-variables"></a>Zuweisen von Strukturvariablen  
 Sie können auch eine Variable auf einen anderen zuweisen, wenn vom selben Strukturtyp angehören. Kopiert alle Elemente einer Struktur in die entsprechenden Elemente in der anderen. Dies wird anhand die folgende Deklaration veranschaulicht.  
  
```  
yourSystem = mySystem  
```  
  
 Wenn ein Strukturelement einen Referenztyp darstellt, wie eine `String`, `Object`, oder Array, der Zeiger auf die Daten kopiert wird. Im vorherigen Beispiel wenn `systemInfo` hatte eine Objektvariable enthalten, und klicken Sie dann im vorherige Beispiel den Zeiger von kopiert haben, würden `mySystem` auf `yourSystem`, und eine Änderung an den Daten des Objekts durch eine Struktur wäre beim Zugriff aktiviert über die andere Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
