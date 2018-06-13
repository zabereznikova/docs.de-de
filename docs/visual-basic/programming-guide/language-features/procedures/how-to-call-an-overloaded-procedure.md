---
title: 'Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 802a312d6ec6640594f3c6b662202d1ffcf2376d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649125"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic)
Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs. Der aufrufende Code erhalten die Informationen, die sie an die Prozedur übergeben, und rufen Sie anschließend auf einen einzelnen Prozedurnamen, unabhängig davon, welche Argumente übergeben werden muss.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Zum Aufrufen einer Prozedur, die mehr als eine Version definiert wurde.  
  
1.  Bestimmen Sie in den aufrufenden Code, welche Daten an die Prozedur übergeben.  
  
2.  Schreiben des Prozeduraufrufs auf normale Weise darstellen der Daten in der Argumentliste. Achten Sie darauf, dass die Argumente die Parameterliste in einer der Versionen für die Prozedur definierten übereinstimmen.  
  
3.  Sie müssen keinen bestimmen, welche Version der Prozedur aufrufen. Visual Basic übergibt die Steuerung an die Version, die Ihre Argumentliste entspricht.  
  
     Im folgenden Beispiel wird die `post` Prozedur deklariert [wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md). Es ruft die Kunden-ID, bestimmt, ob es ist ein `String` oder ein `Integer`, und ruft dann in beiden Fällen das gleiche Verfahren.  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Prozedurüberladung](./procedure-overloading.md)  
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)  
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Gewusst wie: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Gewusst wie: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)  
 [Überladungsauflösung](./overload-resolution.md)  
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
