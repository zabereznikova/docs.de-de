---
title: '#error – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 7203e1271da66e78bfbd70717b0f5e536a7ebd86
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712519"
---
# <a name="error-c-reference"></a><span data-ttu-id="150ba-102">#error (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="150ba-102">#error (C# Reference)</span></span>
<span data-ttu-id="150ba-103">Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus eine benutzerdefinierte Fehlermeldung [CS1029](../compiler-messages/cs1029.md) generieren.</span><span class="sxs-lookup"><span data-stu-id="150ba-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="150ba-104">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="150ba-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="150ba-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="150ba-105">Remarks</span></span>  
 <span data-ttu-id="150ba-106">Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="150ba-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="150ba-107">Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](./preprocessor-warning.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="150ba-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="150ba-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="150ba-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="150ba-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="150ba-109">See also</span></span>

- [<span data-ttu-id="150ba-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="150ba-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="150ba-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="150ba-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="150ba-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="150ba-112">C# Preprocessor Directives</span></span>](./index.md)
