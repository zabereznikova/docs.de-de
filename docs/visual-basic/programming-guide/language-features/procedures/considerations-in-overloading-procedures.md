---
title: "Considerations in Overloading Procedures (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "signatures, ParamArray arguments"
  - "ParamArray keyword, parameter arrays"
  - "ParamArray keyword, arguments and signatures"
  - "function overloading, implicit overloads for ParamArray"
  - "ParamArray keyword, signatures"
  - "Visual Basic code, procedures"
  - "arguments [Visual Basic], parameter arrays"
  - "procedures, overloading"
  - "parameters, lists"
  - "function overloading, typeless programming"
  - "typeless programming"
  - "function overloading, restrictions"
  - "arguments [Visual Basic], optional"
  - "optional arguments, overloading"
  - "signatures, procedure"
  - "parameter lists"
  - "parameter arrays, overloading arguments"
  - "Visual Basic code, parameter lists"
  - "procedure overloading, considerations"
  - "Option Explicit statement"
  - "restrictions, overloading procedures"
  - "procedures, parameter lists"
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Considerations in Overloading Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Wenn Sie eine Prozedur überladen, müssen Sie für jede überladene Version eine andere *Signatur* verwenden.  Dies bedeutet normalerweise, dass jede Version eine andere Parameterliste angeben muss.  Weitere Informationen finden Sie im Abschnitt "Unterschiedliche Signaturen" unter [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
 `Function`\-Prozeduren können mit `Sub`\-Prozeduren überladen werden und umgekehrt, sofern sie unterschiedliche Signaturen besitzen.  Zwei Überladungen können sich nicht nur darin unterscheiden, dass die eine Überladung einen Rückgabewert hat und die andere nicht.  
  
 Eigenschaften werden auf die gleiche Weise und mit den gleichen Beschränkungen überladen wie Prozeduren.  Sie können jedoch keine Prozedur mit einer Eigenschaft überladen oder umgekehrt.  
  
## Alternativen zu überladenen Versionen  
 Gelegentlich stehen Alternativen zu überladenen Versionen zur Verfügung, insbesondere wenn das Vorhandensein von Argumenten optional ist oder wenn die Anzahl der Argumente variabel ist.  
  
 Denken Sie daran, dass optionale Argumente nicht unbedingt von allen Sprachen unterstützt werden und Parameterarrays auf [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] beschränkt sind.  Wenn Sie eine Prozedur schreiben, die möglicherweise von Code aufgerufen wird, der in anderen Sprachen geschrieben wurde, bieten überladene Versionen die größte Flexibilität.  
  
### Überladungen und optionale Argumente  
 Wenn der Aufrufcode optional ein oder mehrere Argumente angeben oder weglassen kann, können Sie mehrere überladene Versionen definieren oder optionale Parameter verwenden.  
  
#### Verwendung von überladenen Versionen  
 In folgenden Fällen können Sie die Definition einer Reihe überladener Versionen in Betracht ziehen:  
  
-   Je nachdem, ob der Aufrufcode ein optionales Argument angibt oder nicht, weist die Logik im Prozedurcode bedeutende Unterschiede auf.  
  
-   Der Prozedurcode kann nicht zuverlässig testen, ob der Aufrufcode ein optionales Argument angegeben hat.  Dies ist z. B. dann der Fall, wenn es keinen möglichen Kandidaten für einen Standardwert gibt, dessen Angabe durch den Aufrufcode nicht zu erwarten ist.  
  
#### Verwendung optionaler Parameter  
 In folgenden Fällen ist die Verwendung mindestens eines optionalen Parameters vorzuziehen:  
  
-   Wenn der Aufrufcode kein optionales Argument angibt, besteht die einzige erforderliche Aktion darin, den Parameter auf einen Standardwert festzulegen.  In einem solchen Fall wird der Prozedurcode unter Umständen vereinfacht, wenn Sie eine einzelne Version mit mindestens einem `Optional`\-Parameter definieren.  
  
 Weitere Informationen finden Sie unter [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
### Überladungen und ParamArrays  
 Wenn der Aufrufcode eine variable Anzahl von Argumenten übergeben kann, können Sie mehrere überladene Versionen definieren oder ein Parameterarray verwenden.  
  
#### Verwendung von überladenen Versionen  
 In folgenden Fällen können Sie die Definition einer Reihe überladener Versionen in Betracht ziehen:  
  
-   Sie wissen, dass der Aufrufcode immer nur eine kleine Anzahl von Werten an den Parameterarray übergibt.  
  
-   Je nach der Anzahl der vom Aufrufcode übergebenen Werte ist die Logik im Prozedurcode sehr unterschiedlich.  
  
-   Der Aufrufcode kann Werte unterschiedlicher Datentypen übergeben.  
  
#### Verwendung eines Parameterarrays  
 In folgenden Fällen stellt ein `ParamArray`\-Parameter die bessere Lösung dar:  
  
-   Sie können nicht vorhersagen, wie viele Werte der Aufrufcode an den Parameterarray übergeben kann, und es kann sich um eine große Anzahl von Werten handeln.  
  
-   Die Prozedurlogik selbst eignet sich dazu, alle vom Aufrufcode übergebenen Werte zu durchlaufen, wobei für jeden Wert im Wesentlichen die gleichen Vorgänge ausgeführt werden.  
  
 Weitere Informationen finden Sie unter [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
## Implizite Überladungen für optionale Parameter  
 Eine Prozedur mit einem [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)\-Parameter entspricht zwei überladenen Prozeduren, einer mit dem optionalen Parameter und einer ohne.  Sie können eine solche Prozedur nicht mit einer Parameterliste überladen, die einer dieser beiden Prozeduren entspricht.  Die folgenden Deklarationen verdeutlichen dies.  
  
 [!code-vb[VbVbcnProcedures#58](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/considerations-in-overloadi_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#60](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/considerations-in-overloadi_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#61](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/considerations-in-overloadi_3.vb)]  
  
 Bei einer Prozedur mit mehr als einem optionalen Parameter gibt es eine Reihe impliziter Überladungen, die sich aus einer dem vorhergehenden Beispiel ähnelnden Logik ergeben.  
  
## Implizite Überladungen für ParamArray\-Parameter  
 Bei Prozeduren mit einem [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)\-Parameter geht der Compiler davon aus, dass sie über eine unendliche Anzahl von Überladungen verfügen, die sich bezüglich der vom Aufrufcode an das Parameterarray übergebenen Werte wie folgt unterscheiden:  
  
-   Eine Überladung für den Fall, dass der Aufrufcode kein Argument an `ParamArray` übergibt  
  
-   Eine Überladung für den Fall, dass der Aufrufcode ein eindimensionales Array des `ParamArray`\-Elementtyps angibt  
  
-   Für jede positive ganze Zahl eine Überladung für den Fall, dass der Aufrufcode die entsprechende Anzahl von Argumenten angibt; diese gehören jeweils zum `ParamArray`\-Elementtyp.  
  
 Die folgenden Deklarationen verdeutlichen diese impliziten Überladungen.  
  
 [!code-vb[VbVbcnProcedures#68](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/considerations-in-overloadi_4.vb)]  
  
 [!code-vb[VbVbcnProcedures#70](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/considerations-in-overloadi_5.vb)]  
  
 Sie können eine solche Prozedur nicht mit einer Parameterliste überladen, die ein eindimensionales Array für das Parameterarray akzeptiert.  Sie können jedoch die Signaturen der anderen impliziten Überladungen verwenden.  Die folgenden Deklarationen verdeutlichen dies.  
  
 [!code-vb[VbVbcnProcedures#71](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/considerations-in-overloadi_6.vb)]  
  
## Programmierung ohne Datentypen als Alternative zur Überladung  
 Wenn Sie den Aufrufcode an verschiedene Datentypen übergeben Sie auf einen Parameter zulassen möchten, ist ein alternativer Ansatz typenloses Programmieren.  Mit der [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) oder der [\/optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md)\-Compileroption können Sie für die Typüberprüfung den Wert `Off` festlegen.  Danach müssen Sie den Datentyp des Parameters nicht deklarieren.  Im Vergleich zum Überladen hat dieser Ansatz jedoch folgende Nachteile:  
  
-   Die Programmierung ohne Datentypen ergibt weniger effizienten Ausführungscode.  
  
-   Die Prozedur muss das Vorhandensein jedes Datentyps testen, dessen Übergabe sie erwartet.  
  
-   Der Compiler kann keinen Fehler signalisieren, wenn der aufrufende Code einen Datentyp übergibt, den die Prozedur nicht unterstützt.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Troubleshooting Procedures](../../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)   
 [How to: Define Multiple Versions of a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-multiple-versions-of-a-procedure.md)   
 [How to: Call an Overloaded Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-overloaded-procedure.md)   
 [How to: Overload a Procedure that Takes Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](../../../../visual-basic/programming-guide/language-features/procedures/how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Overload Resolution](../../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)