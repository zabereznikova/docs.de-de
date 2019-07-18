---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 3ab8028062402e33b787a5a8649d93d975918393
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665704"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
Werttypen und Strukturen können auf NULL festlegbare deklariert werden.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Sie können nicht jedoch die NULL-Werte zulassen Deklaration in Kombination mit den Typrückschluss verwenden. In den folgenden Beispielen werden diese Fehler verursachen.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Fehler-ID:** BC36629  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden einer `As` -Klausel, um die Variable als auf NULL festlegbar deklariert werden.  
  
## <a name="see-also"></a>Siehe auch

- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
