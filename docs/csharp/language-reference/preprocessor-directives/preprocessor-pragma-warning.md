---
title: '#pragma-Warnung (C#-Referenz)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5330b448dc2b328992b2d29699557d20df56dee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="ed032-102">#pragma warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ed032-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="ed032-103">`#pragma warning` kann bestimmte Warnungen aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="ed032-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed032-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ed032-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed032-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ed032-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="ed032-106">Eine durch Trennzeichen getrennte Liste mit Warnzahlen.</span><span class="sxs-lookup"><span data-stu-id="ed032-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="ed032-107">Das Präfix „CS“ ist optional.</span><span class="sxs-lookup"><span data-stu-id="ed032-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="ed032-108">Wenn keine Warnzahlen angegeben werden, deaktiviert `disable` alle Warnungen und `restore` aktiviert sie.</span><span class="sxs-lookup"><span data-stu-id="ed032-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ed032-109">Um Warnzahlen in Visual Studio zu suchen, erstellen Sie Ihr Projekt und suchen Sie nach den Warnzahlen im Fenster **Ausgabe**.</span><span class="sxs-lookup"><span data-stu-id="ed032-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ed032-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ed032-110">Example</span></span>  
  
```csharp
// pragma_warning.cs  
using System;  
  
#pragma warning disable 414, CS3021  
[CLSCompliant(false)]  
public class C  
{  
    int i = 1;  
    static void Main()  
    {  
    }  
}  
#pragma warning restore CS3021  
[CLSCompliant(false)]  // CS3021  
public class D  
{  
    int i = 1;  
    public static void F()  
    {  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ed032-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ed032-111">See Also</span></span>  
 [<span data-ttu-id="ed032-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ed032-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ed032-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ed032-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ed032-114">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="ed032-114">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)  
 [<span data-ttu-id="ed032-115">C#-Compilerfehler</span><span class="sxs-lookup"><span data-stu-id="ed032-115">C# Compiler Errors</span></span>](../../../csharp/language-reference/compiler-messages/index.md)
