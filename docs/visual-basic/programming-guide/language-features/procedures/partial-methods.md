---
title: Partielle Methoden (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 975a86e33eb5744f94cd58efb227bf52eb07c1e8
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2017
---
# <a name="partial-methods-visual-basic"></a>Partielle Methoden (Visual Basic)
Partielle Methoden können Entwickler benutzerdefinierten Logik in Code einzufügen. In der Regel ist der Code Teil einer vom Designer generierte Klasse. Partielle Methoden werden in einer partiellen Klasse, die von einem Codegenerator erstellt wird definiert, und sie werden häufig verwendet, um die Benachrichtigung angeben, dass etwas geändert wurde. Sie ermöglichen es den Entwickler, die benutzerdefiniertes Verhalten als Reaktion auf die Änderung angeben.  
  
 Der Designer des Code-Generators definiert nur die Signatur der Methode und eine oder mehrere Aufrufe der Methode. Entwickler können dann Implementierungen für die Methode bereitstellen, wenn sie das Verhalten des generierten Codes anpassen möchten. Wenn keine Implementierung bereitgestellt wird, werden Aufrufe der Methode durch den Compiler, wodurch keine zusätzliche Leistung beansprucht entfernt.  
  
## <a name="declaration"></a>Deklaration  
 Der generierte Code kennzeichnet die Definition einer partiellen Methode, indem dem Schlüsselwort `Partial` am Anfang der Signaturzeile.  
  
```vb  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 Die Definition muss die folgenden Bedingungen erfüllen:  
  
-   Die Methode muss ein `Sub`, sondern eine `Function`.  
  
-   Der Text der Methode muss leer sein.  
  
-   Der Zugriffsmodifizierer muss `Private`.  
  
## <a name="implementation"></a>Implementierung  
 Die Implementierung besteht im Wesentlichen aus im Text der partiellen Methode zu füllen. Die Implementierung ist in der Regel in einer eigenen partiellen Klasse aus der Definition und durch ein Entwickler möchte, erweitern den generierten Code geschrieben wird.  
  
```vb  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 Im vorherigen Beispiel wird die Signatur in der Deklaration genau dupliziert allerdings Varianten sind möglich. Insbesondere weiteren Modifizierer können hinzugefügt werden, z. B. `Overloads` oder `Overrides`. Nur ein `Overrides` -Modifizierer ist zulässig. Weitere Informationen zur Methodenmodifizierer finden Sie unter [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="use"></a>Verwendung  
 Sie eine partielle Methode aufrufen, wie jeder andere würde `Sub` Prozedur. Wenn die Methode implementiert wurde, die Argumente ausgewertet werden, und der Text der Methode wird ausgeführt. Beachten Sie jedoch, dass eine partielle Methode implementieren optional ist. Wenn die Methode nicht implementiert wird, ein Aufruf hat keine Auswirkungen, und Ausdrücke, die als Argumente an die Methode übergeben werden nicht ausgewertet.  
  
## <a name="example"></a>Beispiel  
 In einer Datei namens Product.Designer.vb, definieren eine `Product` -Klasse, verfügt ein `Quantity` Eigenschaft.  
  
 [!code-vb[VbVbalrPartialMeths#4](./codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 Stellen Sie in einer Datei mit dem Namen Product.vb eine Implementierung für `QuantityChanged`.  
  
 [!code-vb[VbVbalrPartialMeths#5](./codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 Deklarieren Sie schließlich in die Main-Methode eines Projekts eine `Product` Instanz, und geben Sie einen Anfangswert für seine `Quantity` Eigenschaft.  
  
 [!code-vb[VbVbalrPartialMeths#6](./codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 Ein Meldungsfeld sollte angezeigt, in dem diese Meldung angezeigt:  
  
 `Quantity was changed to 100`  
  
## <a name="see-also"></a>Siehe auch  
 [Sub-Anweisung](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Sub-Prozeduren](./sub-procedures.md)  
 [Optionale Parameter](./optional-parameters.md)  
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Codegenerierung in LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [Hinzufügen von Geschäftslogik durch Verwenden partieller Methoden](../../../../../docs/framework/data/adonet/sql/linq/adding-business-logic-by-using-partial-methods.md)
