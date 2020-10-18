---
title: "\"Optional\" erwartet."
ms.date: 07/20/2015
f1_keywords:
- bc30202
- vbc30202
helpviewer_keywords:
- BC30202
ms.assetid: 6f75060c-2db4-4a79-b5d1-5780c09a74cd
ms.openlocfilehash: 9c717cef2052722563e04595ef7a808ea103a75d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159819"
---
# <a name="bc30202-optional-expected"></a>BC30202: "optional" erwartet.

Auf ein optionales Argument in einer Prozedur Deklaration folgt ein erforderliches Argument. Jedes Argument, das auf ein optionales Argument folgt, muss ebenfalls optional sein.

 **Fehler-ID:** BC30202

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Wenn das Argument erforderlich ist, verschieben Sie es vor dem ersten optionalen Argument in der Argumentliste.

- Wenn das Argument optional sein soll, verwenden Sie das- `Optional` Schlüsselwort.

## <a name="see-also"></a>Siehe auch

- [Optionale Parameter](../../programming-guide/language-features/procedures/optional-parameters.md)
