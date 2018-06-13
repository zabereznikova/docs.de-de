---
title: 'Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 1f38c90f0571b3fc73c4c89812092cdada936d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648875"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Gewusst wie: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic
Sie deklarieren eine Variable vom der [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md) durch Angabe `As Object` in einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md). Sie können ein Objekt auf eine solche Variable zuweisen, durch das Objekt hinter dem Gleichheitszeichen aufzunehmen (`=`) in einer Zuordnung-Anweisung oder Initialisierung-Klausel.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine `Object` -Variable und weist dieser aktuellen Instanz.  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 Sie können die Deklaration und Zuweisung kombinieren, durch die Initialisierung der Variablen als Teil der Deklaration. Im folgende Beispiel entspricht im vorangehenden Beispiel.  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Einen Verweis auf den <xref:System>-Namespace  
  
-   Eine Klasse, Struktur oder Modul, in dem Ablegen der `Dim` Anweisung.  
  
-   Eine Prozedur, in dem die zuweisungsanweisung abgelegt werden soll.  
  
## <a name="see-also"></a>Siehe auch  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
