---
title: Methodenparameter (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b20d2d233350cfb9de55cbd07e722082ec311597
ms.sourcegitcommit: 83dd5ec003e788ccb3e33f3412a7af39ae347646
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2018
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="56690-102">Methodenparameter (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="56690-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="56690-103">Parameter, die ohne [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) oder [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) für eine Methode deklariert werden, werden nach Werten an die aufgerufene Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="56690-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="56690-104">Dieser Wert kann in der Methode geändert werden, aber der geänderte Wert wird nicht gespeichert, wenn die aufrufende Prozedur wieder die Steuerung übernimmt.</span><span class="sxs-lookup"><span data-stu-id="56690-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="56690-105">Wenn Sie ein Schlüsselwort für einen Methodenparameter verwenden, können Sie dieses Verhalten ändern.</span><span class="sxs-lookup"><span data-stu-id="56690-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="56690-106">In diesem Abschnitt wird das Schlüsselwort beschrieben, dass Sie verwenden können, wenn Sie Methodenparameter deklarieren.</span><span class="sxs-lookup"><span data-stu-id="56690-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   [<span data-ttu-id="56690-107">params</span><span class="sxs-lookup"><span data-stu-id="56690-107">params</span></span>](../../../csharp/language-reference/keywords/params.md)  
  
-   [<span data-ttu-id="56690-108">in</span><span class="sxs-lookup"><span data-stu-id="56690-108">in</span></span>](../../../csharp/language-reference/keywords/in-parameter-modifier.md)  
  
-   [<span data-ttu-id="56690-109">ref</span><span class="sxs-lookup"><span data-stu-id="56690-109">ref</span></span>](../../../csharp/language-reference/keywords/ref.md)  
  
-   [<span data-ttu-id="56690-110">out</span><span class="sxs-lookup"><span data-stu-id="56690-110">out</span></span>](../../../csharp/language-reference/keywords/out-parameter-modifier.md)  
  
## <a name="see-also"></a><span data-ttu-id="56690-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56690-111">See Also</span></span>  
 [<span data-ttu-id="56690-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="56690-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="56690-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="56690-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="56690-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="56690-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
