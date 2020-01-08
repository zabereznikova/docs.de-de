---
title: 'Unsicherer Code und Zeiger: C#-Programmierhandbuch'
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
ms.openlocfilehash: 013af4e55c8fc396bbc92058d7fb454484f3263e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711830"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="24e60-102">Unsicherer Code und Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="24e60-102">Unsafe code and pointers (C# Programming Guide)</span></span>

<span data-ttu-id="24e60-103">Um Typsicherheit und Sicherheit zu gewährleisten, unterstützt C# standardmäßig keine Zeigerarithmetik.</span><span class="sxs-lookup"><span data-stu-id="24e60-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="24e60-104">Sie können jedoch das [unsafe](../../language-reference/keywords/unsafe.md)-Schlüsselwort verwenden, um einen unsicheren Kontext zu definieren, in dem Zeiger verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="24e60-104">However, by using the [unsafe](../../language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="24e60-105">Weitere Informationen über Zeiger finden Sie unter [Zeigertypen](pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="24e60-105">For more information about pointers, see [Pointer types](pointer-types.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="24e60-106">In der Common Language Runtime (CLR) wird unsicherer Code als „nicht überprüfbarer Code“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="24e60-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="24e60-107">Unsicherer Code in C# ist nicht unbedingt gefährlich, es handelt sich dabei lediglich um einen Code, dessen Sicherheit nicht durch die CLR überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="24e60-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="24e60-108">Die CLR wird daher nur unsicheren Code ausführen, wenn sie sich in einer voll vertrauenswürdigen Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="24e60-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="24e60-109">Wenn Sie unsicheren Code verwenden, liegt es in Ihrer Verantwortung, dafür zu sorgen, dass Ihr Code keine Sicherheitsrisiken oder Zeigerfehler enthält.</span><span class="sxs-lookup"><span data-stu-id="24e60-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="24e60-110">Übersicht über unsicheren Code</span><span class="sxs-lookup"><span data-stu-id="24e60-110">Unsafe code overview</span></span>

<span data-ttu-id="24e60-111">Unsicherer Code verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="24e60-111">Unsafe code has the following properties:</span></span>

- <span data-ttu-id="24e60-112">Methoden, Typen und Codeblöcke können als unsicher definiert werden.</span><span class="sxs-lookup"><span data-stu-id="24e60-112">Methods, types, and code blocks can be defined as unsafe.</span></span>

- <span data-ttu-id="24e60-113">In manchen Fällen kann unsicherer Code die Leistung einer Anwendung erhöhen, indem die Überprüfung von Arraygrenzen entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="24e60-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>

- <span data-ttu-id="24e60-114">Unsicherer Code ist erforderlich, wenn Sie native Funktionen aufrufen, die Zeiger erfordern.</span><span class="sxs-lookup"><span data-stu-id="24e60-114">Unsafe code is required when you call native functions that require pointers.</span></span>

- <span data-ttu-id="24e60-115">Die Verwendung von unsicherem Code führt zu Sicherheits- und Stabilitätsrisiken.</span><span class="sxs-lookup"><span data-stu-id="24e60-115">Using unsafe code introduces security and stability risks.</span></span>

- <span data-ttu-id="24e60-116">Code, in dem unsichere Blöcke enthalten sind, muss mit der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="24e60-116">The code that contains unsafe blocks must be compiled with the [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="24e60-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="24e60-117">Related sections</span></span>

<span data-ttu-id="24e60-118">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="24e60-118">For more information, see:</span></span>

- [<span data-ttu-id="24e60-119">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="24e60-119">Pointer types</span></span>](pointer-types.md)

- [<span data-ttu-id="24e60-120">Fixed size buffers (Puffer fester Größe)</span><span class="sxs-lookup"><span data-stu-id="24e60-120">Fixed size buffers</span></span>](fixed-size-buffers.md)

## <a name="c-language-specification"></a><span data-ttu-id="24e60-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="24e60-121">C# language specification</span></span>

<span data-ttu-id="24e60-122">Weitere Informationen finden Sie unter [Unsicherer Code](~/_csharplang/spec/unsafe-code.md) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="24e60-122">For more information, see the [Unsafe code](~/_csharplang/spec/unsafe-code.md) topic of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="24e60-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24e60-123">See also</span></span>

- [<span data-ttu-id="24e60-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="24e60-124">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="24e60-125">unsafe</span><span class="sxs-lookup"><span data-stu-id="24e60-125">unsafe</span></span>](../../language-reference/keywords/unsafe.md)
