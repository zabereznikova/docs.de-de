---
title: Partielle Methoden (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.PartialMethod
- PartialMethod
helpviewer_keywords:
- custom logic into code [Visual Basic]
- partial methods [Visual Basic]
- partial [Visual Basic], methods [Visual Basic]
- methods [Visual Basic], partial methods
- inserting custom logic into code
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
ms.openlocfilehash: 765a667f18340c53909c3ff1e9fcc5f2ffc0f9bc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791936"
---
# <a name="partial-methods-visual-basic"></a>Partielle Methoden (Visual Basic)
Partielle Methoden können Entwickler benutzerdefinierte Logik in Code einfügen. In der Regel ist der Code Teil einer vom Designer generierten Klasse. Partielle Methoden werden in einer partiellen Klasse, die von einem Codegenerator erstellt wird definiert, und sie werden häufig verwendet, um die Benachrichtigung angeben, dass etwas geändert wurde. Sie können Entwickler benutzerdefiniertes Verhalten als Reaktion auf die Änderung angeben.  
  
 Der Designer des Code-Generators werden nur die Signatur der Methode und eine oder mehrere Aufrufe der Methode definiert. Entwickler können dann Implementierungen für die Methode bereitstellen, wenn sie das Verhalten des generierten Codes anpassen möchten. Wenn keine Implementierung bereitgestellt wird, werden Aufrufe der Methode durch den Compiler, sodass keine zusätzlichen Leistungsaufwand entfernt.  
  
## <a name="declaration"></a>Deklaration  
 Der generierte Code markiert die Definition einer partiellen Methode dem Schlüsselwort `Partial` am Anfang der Zeile für Unterschrift.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 Die Definition muss die folgenden Bedingungen erfüllen:  
  
- Die Methode muss eine `Sub`, sondern eine `Function`.  
  
- Der Text der Methode muss leer sein.  
  
- Der Zugriffsmodifizierer muss `Private`.  
  
## <a name="implementation"></a>Implementierung  
 Die Implementierung besteht in erster Linie im Text der partiellen Methode zu füllen. Die Implementierung ist in der Regel in einer separaten partiellen Klasse aus der Definition und wird von einem Entwickler, der den generierten Code erweitern möchte geschrieben.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 Im vorherige Beispiel dupliziert die Signatur in der Deklaration genau allerdings Variationen möglich sind. Vor allem anderen Modifizierer hinzugefügt werden, z. B. `Overloads` oder `Overrides`. Nur ein `Overrides` -Modifizierer ist zulässig. Weitere Informationen zu Methodenmodifizierer, finden Sie unter [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Mit  
 Sie eine partielle Methode aufrufen, wie jede andere würde `Sub` Verfahren. Wenn die Methode implementiert wurde, wird die Argumente werden ausgewertet, und der Text der Methode wird ausgeführt. Beachten Sie jedoch, dass eine partielle Methode implementieren optional ist. Wenn die Methode nicht implementiert wird, ein Aufruf hat keine Auswirkungen und Ausdrücke, die als Argumente an die Methode übergeben werden nicht ausgewertet.  
  
## <a name="example"></a>Beispiel  
 In einer Datei mit dem Namen Product.Designer.vb, definieren eine `Product` -Klasse, verfügt eine `Quantity` Eigenschaft.  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 Geben Sie in einer Datei mit dem Namen Product.vb eine Implementierung für `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 Deklarieren Sie schließlich in der Main-Methode eines Projekts eine `Product` -Instanz, und geben Sie einen Anfangswert für die `Quantity` Eigenschaft.  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 Ein Meldungsfeld sollte angezeigt, in dem diese Meldung angezeigt:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Siehe auch

- [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Optionale Parameter](./optional-parameters.md)
- [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)
- [Codegenerierung in LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
