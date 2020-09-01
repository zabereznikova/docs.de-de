---
description: Methodenparameter – C#-Referenz
title: Methodenparameter – C#-Referenz
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 7090bf1c3df65cf1e65942404f883b49612e7521
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134405"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="4731d-103">Methodenparameter (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4731d-103">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="4731d-104">Parameter, die ohne [in](./in-parameter-modifier.md), [ref](./ref.md) oder [out](./out-parameter-modifier.md) für eine Methode deklariert werden, werden nach Werten an die aufgerufene Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="4731d-104">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="4731d-105">Dieser Wert kann in der Methode geändert werden, aber der geänderte Wert wird nicht gespeichert, wenn die aufrufende Prozedur wieder die Steuerung übernimmt.</span><span class="sxs-lookup"><span data-stu-id="4731d-105">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="4731d-106">Wenn Sie ein Schlüsselwort für einen Methodenparameter verwenden, können Sie dieses Verhalten ändern.</span><span class="sxs-lookup"><span data-stu-id="4731d-106">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="4731d-107">In diesem Abschnitt wird das Schlüsselwort beschrieben, dass Sie verwenden können, wenn Sie Methodenparameter deklarieren.</span><span class="sxs-lookup"><span data-stu-id="4731d-107">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="4731d-108">Mit [params](./params.md) wird festgelegt, dass für diesen Parameter eine veränderliche Anzahl von Argumenten akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="4731d-108">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="4731d-109">Mit [in](./in-parameter-modifier.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird, jedoch nur von der aufgerufenen Methode gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="4731d-109">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="4731d-110">Mit [ref](./ref.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird und von der aufgerufenen Methode gelesen oder geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="4731d-110">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="4731d-111">Mit [out](./out-parameter-modifier.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird und von der aufgerufenen Methode geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="4731d-111">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4731d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4731d-112">See also</span></span>

- [<span data-ttu-id="4731d-113">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4731d-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="4731d-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4731d-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="4731d-115">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4731d-115">C# Keywords</span></span>](./index.md)
