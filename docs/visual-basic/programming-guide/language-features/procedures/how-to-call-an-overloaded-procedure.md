---
title: "Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, overloading
- procedures, calling
- procedures, multiple versions
- procedure calls, overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 0da83aa63bf013d841f2a01a535726f3b03497a1
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer überladenen Prozedur (Visual Basic)
Der Vorteil der überladen einer Prozedur ist die Flexibilität des Aufrufs. Der aufrufende Code kann die Informationen abrufen, die an die Prozedur übergeben, und rufen Sie dann einen einzelnen Prozedurnamen, unabhängig davon, welche Argumente übergeben werden muss.  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a>Zum Aufrufen einer Prozedur, die mehr als eine Version definiert wurde.  
  
1.  Bestimmen Sie in den aufrufenden Code, welche Daten an die Prozedur übergeben.  
  
2.  Schreiben Sie den Prozeduraufruf auf die übliche Weise, die Präsentation von Daten in der Argumentliste. Werden Sie sicher, dass die Argumente der Parameterliste einer der Versionen für die Prozedur definiert übereinstimmen.  
  
3.  Sie müssen keinen bestimmen, welche Version der Prozedur aufrufen. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]übergibt die Steuerung an die Version der Argumentliste.  
  
     Im folgenden Beispiel wird die `post` Prozedur deklariert [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md). Es ruft die Kunden-ID, bestimmt, ob es ein `String` oder `Integer`, und ruft dann in beiden Fällen das gleiche Verfahren.  
  
     [!code-vb[VbVbcnProcedures&#56;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures&#57;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Prozedurüberladung](./procedure-overloading.md)   
 [Problembehandlung bei Prozeduren](./troubleshooting-procedures.md)   
 [Gewusst wie: Definieren mehrerer Versionen einer Prozedur](./how-to-define-multiple-versions-of-a-procedure.md)   
 [Gewusst wie: überladen eine Prozedur mit optionalen Parametern](./how-to-overload-a-procedure-that-takes-optional-parameters.md)   
 [Gewusst wie: überladen eine Prozedur mit einer unbestimmten Anzahl von Parametern](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)   
 [Überlegungen zur prozedurüberladung](./considerations-in-overloading-procedures.md)   
 [Überladungsauflösung](./overload-resolution.md)   
 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)
