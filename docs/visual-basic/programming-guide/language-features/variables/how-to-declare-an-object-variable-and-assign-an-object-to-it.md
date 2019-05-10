---
title: 'Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: e172d62e5bfadded254d5a5fd25b1dcf2da9634d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663584"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic
Sie deklarieren eine Variable, der die [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) durch Angabe `As Object` in eine [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md). Sie können ein Objekt auf eine solche Variable zuweisen, platzieren Sie das Objekt hinter dem Gleichheitszeichen (`=`) in einer Zuweisung-Anweisung oder Initialisierung-Klausel.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine `Object` -Variable und weist dieser aktuellen Instanz.  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 Sie können die Deklaration und Zuweisung kombinieren, durch die Variable als Teil der Deklaration initialisieren. Das folgende Beispiel entspricht dem vorherigen Beispiel.  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System>-Namespace  
  
- Eine Klasse, Struktur oder Modul, in dem Platzieren der `Dim` Anweisung.  
  
- Eine Prozedur, in dem die zuweisungsanweisung abgelegt werden sollen.  
  
## <a name="see-also"></a>Siehe auch

- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Object-Datentyp](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
