---
title: '#pragma warning – C#-Referenz'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: dc221235e78a187f921815ed6e6c7750778014d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922274"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="f7ca2-102">#pragma warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f7ca2-102">#pragma warning (C# Reference)</span></span>
<span data-ttu-id="f7ca2-103">`#pragma warning` kann bestimmte Warnungen aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f7ca2-103">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7ca2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7ca2-104">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7ca2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f7ca2-105">Parameters</span></span>  
 `warning-list`  
 <span data-ttu-id="f7ca2-106">Eine durch Trennzeichen getrennte Liste mit Warnzahlen.</span><span class="sxs-lookup"><span data-stu-id="f7ca2-106">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="f7ca2-107">Das Präfix „CS“ ist optional.</span><span class="sxs-lookup"><span data-stu-id="f7ca2-107">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="f7ca2-108">Wenn keine Warnzahlen angegeben werden, deaktiviert `disable` alle Warnungen und `restore` aktiviert sie.</span><span class="sxs-lookup"><span data-stu-id="f7ca2-108">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f7ca2-109">Um Warnzahlen in Visual Studio zu suchen, erstellen Sie Ihr Projekt und suchen Sie nach den Warnzahlen im Fenster **Ausgabe**.</span><span class="sxs-lookup"><span data-stu-id="f7ca2-109">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7ca2-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7ca2-110">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f7ca2-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7ca2-111">See also</span></span>

- [<span data-ttu-id="f7ca2-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f7ca2-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f7ca2-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f7ca2-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f7ca2-114">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="f7ca2-114">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="f7ca2-115">C#-Compilerfehler</span><span class="sxs-lookup"><span data-stu-id="f7ca2-115">C# Compiler Errors</span></span>](../compiler-messages/index.md)
