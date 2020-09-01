---
description: '#warning – C#-Referenz'
title: '#warning – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: ab2cc5120492fc2a4b94296eb85e563c0a1d5ad3
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137837"
---
# <a name="warning-c-reference"></a><span data-ttu-id="c8653-103">#warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c8653-103">#warning (C# Reference)</span></span>
<span data-ttu-id="c8653-104">Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Compilerwarnung [CS1030](../../misc/cs1030.md) der Stufe 1 generieren.</span><span class="sxs-lookup"><span data-stu-id="c8653-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="c8653-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c8653-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="c8653-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c8653-106">Remarks</span></span>
 <span data-ttu-id="c8653-107">Eine übliche Verwendung von `#warning` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c8653-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="c8653-108">Es ist auch möglich, einen benutzerdefinierten Fehler mit [#error](./preprocessor-error.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c8653-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c8653-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c8653-109">Example</span></span>  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="c8653-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8653-110">See also</span></span>

- [<span data-ttu-id="c8653-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c8653-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8653-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c8653-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8653-113">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="c8653-113">C# Preprocessor Directives</span></span>](./index.md)
