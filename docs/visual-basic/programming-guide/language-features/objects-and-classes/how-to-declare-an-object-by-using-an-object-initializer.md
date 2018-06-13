---
title: 'Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 3a372ba91377b53c87c05976e416ca8ed55ccbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649164"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)
Objektinitialisierer ermöglichen es Ihnen, deklarieren und instanziieren Sie eine Instanz einer Klasse in einer einzelnen Anweisung. Darüber hinaus können Sie eine oder mehrere Member der Instanz zur gleichen Zeit initialisieren, ohne einen parametrisierten Konstruktor aufzurufen.  
  
 Wenn Sie einen Objektinitialisierer verwenden, um eine Instanz eines benannten Typs zu erstellen, ist der Standardkonstruktor für die Klasse aufgerufen, gefolgt von der Initialisierung der angegebenen Elemente in der Reihenfolge, die Sie angeben.  
  
 Das folgende Verfahren zeigt, wie zum Erstellen einer Instanz von einem `Student` Klasse auf drei verschiedene Arten. Die Klasse verfügt über Vorname, Nachname und Jahr von Klasseneigenschaften o. ä. Jede dieser drei Deklarationen erstellt eine neue Instanz der `Student`, mit der Eigenschaft `First` legen Sie auf "Michael,"-Eigenschaft `Last` auf "Tucker verbleibenden" und alle anderen Mitglieder auf ihre Standardwerte festgelegt. Das Ergebnis jeder Deklaration im Verfahren entspricht im folgenden Beispiel, das einen Objektinitialisierer nicht verwendet.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 Eine Implementierung der `Student` Klasse, finden Sie unter [Vorgehensweise: Erstellen Sie eine Liste der Elemente](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Kopieren Sie den Code aus diesem Thema richten Sie die Klasse, und erstellen eine Liste der `Student` Objekten arbeiten.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>So erstellen ein Objekt einer benannten Klasse mithilfe eines Objektinitialisierers  
  
1.  Beginnen Sie die Deklaration, als ob Sie einen Konstruktor verwenden geplant.  
  
     `Dim student1 As New Student`  
  
2.  Geben Sie das Schlüsselwort `With`, gefolgt von einer Initialisierungsliste in geschweiften Klammern.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  Verfügen Sie in der Initialisierungsliste über jede Eigenschaft, die Sie initialisieren und ihm einen Anfangswert zuweisen möchten. Der Name der Eigenschaft ist ein Punkt vorangestellt.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     Sie können eine oder mehrere Member der Klasse initialisieren.  
  
4.  Alternativ können Sie eine neue Instanz der Klasse deklarieren, und klicken Sie dann einen Wert zuweisen. Deklarieren Sie zuerst eine Instanz von `Student`:  
  
     `Dim student2 As Student`  
  
5.  Beginnen Sie mit der Erstellung einer Instanz von `Student` auf die übliche Weise.  
  
     `Dim student2 As Student = New Student`  
  
6.  Typ `With` , und klicken Sie dann mit einem Objektinitialisierer initialisiert werden, mindestens Mitglied der neuen Instanz.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  Sie können die Definition im vorherigen Schritt vereinfachen, indem das Auslassen `As Student`. Wenn Sie dies tun, wird der Compiler bestimmt, die `student3` ist eine Instanz der `Student` mithilfe von lokalen Typrückschluss.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
