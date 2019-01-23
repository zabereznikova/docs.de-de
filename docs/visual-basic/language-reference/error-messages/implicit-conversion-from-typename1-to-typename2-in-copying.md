---
title: Implizite Konvertierung von &#39; &lt;Typname1&gt; &#39; zu &#39; &lt;Typname2&gt; &#39; beim Kopieren des Werts der &#39;ByRef&#39; Parameter &#39; &lt; Parametername&gt; &#39; zurück in das entsprechende Argument.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: 9f05a5fbcbef828b4ffa920d8cade475cedb64d5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54537234"
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Implizite Konvertierung von &#39; &lt;Typname1&gt; &#39; zu &#39; &lt;Typname2&gt; &#39; beim Kopieren des Werts der &#39;ByRef&#39; Parameter &#39; &lt; Parametername&gt; &#39; zurück in das entsprechende Argument.
Eine Prozedur wird aufgerufen, mit einem [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Argument eines anderen Typs als die des entsprechenden Parameters.  
  
 Wenn Sie ein Argument übergeben `ByRef`, kopiert Visual Basic zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben. In diesem Fall müssen Visual Basic klicken Sie dann die Prozedur gibt den Wert den lokalen Variablen zurück in das Argument im aufrufenden Code kopieren.  
  
 Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich. Aber wenn die Typen unterschiedlich sind, müssen in beide Richtungen Visual Basic konvertieren. Da Sie nicht verwenden können `CType` oder eines anderes Konvertierungsschlüsselwort eines Prozedurarguments oder Parameter, eine solche Konvertierung ist immer implizit.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC41999  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie möglichst ein aufrufendes Argument desselben Typs wie der Prozedurparameter ein, damit Visual Basic nicht Konvertierung vornehmen muss.  
  
-   Wenn Sie die Prozedur mit einem Argument aufrufen müssen, dessen Typ sich vom Parametertyp unterscheidet, jedoch kein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Parameter und Argumente von Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
