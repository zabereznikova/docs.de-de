---
title: "Typparameter können nicht als Qualifizierer verwendet werden."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords: BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 58be51e0c05750ee044f0287cde8db037718b4aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a>Typparameter können nicht als Qualifizierer verwendet werden.
Ein Programmierelement wird mit einem Qualifizierungspfad qualifiziert, der einen Typparameter enthält.  
  
 Einen Typparameter darstellt, eine Anforderung für einen Typ, der bereitgestellt werden, wenn der generische Typ konstruiert wird. Es stellt einen bestimmten definierten Typ dar. Ein Qualifizierungspfad darf nur Elemente enthalten, die zum Zeitpunkt der Kompilierung definiert sind.  
  
 Dieser Fehler kann durch die folgenden Anweisungen generiert werden.  
  
```  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 **Fehler-ID:** BC32098  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie den Typparameter in der qualifizierungszeichenfolge oder Ersetzen Sie ihn durch einen definierten Typ.  
  
2.  Wenn Sie einen konstruierten Typ verwenden, suchen Sie das Programmierelement qualifiziert werden müssen, müssen Sie zusätzliche Programmlogik verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Typliste](../../../visual-basic/language-reference/statements/type-list.md)
