---
title: 'Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 314706207800b2e86aa0032a52d8c50fbb726887
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58825135"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Vorgehensweise: Deklarieren eines Objekts mithilfe eines Objektinitialisierers (Visual Basic)
Objektinitialisierer ermöglichen Sie deklarieren und instanziieren Sie eine Instanz einer Klasse in einer einzigen Anweisung. Darüber hinaus können Sie eine oder mehrere Member der Instanz zur gleichen Zeit, initialisieren, ohne einen parametrisierten Konstruktor aufzurufen.  
  
 Wenn Sie einen Objektinitialisierer verwenden, um eine Instanz eines benannten Typs erstellen, wird der Standardkonstruktor für die Klasse aufgerufen, gefolgt von der Initialisierung der angegebenen Member in der Reihenfolge, in die Sie angeben.  
  
 Das folgende Verfahren zeigt, wie zum Erstellen einer Instanz von einem `Student` Klasse auf drei verschiedene Arten. Die Klasse verfügt über Vorname, Nachname und Jahr Klasseneigenschaften, u. a. Jede dieser drei Deklarationen erstellt eine neue Instanz der `Student`, mit der Eigenschaft `First` legen Sie auf "Michael,"-Eigenschaft `Last` "Tucker" festgelegt, und alle anderen Elemente auf ihre Standardwerte festgelegt. Das Ergebnis jeder Deklaration in der Prozedur entspricht im folgenden Beispiel, das einen Objektinitialisierer nicht verwendet.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Eine Implementierung der `Student` Klasse, finden Sie unter [Vorgehensweise: Erstellen Sie eine Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). Kopieren Sie den Code in diesem Thema richten Sie die Klasse, und erstellen eine Liste der `Student` Objekte zusammenarbeiten.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>So erstellen Sie ein Objekt einer benannten Klasse mit einem Objektinitialisierer  
  
1.  Beginnen Sie die Deklaration, als ob Sie einen Konstruktor nutzen will.  
  
     `Dim student1 As New Student`  
  
2.  Geben Sie das Schlüsselwort `With`, gefolgt von einer Initialisierungsliste in geschweiften Klammern.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  Enthalten Sie in der Initialisierungsliste jede Eigenschaft, die Sie verwenden möchten, initialisieren und einen Anfangswert zuweisen. Der Name der Eigenschaft wird ein Punkt voranstehen.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     Sie können eine oder mehrere Member der Klasse initialisieren.  
  
4.  Alternativ können Sie eine neue Instanz der Klasse deklarieren, und klicken Sie dann einen Wert zuzuweisen. Deklarieren Sie zuerst eine Instanz von `Student`:  
  
     `Dim student2 As Student`  
  
5.  Beginnen Sie mit der Erstellung einer Instanz von `Student` auf die übliche Weise.  
  
     `Dim student2 As Student = New Student`  
  
6.  Typ `With` und klicken Sie dann einen Objektinitialisierer zum Initialisieren von Membern von ein oder mehrere der neuen Instanz.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7.  Sie können die Definition im vorherigen Schritt vereinfachen, indem das Auslassen `As Student`. Wenn Sie dies tun, wird der Compiler bestimmt, die `student3` ist eine Instanz der `Student` mithilfe von lokalen Typrückschluss.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Weitere Informationen finden Sie unter [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>Siehe auch

- [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Vorgehensweise: Erstellen Sie eine Liste von Elementen](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
