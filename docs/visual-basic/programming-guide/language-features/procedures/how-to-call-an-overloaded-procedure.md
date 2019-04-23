---
title: 'Vorgehensweise: Aufrufen einer überladenen Prozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: d325c09516b4ce03facedce86f17ea49480b997a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59317805"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Vorgehensweise: Aufrufen einer überladenen Prozedur (Visual Basic)
Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs. Der aufrufende Code kann die Informationen abrufen, die er an die Prozedur übergeben, und rufen Sie dann auf einen einzelnen Prozedurnamen, unabhängig davon, welche Argumente übergeben werden muss.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Zum Aufrufen einer Prozedur, die mehr als eine Version, die definiert wurde.  
  
1. Bestimmen Sie im aufrufenden Code, welche Daten an die Prozedur übergeben.  
  
2. Schreiben Sie den Aufruf der Prozedur, auf die übliche Weise, die darstellen der Daten in der Argumentliste. Achten Sie darauf, dass die Argumente die Parameterliste in einer der Versionen für die Prozedur definierten übereinstimmen.  
  
3. Sie müssen nicht festlegen, welche Version der Prozedur aufrufen. Visual Basic übergibt die Steuerung an die Version, die angegebene Argumentliste passt.  
  
     Im folgenden Beispiel wird die `post` Prozedur deklariert [Vorgehensweise: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md). Es ruft die Kunden-ID, die bestimmt, ob es eine `String` oder `Integer`, und ruft dann in beiden Fällen das gleiche Verfahren.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Definieren Sie mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Überladungsauflösung](./overload-resolution.md)
- [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
