---
title: 'Vorgehensweise: Aufrufen einer überladenen Prozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
ms.openlocfilehash: 68b8a9898cba846b63ed8ce9d8329516f12e90cb
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91075173"
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic)

Der Vorteil beim Überladen einer Prozedur ist die Flexibilität des Aufrufes. Der aufrufende Code kann die Informationen abrufen, die er an die Prozedur übergeben muss, und dann einen einzelnen Prozedur Namen aufrufen, unabhängig davon, welche Argumente er übergibt.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>So wenden Sie eine Prozedur an, für die mehr als eine Version definiert ist  
  
1. Legen Sie im aufrufenden Code fest, welche Daten an die Prozedur übergeben werden sollen.  
  
2. Schreiben Sie den Prozedur Befehl auf die normale Weise, und stellen Sie die Daten in der Argumentliste dar. Stellen Sie sicher, dass die Argumente der Parameterliste in einer der für die Prozedur definierten Versionen entsprechen.  
  
3. Sie müssen nicht ermitteln, welche Version der Prozedur aufgerufen werden soll. Visual Basic übergibt die Steuerung an die Version, die mit der Argumentliste übereinstimmt.  
  
     Im folgenden Beispiel wird die `post` in Gewusst [wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)deklarierte Prozedur aufgerufen. Er ruft die Kundenidentifikation ab, bestimmt, ob es sich um ein `String` oder handelt `Integer` , und ruft dann in beiden Fällen dieselbe Prozedur auf.  
  
     [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
     [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweisen](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Prozedurüberladung](./procedure-overloading.md)
- [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)
- [Vorgehensweise: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)
- [Vorgehensweise: Überladen einer Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Vorgehensweise: Überladen einer Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Überlegungen zur Prozedurüberladung](./considerations-in-overloading-procedures.md)
- [Overload Resolution](./overload-resolution.md)
- [Überladungen](../../../language-reference/modifiers/overloads.md)
