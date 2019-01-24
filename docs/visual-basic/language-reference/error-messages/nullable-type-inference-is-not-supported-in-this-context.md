---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 7dffc5233656257cd892f573a2f8b9f91d781c21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54611890"
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
  
-   Verwenden einer `As` -Klausel, um die Variable als auf NULL festlegbar deklariert werden.  
  
## <a name="see-also"></a>Siehe auch
- [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
