---
title: Implizite Konvertierung von "<typename1>" in "<typename2>" beim Zurückkopieren des Wertes des ByRef-Parameters "<parametername>" in das entsprechende Argument.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: fced95fe24d42d4af2118706bcaf3337429fea91
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873987"
---
# <a name="implicit-conversion-from-typename1-to-typename2-in-copying-the-value-of-byref-parameter-parametername-back-to-the-matching-argument"></a>Implizite Konvertierung von "\<typename1>" in "\<typename2>" beim Zurückkopieren des Wertes des ByRef-Parameters "\<parametername>" in das entsprechende Argument.

Eine Prozedur wird mit einem [ByRef](../modifiers/byref.md) -Argument eines anderen Typs aufgerufen als der des entsprechenden Parameters.  
  
 Wenn Sie ein Argument übergeben `ByRef` , kopiert Visual Basic manchmal den Argument Wert in eine lokale Variable in der Prozedur, statt einen Verweis zu übergeben. In diesem Fall muss Visual Basic den Wert der lokalen Variablen zurück in das Argument im aufrufenden Code kopieren, wenn die Prozedur zurückgibt.  
  
 Wenn ein `ByRef` -Argumentwert in die Prozedur kopiert wird und das Argument und der Parameter denselben Typ aufweisen, ist keine Konvertierung erforderlich. Wenn die Typen jedoch unterschiedlich sind, müssen Visual Basic in beide Richtungen konvertieren. Da Sie `CType` oder keines der anderen Konvertierungs Schlüsselwörter für ein Prozedur Argument oder einen Parameter verwenden können, ist eine solche Konvertierung immer implizit.  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC41999  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie nach Möglichkeit ein Aufruf Endes Argument desselben Typs wie der Prozedur Parameter, sodass Visual Basic keine Konvertierung durchführen muss.  
  
- Wenn Sie die Prozedur mit einem Argument aufrufen müssen, dessen Typ sich vom Parametertyp unterscheidet, jedoch kein Wert in das aufrufende Argument zurückgegeben werden muss, definieren Sie den Parameter als [ByVal](../modifiers/byval.md) anstelle von `ByRef`.  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweisen](../../programming-guide/language-features/procedures/index.md)
- [Parameter und Argumente von Prozeduren](../../programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Übergeben von Argumenten als Wert und als Verweis](../../programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
- [Implizite und explizite Konvertierungen](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
