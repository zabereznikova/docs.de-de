---
title: 'Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: ae04d338b61027c3917ad3a7f62ff40f0a95e53e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347138"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Gewusst wie: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)
Objektinitialisierer ermöglichen es Ihnen, eine Instanz einer Klasse in einer einzelnen Anweisung zu deklarieren und zu instanziieren. Außerdem können Sie einen oder mehrere Member der-Instanz gleichzeitig initialisieren, ohne einen parametrisierten Konstruktor aufzurufen.  
  
 Wenn Sie einen Objektinitialisierer verwenden, um eine Instanz eines benannten Typs zu erstellen, wird der Parameter lose Konstruktor für die Klasse aufgerufen, gefolgt von der Initialisierung der designierten Elemente in der von Ihnen angegebenen Reihenfolge.  
  
 Im folgenden Verfahren wird gezeigt, wie Sie eine Instanz einer `Student`-Klasse auf drei verschiedene Arten erstellen. Die Klasse verfügt unter anderem über die Eigenschaften "Vorname", "Nachname" und "Klassen Jahr". Jede der drei Deklarationen erstellt eine neue Instanz `Student`, bei der die-`First` Eigenschaft auf "Michael" festgelegt ist, die-`Last` Eigenschaft auf "Tucker" festgelegt ist und alle anderen Member auf ihre Standardwerte festgelegt sind. Das Ergebnis jeder Deklaration in der Prozedur entspricht dem folgenden Beispiel, in dem kein Objektinitialisierer verwendet wird.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Eine Implementierung der `Student`-Klasse finden Sie unter Gewusst [wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Sie können den Code aus diesem Thema kopieren, um die-Klasse einzurichten und eine Liste mit `Student` Objekten zu erstellen, mit denen Sie arbeiten möchten.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>So erstellen Sie ein Objekt einer benannten Klasse mithilfe eines Objektinitialisierers  
  
1. Beginnen Sie die Deklaration, als ob Sie einen Konstruktor verwenden möchten.  
  
     `Dim student1 As New Student`  
  
2. Geben Sie das Schlüsselwort `With`ein, gefolgt von einer Initialisierungs Liste in geschweiften Klammern.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. Fügen Sie in der Initialisierungs Liste jede Eigenschaft ein, die Sie initialisieren möchten, und weisen Sie Ihr einen Anfangswert zu. Dem Namen der Eigenschaft wird ein Zeitraum vorangestellt.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     Sie können einen oder mehrere Member der-Klasse initialisieren.  
  
4. Alternativ können Sie eine neue Instanz der Klasse deklarieren und ihr dann einen Wert zuweisen. Deklarieren Sie zuerst eine Instanz von `Student`:  
  
     `Dim student2 As Student`  
  
5. Beginnen Sie mit der Erstellung einer Instanz von `Student` auf die übliche Weise.  
  
     `Dim student2 As Student = New Student`  
  
6. Geben Sie `With` und dann einen Objektinitialisierer ein, um einen oder mehrere Member der neuen Instanz zu initialisieren.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. Sie können die Definition im vorherigen Schritt vereinfachen, indem Sie `As Student`weglassen. Wenn Sie dies tun, bestimmt der Compiler, dass `student3` eine Instanz von `Student` ist, indem der lokale Typrückschluss verwendet wird.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Weitere Informationen finden Sie unter [lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>Siehe auch

- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Gewusst wie: Erstellen einer Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
