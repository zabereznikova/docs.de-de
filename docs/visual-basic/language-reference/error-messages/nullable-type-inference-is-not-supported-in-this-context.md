---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: f2d3bcdaccfd993da1eebf81ae961f35eb22b294
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873675"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt

Werttypen und Strukturen können als Nullable deklariert werden.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Es ist jedoch nicht möglich, die Deklaration, die NULL zulässt, in Kombination mit dem Typrückschluss In den folgenden Beispielen wird dieser Fehler verursacht.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Fehler-ID:** BC36629  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Verwenden Sie eine- `As` Klausel, um die Variable als Werte zulässt-Werttyp zu deklarieren.  
  
## <a name="see-also"></a>Weitere Informationen

- [Auf NULL festlegbare Werttypen](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md)
