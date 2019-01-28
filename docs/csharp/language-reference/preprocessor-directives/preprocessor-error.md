---
title: '#error – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 3aa31ce7e189684bd60c238905df3bcbd1818ed6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559336"
---
# <a name="error-c-reference"></a><span data-ttu-id="33a7e-102">#error (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="33a7e-102">#error (C# Reference)</span></span>
<span data-ttu-id="33a7e-103">Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus eine benutzerdefinierte Fehlermeldung [CS1029](../compiler-messages/cs1029.md) generieren.</span><span class="sxs-lookup"><span data-stu-id="33a7e-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="33a7e-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="33a7e-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="33a7e-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33a7e-105">Remarks</span></span>  
 <span data-ttu-id="33a7e-106">Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="33a7e-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="33a7e-107">Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="33a7e-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="33a7e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="33a7e-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="33a7e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33a7e-109">See also</span></span>

- [<span data-ttu-id="33a7e-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="33a7e-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="33a7e-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="33a7e-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="33a7e-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="33a7e-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
