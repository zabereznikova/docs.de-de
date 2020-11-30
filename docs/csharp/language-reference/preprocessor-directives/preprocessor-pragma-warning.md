---
description: '#pragma warning – C#-Referenz'
title: '#pragma warning – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#pragma warning'
helpviewer_keywords:
- '#pragma warning [C#]'
ms.assetid: 723493d5-9753-4cec-babb-54e2b8eb36b6
ms.openlocfilehash: 5b67d384e37a5e509ce8ebcc5ddeb16a4437ea2b
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91168529"
---
# <a name="pragma-warning-c-reference"></a><span data-ttu-id="b9106-103">#pragma warning (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b9106-103">#pragma warning (C# Reference)</span></span>

<span data-ttu-id="b9106-104">`#pragma warning` kann bestimmte Warnungen aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="b9106-104">`#pragma warning` can enable or disable certain warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9106-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b9106-105">Syntax</span></span>  
  
```csharp
#pragma warning disable warning-list  
#pragma warning restore warning-list  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9106-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b9106-106">Parameters</span></span>  

 `warning-list`  
 <span data-ttu-id="b9106-107">Eine durch Trennzeichen getrennte Liste mit Warnzahlen.</span><span class="sxs-lookup"><span data-stu-id="b9106-107">A comma-separated list of warning numbers.</span></span> <span data-ttu-id="b9106-108">Das Präfix „CS“ ist optional.</span><span class="sxs-lookup"><span data-stu-id="b9106-108">The "CS" prefix is optional.</span></span>  
  
 <span data-ttu-id="b9106-109">Wenn keine Warnzahlen angegeben werden, deaktiviert `disable` alle Warnungen und `restore` aktiviert sie.</span><span class="sxs-lookup"><span data-stu-id="b9106-109">When no warning numbers are specified, `disable` disables all warnings and `restore` enables all warnings.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9106-110">Um Warnzahlen in Visual Studio zu suchen, erstellen Sie Ihr Projekt und suchen Sie nach den Warnzahlen im Fenster **Ausgabe**.</span><span class="sxs-lookup"><span data-stu-id="b9106-110">To find warning numbers in Visual Studio, build your project and then look for the warning numbers in the **Output** window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9106-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b9106-111">Example</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b9106-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9106-112">See also</span></span>

- [<span data-ttu-id="b9106-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b9106-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b9106-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b9106-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b9106-115">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="b9106-115">C# Preprocessor Directives</span></span>](./index.md)
- [<span data-ttu-id="b9106-116">C#-Compilerfehler</span><span class="sxs-lookup"><span data-stu-id="b9106-116">C# Compiler Errors</span></span>](../compiler-messages/index.md)
