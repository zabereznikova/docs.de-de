---
title: 'Entschärfung: Neuer 64-Bit-JIT-Compiler'
description: Informationen zum neuen 64-Bit-JIT-Compiler, der in .NET Framework 4.6 enthalten ist, sowie zu unerwartetem Verhalten oder Ausnahmen, die während der Kompilierung auftreten können.
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compiler, 64-bit
- JIT compilation, 64-bit
- RyuJIT compiler
ms.assetid: 0332dabc-72c5-4bdc-8975-20d717802b17
ms.openlocfilehash: 228c286f6c5620dc838df5002edc60863a0fe4e2
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96256598"
---
# <a name="mitigation-new-64-bit-jit-compiler"></a><span data-ttu-id="58636-103">Entschärfung: Der neue 64-Bit-JIT-Compiler</span><span class="sxs-lookup"><span data-stu-id="58636-103">Mitigation: New 64-bit JIT Compiler</span></span>

<span data-ttu-id="58636-104">Ab .NET Framework 4.6 enthält die Runtime einen neuen 64-Bit-JIT-Compiler für die Just-in-Time-Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="58636-104">Starting with .NET Framework 4.6, the runtime includes a new 64-bit JIT compiler for just-in-time compilation.</span></span> <span data-ttu-id="58636-105">Diese Änderung wirkt sich nicht auf die Kompilierung mit dem 32-Bit-JIT-Compiler aus.</span><span class="sxs-lookup"><span data-stu-id="58636-105">This change does not affect compilation with the 32-bit JIT compiler.</span></span>  
  
## <a name="unexpected-behavior-or-exceptions"></a><span data-ttu-id="58636-106">Unerwartetes Verhalten oder Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="58636-106">Unexpected behavior or exceptions</span></span>  

 <span data-ttu-id="58636-107">In einigen Fällen führt die Kompilierung mit dem neuen 64-Bit-JIT-Compiler zu einer Laufzeitausnahme oder zu Verhalten, das beim Ausführen von mit dem älteren 64-Bit-JIT-Compiler kompiliertem Code nicht zu beobachten ist.</span><span class="sxs-lookup"><span data-stu-id="58636-107">In some cases, compilation with the new 64-bit JIT compiler results in a runtime exception or in behavior that is not observed when executing code compiled by the older 64-bit JIT compiler.</span></span> <span data-ttu-id="58636-108">Die bekannten Unterschiede umfassen folgende Punkte:</span><span class="sxs-lookup"><span data-stu-id="58636-108">The known differences include the following:</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="58636-109">Alle diese bekannten Probleme wurden im neuen 64-Bit-Compiler behoben, der mit .NET Framework 4.6.2 veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="58636-109">All of these known issues have been addressed in the new 64-bit compiler released with the .NET Framework 4.6.2.</span></span> <span data-ttu-id="58636-110">Die meisten wurden auch in Service Releases von .NET Framework 4.6 und 4.6.1 behoben, die in Windows Update enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="58636-110">Most have also been addressed in service releases of the .NET Framework 4.6 and 4.6.1 that are included with Windows Update.</span></span> <span data-ttu-id="58636-111">Sie können diese Probleme vollständig beseitigen, indem Sie sicherstellen, dass Ihre Windows-Version auf dem aktuellen Stand ist oder ein Upgrade auf .NET Framework 4.6.2 ausführen.</span><span class="sxs-lookup"><span data-stu-id="58636-111">You can eliminate these issues by ensuring that your version of Windows is up to date, or by upgrading to the .NET Framework 4.6.2.</span></span>  
  
- <span data-ttu-id="58636-112">Unter bestimmten Umständen kann ein Unboxingvorgang in Releasebuilds mit aktivierter Optimierung eine <xref:System.NullReferenceException>-Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="58636-112">Under certain conditions, an unboxing operation may throw a <xref:System.NullReferenceException> in Release builds with optimization turned on.</span></span>  
  
- <span data-ttu-id="58636-113">In manchen Fällen kann bei der Ausführung von Produktionscode in einem großen Methodentext eine <xref:System.StackOverflowException>-Ausnahme ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="58636-113">In some cases, execution of production code in a large method body may throw a <xref:System.StackOverflowException>.</span></span>  
  
- <span data-ttu-id="58636-114">Unter bestimmtem Bedingungen werden in Releasebuilds an eine Methode übergebene Strukturen als Verweistypen statt als Werttypen behandelt.</span><span class="sxs-lookup"><span data-stu-id="58636-114">Under certain conditions, structures passed to a method are treated as reference types rather than value types in Release builds.</span></span> <span data-ttu-id="58636-115">Eins der Anzeichen dieses Problems besteht darin, dass die einzelnen Elemente einer Sammlung in unerwarteter Reihenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="58636-115">One of the manifestations of this issue is that the individual items in a collection appear in an unexpected order.</span></span>  
  
- <span data-ttu-id="58636-116">Unter bestimmten Bedingungen ist der Vergleich von <xref:System.UInt16>-Werten mit festgelegtem hohem Bit fehlerhaft, wenn Optimierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="58636-116">Under certain conditions, the comparison of <xref:System.UInt16> values with their high bit set is incorrect if optimization is enabled.</span></span>  
  
- <span data-ttu-id="58636-117">Unter bestimmten Umständen, insbesondere beim Initialisieren von Arraywerten, kann die Speicherinitialisierung durch die IL-Anweisung <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> mit einem falschen Wert erfolgen.</span><span class="sxs-lookup"><span data-stu-id="58636-117">Under certain conditions, particularly when initializing array values, memory initialization by the <xref:System.Reflection.Emit.OpCodes.Initblk?displayProperty=nameWithType> IL instruction may initialize memory with an incorrect value.</span></span> <span data-ttu-id="58636-118">Dies kann entweder zu einem Ausnahmefehler oder zu einer falschen Ausgabe führen.</span><span class="sxs-lookup"><span data-stu-id="58636-118">This can result either in an unhandled exception or incorrect output.</span></span>  
  
- <span data-ttu-id="58636-119">Unter bestimmten seltenen Bedingungen kann ein bedingter Bittest den falschen <xref:System.Boolean>-Wert zurückgeben oder eine Ausnahme auslösen, wenn Compileroptimierungen aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="58636-119">Under certain rare conditions, a conditional bit test can return the incorrect <xref:System.Boolean> value or throw an exception if compiler optimizations are enabled.</span></span>  
  
- <span data-ttu-id="58636-120">Wenn unter bestimmten Umständen eine `if`-Anweisung für die Prüfung auf eine Bedingung vor dem Eintritt in einen `try`-Block oder beim Verlassen eines `try`-Blocks erfolgt und die gleiche Bedingung im `catch`- oder `finally`-Block ausgewertet wird, entfernt der neue 64-Bit-JIT-Compiler beim Optimieren von Code die `if`-Bedingung aus dem `catch`- oder `finally`-Block.</span><span class="sxs-lookup"><span data-stu-id="58636-120">Under certain conditions, if an `if` statement is used to test for a condition before entering  a `try` block and in the exit from the `try` block, and the same condition is evaluated in the `catch` or `finally` block, the new 64-bit JIT compiler removes the `if` condition from the `catch` or `finally` block when it optimizes code.</span></span> <span data-ttu-id="58636-121">Daher wird Code innerhalb der `if`-Anweisung im `catch`- oder `finally`-Block ohne Bedingung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="58636-121">As a result, code inside the `if` statement in the `catch` or `finally` block is executed unconditionally.</span></span>  
  
<a name="General"></a>

## <a name="mitigation-of-known-issues"></a><span data-ttu-id="58636-122">Entschärfung bekannter Probleme</span><span class="sxs-lookup"><span data-stu-id="58636-122">Mitigation of known issues</span></span>  

 <span data-ttu-id="58636-123">Wenn bei Ihnen die oben aufgeführten Probleme auftreten, können Sie darauf mit einer der folgenden Maßnahmen reagieren:</span><span class="sxs-lookup"><span data-stu-id="58636-123">If you encounter the issues listed above, you can address them by doing any of the following:</span></span>  
  
- <span data-ttu-id="58636-124">Ausführen eines Upgrades auf .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="58636-124">Upgrade to the .NET Framework 4.6.2.</span></span> <span data-ttu-id="58636-125">Der neue 64-Bit-Compiler, der in .NET Framework 4.6.2 enthalten ist, behebt jedes dieser bekannten Probleme.</span><span class="sxs-lookup"><span data-stu-id="58636-125">The new 64-bit compiler included with the .NET Framework 4.6.2 addresses each of these known issues.</span></span>  
  
- <span data-ttu-id="58636-126">Stellen Sie sicher, dass ihre Windows-Version auf dem aktuellen Stand ist, indem Sie Windows Update ausführen.</span><span class="sxs-lookup"><span data-stu-id="58636-126">Ensure that your version of Windows is up to date by running Windows Update.</span></span> <span data-ttu-id="58636-127">Serviceupdates für .NET Framework 4.6 und 4.6.1 beheben jedes dieser Probleme, mit Ausnahme der <xref:System.NullReferenceException>-Ausnahme bei Unboxingvorgängen.</span><span class="sxs-lookup"><span data-stu-id="58636-127">Service updates to the .NET Framework 4.6 and 4.6.1 address each of these issues except the <xref:System.NullReferenceException> in an unboxing operation.</span></span>  
  
- <span data-ttu-id="58636-128">Kompilieren Sie mit dem älteren 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="58636-128">Compile with the older 64-bit JIT compiler.</span></span> <span data-ttu-id="58636-129">Informationen zum Vorgehen dazu finden Sie unter [Entschärfung anderer Probleme](#Other).</span><span class="sxs-lookup"><span data-stu-id="58636-129">See the [Mitigation of other issues](#Other) section for more information on how to do this.</span></span>  
  
<a name="Other"></a>

## <a name="mitigation-of-other-issues"></a><span data-ttu-id="58636-130">Entschärfung anderer Probleme</span><span class="sxs-lookup"><span data-stu-id="58636-130">Mitigation of other issues</span></span>  

 <span data-ttu-id="58636-131">Wenn Sie andere Unterschiede im Verhalten zwischen Code, der mit dem älteren 64-Bit-Compiler kompiliert wurde, gegenüber mit dem neuen 64-Bit-JIT-Compiler kompiliertem Code oder zwischen den Debug- und Releaseversionen Ihrer App feststellen, die beide mit dem neuen 64-Bit-JIT-Compiler kompiliert wurden, können Sie folgendermaßen vorgehen, um Ihre App mit dem älteren 64-Bit-JIT-Compiler zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="58636-131">If you encounter any other difference in behavior between code compiled with the older 64-bit compiler and the new 64-bit JIT compiler, or between the debug and release versions of your app that are both compiled with the new 64-bit JIT compiler, you can do the following to compile your app with the older 64-bit JIT compiler:</span></span>  
  
- <span data-ttu-id="58636-132">Sie können der Konfigurationsdatei Ihrer Anwendung auf Anwendungsbasis das [\<useLegacyJit>](../configure-apps/file-schema/runtime/uselegacyjit-element.md)-Element hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="58636-132">On a per-application basis, you can add the [\<useLegacyJit>](../configure-apps/file-schema/runtime/uselegacyjit-element.md) element to your application's configuration file.</span></span> <span data-ttu-id="58636-133">Die folgende Anweisung deaktiviert die Kompilierung mit dem neuen 64-Bit-JIT-Compiler und verwendet stattdessen den 64-Bit-Legacy-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="58636-133">The following disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
    ```xml  
    <?xml version ="1.0"?>  
    <configuration>  
        <runtime>  
           <useLegacyJit enabled="1" />  
        </runtime>  
    </configuration>  
    ```  
  
- <span data-ttu-id="58636-134">Auf Benutzerbasis können Sie dem `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`-Wert der Registrierung einen `REG_DWORD`-Wert mit dem Namen `useLegacyJit` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="58636-134">On a per-user basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="58636-135">Der Wert 1 aktiviert den 64-Bit-Legacy-JIT-Compiler, der Wert 0 deaktiviert ihn und aktiviert stattdessen den neuen 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="58636-135">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
- <span data-ttu-id="58636-136">Auf Computerbasis können Sie dem `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`-Schlüssel der Registrierung einen `REG_DWORD`-Wert mit dem Namen `useLegacyJit` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="58636-136">On a per-machine basis, you can add a `REG_DWORD` value named `useLegacyJit` to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key of the registry.</span></span> <span data-ttu-id="58636-137">Der Wert 1 aktiviert den 64-Bit-Legacy-JIT-Compiler, der Wert 0 deaktiviert ihn und aktiviert stattdessen den neuen 64-Bit-JIT-Compiler.</span><span class="sxs-lookup"><span data-stu-id="58636-137">A value of 1 enables the legacy 64-bit JIT compiler; a value of 0 disables it and enables the new 64-bit JIT compiler.</span></span>  
  
 <span data-ttu-id="58636-138">Ferner können Sie uns über das Problem informieren, indem Sie einen Bug auf [Microsoft Connect](https://connect.microsoft.com/VisualStudio) melden.</span><span class="sxs-lookup"><span data-stu-id="58636-138">You can also let us know about the problem by reporting a bug on [Microsoft Connect](https://connect.microsoft.com/VisualStudio).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58636-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58636-139">See also</span></span>

- [<span data-ttu-id="58636-140">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="58636-140">Application compatibility</span></span>](application-compatibility.md)
- [<span data-ttu-id="58636-141">\<useLegacyJit>-Element</span><span class="sxs-lookup"><span data-stu-id="58636-141">\<useLegacyJit> Element</span></span>](../configure-apps/file-schema/runtime/uselegacyjit-element.md)
