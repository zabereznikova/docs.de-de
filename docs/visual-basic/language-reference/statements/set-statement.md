---
title: "Set Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Set"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "property procedures, Set statements"
  - "Set statement"
  - "Set statement, syntax"
  - "write-only properties"
  - "properties [Visual Basic], write-only"
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Set Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Deklariert eine `Set`\-Eigenschaftenprozedur, mit der einer Eigenschaft ein Wert zugewiesen wird.  
  
## Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## Teile  
 `attributelist`  
 Optional.  Siehe [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Optional für höchstens eine der `Get`\-Anweisungen und `Set`\-Anweisungen in dieser Eigenschaft.  Einer der folgenden Werte ist möglich:  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Erforderlich.  Parameter mit dem neuen Wert für die Eigenschaft.  
  
 `datatype`  
 Erforderlich, wenn `Option Strict` den Wert `On` aufweist.  Der Typ des `value`\-Parameters.  Der angegebene Datentyp muss mit dem Datentyp der Eigenschaft identisch sein, in dem diese `Set`\-Anweisung deklariert wird.  
  
 `statements`  
 Optional.  Eine oder mehrere Anweisungen, die ausgeführt werden, wenn die `Set`\-Eigenschaftenprozedur aufgerufen wird.  
  
 `End Set`  
 Erforderlich.  Beendet die Definition der `Set`\-Eigenschaftenprozedur.  
  
## Hinweise  
 Jede Eigenschaft muss über eine `Set`\-Eigenschaftenprozedur verfügen, sofern die Eigenschaft nicht als `ReadOnly` markiert ist.  Die `Set`\-Prozedur wird verwendet, um den Wert der Eigenschaft festzulegen.  
  
 Visual Basic ruft die `Set`\-Prozedur einer Eigenschaft automatisch auf, wenn eine Zuweisungsanweisung einen in der Eigenschaft zu speichernden Wert bereitstellt.  
  
 Visual Basic übergibt bei Eigenschaftenzuweisungen einen Parameter an die `Set`\-Prozedur.  Wenn Sie keinen Parameter für `Set` angeben, verwendet die integrierte Entwicklungsumgebung \(IDE\) den impliziten Parameter `value`.  Der Parameter enthält den der Eigenschaft zuzuweisenden Wert.  Sie speichern diesen Wert i. d. R. in einer privaten lokalen Variablen und geben ihn bei jedem Aufruf der `Get`\-Prozedur zurück.  
  
 Der Text der Eigenschaftendeklaration kann die `Get`\-Prozedur und die `Set`\-Prozedur nur zwischen der [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property`\-Anweisung enthalten.  In der Deklaration können nur diese Prozeduren gespeichert werden.  Der aktuelle Wert der Eigenschaft kann nicht in ihr gespeichert werden.  Sie müssen diesen Wert außerhalb der Eigenschaft speichern, da die jeweils andere Eigenschaftenprozedur nicht darauf zugreifen kann, wenn Sie ihn in einer der Eigenschaftenprozeduren speichern.  Die übliche Vorgehensweise besteht im Speichern des Werts in einer [Private](../../../visual-basic/language-reference/modifiers/private.md)\-Variablen, die auf derselben Ebene wie die Eigenschaft deklariert ist.  Sie müssen eine `Set`\-Prozedur in der Eigenschaft definieren, auf die sie angewendet wird.  
  
 Die Standardzugriffsebene der `Set`\-Prozedur ist die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden in der `Set`\-Anweisung `accessmodifier`.  
  
## Regeln  
  
-   **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Schreib\-\/Lesezugriff definieren, können Sie optional entweder für die `Get`\-Prozedur oder für die `Set`\-Prozedur, jedoch nicht für beide Prozeduren, eine andere Zugriffsebene festlegen.  Wenn Sie auf diese Weise vorgehen, muss die Zugriffsebene der Prozedur restriktiver als die Zugriffsebene der Eigenschaft sein.  Wenn beispielsweise die Eigenschaft als `Friend` deklariert ist, können Sie die `Set`\-Prozedur als `Private`, jedoch nicht als `Public` deklarieren.  
  
     Wenn Sie eine `WriteOnly`\-Eigenschaft definieren, stellt die `Set`\-Prozedur die gesamte Eigenschaft dar.  Sie können für `Set` keine andere Zugriffsebene deklarieren, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
## Verhalten  
  
-   **Beenden einer Eigenschaftenprozedur.** Wenn die `Set`\-Prozedur zum aufrufenden Code zurückkehrt, wird die Ausführung nach der Anweisung fortgesetzt, die den zu speichernden Wert bereitgestellt hat.  
  
     `Set`\-Eigenschaftenprozeduren können entweder mit [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) oder mit [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md) beendet werden.  
  
     Die `Exit Property`\-Anweisung und die `Return`\-Anweisung führen zur unmittelbaren Beendigung einer Eigenschaftenprozedur.  In der Prozedur können beliebig viele `Exit Property`\-Anweisungen und `Return`\-Anweisungen an beliebiger Stelle vorkommen, und Sie können `Exit Property`\-Anweisungen und `Return`\-Anweisungen kombinieren.  
  
## Beispiel  
 Im folgenden Beispiel wird mit der `Set`\-Anweisung der Wert einer Eigenschaft festgelegt.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## Siehe auch  
 [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)