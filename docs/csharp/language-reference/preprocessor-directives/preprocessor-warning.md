---
description: '#warning – C#-Referenz'
title: '#warning – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 9ade723bdca17597dcd56240f506e60f2debf6be
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186418"
---
# <a name="warning-c-reference"></a><span data-ttu-id="6169b-103">#warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6169b-103">#warning (C# Reference)</span></span>

<span data-ttu-id="6169b-104">Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Compilerwarnung [CS1030](../../misc/cs1030.md) der Stufe 1 generieren.</span><span class="sxs-lookup"><span data-stu-id="6169b-104">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="6169b-105">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6169b-105">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="6169b-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6169b-106">Remarks</span></span>

 <span data-ttu-id="6169b-107">Eine übliche Verwendung von `#warning` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6169b-107">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="6169b-108">Es ist auch möglich, einen benutzerdefinierten Fehler mit [#error](./preprocessor-error.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6169b-108">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6169b-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6169b-109">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="6169b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6169b-110">See also</span></span>

- [<span data-ttu-id="6169b-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6169b-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6169b-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6169b-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6169b-113">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="6169b-113">C# Preprocessor Directives</span></span>](./index.md)
