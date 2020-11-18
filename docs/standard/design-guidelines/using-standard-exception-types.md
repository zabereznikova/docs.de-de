---
title: Verwenden von Standardausnahmetypen
description: Informieren Sie sich über Standard Ausnahme Typen in .net. Erfahren Sie mehr über "SystemException", "ApplicationException", "argumumtexception", "COMException" und mehr.
ms.date: 10/22/2008
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
ms.openlocfilehash: d8e75f7104b755476f255563c9c1f7ece14f67db
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828464"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="e15c5-104">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="e15c5-104">Using Standard Exception Types</span></span>
<span data-ttu-id="e15c5-105">In diesem Abschnitt werden die Standard Ausnahmen, die vom Framework bereitgestellt werden, und die Details ihrer Verwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e15c5-105">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="e15c5-106">Die Liste ist keineswegs vollständig.</span><span class="sxs-lookup"><span data-stu-id="e15c5-106">The list is by no means exhaustive.</span></span> <span data-ttu-id="e15c5-107">Weitere Informationen zur Verwendung von frameworkausnahmetypen finden Sie in der .NET Framework Referenz Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="e15c5-107">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>

## <a name="exception-and-systemexception"></a><span data-ttu-id="e15c5-108">Exception und SystemException</span><span class="sxs-lookup"><span data-stu-id="e15c5-108">Exception and SystemException</span></span>
 <span data-ttu-id="e15c5-109">❌ Lösen Sie nicht <xref:System.Exception?displayProperty=nameWithType> oder aus <xref:System.SystemException?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e15c5-109">❌ DO NOT throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>

 <span data-ttu-id="e15c5-110">❌ Fangen `System.Exception` Sie oder nicht `System.SystemException` im Frameworkcode ab, es sei denn, Sie möchten erneut auslösen.</span><span class="sxs-lookup"><span data-stu-id="e15c5-110">❌ DO NOT catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>

 <span data-ttu-id="e15c5-111">❌ Vermeiden Sie das Abfangen von `System.Exception` oder `System.SystemException` , außer in Ausnahme Handlern der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="e15c5-111">❌ AVOID catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>

## <a name="applicationexception"></a><span data-ttu-id="e15c5-112">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="e15c5-112">ApplicationException</span></span>
 <span data-ttu-id="e15c5-113">❌ Lösen Sie nicht aus oder leiten Sie von ab <xref:System.ApplicationException> .</span><span class="sxs-lookup"><span data-stu-id="e15c5-113">❌ DO NOT throw or derive from <xref:System.ApplicationException>.</span></span>

## <a name="invalidoperationexception"></a><span data-ttu-id="e15c5-114">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="e15c5-114">InvalidOperationException</span></span>
 <span data-ttu-id="e15c5-115">✔️ lösen eine <xref:System.InvalidOperationException> aus, wenn sich das Objekt in einem unzulässigen Zustand befindet.</span><span class="sxs-lookup"><span data-stu-id="e15c5-115">✔️ DO throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>

## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="e15c5-116">Argumumtexception, ArgumentNullException und argumentoudefrangeexception</span><span class="sxs-lookup"><span data-stu-id="e15c5-116">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>
 <span data-ttu-id="e15c5-117">✔️ Throw <xref:System.ArgumentException> oder einen seiner Untertypen aus, wenn ungültige Argumente an einen Member übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e15c5-117">✔️ DO throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="e15c5-118">Bevorzugen Sie ggf. den am weitesten abgeleiteten Ausnahmetyp.</span><span class="sxs-lookup"><span data-stu-id="e15c5-118">Prefer the most derived exception type, if applicable.</span></span>

 <span data-ttu-id="e15c5-119">✔️ die-Eigenschaft festlegen, `ParamName` Wenn eine der Unterklassen von ausgelöst wird `ArgumentException` .</span><span class="sxs-lookup"><span data-stu-id="e15c5-119">✔️ DO set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>

 <span data-ttu-id="e15c5-120">Diese Eigenschaft stellt den Namen des Parameters dar, der bewirkt hat, dass die Ausnahme ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="e15c5-120">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="e15c5-121">Beachten Sie, dass die-Eigenschaft mit einer der-Konstruktorüberladungen festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e15c5-121">Note that the property can be set using one of the constructor overloads.</span></span>

 <span data-ttu-id="e15c5-122">✔️ Verwenden Sie `value` für den Namen des impliziten value-Parameters von Eigenschaften Settern.</span><span class="sxs-lookup"><span data-stu-id="e15c5-122">✔️ DO use `value` for the name of the implicit value parameter of property setters.</span></span>

## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="e15c5-123">NullReferenceException, indexouesfrangeexception und AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="e15c5-123">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>
 <span data-ttu-id="e15c5-124">❌ Lassen Sie nicht zu, dass öffentlich Aufruf Bare APIs, oder explizit oder implizit auslösen <xref:System.NullReferenceException> <xref:System.AccessViolationException> <xref:System.IndexOutOfRangeException> .</span><span class="sxs-lookup"><span data-stu-id="e15c5-124">❌ DO NOT allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="e15c5-125">Diese Ausnahmen sind von der Ausführungs-Engine reserviert und werden ausgelöst und weisen in den meisten Fällen auf einen Fehler hin.</span><span class="sxs-lookup"><span data-stu-id="e15c5-125">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>

 <span data-ttu-id="e15c5-126">Argument Überprüfung, um das Auslösen dieser Ausnahmen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e15c5-126">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="e15c5-127">Wenn Sie diese Ausnahmen auslösen, werden Implementierungsdetails der Methode angezeigt, die sich im Laufe der Zeit ändern können.</span><span class="sxs-lookup"><span data-stu-id="e15c5-127">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>

## <a name="stackoverflowexception"></a><span data-ttu-id="e15c5-128">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="e15c5-128">StackOverflowException</span></span>
 <span data-ttu-id="e15c5-129">❌ Nicht explizit auslösen <xref:System.StackOverflowException> .</span><span class="sxs-lookup"><span data-stu-id="e15c5-129">❌ DO NOT explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="e15c5-130">Die Ausnahme sollte explizit nur durch die CLR ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e15c5-130">The exception should be explicitly thrown only by the CLR.</span></span>

 <span data-ttu-id="e15c5-131">❌ Nicht abfangen `StackOverflowException` .</span><span class="sxs-lookup"><span data-stu-id="e15c5-131">❌ DO NOT catch `StackOverflowException`.</span></span>

 <span data-ttu-id="e15c5-132">Es ist beinahe unmöglich, verwalteten Code zu schreiben, der bei der Anwesenheit beliebiger Stapel Überläufe konsistent bleibt.</span><span class="sxs-lookup"><span data-stu-id="e15c5-132">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="e15c5-133">Die nicht verwalteten Teile der CLR bleiben konsistent, indem Sie die Stapel Überläufe mithilfe von Tests an klar definierte Orte verschieben, anstatt Sie aus willkürlichen Stapel Überläufen zu sichern.</span><span class="sxs-lookup"><span data-stu-id="e15c5-133">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>

## <a name="outofmemoryexception"></a><span data-ttu-id="e15c5-134">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="e15c5-134">OutOfMemoryException</span></span>
 <span data-ttu-id="e15c5-135">❌ Nicht explizit auslösen <xref:System.OutOfMemoryException> .</span><span class="sxs-lookup"><span data-stu-id="e15c5-135">❌ DO NOT explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="e15c5-136">Diese Ausnahme wird nur durch die CLR-Infrastruktur ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="e15c5-136">This exception is to be thrown only by the CLR infrastructure.</span></span>

## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="e15c5-137">COMException, Seh Exception und ExecutionEngineException</span><span class="sxs-lookup"><span data-stu-id="e15c5-137">ComException, SEHException, and ExecutionEngineException</span></span>
 <span data-ttu-id="e15c5-138">❌ Lösen Sie, und nicht explizit aus <xref:System.Runtime.InteropServices.COMException>  <xref:System.ExecutionEngineException> <xref:System.Runtime.InteropServices.SEHException> .</span><span class="sxs-lookup"><span data-stu-id="e15c5-138">❌ DO NOT explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="e15c5-139">Diese Ausnahmen müssen nur von der CLR-Infrastruktur ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="e15c5-139">These exceptions are to be thrown only by the CLR infrastructure.</span></span>

 <span data-ttu-id="e15c5-140">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="e15c5-140">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="e15c5-141">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="e15c5-141">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="e15c5-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e15c5-142">See also</span></span>

- [<span data-ttu-id="e15c5-143">Framework-Entwurfs Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e15c5-143">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="e15c5-144">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="e15c5-144">Design Guidelines for Exceptions</span></span>](exceptions.md)
