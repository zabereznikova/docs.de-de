---
title: "Implizite Konvertierung von &quot;&lt;&quot;Typname1&quot;&gt;&quot;to&quot;&lt;typename2&gt;&quot;in das Zurückkopieren des ByRef-Parameters&quot;&lt;Parametername&gt;&quot;in das entsprechende Argument. | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
dev_langs:
- VB
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: e397241aab78e17ea4efde0ea682d0e237fb8f8a
ms.lasthandoff: 03/13/2017

---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a>Implizite Konvertierung von '&lt;"Typname1"&gt;'to'&lt;typename2&gt;'in das Zurückkopieren des ByRef-Parameters'&lt;Parametername&gt;"in das entsprechende Argument.
Eine Prozedur wird aufgerufen, mit einem [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) Argument eines anderen Typs als die des entsprechenden Parameters.  
  
 Wenn Sie ein Argument übergeben `ByRef`, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] kopiert zuweilen den Argumentwert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben. In diesem Fall gibt die Prozedur [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen den Wert der lokalen Variablen in das Argument im aufrufenden Code kopieren.  
  
 Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich. Wenn die Typen unterschiedlich sind, aber [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] müssen in beide Richtungen konvertieren. Da Sie verwenden können `CType` oder eines der anderen Konvertierungsschlüsselwörter auf Prozedurarguments oder Parameter, eine solche Konvertierung immer implizit ist.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC41999  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden Sie nach Möglichkeit ein aufrufendes Argument vom gleichen Typ wie der Prozedurparameter also [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] muss nicht Konvertierung ausführen.  
  
-   Wenn Sie die Prozedur mit einem Argument aufrufen müssen anderen vom Parametertyp müssen jedoch nicht in das aufrufende Argument kein Wert zurückgegeben, definieren Sie den Parameter als [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) anstelle von `ByRef`.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Prozedurparameter und Argumente](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Übergeben von Argumenten als Wert und als Verweis](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
