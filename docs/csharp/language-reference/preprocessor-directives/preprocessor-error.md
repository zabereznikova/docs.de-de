---
description: '#error – C#-Referenz'
title: '#error – C#-Referenz'
ms.date: 08/24/2020
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 76325901c5e39f340545b186a0aa9546cd853ff8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89138097"
---
# <a name="error-c-reference"></a>#error (C#-Referenz)

Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus eine benutzerdefinierte Fehlermeldung [CS1029](../compiler-messages/cs1029.md) generieren. Beispiel:

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> Der Compiler behandelt `#error version` auf besondere Weise und meldet den Compilerfehler CS8304 mit einer Nachricht, die die verwendeten Compiler- und Sprachversionen enthält.

## <a name="remarks"></a>Bemerkungen

Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.

Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](./preprocessor-warning.md) zu generieren.

## <a name="example"></a>Beispiel

```csharp
// preprocessor_error.cs
// CS1029 expected
#define DEBUG
class MainClass
{
    static void Main()
    {
#if DEBUG
#error DEBUG is defined
#endif
    }
}
```

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)
