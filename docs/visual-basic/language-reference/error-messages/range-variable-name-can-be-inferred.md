---
title: Der Name einer Bereichsvariablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: 63990b7d37388057ff2cdb430d29878a1c7b39ba
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162361"
---
# <a name="bc36599-range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>BC36599: der Name der Bereichs Variablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden.

Ein Programmier Element, das ein oder mehrere Argumente annimmt, ist in einer LINQ-Abfrage enthalten. Der Compiler kann keine Bereichs Variable von diesem Programmier Element ableiten.

**Fehler-ID:** BC36599

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Geben Sie für das Programmier Element einen expliziten Variablennamen an, wie im folgenden Code gezeigt:

```vb
Dim query = From var1 In collection1
            Select VariableAlias= SampleFunction(var1), var1
```

## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [SELECT-Klausel](../queries/select-clause.md)
