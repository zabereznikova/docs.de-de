---
title: "Parameter Arrays (Visual Basic) | Microsoft Docs"
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
  - "parameter arrays, about parameter arrays"
  - "ParamArray keyword, parameter arrays"
  - "Visual Basic code, procedures"
  - "parameters, parameter arrays"
  - "arguments [Visual Basic], parameter arrays"
  - "procedures, indefinite number of argument values"
  - "arrays [Visual Basic], parameter arrays"
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Parameter Arrays (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Normalerweise kann eine Prozedur nur mit der in der Prozedurdeklaration angegebenen Anzahl an Argumenten aufgerufen werden.  Wenn jedoch eine unbestimmte Anzahl von Argumenten erforderlich ist, können Sie ein *Parameterarray* deklarieren. Dadurch akzeptiert die Prozedur ein Array von Werten für einen Parameter.  Beim Definieren der Prozedur müssen Sie die Anzahl der Elemente im Parameterarray nicht kennen.  Die Arraygröße wird durch die einzelnen Aufrufe der Prozedur jeweils individuell festgelegt.  
  
## Deklarieren eines ParamArray  
 Um auf ein Parameterarray in der Parameterliste hinzudeuten, verwenden Sie das [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)\-Schlüsselwort.  Dabei gelten folgende Regeln:  
  
-   Eine Prozedur kann nur 1 Parameterarray definieren, und es muss sich um den letzten Parameter in der Prozedurdefinition handeln.  
  
-   Das Parameterarray muss durch Wert übergeben werden.  Eine gute Lösung beim Programmieren ist es, das [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)\-Schlüsselwort explizit in die Prozedurdefinition einzufügen.  
  
-   Das Parameterarray ist automatisch optional.  Sein Standardwert ist ein leeres, eindimensionales Array mit dem Elementtyp des Parameterarrays.  
  
-   Dem Parameterarray dürfen nur erforderliche Parameter vorangehen.  Als optionaler Parameter ist nur das Parameterarray zulässig.  
  
## Aufrufen eines ParamArray  
 Wenn Sie eine Prozedur aufrufen, die ein Parameterarray definiert, können Sie das Argument auf eine der folgenden Weisen angeben:  
  
-   Nothing. Das [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md)\-Argument kann weggelassen werden.  In diesem Fall wird der Prozedur ein leeres Array übergeben.  Dasselbe kann auch durch Übergabe des [Nothing](../../../../visual-basic/language-reference/nothing.md)\-Schlüsselworts erreicht werden.  
  
-   Eine Liste mit einer beliebigen Anzahl von Argumenten, die durch Kommas voneinander getrennt sind.  Der Datentyp der einzelnen Argumente muss implizit in den `ParamArray`\-Elementtyp konvertiert werden können.  
  
-   Ein Array mit dem gleichen Elementtyp wie der Elementtyp des Parameterarrays.  
  
 In jedem Fall muss der Code innerhalb der Prozedur das Parameterarray als eindimensionales Array behandeln, dessen Elemente jeweils denselben Datentyp haben wie `ParamArray`.  
  
> [!IMPORTANT]
>  Wenn Sie mit einem Array arbeiten, das unendlich groß sein kann, besteht die Gefahr, dass eine interne Kapazität der Anwendung überschritten wird.  Wenn Sie ein Parameterarray annehmen, sollten Sie die Größe des Arrays ermitteln, das der Aufrufcode an das Parameterarray übergeben hat.  Ergreifen Sie entsprechende Schritte, wenn das Array für die Anwendung zu groß ist.  Weitere Informationen finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## Beispiel  
 Das folgende Beispiel definiert und ruft die Funktion `calcSum`an.  Der `ParamArray`\-Modifizierer für den Parameter `args` aktiviert die Funktion eine variable Anzahl von Argumenten akzeptieren.  
  
 [!code-vb[VbVbalrStatements#26](../../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-arrays_1.vb)]  
  
 Im folgenden Beispiel wird eine Prozedur mit einem Parameterarray definiert. Diese Prozedur gibt die Werte aller Arrayelemente zurück, die an das Parameterarray übergeben wurden.  
  
 [!code-vb[VbVbcnProcedures#48](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/parameter-arrays_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#49](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/VisualBasic/parameter-arrays_3.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>   
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Passing Arguments by Value and by Reference](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Passing Arguments by Position and by Name](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Optional Parameters](../../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [Optional](../../../../visual-basic/language-reference/modifiers/optional.md)