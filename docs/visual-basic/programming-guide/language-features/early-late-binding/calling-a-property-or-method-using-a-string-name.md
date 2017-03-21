---
title: Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- passing operators
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls, strings
- methods [Visual Basic], calling with string names
- calling methods, string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87af2816ba42e2901c53bec5e9c19f34c676ed5c
ms.lasthandoff: 03/13/2017

---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Aufrufen einer Eigenschaft oder Methode mit einem Zeichenfolgennamen (Visual Basic)
In den meisten Fällen können Sie die Eigenschaften und Methoden eines Objekts zur Entwurfszeit zu ermitteln und Code schreiben, um sie zu behandeln. Jedoch in einigen Fällen Sie möglicherweise nicht über Eigenschaften und Methoden eines Objekts im Voraus wissen, oder Sie sollten nur die Flexibilität, dass einen Benutzer für das Festlegen von Eigenschaften oder Methoden zur Laufzeit ausführen.  
  
## <a name="callbyname-function"></a>CallByName-Funktion  
 Betrachten Sie z. B. eine Clientanwendung, die vom Benutzer eingegeben wird, übergeben Sie einen Operator für eine COM-Komponente Ausdrücke auswertet. Angenommen Sie, Sie werden ständig neue Funktionen hinzufügen, auf die Komponente, die neue Operatoren benötigen. Wenn Sie standard für den Objektzugriff verwenden, müssen Sie erneut kompilieren und verteilen die Client-Anwendung, die neuen Operatoren verwendet werden können. Um dies zu vermeiden, können Sie die `CallByName` Funktion, um die neuen Operatoren als Zeichenfolge übergeben, ohne die Anwendung zu ändern.  
  
 Die `CallByName` -Funktion können Sie eine Zeichenfolge verwenden, um eine Eigenschaft oder Methode zur Laufzeit angeben. Die Signatur für die `CallByName` -Funktion sieht wie folgt:  
  
 *Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())  
  
 Das erste Argument, *Objekt*, erhält den Namen des Objekts, auf die reagiert werden soll. Die *Prozedurname* Argument akzeptiert eine Zeichenfolge mit dem Namen der Methode oder Eigenschaft Prozedur aufgerufen werden soll. Die *Aufruftyp* Argument akzeptiert eine Konstante, die den Typ der aufzurufenden Prozedur darstellt: eine Methode (`Microsoft.VisualBasic.CallType.Method`), eine gelesene Eigenschaft (`Microsoft.VisualBasic.CallType.Get`), oder eine festgelegte Eigenschaft (`Microsoft.VisualBasic.CallType.Set`). Die *Argumente* das optionale Argument akzeptiert ein Array vom Typ `Object` , die keine Argumente an die Prozedur enthält.  
  
 Sie können `CallByName` mit Klassen in der aktuellen Projektmappe jedoch am häufigsten verwendet, um den Zugriff auf COM-Objekte oder Objekte aus [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Assemblys.  
  
 Angenommen, Sie einen Verweis auf eine Assembly hinzufügen, die eine Klasse namens enthält `MathClass`, das ist einer neue Funktion namens `SquareRoot`, wie im folgenden Code gezeigt:  
  
 [!code-vb[VbVbalrOOP&#53;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 Die Anwendung konnte Textfeld-Steuerelemente zum Steuerelement festzulegen, welche Methode aufgerufen wird und seine Argumente verwenden. Zum Beispiel wenn `TextBox1` enthält den Ausdruck ausgewertet werden soll, und `TextBox2` wird verwendet, um den Namen der Funktion eingeben, können Sie den folgenden Code zum Aufrufen der `SquareRoot` -Funktion für den Ausdruck in `TextBox1`:  
  
 [!code-vb[VbVbalrOOP&#54;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Bei der Eingabe von "64" in `TextBox1`, in "SquareRoot" `TextBox2`, und rufen Sie dann die `CallMath` Prozedur, die Quadratwurzel der Zahl in `TextBox1` ausgewertet wird. Der Code im Beispiel ruft die `SquareRoot` -Funktion (der akzeptiert einer Zeichenfolge, die den Ausdruck als ein erforderliches Argument enthält) und gibt "8" in `TextBox1` (die Quadratwurzel von 64). Natürlich auch, wenn der Benutzer eine ungültige Zeichenfolge in eingibt `TextBox2`, wenn die Zeichenfolge den Namen einer Eigenschaft anstelle einer Methode enthält oder die Methode ein weiteres erforderliches Argument aufweist, ein Laufzeitfehler ausgegeben tritt. Müssen Sie stabile Fehlerbehandlungscode hinzufügen, bei Verwendung von `CallByName` auf diese und andere Fehler zu erwarten.  
  
> [!NOTE]
>  Während der `CallByName` Funktion kann in einigen Fällen nützlich sein, Sie sollten Leistungseinbußen – mit `CallByName` zum Aufrufen einer Prozedur ist etwas langsamer als eine spät gebundenen Aufruf. Wenn Sie eine Funktion aufrufen, die wiederholt, z. B. in einer Schleife aufgerufen wird `CallByName` kann eine schwerwiegende Auswirkungen auf die Leistung haben.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A></xref:Microsoft.VisualBasic.Interaction.CallByName%2A>   
 [Bestimmen des Objekttyps](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
