---
title: "Operator Statement | Microsoft Docs"
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
  - "vb.operator"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operators [Visual Basic]"
  - "procedures, operator"
  - "Narrowing keyword, conversion operators"
  - "Visual Basic code, operators"
  - "Widening keyword, conversion operators"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "overloaded operators"
  - "operator overloading"
  - "operator procedures"
  - "Operator statement"
  - "CType function, Operator statement"
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Operator Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Deklariert Symbol, Operanden und Code eines Operators, die eine Operatorprozedur für eine Klasse oder Struktur definieren.  
  
## Syntax  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## Teile  
 `attrlist`  
 Optional.  Siehe [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `Public`  
 Erforderlich.  Gibt an, dass diese Operatorprozedur [Public](../../../visual-basic/language-reference/modifiers/public.md)\-Zugriff aufweist.  
  
 `Overloads`  
 Optional.  Weitere Informationen finden Sie unter [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).  
  
 `Shared`  
 Erforderlich.  Gibt an, dass die Operatorprozedur eine [Shared](../../../visual-basic/language-reference/modifiers/shared.md)\-Prozedur ist.  
  
 `Shadows`  
 Optional.  Weitere Informationen finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `Widening`  
 Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Narrowing` an.  Gibt an, dass die Operatorprozedur eine [Widening](../../../visual-basic/language-reference/modifiers/widening.md)\-Konvertierung definiert.  Siehe "Erweiterungs\- und Eingrenzungskonvertierungen" auf dieser Hilfeseite.  
  
 `Narrowing`  
 Für einen Konvertierungsoperator erforderlich, es sei denn, Sie geben `Widening` an.  Gibt an, dass die Operatorprozedur eine [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)\-Konvertierung definiert.  Siehe "Erweiterungs\- und Eingrenzungskonvertierungen" auf dieser Hilfeseite.  
  
 `operatorsymbol`  
 Erforderlich.  Das Symbol oder der Bezeichner des Operators, das bzw. der diese Operatorprozedur definiert.  
  
 `operand1`  
 Erforderlich.  Der Name und Typ des einzigen Operanden eines unären Operators \(einschließlich eines Konvertierungsoperators\) oder des linken Operanden eines binären Operators.  
  
 `operand2`  
 Für binäre Operatoren erforderlich.  Der Name und Typ des rechten Operanden eines binären Operators.  
  
 `operand1` und `operand2` weisen folgende Syntax und Bestandteile auf:  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|Bestandteil|Beschreibung|  
|-----------------|------------------|  
|`ByVal`|Optional, doch der Übergabemechanismus muss [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) sein.|  
|`operandname`|Erforderlich.  Name der Variablen, die den Operanden darstellt.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`operandtype`|Optional, sofern `Option Strict` nicht `On` ist.  Datentyp dieses Operanden.|  
  
 `type`  
 Optional, sofern `Option Strict` nicht `On` ist.  Datentyp des Werts, der von der Operatorprozedur zurückgegeben wird.  
  
 `statements`  
 Optional.  Block von Anweisungen, die von der Operatorprozedur ausgeführt werden.  
  
 `returnvalue`  
 Erforderlich.  Der Wert, den die Operatorprozedur an den aufrufenden Code zurückgibt.  
  
 `End` `Operator`  
 Erforderlich.  Beendet die Definition dieser Operatorprozedur.  
  
## Hinweise  
 Sie können `Operator` nur in einer Klasse oder einer Struktur verwenden.  Daher kann der *Deklarationskontext* für einen Operator keine Quelldatei, kein Namespace, kein Modul, keine Schnittstelle, keine Prozedur und kein Block sein.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Alle Konvertierungen müssen `Public Shared` sein.  Sie können für beide Operanden nicht `ByRef`, `Optional` oder `ParamArray` angeben.  
  
 Sie können das Operatorsymbol oder den Operatorbezeichner nicht zum Speichern eines Rückgabewerts verwenden.  Sie müssen die `Return`\-Anweisung verwenden, in der ein Wert angegeben werden muss.  In der Prozedur können beliebig viele `Return`\-Anweisungen an beliebiger Stelle vorkommen.  
  
 Das Definieren eines Operators auf diese Weise wird als *Operatorüberladung* bezeichnet, unabhängig davon, ob Sie das `Overloads`\-Schlüsselwort verwenden.  In der folgenden Tabelle werden die Operatoren aufgelistet, die Sie definieren können.  
  
|Typ|Operatoren|  
|---------|----------------|  
|Unär|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binär|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Konvertierung \(unär\)|`CType`|  
  
 Beachten Sie, dass der Operator `=` in der Liste binärer Operatoren der Vergleichsoperator und nicht der Zuweisungsoperator ist.  
  
 Wenn Sie `CType` definieren, müssen Sie entweder `Widening` oder `Narrowing` angeben.  
  
## Zueinander passende Paare  
 Sie müssen bestimmte Operatoren als zueinander passende Paare definieren.  Wenn Sie den einen Operator eines solchen Paars definieren, müssen Sie den anderen ebenso definieren.  Die zueinander passenden Paare lauten wie folgt:  
  
-   `=` und `<>`  
  
-   `>` und `<`  
  
-   `>=` und `<=`  
  
-   `IsTrue` und `IsFalse`  
  
## Datentypeinschränkungen  
 Jeder Operator, den Sie definieren, muss die Klasse oder die Struktur umfassen, für die Sie ihn definieren.  Dies bedeutet, dass die Klasse oder Struktur als Datentyp eines der folgenden Elemente angegeben werden muss:  
  
-   Des Operanden eines unären Operators  
  
-   Mindestens eines Operanden eines binären Operators  
  
-   Entweder des Operanden oder des Rückgabetyps eines Konvertierungsoperators  
  
 Für bestimmte Operatoren gelten zusätzliche Datentypeinschränkungen:  
  
-   Wenn Sie den Operator `IsTrue` und den Operator `IsFalse` definieren, müssen beide den `Boolean`\-Typ zurückgeben.  
  
-   Wenn Sie den Operator `<<` und den Operator `>>` definieren, müssen beide für den `operandtype` von `operand2` den `Integer`\-Typ angeben.  
  
 Der Rückgabetyp muss nicht dem Typ eines der beiden Operanden entsprechen.  Beispielsweise kann ein Vergleichsoperator wie `=` oder `<>` den Typ `Boolean` zurückgeben, auch wenn keiner der Operanden vom Typ `Boolean` ist.  
  
## Logische und bitweise Operatoren  
 Die Operanden `And`, `Or`, `Not` und `Xor` können in Visual Basic logische oder bitweise Operationen ausführen.  Wenn Sie einen dieser Operatoren für eine Klasse oder Struktur definieren, können Sie jedoch nur dessen bitweise Operation definieren.  
  
 Sie können den Operator `AndAlso` nicht direkt für eine `Operator`\-Anweisung definieren.  Sie können jedoch `AndAlso` verwenden, wenn Sie die folgenden Bedingungen erfüllt haben:  
  
-   Sie haben `And` mit den gleichen Operandentypen definiert, die Sie für `AndAlso` verwenden möchten.  
  
-   Die Definition von `And` gibt denselben Typ wie die Klasse oder Struktur zurück, in der Sie den Operator definiert haben.  
  
-   Sie haben den Operator `IsFalse` in der Klasse oder Struktur definiert, in der Sie `And` definiert haben.  
  
 Ebenso können Sie `OrElse` verwenden, wenn Sie `Or` mit denselben Operanden und dem Rückgabetyp der Klasse oder Struktur und für die Klasse oder Struktur `IsTrue` definiert haben.  
  
## Erweiterungs\- und Eingrenzungskonvertierungen  
 Eine *erweiternde Konvertierung* ist zur Laufzeit immer erfolgreich, während eine *einschränkende Konvertierung* zur Laufzeit fehlschlagen kann.  Weitere Informationen finden Sie unter [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Wenn Sie eine Konvertierungsprozedur als `Widening` deklarieren, darf der Prozedurcode keine Fehler generieren.  Dies bedeutet Folgendes:  
  
-   Der Code muss immer einen gültigen Wert vom Typ `type` zurückgeben.  
  
-   Er muss alle möglichen Ausnahmen und andere Fehlerbedingungen behandeln.  
  
-   Er muss jeden zurückgegebenen Fehler von jeder Prozedur behandeln, die er aufruft.  
  
 Wenn die Möglichkeit besteht, dass eine Konvertierungsprozedur fehlschlägt oder eine nicht behandelte Ausnahme verursacht, müssen Sie sie als `Narrowing` deklarieren.  
  
## Beispiel  
 Im folgenden Codebeispiel wird die `Operator`\-Anweisung verwendet, um die Gliederung einer Struktur zu definieren, die Operatorprozeduren für die Operatoren `And`, `Or`, `IsFalse` und `IsTrue` enthält.  `And` und `Or` akzeptieren jeweils zwei Operanden vom Typ `abc` mit dem Rückgabetyp `abc`.  `IsFalse` und `IsTrue` akzeptieren jeweils einen einzigen Operanden vom Typ `abc` und geben `Boolean` zurück.  Mit diesen Definitionen kann im aufrufenden Code `And`, `AndAlso`, `Or` und `OrElse` mit Operanden vom Typ `abc` verwendet werden.  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## Siehe auch  
 [IsFalse Operator](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [How to: Call an Operator Procedure](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [How to: Use a Class that Defines Operators](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)