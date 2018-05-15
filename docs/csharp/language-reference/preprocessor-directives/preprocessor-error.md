---
title: '#error (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 9ea4c24dcc3c0a4d39499bee5900cb9c6cc768c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="error-c-reference"></a><span data-ttu-id="c905f-102">#error (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c905f-102">#error (C# Reference)</span></span>
<span data-ttu-id="c905f-103">Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus einen Fehler generieren.</span><span class="sxs-lookup"><span data-stu-id="c905f-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="c905f-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c905f-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="c905f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c905f-105">Remarks</span></span>  
 <span data-ttu-id="c905f-106">Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c905f-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="c905f-107">Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c905f-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c905f-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c905f-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c905f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c905f-109">See Also</span></span>  
 [<span data-ttu-id="c905f-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c905f-110">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c905f-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c905f-111">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c905f-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="c905f-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
