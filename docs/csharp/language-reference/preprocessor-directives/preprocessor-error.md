---
title: '#<a name="error-c-reference"></a>error (C#-Referenz)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#error'
dev_langs:
- CSharp
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
caps.latest.revision: 10
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d2d497d7b8345b94dfc77176bf2b0ca79674e9be
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="error-c-reference"></a><span data-ttu-id="be35b-102">#error (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="be35b-102">#error (C# Reference)</span></span>
<span data-ttu-id="be35b-103">Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus einen Fehler generieren.</span><span class="sxs-lookup"><span data-stu-id="be35b-103">`#error` lets you generate an error from a specific location in your code.</span></span> <span data-ttu-id="be35b-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="be35b-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="be35b-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be35b-105">Remarks</span></span>  
 <span data-ttu-id="be35b-106">Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="be35b-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="be35b-107">Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="be35b-107">It is also possible to generate a user-defined warning with [#warning](../../../csharp/language-reference/preprocessor-directives/preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be35b-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be35b-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="be35b-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be35b-109">See Also</span></span>  
 <span data-ttu-id="be35b-110">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="be35b-110">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="be35b-111">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="be35b-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="be35b-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="be35b-112">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

