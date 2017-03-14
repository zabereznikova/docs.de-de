---
title: "Eigenschaftenprozeduren (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Set-Anweisung, Eigenschaftenprozeduren"
  - "Visual Basic-Code, Prozeduren"
  - "Rückgabewerte, Eigenschaftenprozeduren"
  - "Syntax, Eigenschaftenprozeduren"
  - "Prozeduren, Eigenschaften"
  - "Visual Basic-Code, Eigenschaften"
  - "Prozeduren, Aufrufen"
  - "Eigenschaften [Visual Basic], benutzerdefiniert"
  - "Eigenschaftenprozeduren"
  - "Get-Anweisung, Eigenschaftenprozeduren"
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Eigenschaftenprozeduren (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Bei einer Eigenschaftenprozedur handelt es sich um eine Reihe von [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Anweisungen zum Ändern von benutzerdefinierten Eigenschaften in Modulen, Klassen oder Strukturen.  Property\-Prozeduren werden auch als *Eigenschaften\-Accessoren* bezeichnet.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enthält die folgenden Eigenschaftenprozeduren:  
  
-   Die `Get`\-Prozedur gibt den Wert einer Eigenschaft zurück.  Sie wird aufgerufen, wenn Sie in einem Ausdruck auf die Eigenschaft zugreifen.  
  
-   Eine `Set`\-Prozedur legt eine Eigenschaft auf einen Wert fest; hierzu gehören auch Objektverweise.  Sie wird aufgerufen, wenn Sie der Eigenschaft einen Wert zuweisen.  
  
 In der Regel werden Eigenschaftenprozeduren paarweise mit den Anweisungen `Get` und `Set` definiert. Sie können jedoch jede der beiden Eigenschaften einzeln definieren, wenn die Eigenschaft schreibgeschützt \([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)\) oder lesegeschützt \([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)\) ist.  
  
 Beim Verwenden einer automatisch implementierten Eigenschaft müssen die `Get`\-Prozedur und die `Set`\-Prozedur nicht angegeben werden.  Weitere Informationen finden Sie unter [Auto\-Implemented Properties](../../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Eigenschaften können in Modulen, Klassen und Strukturen definiert werden.  Eigenschaften sind standardmäßig `Public`; d. h., Sie können sie in Ihrer Anwendung, die auf den Container der Eigenschaft zugreifen kann, von einer beliebigen Stelle aus aufrufen.  
  
 Einen Vergleich von Eigenschaften und Variablen finden Sie unter [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md).  
  
## Deklarationssyntax  
 Eine Eigenschaft selbst wird als zwischen der [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property`\-Anweisung stehender Codeblock definiert.  Innerhalb dieses Blocks wird jede Eigenschaftenprozedur als interner, zwischen einer Deklarationsanweisung \(`Get` oder `Set`\) und der entsprechenden `End`\-Deklaration stehender Block angezeigt.  
  
 Die Syntax zur Deklaration einer Eigenschaft und ihrer Prozeduren lautet wie folgt:  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 Die `Modifiers` können die Zugriffsebene und Informationen zum Überladen, Überschreiben, Freigeben und Shadowing angeben und spezifizieren, ob die Eigenschaft schreibgeschützt oder lesegeschützt ist.  `AccessLevel` auf der `Get` oder `Set` Prozedur kann jede Ebene, die restriktiver als, ist die Zugriffsebene sein, die für die Eigenschaft selbst.  Weitere Informationen finden Sie unter [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).  
  
### Datentyp  
 Der Datentyp einer Eigenschaft und die Hauptzugriffsebene werden in der `Property`\-Anweisung definiert, nicht in den Eigenschaftenprozeduren.  Eine Eigenschaft kann nur einem Datentyp angehören.  Wenn Sie z. B. eine Eigenschaft definieren, die einen `Decimal`\-Wert speichert, kann kein `Double`\-Wert abgerufen werden.  
  
### Zugriffsebene  
 Sie können jedoch eine Hauptzugriffsebene für eine Eigenschaft definieren und die Zugriffsebene in einer der Eigenschaftenprozeduren weiter einschränken.  Beispielsweise können Sie eine `Public`\-Eigenschaft definieren und anschließend eine `Private Set`\-Prozedur.  Die `Get`\-Prozedur bleibt `Public`.  Sie können die Zugriffsebene in nur einer der Prozeduren einer Eigenschaft ändern. Die geänderte Zugriffsebene kann allerdings nur restriktiver sein als die Hauptzugriffsebene.  Weitere Informationen finden Sie unter [How to: Declare a Property with Mixed Access Levels](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-a-property-with-mixed-access-levels.md).  
  
## Parameterdeklaration  
 Jeder Parameter wird auf die gleiche Weise deklariert wie bei [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md), nur für den Übergabemechanismus muss `ByVal` verwendet werden.  
  
 Die Syntax für jeden Parameter in der Parameterliste lautet folgendermaßen:  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 Wenn der Parameter optional ist, müssen Sie bei seiner Deklaration auch einen Standardwert angeben.  Die Syntax zur Angabe eines Standardwerts lautet folgendermaßen:  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## Eigenschaftswert  
 In `Get`\-Prozeduren wird dem Aufrufausdruck der Rückgabewert als Wert der Eigenschaft bereitgestellt.  
  
 In `Set`\-Prozeduren wird der neue Eigenschaftswert dem Parameter der `Set`\-Anweisung übergeben.  Ein explizit deklarierter Parameter muss mit dem gleichen Datentyp deklariert werden wie die zugehörige Eigenschaft.  Wenn kein Parameter deklariert wird, stellt der Compiler den neuen Wert, der der Eigenschaft zugewiesen werden soll, mit dem impliziten `Value`\-Parameter dar.  
  
## Aufrufsyntax  
 Eine Eigenschaftenprozedur wird durch einen Verweis auf die Eigenschaft implizit aufgerufen.  Sie verwenden den Namen der Eigenschaft wie den Namen einer Variablen. Allerdings müssen Sie Werte für alle nicht optionalen Argumente angeben und die Argumentliste in Klammern setzen.  Wenn keine Argumente angegeben werden, können Sie die Klammern auch weglassen.  
  
 Die Syntax für einen impliziten Aufruf einer `Set`\-Prozedur lautet wie folgt:  
  
 `propertyname[(argumentlist)] = expression`  
  
 Die Syntax für einen impliziten Aufruf einer `Get`\-Prozedur lautet wie folgt:  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### Darstellung von Deklaration und Aufruf  
 Die folgende Eigenschaft speichert einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen.  Wenn der Aufrufcode `fullName` liest, kombiniert die `Get`\-Prozedur die beiden konstituierenden Namen und gibt den vollständigen Namen zurück.  Wenn der Aufrufcode einen neuen vollständigen Namen zuweist, versucht die `Set`\-Prozedur, den Namen in zwei konstituierende Namen aufzulösen.  Wird kein Leerzeichen gefunden, wird der gesamte Name als Vorname gespeichert.  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 Im folgenden Beispiel werden typische Aufrufe der Eigenschaftenprozeduren von `fullName` dargestellt.  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Operator Procedures](../../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Differences Between Properties and Variables in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-properties-and-variables.md)   
 [How to: Create a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-property.md)   
 [How to: Call a Property Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-property-procedure.md)   
 [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md)   
 [How to: Put a Value in a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-put-a-value-in-a-property.md)   
 [How to: Get a Value from a Property](../../../../visual-basic/programming-guide/language-features/procedures/how-to-get-a-value-from-a-property.md)