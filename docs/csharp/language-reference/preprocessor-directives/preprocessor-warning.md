---
title: '#warning – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 3d09cd95ef4d53e3f11d9feb9675ebba22d6f857
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608525"
---
# <a name="warning-c-reference"></a><span data-ttu-id="6ebe8-102">#warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6ebe8-102">#warning (C# Reference)</span></span>
<span data-ttu-id="6ebe8-103">Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Compilerwarnung [CS1030](../../misc/cs1030.md) der Stufe 1 generieren.</span><span class="sxs-lookup"><span data-stu-id="6ebe8-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="6ebe8-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6ebe8-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="6ebe8-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="6ebe8-105">Remarks</span></span>
 <span data-ttu-id="6ebe8-106">Eine übliche Verwendung von `#warning` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6ebe8-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="6ebe8-107">Es ist auch möglich, einen benutzerdefinierten Fehler mit [#error](./preprocessor-error.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6ebe8-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ebe8-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ebe8-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="6ebe8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ebe8-109">See also</span></span>

- [<span data-ttu-id="6ebe8-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6ebe8-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6ebe8-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6ebe8-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6ebe8-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="6ebe8-112">C# Preprocessor Directives</span></span>](./index.md)
