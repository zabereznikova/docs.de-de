---
title: Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 610d2dc427d882c412b87eb67f021a8a86025f25
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159925"
---
# <a name="bc36629-nullable-type-inference-is-not-supported-in-this-context"></a>BC36629: der Typrückschluss, der NULL zulässt, wird in diesem Kontext nicht unterstützt

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

## <a name="see-also"></a>Siehe auch

- [Auf NULL festlegbare Werttypen](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md)
