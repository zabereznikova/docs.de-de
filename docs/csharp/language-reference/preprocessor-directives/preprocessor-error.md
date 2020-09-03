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
# <a name="error-c-reference"></a><span data-ttu-id="72995-103">#error (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="72995-103">#error (C# Reference)</span></span>

<span data-ttu-id="72995-104">Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus eine benutzerdefinierte Fehlermeldung [CS1029](../compiler-messages/cs1029.md) generieren.</span><span class="sxs-lookup"><span data-stu-id="72995-104">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="72995-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="72995-105">For example:</span></span>

```csharp
#error Deprecated code in this method.
```

> [!NOTE]
> <span data-ttu-id="72995-106">Der Compiler behandelt `#error version` auf besondere Weise und meldet den Compilerfehler CS8304 mit einer Nachricht, die die verwendeten Compiler- und Sprachversionen enthält.</span><span class="sxs-lookup"><span data-stu-id="72995-106">The compiler treats `#error version` in a special way and reports a compiler error, CS8304, with a message containing the used compiler and language versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="72995-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="72995-107">Remarks</span></span>

<span data-ttu-id="72995-108">Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="72995-108">A common use of `#error` is in a conditional directive.</span></span>

<span data-ttu-id="72995-109">Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](./preprocessor-warning.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="72995-109">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>

## <a name="example"></a><span data-ttu-id="72995-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72995-110">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="72995-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72995-111">See also</span></span>

- [<span data-ttu-id="72995-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="72995-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="72995-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="72995-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="72995-114">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="72995-114">C# Preprocessor Directives</span></span>](./index.md)
