---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249499"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
Werttypen und -strukturen können als null deklariert werden.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Sie können die nullfähige Deklaration jedoch nicht in Kombination mit dem Typrückschluss verwenden. Die folgenden Beispiele verursachen diesen Fehler.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Fehler-ID:** BC36629  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden `As` Sie eine Klausel, um die Variable als NULL-Werttyp zu deklarieren.  
  
## <a name="see-also"></a>Siehe auch

- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
