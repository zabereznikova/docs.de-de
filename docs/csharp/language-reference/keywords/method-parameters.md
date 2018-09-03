---
title: Methodenparameter (C#-Referenz)
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 446a5239fa1de8559dea50f7e8b8869aed0297c5
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43389999"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="72388-102">Methodenparameter (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="72388-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="72388-103">Parameter, die ohne [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) oder [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) für eine Methode deklariert werden, werden nach Werten an die aufgerufene Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="72388-103">Parameters declared for a method without [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md), [ref](../../../csharp/language-reference/keywords/ref.md) or [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="72388-104">Dieser Wert kann in der Methode geändert werden, aber der geänderte Wert wird nicht gespeichert, wenn die aufrufende Prozedur wieder die Steuerung übernimmt.</span><span class="sxs-lookup"><span data-stu-id="72388-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="72388-105">Wenn Sie ein Schlüsselwort für einen Methodenparameter verwenden, können Sie dieses Verhalten ändern.</span><span class="sxs-lookup"><span data-stu-id="72388-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="72388-106">In diesem Abschnitt wird das Schlüsselwort beschrieben, dass Sie verwenden können, wenn Sie Methodenparameter deklarieren.</span><span class="sxs-lookup"><span data-stu-id="72388-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
-   <span data-ttu-id="72388-107">Mit [params](../../../csharp/language-reference/keywords/params.md) wird festgelegt, dass für diesen Parameter eine veränderliche Anzahl von Argumenten akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="72388-107">[params](../../../csharp/language-reference/keywords/params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
-   <span data-ttu-id="72388-108">Mit [in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird, jedoch nur von der aufgerufenen Methode gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="72388-108">[in](../../../csharp/language-reference/keywords/in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
-   <span data-ttu-id="72388-109">Mit [ref](../../../csharp/language-reference/keywords/ref.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird und von der aufgerufenen Methode gelesen oder geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="72388-109">[ref](../../../csharp/language-reference/keywords/ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
-   <span data-ttu-id="72388-110">Mit [out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird und von der aufgerufenen Methode geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="72388-110">[out](../../../csharp/language-reference/keywords/out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="72388-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72388-111">See Also</span></span>

- [<span data-ttu-id="72388-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="72388-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="72388-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="72388-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="72388-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="72388-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
