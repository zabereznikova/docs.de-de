---
title: Konstanten müssen einen systeminternen oder enumerierten Typ aufweisen, keinen Klassen-, Struktur-, Typparameter- oder Arraytyp.
ms.date: 07/20/2015
f1_keywords:
- vbc30424
- bc30424
helpviewer_keywords:
- BC30424
ms.assetid: 2d402c2f-27ad-428b-b699-d45cd62f7196
ms.openlocfilehash: e820287f0ddf462b30867d90501f7d730c9c6739
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163154"
---
# <a name="bc30424-constants-must-be-of-an-intrinsic-or-enumerated-type-not-a-class-structure-type-parameter-or-array-type"></a>BC30424: Konstanten müssen einen systeminternen oder enumerierten Typ aufweisen, keine Klasse, Struktur, Typparameter oder Arraytyp.

Sie haben versucht, eine Konstante als Klasse, Struktur oder Arraytyp oder als Typparameter zu deklarieren, der durch einen enthaltenden generischen Typ definiert wird.

 Konstanten müssen einen systeminternen Typ aufweisen ( `Boolean` , `Byte` , `Date` , `Decimal` , `Double` , `Integer` , `Long` , `Object` , `SByte` , `Short` , `Single` , `String` , `UInteger` , `ULong` oder `UShort` ), oder ein Typ, der `Enum` auf einem der ganzzahligen Typen basiert.

 **Fehler-ID:** BC30424

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Deklarieren Sie die Konstante als systeminterne oder- `Enum` Typ.

2. Eine Konstante kann auch ein spezieller Wert sein, z `True` `False` . b., oder `Nothing` . Der Compiler betrachtet diese vordefinierten Werte als den geeigneten systeminternen Typ.

## <a name="see-also"></a>Siehe auch

- [Konstanten und Enumerationen](../constants-and-enumerations.md)
- [Datentypen](../../programming-guide/language-features/data-types/index.md)
- [Datentypen](../data-types/index.md)
