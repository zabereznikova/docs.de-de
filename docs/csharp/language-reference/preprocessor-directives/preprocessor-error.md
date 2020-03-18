---
title: '#error – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#error'
helpviewer_keywords:
- '#error directive [C#]'
ms.assetid: f2a7f3af-4cf9-4111-b369-70204d24b26b
ms.openlocfilehash: 28e77304edee617adc1422e6a52d0a617cd9b3bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173405"
---
# <a name="error-c-reference"></a><span data-ttu-id="bc9a5-102">#error (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bc9a5-102">#error (C# Reference)</span></span>
<span data-ttu-id="bc9a5-103">Mit `#error` können Sie von einem bestimmten Ort in Ihrem Code aus eine benutzerdefinierte Fehlermeldung [CS1029](../compiler-messages/cs1029.md) generieren.</span><span class="sxs-lookup"><span data-stu-id="bc9a5-103">`#error` lets you generate a [CS1029](../compiler-messages/cs1029.md) user-defined error from a specific location in your code.</span></span> <span data-ttu-id="bc9a5-104">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bc9a5-104">For example:</span></span>  
  
```csharp
#error Deprecated code in this method.  
```  
  
## <a name="remarks"></a><span data-ttu-id="bc9a5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bc9a5-105">Remarks</span></span>  
 <span data-ttu-id="bc9a5-106">Eine übliche Verwendung von `#error` ist die Verwendung in einer bedingten Anweisung.</span><span class="sxs-lookup"><span data-stu-id="bc9a5-106">A common use of `#error` is in a conditional directive.</span></span>  
  
 <span data-ttu-id="bc9a5-107">Es ist auch möglich, eine benutzerdefinierte Warnung mit [#warning](./preprocessor-warning.md) zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bc9a5-107">It is also possible to generate a user-defined warning with [#warning](./preprocessor-warning.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc9a5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc9a5-108">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc9a5-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc9a5-109">See also</span></span>

- [<span data-ttu-id="bc9a5-110">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bc9a5-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bc9a5-111">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bc9a5-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bc9a5-112">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="bc9a5-112">C# Preprocessor Directives</span></span>](./index.md)
