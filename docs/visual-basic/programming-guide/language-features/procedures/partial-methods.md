---
title: "Partial Methods (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.PartialMethod"
  - "PartialMethod"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "custom logic into code [Visual Basic]"
  - "partial methods [Visual Basic]"
  - "partial, methods [Visual Basic]"
  - "methods [Visual Basic], partial methods"
  - "inserting custom logic into code"
ms.assetid: 74b3368b-b348-44a0-a326-7d7dc646f4e9
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Partial Methods (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit partiellen Methoden können Entwickler benutzerdefinierte Logik in Code einfügen.  In der Regel ist der Code Teil einer vom Designer generierten Klasse.  Partielle Methoden werden in einer partiellen Klasse definiert, die von einem Code\-Generator erstellt wird. Sie werden im Allgemeinen verwendet, um Benachrichtigungen über Änderungen bereitzustellen.  Sie ermöglichen es dem Entwickler, eine benutzerdefinierte Reaktion auf eine Änderung anzugeben.  
  
 Vom Designer des Code\-Generators werden nur die Methodensignatur und ein oder mehrere Aufrufe für die Methode definiert.  Anschließend können Entwickler Implementierungen für die Methode bereitstellen, wenn sie das Verhalten des generierten Codes anpassen möchten.  Wenn keine Implementierung bereitgestellt wird, werden Aufrufe der Methode vom Compiler entfernt, sodass kein überflüssiger Leistungsverlust auftritt.  
  
## Deklaration  
 Im generierten Code wird die Definition einer partiellen Methode am Anfang der Signatur mit dem Schlüsselwort `Partial` gekennzeichnet.  
  
```vb#  
Partial Private Sub QuantityChanged()  
End Sub  
```  
  
 Die Definition muss die folgenden Bedingungen erfüllen:  
  
-   Die Methode muss als `Sub` und nicht als `Function` deklariert sein.  
  
-   Der Methodentext muss leer sein.  
  
-   Der Zugriffsmodifizierer muss `Private` sein.  
  
## Implementierung  
 In der Implementierung wird hauptsächlich der partielle Methodentext ausgefüllt.  Die Implementierung erfolgt in der Regel in einer von der Definition getrennten partiellen Klasse und wird von einem Entwickler geschrieben, der den generierten Code erweitern möchte.  
  
```vb#  
Private Sub QuantityChanged()  
'    Code for executing the desired action.  
End Sub  
```  
  
 Im vorherigen Beispiel wird die Signatur aus der Deklaration genau übernommen, es sind jedoch auch Variationen möglich.  Insbesondere können weitere Modifizierer hinzugefügt werden, z. B. `Overloads` oder `Overrides`.  Es ist nur ein `Overrides`\-Modifizierer erlaubt.  Weitere Informationen über Methodenmodifizierer finden Sie unter [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## Verwendung  
 Sie rufen eine partielle Methode genauso wie jede andere `Sub`\-Prozedur auf.  Wenn die Methode implementiert wurde, werden die Argumente ausgewertet und der Methodentext wird ausgeführt.  Beachten Sie jedoch, dass eine partielle Methode nicht implementiert werden muss.  Wenn die Methode nicht implementiert wurde, hat ein Aufruf der Methode keine Auswirkungen, und die der Methode als Argumente übergebenen Ausdrücke werden nicht ausgewertet.  
  
## Beispiel  
 Definieren Sie in einer Datei mit dem Namen Product.Designer.vb die Klasse `Product` mit der Eigenschaft `Quantity`.  
  
 [!code-vb[VbVbalrPartialMeths#4](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_1.vb)]  
  
 Stellen Sie in einer Datei mit dem Namen Product.vb eine Implementierung für `QuantityChanged` bereit.  
  
 [!code-vb[VbVbalrPartialMeths#5](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_2.vb)]  
  
 Deklarieren Sie abschließend in der Main\-Methode eines Projekts eine `Product`\-Instanz, und stellen Sie einen Anfangswert für die `Quantity`\-Eigenschaft bereit.  
  
 [!code-vb[VbVbalrPartialMeths#6](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/partial-methods_3.vb)]  
  
 Es sollte ein Meldungsfeld mit der folgenden Meldung angezeigt werden:  
  
 `Quantity was changed to 100`  
  
## Siehe auch  
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Partial](../../../../visual-basic/language-reference/modifiers/partial.md)   
 [Codegenerierung in LINQ to SQL](../Topic/Code%20Generation%20in%20LINQ%20to%20SQL.md)   
 [Hinzufügen von Geschäftslogik durch das Verwenden partieller Methoden](../Topic/Adding%20Business%20Logic%20By%20Using%20Partial%20Methods.md)