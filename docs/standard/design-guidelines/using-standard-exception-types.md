---
title: Verwenden von Standardausnahmetypen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: 3caa94d9a39966614161e4b19201dcf6065776a2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743540"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="561cb-102">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="561cb-102">Using Standard Exception Types</span></span>
<span data-ttu-id="561cb-103">In diesem Abschnitt werden die Standard Ausnahmen, die vom Framework bereitgestellt werden, und die Details ihrer Verwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="561cb-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="561cb-104">Die Liste ist keineswegs vollständig.</span><span class="sxs-lookup"><span data-stu-id="561cb-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="561cb-105">Weitere Informationen zur Verwendung von frameworkausnahmetypen finden Sie in der .NET Framework Referenz Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="561cb-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>

## <a name="exception-and-systemexception"></a><span data-ttu-id="561cb-106">Exception und SystemException</span><span class="sxs-lookup"><span data-stu-id="561cb-106">Exception and SystemException</span></span>
 <span data-ttu-id="561cb-107">❌ keine <xref:System.Exception?displayProperty=nameWithType> oder <xref:System.SystemException?displayProperty=nameWithType>auslösen.</span><span class="sxs-lookup"><span data-stu-id="561cb-107">❌ DO NOT throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="561cb-108">❌ können keine `System.Exception` oder `System.SystemException` im Frameworkcode erfassen, es sei denn, Sie beabsichtigen, Sie erneut auszulösen.</span><span class="sxs-lookup"><span data-stu-id="561cb-108">❌ DO NOT catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>

 <span data-ttu-id="561cb-109">❌ vermeiden Sie das Abfangen von `System.Exception` oder `System.SystemException`, außer in Ausnahme Handlern der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="561cb-109">❌ AVOID catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>

## <a name="applicationexception"></a><span data-ttu-id="561cb-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="561cb-110">ApplicationException</span></span>
 <span data-ttu-id="561cb-111">❌ die <xref:System.ApplicationException>nicht auslösen oder ableiten.</span><span class="sxs-lookup"><span data-stu-id="561cb-111">❌ DO NOT throw or derive from <xref:System.ApplicationException>.</span></span>

## <a name="invalidoperationexception"></a><span data-ttu-id="561cb-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="561cb-112">InvalidOperationException</span></span>
 <span data-ttu-id="561cb-113">✔️ eine <xref:System.InvalidOperationException> auslösen, wenn sich das Objekt in einem unzulässigen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="561cb-113">✔️ DO throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="561cb-114">Argumumtexception, ArgumentNullException und argumentoudefrangeexception</span><span class="sxs-lookup"><span data-stu-id="561cb-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>
 <span data-ttu-id="561cb-115">✔️ lösen <xref:System.ArgumentException> oder einen seiner Untertypen aus, wenn ungültige Argumente an einen Member übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="561cb-115">✔️ DO throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="561cb-116">Bevorzugen Sie ggf. den am weitesten abgeleiteten Ausnahmetyp.</span><span class="sxs-lookup"><span data-stu-id="561cb-116">Prefer the most derived exception type, if applicable.</span></span>

 <span data-ttu-id="561cb-117">✔️ Legen Sie die `ParamName`-Eigenschaft fest, wenn Sie eine der Unterklassen von `ArgumentException`auslösen.</span><span class="sxs-lookup"><span data-stu-id="561cb-117">✔️ DO set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>

 <span data-ttu-id="561cb-118">Diese Eigenschaft stellt den Namen des Parameters dar, der bewirkt hat, dass die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="561cb-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="561cb-119">Beachten Sie, dass die-Eigenschaft mit einer der-Konstruktorüberladungen festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="561cb-119">Note that the property can be set using one of the constructor overloads.</span></span>

 <span data-ttu-id="561cb-120">✔️ Verwenden Sie `value` für den Namen des impliziten value-Parameters von Eigenschaften Settern.</span><span class="sxs-lookup"><span data-stu-id="561cb-120">✔️ DO use `value` for the name of the implicit value parameter of property setters.</span></span>

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="561cb-121">NullReferenceException, indexouesfrangeexception und AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="561cb-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>
 <span data-ttu-id="561cb-122">❌ erlauben Sie nicht, öffentlich aufrufbare APIs explizit oder implizit <xref:System.NullReferenceException>, <xref:System.AccessViolationException>oder <xref:System.IndexOutOfRangeException>auszulösen.</span><span class="sxs-lookup"><span data-stu-id="561cb-122">❌ DO NOT allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="561cb-123">Diese Ausnahmen sind von der Ausführungs-Engine reserviert und werden ausgelöst und weisen in den meisten Fällen auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="561cb-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>

 <span data-ttu-id="561cb-124">Argument Überprüfung, um das Auslösen dieser Ausnahmen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="561cb-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="561cb-125">Wenn Sie diese Ausnahmen auslösen, werden Implementierungsdetails der Methode angezeigt, die sich im Laufe der Zeit ändern können.</span><span class="sxs-lookup"><span data-stu-id="561cb-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>

## <a name="stackoverflowexception"></a><span data-ttu-id="561cb-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="561cb-126">StackOverflowException</span></span>
 <span data-ttu-id="561cb-127">❌ nicht explizit <xref:System.StackOverflowException>auslösen.</span><span class="sxs-lookup"><span data-stu-id="561cb-127">❌ DO NOT explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="561cb-128">Die Ausnahme sollte explizit nur durch die CLR ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="561cb-128">The exception should be explicitly thrown only by the CLR.</span></span>

 <span data-ttu-id="561cb-129">❌ `StackOverflowException`nicht auffangen.</span><span class="sxs-lookup"><span data-stu-id="561cb-129">❌ DO NOT catch `StackOverflowException`.</span></span>

 <span data-ttu-id="561cb-130">Es ist beinahe unmöglich, verwalteten Code zu schreiben, der bei der Anwesenheit beliebiger Stapel Überläufe konsistent bleibt.</span><span class="sxs-lookup"><span data-stu-id="561cb-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="561cb-131">Die nicht verwalteten Teile der CLR bleiben konsistent, indem Sie die Stapel Überläufe mithilfe von Tests an klar definierte Orte verschieben, anstatt Sie aus willkürlichen Stapel Überläufen zu sichern.</span><span class="sxs-lookup"><span data-stu-id="561cb-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>

## <a name="outofmemoryexception"></a><span data-ttu-id="561cb-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="561cb-132">OutOfMemoryException</span></span>
 <span data-ttu-id="561cb-133">❌ nicht explizit <xref:System.OutOfMemoryException>auslösen.</span><span class="sxs-lookup"><span data-stu-id="561cb-133">❌ DO NOT explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="561cb-134">Diese Ausnahme wird nur durch die CLR-Infrastruktur ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="561cb-134">This exception is to be thrown only by the CLR infrastructure.</span></span>

## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="561cb-135">COMException, Seh Exception und ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="561cb-135">ComException, SEHException, and ExecutionEngineException</span></span>
 <span data-ttu-id="561cb-136">❌ <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>und <xref:System.Runtime.InteropServices.SEHException>nicht explizit auslösen.</span><span class="sxs-lookup"><span data-stu-id="561cb-136">❌ DO NOT explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="561cb-137">Diese Ausnahmen müssen nur von der CLR-Infrastruktur ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="561cb-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>

 <span data-ttu-id="561cb-138">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="561cb-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="561cb-139">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="561cb-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="561cb-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="561cb-140">See also</span></span>

- [<span data-ttu-id="561cb-141">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="561cb-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="561cb-142">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="561cb-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
