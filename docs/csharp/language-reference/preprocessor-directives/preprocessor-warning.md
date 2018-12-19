---
title: '#warning – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 08fcefd904ad43c781017087082592120e21f5cd
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236829"
---
# <a name="warning-c-reference"></a><span data-ttu-id="cdb26-102">#warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="cdb26-102">#warning (C# Reference)</span></span>
<span data-ttu-id="cdb26-103">Mit `#warning` können Sie von einem bestimmten Ort in Ihrem Code aus eine Compilerwarnung [CS1030](../../misc/cs1030.md) der Stufe 1 generieren.</span><span class="sxs-lookup"><span data-stu-id="cdb26-103">`#warning` lets you generate a [CS1030](../../misc/cs1030.md) level one compiler warning from a specific location in your code.</span></span> <span data-ttu-id="cdb26-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="cdb26-104">For example:</span></span>  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="cdb26-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cdb26-105">Remarks</span></span>
 <span data-ttu-id="cdb26-106">Eine übliche Verwendung von `#warning` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="cdb26-106">A common use of `#warning` is in a conditional directive.</span></span> <span data-ttu-id="cdb26-107">Es ist auch möglich, einen benutzerdefinierten Fehler mit [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="cdb26-107">It is also possible to generate a user-defined error with [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cdb26-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cdb26-108">Example</span></span>  

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

## <a name="see-also"></a><span data-ttu-id="cdb26-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdb26-109">See Also</span></span>

- [<span data-ttu-id="cdb26-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="cdb26-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="cdb26-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cdb26-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="cdb26-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="cdb26-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
