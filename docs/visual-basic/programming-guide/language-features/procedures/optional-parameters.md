---
title: "Optional Parameters (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "parameters, optional"
  - "Visual Basic code, procedures"
  - "procedures, optional arguments"
  - "optional arguments"
  - "named arguments, and optional arguments"
  - "optional parameters"
  - "Optional keyword, optional arguments"
  - "arguments [Visual Basic], optional"
  - "optional arguments, and named arguments"
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Optional Parameters (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Sie können angeben, dass ein Prozedurparameter optional ist und in Aufrufen der Prozedur kein Argument dafür bereitgestellt werden muss.  *Optionale Parameter* werden in der Prozedurdefinition durch das `Optional`\-Schlüsselwort gekennzeichnet.  Dabei gelten folgende Regeln:  
  
-   Für jeden optionalen Parameter in der Prozedurdefinition muss ein Standardwert angegeben werden.  
  
-   Der Standardwert für einen optionalen Parameter muss ein konstanter Ausdruck sein.  
  
-   Jeder Parameter, der in der Prozedurdefinition auf einen optionalen Parameter folgt, muss ebenfalls optional sein.  
  
 Die folgende Syntax zeigt eine Prozedurdeklaration mit einem optionalen Parameter:  
  
```  
Sub sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## Aufrufprozeduren mit optionalen Parametern  
 Wenn eine Prozedur mit einem optionalen Parameter aufgerufen wird, können Sie entscheiden, ob das Argument bereitgestellt werden soll.  Wird das Argument nicht bereitgestellt, verwendet die Prozedur den für diesen Parameter deklarierten Standardwert.  
  
 Wenn Sie in der Argumentliste eines oder mehrere optionale Argumente auslassen, werden deren Positionen durch aufeinanderfolgende Kommas markiert.  Im folgenden Beispielaufruf werden das erste und das vierte Argument bereitgestellt, das zweite und dritte jedoch nicht:  
  
```  
  
sub name(argument 1, , , argument 4)  
```  
  
 Im folgenden Beispiel wird die `MsgBox`\-Funktion mehrmals aufgerufen.  `MsgBox` besitzt einen erforderlichen Parameter und zwei optionale Parameter.  
  
 Beim ersten Aufruf von `MsgBox` werden alle drei Argumente in der Reihenfolge angegeben, in der sie von `MsgBox` definiert werden.  Beim zweiten Aufruf wird nur das erforderliche Argument angegeben.  Beim dritten und vierten Aufruf werden das erste und dritte Argument angegeben.  Im dritten Aufruf geschieht dies über die Position, im vierten Aufruf über den Namen.  
  
 [!code-vb[VbVbcnProcedures#47](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/optional-parameters_1.vb)]  
  
## Bestimmen, ob ein optionales Argument vorhanden ist  
 Prozeduren können zur Laufzeit nicht feststellen, ob ein bestimmtes Argument ausgelassen oder der Standardwert durch den Aufrufcode explizit bereitgestellt wurde.  Wenn diese Unterscheidung wichtig ist, sollten Sie einen unwahrscheinlichen Standardwert festlegen.  In der folgenden Prozedur wird der optionale  `office`\-Parameter definiert und anschließend überprüft, ob sein Standardwert  `QJZ` im Aufruf ausgelassen wurde:  
  
 [!code-vb[VbVbcnProcedures#46](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/optional-parameters_2.vb)]  
  
 Wenn es sich beim optionalen Parameter um einen Verweistyp wie `String` handelt, kann `Nothing` als Standardwert verwendet werden, sofern dieser kein zu erwartender Wert für das Argument ist.  
  
## Optionale Parameter und Überladen  
 Eine weitere Möglichkeit, eine Prozedur mit optionalen Parametern zu definieren, ist das Überladen.  Wenn ein optionaler Parameter vorhanden ist, können Sie zwei überladene Versionen der Prozedur definieren, eine mit und eine ohne Parameter.  Mit steigender Anzahl an optionalen Parametern wird dieses Konzept jedoch komplizierter.  Allerdings hat es den Vorteil, dass Sie immer genau wissen, ob das aufrufende Programm jedes optionale Argument bereitgestellt hat.  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Parameter Arrays](../../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)   
 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)