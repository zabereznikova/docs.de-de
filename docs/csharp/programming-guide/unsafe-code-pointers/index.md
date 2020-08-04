---
title: 'Unsicherer Code und Zeiger: C#-Programmierhandbuch'
Description: Hier erfahren Sie mehr über unsicheren Code und Zeiger. C# unterstützt keine Zeiger, Sie können jedoch einen unsicheren Kontext definieren, in dem Zeiger mit dem Schlüsselwort unsafe verwendet werden können.
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 5684a97ed6f7b6632d8fe3d52747d9187c4b8cbc
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381774"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="4c8bb-104">Unsicherer Code und Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4c8bb-104">Unsafe code and pointers (C# Programming Guide)</span></span>

<span data-ttu-id="4c8bb-105">Um Typsicherheit und Sicherheit zu gewährleisten, unterstützt C# standardmäßig keine Zeigerarithmetik.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-105">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="4c8bb-106">Sie können jedoch das [unsafe](../../language-reference/keywords/unsafe.md)-Schlüsselwort verwenden, um einen unsicheren Kontext zu definieren, in dem Zeiger verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-106">However, by using the [unsafe](../../language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="4c8bb-107">Weitere Informationen über Zeiger finden Sie unter [Zeigertypen](pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="4c8bb-107">For more information about pointers, see [Pointer types](pointer-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c8bb-108">In der Common Language Runtime (CLR) wird unsicherer Code als „nicht überprüfbarer Code“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-108">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="4c8bb-109">Unsicherer Code in C# ist nicht unbedingt gefährlich, es handelt sich dabei lediglich um einen Code, dessen Sicherheit nicht durch die CLR überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-109">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="4c8bb-110">Die CLR wird daher nur unsicheren Code ausführen, wenn sie sich in einer voll vertrauenswürdigen Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-110">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="4c8bb-111">Wenn Sie unsicheren Code verwenden, liegt es in Ihrer Verantwortung, dafür zu sorgen, dass Ihr Code keine Sicherheitsrisiken oder Zeigerfehler enthält.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-111">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="4c8bb-112">Übersicht über unsicheren Code</span><span class="sxs-lookup"><span data-stu-id="4c8bb-112">Unsafe code overview</span></span>

<span data-ttu-id="4c8bb-113">Unsicherer Code verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="4c8bb-113">Unsafe code has the following properties:</span></span>

- <span data-ttu-id="4c8bb-114">Methoden, Typen und Codeblöcke können als unsicher definiert werden.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-114">Methods, types, and code blocks can be defined as unsafe.</span></span>

- <span data-ttu-id="4c8bb-115">In manchen Fällen kann unsicherer Code die Leistung einer Anwendung erhöhen, indem die Überprüfung von Arraygrenzen entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-115">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>

- <span data-ttu-id="4c8bb-116">Unsicherer Code ist erforderlich, wenn Sie native Funktionen aufrufen, die Zeiger erfordern.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-116">Unsafe code is required when you call native functions that require pointers.</span></span>

- <span data-ttu-id="4c8bb-117">Die Verwendung von unsicherem Code führt zu Sicherheits- und Stabilitätsrisiken.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-117">Using unsafe code introduces security and stability risks.</span></span>

- <span data-ttu-id="4c8bb-118">Code, in dem unsichere Blöcke enthalten sind, muss mit der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="4c8bb-118">The code that contains unsafe blocks must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="4c8bb-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="4c8bb-119">Related sections</span></span>

<span data-ttu-id="4c8bb-120">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="4c8bb-120">For more information, see:</span></span>

- [<span data-ttu-id="4c8bb-121">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="4c8bb-121">Pointer types</span></span>](pointer-types.md)

- [<span data-ttu-id="4c8bb-122">Fixed size buffers (Puffer fester Größe)</span><span class="sxs-lookup"><span data-stu-id="4c8bb-122">Fixed size buffers</span></span>](fixed-size-buffers.md)

## <a name="c-language-specification"></a><span data-ttu-id="4c8bb-123">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="4c8bb-123">C# language specification</span></span>

<span data-ttu-id="4c8bb-124">Weitere Informationen finden Sie unter [Unsicherer Code](~/_csharplang/spec/unsafe-code.md) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4c8bb-124">For more information, see the [Unsafe code](~/_csharplang/spec/unsafe-code.md) topic of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c8bb-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4c8bb-125">See also</span></span>

- [<span data-ttu-id="4c8bb-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4c8bb-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4c8bb-127">unsafe</span><span class="sxs-lookup"><span data-stu-id="4c8bb-127">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
