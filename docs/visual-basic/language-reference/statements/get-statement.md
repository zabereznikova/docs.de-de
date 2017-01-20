---
title: "Get Statement | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Get"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Get statement, syntax"
  - "Get statement"
  - "properties [Visual Basic], read-only"
  - "read-only properties"
  - "Get keyword"
  - "property procedures, Get statements"
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Get Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Deklariert eine `Get`\-Eigenschaftenprozedur, die zum Abrufen eines Eigenschaftswerts verwendet wird.  
  
## Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`attributelist`|Optional.  Siehe [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional für höchstens eine der `Get`\-Anweisungen und `Set`\-Anweisungen in dieser Eigenschaft.  Einer der folgenden Werte ist möglich:<br /><br /> -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`statements`|Optional.  Eine oder mehrere Anweisungen, die ausgeführt werden, wenn die `Get`\-Eigenschaftenprozedur aufgerufen wird.|  
|`End Get`|Erforderlich.  Beendet die Definition der `Get`\-Eigenschaftenprozedur.|  
  
## Hinweise  
 Jede Eigenschaft muss über eine `Get`\-Eigenschaftenprozedur verfügen, sofern die Eigenschaft nicht als `WriteOnly` markiert ist.  Die `Get`\-Prozedur wird verwendet, um den aktuellen Wert der Eigenschaft zurückzugeben.  
  
 Visual Basic ruft die `Get`\-Prozedur einer Eigenschaft automatisch auf, wenn ein Ausdruck den Wert der Eigenschaft anfordert.  
  
 Der Text der Eigenschaftendeklaration kann die `Get`\-Prozedur und die `Set`\-Prozedur nur zwischen der [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property`\-Anweisung enthalten.  In der Deklaration können nur diese Prozeduren gespeichert werden.  Der aktuelle Wert der Eigenschaft kann nicht in ihr gespeichert werden.  Sie müssen diesen Wert außerhalb der Eigenschaft speichern, da die jeweils andere Eigenschaftenprozedur nicht darauf zugreifen kann, wenn Sie ihn in einer der Eigenschaftenprozeduren speichern.  Die übliche Vorgehensweise besteht im Speichern des Werts in einer [Private](../../../visual-basic/language-reference/modifiers/private.md)\-Variablen, die auf derselben Ebene wie die Eigenschaft deklariert ist.  Sie müssen eine `Get`\-Prozedur in der Eigenschaft definieren, auf die sie angewendet wird.  
  
 Die Standardzugriffsebene der `Get`\-Prozedur ist die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden in der `Get`\-Anweisung `accessmodifier`.  
  
## Regeln  
  
-   **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Schreib\-\/Lesezugriff definieren, können Sie optional entweder für die `Get`\-Prozedur oder für die `Set`\-Prozedur, jedoch nicht für beide Prozeduren, eine andere Zugriffsebene festlegen.  Wenn Sie auf diese Weise vorgehen, muss die Zugriffsebene der Prozedur restriktiver als die Zugriffsebene der Eigenschaft sein.  Wenn beispielsweise die Eigenschaft als `Friend` deklariert ist, können Sie die `Get`\-Prozedur als `Private`, jedoch nicht als `Public` deklarieren.  
  
     Wenn Sie eine `ReadOnly`\-Eigenschaft definieren, stellt die `Get`\-Prozedur die gesamte Eigenschaft dar.  Sie können für `Get` keine andere Zugriffsebene deklarieren, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
-   **Rückgabetyp.** Die [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) kann den Datentyp des zurückgegebenen Werts deklarieren.  Die `Get`\-Prozedur gibt diesen Datentyp automatisch zurück.  Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
     Wenn die `Property`\-Anweisung nicht `returntype` angibt, gibt die Prozedur `Object` zurück.  
  
## Verhalten  
  
-   **Beenden einer Prozedur.** Wenn die `Get`\-Prozedur zum aufrufenden Code zurückkehrt, wird die Ausführung in der Anweisung fortgesetzt, die den Eigenschaftswert angefordert hat.  
  
     `Get`\-Eigenschaftenprozeduren können einen Wert zurückgeben, indem sie entweder die [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) verwenden oder dem Eigenschaftennamen den Rückgabewert zuweisen.  Weitere Informationen finden Sie im Abschnitt "Rückgabewert" unter [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Die `Exit Property`\-Anweisung und die `Return`\-Anweisung führen zur unmittelbaren Beendigung einer Eigenschaftenprozedur.  In der Prozedur können beliebig viele `Exit Property`\-Anweisungen und `Return`\-Anweisungen an beliebiger Stelle vorkommen, und Sie können `Exit Property`\-Anweisungen und `Return`\-Anweisungen kombinieren.  
  
-   **Rückgabewert.** Der Wert einer `Get`\-Prozedur wird zurückgegeben, indem Sie den Wert dem Eigenschaftennamen zuweisen oder ihn in eine [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) einfügen.  Die `Return`\-Anweisung weist der `Get`\-Prozedur den Rückgabewert zu und beendet gleichzeitig die Prozedur.  
  
     Wenn Sie `Exit Property` verwenden, ohne dem Eigenschaftennamen einen Wert zuzuweisen, gibt die `Get`\-Prozedur den Standardwert für den Datentyp der Eigenschaft zurück.  Weitere Informationen finden Sie im Abschnitt "Rückgabewert" unter [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md).  
  
     Im folgenden Beispiel werden zwei Verfahren veranschaulicht, mit denen die schreibgeschützte Eigenschaft `quoteForTheDay` den Wert in der privaten Variablen `quoteValue` zurückgeben kann.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_2.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_3.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird mit der `Get`\-Anweisung der Wert einer Eigenschaft zurückgegeben.  
  
 [!code-vb[VbVbalrStatements#30](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/get-statement_4.vb)]  
  
## Siehe auch  
 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Walkthrough: Defining Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)