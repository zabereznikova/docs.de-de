---
title: '#warning – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 38c3807a696599390667060d3bf374c68845fed0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715068"
---
# <a name="warning-c-reference"></a><span data-ttu-id="0edb5-102">#warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="0edb5-102">#warning (C# Reference)</span></span>
<span data-ttu-id="0edb5-103">Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Compilerwarnung [CS1030](../../misc/cs1030.md) der Stufe 1 generieren.</span><span class="sxs-lookup"><span data-stu-id="0edb5-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="0edb5-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="0edb5-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="0edb5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0edb5-105">Remarks</span></span>
 <span data-ttu-id="0edb5-106">Eine übliche Verwendung von `#warning` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0edb5-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="0edb5-107">Es ist auch möglich, einen benutzerdefinierten Fehler mit [#error](./preprocessor-error.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="0edb5-107">It is also possible to generate a user-defined error with [#error](./preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0edb5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0edb5-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="0edb5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0edb5-109">See also</span></span>

- [<span data-ttu-id="0edb5-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="0edb5-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="0edb5-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="0edb5-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="0edb5-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="0edb5-112">C# Preprocessor Directives</span></span>](./index.md)
