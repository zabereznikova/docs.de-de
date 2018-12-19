---
title: '#error – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: b335dfeed23d43938c66f0753590af55ac99b12a
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53235589"
---
# <a name="error-c-reference"></a><span data-ttu-id="7aea8-102">#error (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7aea8-102">#error (C# Reference)</span></span>
<span data-ttu-id="7aea8-103">Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus eine benutzerdefinierte Fehlermeldung [CS1029](../compiler-messages/cs1029.md) generieren.</span><span class="sxs-lookup"><span data-stu-id="7aea8-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="7aea8-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7aea8-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="7aea8-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7aea8-105">Remarks</span></span>  
 <span data-ttu-id="7aea8-106">Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="7aea8-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="7aea8-107">Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7aea8-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7aea8-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7aea8-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7aea8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7aea8-109">See Also</span></span>

- [<span data-ttu-id="7aea8-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7aea8-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="7aea8-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7aea8-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="7aea8-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="7aea8-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
