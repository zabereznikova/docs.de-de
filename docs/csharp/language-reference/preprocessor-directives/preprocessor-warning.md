---
title: '#warning (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 59ca63d5089e377627a9116f24f9a0a1681bb4b2
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932676"
---
# <a name="warning-c-reference"></a><span data-ttu-id="43a64-102">#warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="43a64-102">#warning (C# Reference)</span></span>
<span data-ttu-id="43a64-103">Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Compilerwarnung [CS1030](../../misc/cs1030.md) der Stufe 1 generieren.</span><span class="sxs-lookup"><span data-stu-id="43a64-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="43a64-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="43a64-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="43a64-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43a64-105">Remarks</span></span>
 <span data-ttu-id="43a64-106">Eine übliche Verwendung von `#warning` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="43a64-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="43a64-107">Es ist auch möglich, einen benutzerdefinierten Fehler mit [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="43a64-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="43a64-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="43a64-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="43a64-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43a64-109">See Also</span></span>

- [<span data-ttu-id="43a64-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="43a64-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="43a64-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="43a64-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="43a64-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="43a64-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
