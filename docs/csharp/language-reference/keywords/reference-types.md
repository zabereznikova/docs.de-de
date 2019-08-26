---
title: Verweistypen – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.referencetypes
helpviewer_keywords:
- reference types [C#]
- C# language, reference types
- types [C#], reference types
ms.assetid: 801cf030-6e2d-4a0d-9daf-1431b0c31f47
ms.openlocfilehash: 27aed0a1805c1daf4491a3da26371e3312547a6f
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608607"
---
# <a name="reference-types-c-reference"></a>Verweistypen (C#-Referenz)

Es gibt zwei Arten von Typen in C#: Verweistypen und Werttypen. Variablen von Verweistypen speichern Verweise auf ihre Daten (Objekte), während Variablen von Werttypen ihre Daten direkt enthalten. Bei Verweistypen können zwei Variablen auf dasselbe Objekt verweisen. Daher können auf eine Variable angewendete Operationen das Objekt beeinflussen, auf das von der anderen Variablen verwiesen wird. Bei Werttypen besitzt jede Variable eine eigene Kopie der Daten, und auf eine Variable angewendete Operationen können die andere Variable nicht beeinflussen (außer im Fall von ref- und out-Parametervariablen, siehe [in](in-parameter-modifier.md), [ref](ref.md) und [out](out-parameter-modifier.md)-Parametermodifizierer).

 Die folgenden Schlüsselwörter werden verwendet, um Verweistypen zu deklarieren:

- [class](class.md)

- [interface](interface.md)

- [delegate](delegate.md)

 C# enthält auch die folgenden integrierten Referenztypen:

- [dynamic](dynamic.md)

- [object](object.md)

- [string](string.md)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Typen](types.md)
- [Werttypen](value-types.md)
