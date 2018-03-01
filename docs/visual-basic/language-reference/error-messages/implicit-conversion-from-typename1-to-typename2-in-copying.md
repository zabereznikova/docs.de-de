---
title: "Implizite Konvertierung von &#39; &lt;Typname1&gt;&#39; in &#39;&lt; Typname2&gt;&#39; kopieren Sie den Wert des &#39; ByRef &#39; Parameter &#39; &lt;Parametername&gt;&#39; zurück in das entsprechende Argument."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e858b475a816a35d18822643de5a273abe28562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Implizite Konvertierung von &#39; &lt;Typname1&gt;&#39; in &#39;&lt; Typname2&gt;&#39; kopieren Sie den Wert des &#39; ByRef &#39; Parameter &#39; &lt;Parametername&gt;&#39; zurück in das entsprechende Argument.
Eine Prozedur wird aufgerufen, mit einem [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Argument eines anderen Typs als die des entsprechenden Parameters.  
  
 Wenn Sie ein Argument übergeben `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kopiert zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben. In diesem Fall muss [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] nach Abschluss der Prozedur den Wert der lokalen Variablen zurück in das Argument im aufrufenden Code kopieren.  
  
 Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich. Wenn hingegen die Typen unterschiedlich sind, muss [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] die Konvertierung in beide Richtungen ausführen. Da Sie nicht über `CType` oder eines anderes Konvertierungsschlüsselwort eines Prozedurarguments oder Parameter, eine solche Konvertierung ist immer implizit.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC41999  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie nach Möglichkeit ein aufrufendes Argument, das denselben Typ aufweist wie der Prozedurparameter, sodass [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keine Konvertierung ausführen muss.  
  
-   Wenn Sie die Prozedur mit einem Argument aufrufen müssen, Typ sich vom Parametertyp unterscheidet, jedoch müssen nicht in das aufrufende Argument einen Wert zurückgeben, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Parameter und Argumente von Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
