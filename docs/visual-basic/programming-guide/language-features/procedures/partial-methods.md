---
title: Partielle Methoden
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
ms.openlocfilehash: 61a1398ba7de8dab005fa1e9efa13dc2ba18cc3c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364122"
---
# <a name="partial-methods-visual-basic"></a>Partielle Methoden (Visual Basic)
Mit partiellen Methoden können Entwickler benutzerdefinierte Logik in den Code einfügen. In der Regel ist der Code Teil einer vom Designer generierten Klasse. Partielle Methoden werden in einer partiellen Klasse definiert, die von einem Code Generator erstellt wird, und Sie werden häufig verwendet, um Benachrichtigungen bereitzustellen, dass etwas geändert wurde. Sie ermöglichen es dem Entwickler, als Reaktion auf die Änderung benutzerdefiniertes Verhalten anzugeben.  
  
 Der Designer des Code-Generators definiert nur die Methoden Signatur und mindestens einen Aufruf der-Methode. Entwickler können dann Implementierungen für die-Methode bereitstellen, wenn Sie das Verhalten des generierten Codes anpassen möchten. Wenn keine Implementierung bereitgestellt wird, werden Aufrufe der-Methode durch den Compiler entfernt, was zu keinem zusätzlichen Leistungs Aufwand führt.  
  
## <a name="declaration"></a>Deklaration  
 Der generierte Code markiert die Definition einer partiellen Methode, indem das Schlüsselwort `Partial` am Anfang der Signatur Zeile platziert wird.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 Die Definition muss die folgenden Bedingungen erfüllen:  
  
- Die-Methode muss ein `Sub` und keine sein `Function` .  
  
- Der Text der Methode muss leer gelassen werden.  
  
- Der Zugriffsmodifizierer muss sein `Private` .  
  
## <a name="implementation"></a>Implementierung  
 Die-Implementierung besteht hauptsächlich aus dem Ausfüllen des Texts der partiellen-Methode. Die Implementierung befindet sich in der Regel in einer separaten partiellen Klasse von der Definition und wird von einem Entwickler geschrieben, der den generierten Code erweitern möchte.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 Im vorherigen Beispiel wird die Signatur in der Deklaration genau dupliziert, aber Variationen sind möglich. Insbesondere können andere modifiziererer hinzugefügt werden, z `Overloads` . b `Overrides` . oder. `Overrides`Es ist nur ein Modifizierer zulässig. Weitere Informationen über methodenmodifiziererer finden Sie [unter Sub-Anweisung](../../../language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Zweck  
 Sie sollten eine partielle Methode wie jede andere Prozedur aufzurufen `Sub` . Wenn die-Methode implementiert wurde, werden die Argumente ausgewertet, und der Text der Methode wird ausgeführt. Beachten Sie jedoch, dass die Implementierung einer partiellen Methode optional ist. Wenn die Methode nicht implementiert wird, hat ein-aufrufsvorgang keine Auswirkung, und Ausdrücke, die als Argumente an die-Methode übermittelt werden, werden nicht ausgewertet.  
  
## <a name="example"></a>Beispiel  
 Definieren Sie in einer Datei mit dem Namen Product. Designer. vb eine `Product` Klasse, die über eine- `Quantity` Eigenschaft verfügt.  
  
 [!code-vb[VbVbalrPartialMeths#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#4)]  
  
 Stellen Sie in einer Datei mit dem Namen Product. vb eine Implementierung für bereit `QuantityChanged` .  
  
 [!code-vb[VbVbalrPartialMeths#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#5)]  
  
 Deklarieren Sie schließlich in der Main-Methode eines Projekts eine `Product` -Instanz, und geben Sie einen Anfangswert für die zugehörige- `Quantity` Eigenschaft an.  
  
 [!code-vb[VbVbalrPartialMeths#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrPartialMeths/VB/Class1.vb#6)]  
  
 Daraufhin wird ein Meldungs Feld angezeigt, in dem diese Meldung angezeigt wird:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Weitere Informationen

- [Sub-Anweisung](../../../language-reference/statements/sub-statement.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Optionale Parameter](./optional-parameters.md)
- [Partial](../../../language-reference/modifiers/partial.md)
- [Codegenerierung in LINQ to SQL](../../../../framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden](../../../../framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
