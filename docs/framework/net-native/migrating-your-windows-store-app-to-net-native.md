---
title: Migrieren der Windows Store-App auf .NET Native
ms.date: 03/30/2017
ms.assetid: 4153aa18-6f56-4a0a-865b-d3da743a1d05
ms.openlocfilehash: 987669fc51eeaf7e3bdef3e91a2f1ce23164a055
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "81389704"
---
# <a name="migrate-your-windows-store-app-to-net-native"></a><span data-ttu-id="7f069-102">Migrieren Ihrer Windows Store-App zu .net Native</span><span class="sxs-lookup"><span data-stu-id="7f069-102">Migrate Your Windows Store App to .NET Native</span></span>

<span data-ttu-id="7f069-103">.Net Native bietet eine statische Kompilierung von apps im Windows Store oder auf dem Computer des Entwicklers.</span><span class="sxs-lookup"><span data-stu-id="7f069-103">.NET Native provides static compilation of apps in the Windows Store or on the developer’s computer.</span></span> <span data-ttu-id="7f069-104">Dies unterscheidet sich von der dynamischen Kompilierung für Windows Store-Apps durch den JIT-Compiler (Just-in-Time) oder den [Native Image Generator (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="7f069-104">This differs from the dynamic compilation performed for Windows Store apps by the just-in-time (JIT) compiler or the [Native Image Generator (Ngen.exe)](../tools/ngen-exe-native-image-generator.md) on the device.</span></span> <span data-ttu-id="7f069-105">Trotz der Unterschiede wird von .net Native versucht, die Kompatibilität mit den [.net für Windows Store-Apps](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="7f069-105">Despite the differences, .NET Native tries to maintain compatibility with the [.NET for Windows Store apps](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29).</span></span> <span data-ttu-id="7f069-106">In den meisten Fällen funktionieren Dinge, die in .net für Windows Store-Apps funktionieren, auch mit .net Native.</span><span class="sxs-lookup"><span data-stu-id="7f069-106">For the most part, things that work on the .NET for Windows Store apps also work with .NET Native.</span></span>  <span data-ttu-id="7f069-107">In einigen Fällen können jedoch Verhaltensänderungen auftreten.</span><span class="sxs-lookup"><span data-stu-id="7f069-107">However, in some cases, you may encounter behavioral changes.</span></span> <span data-ttu-id="7f069-108">In diesem Dokument werden diese Unterschiede zwischen den standardmäßigen .net für Windows Store-Apps und .net Native in den folgenden Bereichen erläutert:</span><span class="sxs-lookup"><span data-stu-id="7f069-108">This document discusses these differences between the standard .NET for Windows Store apps and .NET Native in the following areas:</span></span>

- [<span data-ttu-id="7f069-109">Allgemeine Laufzeitunterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-109">General runtime differences</span></span>](#Runtime)

- [<span data-ttu-id="7f069-110">Dynamische Programmierunterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-110">Dynamic programming differences</span></span>](#Dynamic)

- [<span data-ttu-id="7f069-111">Andere Unterschiede im Zusammenhang mit Reflektion</span><span class="sxs-lookup"><span data-stu-id="7f069-111">Other reflection-related differences</span></span>](#Reflection)

- [<span data-ttu-id="7f069-112">Nicht unterstützte Szenarios und APIs</span><span class="sxs-lookup"><span data-stu-id="7f069-112">Unsupported scenarios and APIs</span></span>](#Unsupported)

- [<span data-ttu-id="7f069-113">Visual Studio-Unterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-113">Visual Studio differences</span></span>](#VS)

<a name="Runtime"></a>

## <a name="general-runtime-differences"></a><span data-ttu-id="7f069-114">Allgemeine Laufzeitunterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-114">General runtime differences</span></span>

- <span data-ttu-id="7f069-115">Ausnahmen, wie z. b. <xref:System.TypeLoadException> , die vom JIT-Compiler ausgelöst werden, wenn eine APP auf dem Common Language Runtime (CLR) ausgeführt wird, führen in der Regel zu Kompilier Zeitfehlern, wenn Sie von .net Native verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-115">Exceptions, such as <xref:System.TypeLoadException>, that are thrown by the JIT compiler when an app runs on the common language runtime (CLR) generally result in compile-time errors when processed by .NET Native.</span></span>

- <span data-ttu-id="7f069-116">Rufen Sie die <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> -Methode nicht vom UI-Thread einer Anwendung auf.</span><span class="sxs-lookup"><span data-stu-id="7f069-116">Don't call the <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType> method from an app's UI thread.</span></span> <span data-ttu-id="7f069-117">Dies kann zu einem Deadlock auf .net Native führen.</span><span class="sxs-lookup"><span data-stu-id="7f069-117">This can result in a deadlock on .NET Native.</span></span>

- <span data-ttu-id="7f069-118">Verlassen Sie sich nicht auf die Aufrufreihenfolge des statischen Klassenkonstruktors.</span><span class="sxs-lookup"><span data-stu-id="7f069-118">Don't rely on static class constructor invocation ordering.</span></span> <span data-ttu-id="7f069-119">In .net Native unterscheidet sich die Aufruf Reihenfolge von der Reihenfolge in der Standardlaufzeit.</span><span class="sxs-lookup"><span data-stu-id="7f069-119">In .NET Native, the invocation order is different from the order on the standard runtime.</span></span> <span data-ttu-id="7f069-120">(Auch mit der Standardlaufzeit sollten Sie sich nicht auf die Reihenfolge der Ausführung der statischen Klassenkonstruktoren verlassen.)</span><span class="sxs-lookup"><span data-stu-id="7f069-120">(Even with the standard runtime, you shouldn't rely on the order of execution of static class constructors.)</span></span>

- <span data-ttu-id="7f069-121">Endlosschleifen ohne einen Anruf (z. B. `while(true);`) auf einem beliebigen Thread kann die App zum Stillstand bringen.</span><span class="sxs-lookup"><span data-stu-id="7f069-121">Infinite looping without making a call (for example, `while(true);`) on any thread may bring the app to a halt.</span></span> <span data-ttu-id="7f069-122">Auf ähnliche Weise können lange oder unendliche Wartezeiten die Anwendung zum Stillstand bringen.</span><span class="sxs-lookup"><span data-stu-id="7f069-122">Similarly, large or infinite waits may bring the app to a halt.</span></span>

- <span data-ttu-id="7f069-123">Bestimmte generische Initialisierungs Zyklen lösen in .net Native keine Ausnahmen aus.</span><span class="sxs-lookup"><span data-stu-id="7f069-123">Certain generic initialization cycles don't throw exceptions in .NET Native.</span></span> <span data-ttu-id="7f069-124">Das folgende Codebeispiel löst eine <xref:System.TypeLoadException> -Ausnahme auf der Standard-CLR aus.</span><span class="sxs-lookup"><span data-stu-id="7f069-124">For example, the following code throws a <xref:System.TypeLoadException> exception on the standard CLR.</span></span> <span data-ttu-id="7f069-125">In .net Native ist dies nicht der Fall.</span><span class="sxs-lookup"><span data-stu-id="7f069-125">In .NET Native, it doesn't.</span></span>

  [!code-csharp[ProjectN#8](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat1.cs#8)]

- <span data-ttu-id="7f069-126">In einigen Fällen stellt .net Native verschiedene Implementierungen .NET Framework Klassenbibliotheken bereit.</span><span class="sxs-lookup"><span data-stu-id="7f069-126">In some cases, .NET Native provides different implementations of .NET Framework class libraries.</span></span> <span data-ttu-id="7f069-127">Ein von einer Methode zurückgegebenes Objekt implementiert immer die Member des zurückgegebenen Typs.</span><span class="sxs-lookup"><span data-stu-id="7f069-127">An object returned from a method will always implement the members of the returned type.</span></span> <span data-ttu-id="7f069-128">Da aber die Unterstützungsimplementierung unterschiedlich ist, können Sie es möglicherweise nicht in dieselben Typen wie auf anderen .NET Framework-Plattformen umwandeln.</span><span class="sxs-lookup"><span data-stu-id="7f069-128">However, since its backing implementation is different, you may not be able to cast it to the same set of types as you could on other .NET Framework platforms.</span></span> <span data-ttu-id="7f069-129">In einigen Fällen sind Sie zum Beispiel möglicherweise nicht in der Lage, das <xref:System.Collections.Generic.IEnumerable%601> -Schnittstellenobjekt, das von Methoden wie <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> oder <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> zurückgegeben wird, in `T[]`umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="7f069-129">For example, in some cases, you may not be able to cast the <xref:System.Collections.Generic.IEnumerable%601> interface object returned by methods such as <xref:System.Reflection.TypeInfo.DeclaredMembers%2A?displayProperty=nameWithType> or <xref:System.Reflection.TypeInfo.DeclaredProperties%2A?displayProperty=nameWithType> to `T[]`.</span></span>

- <span data-ttu-id="7f069-130">Der WinInet-Cache ist in .net für Windows Store-Apps standardmäßig nicht aktiviert, er befindet sich jedoch auf .net Native.</span><span class="sxs-lookup"><span data-stu-id="7f069-130">The WinInet cache isn't enabled by default on .NET for Windows Store apps, but it is on .NET Native.</span></span> <span data-ttu-id="7f069-131">Dies verbessert die Leistung, hat aber Auswirkungen auf das Workingset.</span><span class="sxs-lookup"><span data-stu-id="7f069-131">This improves performance but has working set implications.</span></span> <span data-ttu-id="7f069-132">Es ist keine Entwickleraktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f069-132">No developer action is necessary.</span></span>

<a name="Dynamic"></a>

## <a name="dynamic-programming-differences"></a><span data-ttu-id="7f069-133">Dynamische Programmierunterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-133">Dynamic programming differences</span></span>

<span data-ttu-id="7f069-134">.Net Native statisch Links im Code aus dem .NET Framework, um den Code für die maximale Leistung lokal zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="7f069-134">.NET Native statically links in code from the .NET Framework to make the code app-local for maximum performance.</span></span> <span data-ttu-id="7f069-135">Binäre Größen müssen jedoch klein bleiben, sodass nicht das gesamte .NET Framework einbezogen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7f069-135">However, binary sizes have to remain small, so the entire .NET Framework can't be brought in.</span></span> <span data-ttu-id="7f069-136">Der .net Native Compiler löst diese Einschränkung mit einem Abhängigkeits Reducer, der Verweise auf nicht verwendeten Code entfernt.</span><span class="sxs-lookup"><span data-stu-id="7f069-136">The .NET Native compiler resolves this limitation by using a dependency reducer that removes references to unused code.</span></span> <span data-ttu-id="7f069-137">.Net Native werden jedoch möglicherweise keine Typinformationen und keinen Code beibehalten oder generieren, wenn diese Informationen zur Kompilierzeit nicht statisch abgeleitet werden können, sondern stattdessen dynamisch zur Laufzeit abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-137">However, .NET Native might not maintain or generate some type information and code when that information can't be inferred statically at compile time, but instead is retrieved dynamically at runtime.</span></span>

<span data-ttu-id="7f069-138">.Net Native aktiviert Reflektion und dynamische Programmierung.</span><span class="sxs-lookup"><span data-stu-id="7f069-138">.NET Native does enable reflection and dynamic programming.</span></span> <span data-ttu-id="7f069-139">Allerdings können nicht alle Typen für die Reflektion markiert werden, da die Größe des generierten Codes zu stark ansteigen würde (vor allem, da das Reflektieren von öffentlichen APIs im .NET Framework unterstützt wird).</span><span class="sxs-lookup"><span data-stu-id="7f069-139">However, not all types can be marked for reflection, because this would make the generated code size too large (especially because reflecting on public APIs in the .NET Framework is supported).</span></span> <span data-ttu-id="7f069-140">Der .net Native-Compiler trifft intelligente Entscheidungen darüber, welche Typen Reflektion unterstützen sollen, und er behält die Metadaten bei und generiert Code nur für diese Typen.</span><span class="sxs-lookup"><span data-stu-id="7f069-140">The .NET Native compiler makes smart choices about which types should support reflection, and it keeps the metadata and generates code only for those types.</span></span>

<span data-ttu-id="7f069-141">Beispielsweise erfordert die Datenbindung, dass eine App Eigenschaftennamen Funktionen zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="7f069-141">For example, data binding requires an app to be able to map property names to functions.</span></span> <span data-ttu-id="7f069-142">In .NET für Windows Store-Apps verwendet die Common Language Runtime automatisch Reflektion, um diese Funktion für verwaltete Typen und öffentlich verfügbare systemeigene Typen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="7f069-142">In .NET for Windows Store apps, the common language runtime automatically uses reflection to provide this capability for managed types and publicly available native types.</span></span> <span data-ttu-id="7f069-143">In .net Native schließt der Compiler automatisch Metadaten für Typen ein, an die Sie Daten binden.</span><span class="sxs-lookup"><span data-stu-id="7f069-143">In .NET Native, the compiler automatically includes metadata for types to which you bind data.</span></span>

<span data-ttu-id="7f069-144">Der .net Native-Compiler kann auch häufig verwendete generische Typen verarbeiten <xref:System.Collections.Generic.List%601> , z <xref:System.Collections.Generic.Dictionary%602> . b. und, die ohne Hinweise oder Anweisungen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7f069-144">The .NET Native compiler can also handle commonly used generic types such as <xref:System.Collections.Generic.List%601> and <xref:System.Collections.Generic.Dictionary%602>, which work without requiring any hints or directives.</span></span> <span data-ttu-id="7f069-145">Das [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) -Schlüsselwort wird ebenfalls innerhalb bestimmter Grenzen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-145">The [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) keyword is also supported within certain limits.</span></span>

> [!NOTE]
> <span data-ttu-id="7f069-146">Sie sollten alle dynamischen Codepfade gründlich testen, wenn Sie Ihre APP auf .net Native portieren.</span><span class="sxs-lookup"><span data-stu-id="7f069-146">You should test all dynamic code paths thoroughly when porting your app to .NET Native.</span></span>

<span data-ttu-id="7f069-147">Die Standardkonfiguration für .net Native ist für die meisten Entwickler ausreichend, aber einige Entwickler möchten Ihre Konfigurationen möglicherweise mithilfe einer laufzeitdirektivendatei (. rd. Xml) optimieren.</span><span class="sxs-lookup"><span data-stu-id="7f069-147">The default configuration for .NET Native is sufficient for most developers, but some developers might want to fine- tune their configurations by using a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="7f069-148">Außerdem kann der .net Native Compiler in einigen Fällen nicht ermitteln, welche Metadaten für die Reflektion verfügbar sein müssen, und hängt auf Hinweise aus, insbesondere in den folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="7f069-148">In addition, in some cases, the .NET Native compiler is unable to determine which metadata must be available for reflection and relies on hints, particularly in the following cases:</span></span>

- <span data-ttu-id="7f069-149">Einige Konstrukte wie <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> und <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> können nicht statisch bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-149">Some constructs like <xref:System.Type.MakeGenericType%2A?displayProperty=nameWithType> and <xref:System.Reflection.MethodInfo.MakeGenericMethod%2A?displayProperty=nameWithType> can't be determined statically.</span></span>

- <span data-ttu-id="7f069-150">Da der Compiler die Instanziierungen nicht ermitteln kann, muss ein generischer Typ, den Sie für die Reflektion verwenden möchten, durch Laufzeitdirektiven angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-150">Because the compiler can't determine the instantiations, a generic type that you want to reflect on has to be specified by runtime directives.</span></span> <span data-ttu-id="7f069-151">Nicht nur, weil der gesamte Code enthalten sein muss, sondern auch, weil die Reflektion für generische Typen (z. B. wenn eine generische Methode für einen generischen Typ aufgerufen wird) einen unendlichen Zyklus bilden kann.</span><span class="sxs-lookup"><span data-stu-id="7f069-151">This isn't just because all code must be included, but because reflection on generic types can form an infinite cycle (for example, when a generic method is invoked on a generic type).</span></span>

> [!NOTE]
> <span data-ttu-id="7f069-152">Laufzeitdirektiven werden in einer Laufzeitdirektivendatei (.rd.xml) definiert.</span><span class="sxs-lookup"><span data-stu-id="7f069-152">Runtime directives are defined in a runtime directives (.rd.xml) file.</span></span> <span data-ttu-id="7f069-153">Allgemeine Informationen zur Verwendung dieser Datei finden Sie unter [Getting Started with .NET Native (Erste Schritte mit .NET Native)](getting-started-with-net-native.md).</span><span class="sxs-lookup"><span data-stu-id="7f069-153">For general information about using this file, see [Getting Started](getting-started-with-net-native.md).</span></span> <span data-ttu-id="7f069-154">Informationen zu Laufzeitdirektiven finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span><span class="sxs-lookup"><span data-stu-id="7f069-154">For information about the runtime directives, see [Runtime Directives (rd.xml) Configuration File Reference](runtime-directives-rd-xml-configuration-file-reference.md).</span></span>

<span data-ttu-id="7f069-155">.Net Native umfasst auch Profil Erstellungs Tools, mit deren Hilfe Entwickler bestimmen, welche Typen außerhalb des Standardsatzes Reflektion unterstützen sollen.</span><span class="sxs-lookup"><span data-stu-id="7f069-155">.NET Native also includes profiling tools that help the developer determine which types outside the default set should support reflection.</span></span>

<a name="Reflection"></a>

## <a name="other-reflection-related-differences"></a><span data-ttu-id="7f069-156">Andere Unterschiede im Zusammenhang mit Reflektion</span><span class="sxs-lookup"><span data-stu-id="7f069-156">Other reflection-related differences</span></span>

<span data-ttu-id="7f069-157">Es gibt eine Reihe von anderen individuellen reflektionsbezogenen Unterschieden im Verhalten zwischen .net für Windows Store-Apps und .net Native.</span><span class="sxs-lookup"><span data-stu-id="7f069-157">There are a number of other individual reflection-related differences in behavior between the .NET for Windows Store apps and .NET Native.</span></span>

<span data-ttu-id="7f069-158">In .net Native:</span><span class="sxs-lookup"><span data-stu-id="7f069-158">In .NET Native:</span></span>

- <span data-ttu-id="7f069-159">Private Reflektion über Typen und Member in der .NET Framework-Klassenbibliothek wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-159">Private reflection over types and members in the .NET Framework class library is not supported.</span></span> <span data-ttu-id="7f069-160">Sie können jedoch eigene private Typen und Member sowie Typen und Member in Bibliotheken von Drittanbietern für die Reflektion verwenden.</span><span class="sxs-lookup"><span data-stu-id="7f069-160">You can, however, reflect over your own private types and members, as well as types and members in third-party libraries.</span></span>

- <span data-ttu-id="7f069-161">Die <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> -Eigenschaft gibt ordnungsgemäß `false` für ein <xref:System.Reflection.ParameterInfo> -Objekt zurück, das einen Rückgabewert darstellt.</span><span class="sxs-lookup"><span data-stu-id="7f069-161">The <xref:System.Reflection.ParameterInfo.HasDefaultValue%2A?displayProperty=nameWithType> property correctly returns `false` for a <xref:System.Reflection.ParameterInfo> object that represents a return value.</span></span> <span data-ttu-id="7f069-162">In den .NET für Windows Store-Apps gibt es `true`zurück.</span><span class="sxs-lookup"><span data-stu-id="7f069-162">In the .NET for Windows Store apps, it returns `true`.</span></span> <span data-ttu-id="7f069-163">Intermediate Language (IL) unterstützt dies nicht direkt, und die Interpretation bleibt der Sprache überlassen.</span><span class="sxs-lookup"><span data-stu-id="7f069-163">Intermediate language (IL) doesn’t support this directly, and interpretation is left to the language.</span></span>

- <span data-ttu-id="7f069-164">Öffentliche Member in den <xref:System.RuntimeFieldHandle> - und <xref:System.RuntimeMethodHandle> -Strukturen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-164">Public members on the <xref:System.RuntimeFieldHandle> and <xref:System.RuntimeMethodHandle> structures aren't supported.</span></span> <span data-ttu-id="7f069-165">Diese Typen werden nur für LINQ, Ausdrucksbaumstrukturen und statische Arrayinitialisierungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-165">These types are supported only for LINQ, expression trees, and static array initialization.</span></span>

- <span data-ttu-id="7f069-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> und <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> enthalten ausgeblendete Member in Basisklassen und können daher ohne explizite Überschreibungen überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-166"><xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeProperties%2A?displayProperty=nameWithType> and <xref:System.Reflection.RuntimeReflectionExtensions.GetRuntimeEvents%2A?displayProperty=nameWithType> include hidden members in base classes and thus may be overridden without explicit overrides.</span></span> <span data-ttu-id="7f069-167">Dies gilt auch für andere [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) -Methoden.</span><span class="sxs-lookup"><span data-stu-id="7f069-167">This is also true of other [RuntimeReflectionExtensions.GetRuntime\*](xref:System.Reflection.RuntimeReflectionExtensions) methods.</span></span>

- <span data-ttu-id="7f069-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType>und <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> schlagen nicht fehl, wenn Sie versuchen, bestimmte Kombinationen (z. b. ein Array von `byref` Objekten) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7f069-168"><xref:System.Type.MakeArrayType%2A?displayProperty=nameWithType> and <xref:System.Type.MakeByRefType%2A?displayProperty=nameWithType> don't fail when you try to create certain combinations (for example, an array of `byref` objects).</span></span>

- <span data-ttu-id="7f069-169">Sie können mithilfe der Reflektion keine Member mit Zeigerparametern aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7f069-169">You can't use reflection to invoke members that have pointer parameters.</span></span>

- <span data-ttu-id="7f069-170">Sie können mithilfe der Reflektion kein Zeigerfeld abrufen oder festlegen.</span><span class="sxs-lookup"><span data-stu-id="7f069-170">You can't use reflection to get or set a pointer field.</span></span>

- <span data-ttu-id="7f069-171">Wenn die Anzahl der Argumente falsch ist und der Typ eines der Argumente falsch ist, löst .net Native eine anstelle eines aus <xref:System.ArgumentException> <xref:System.Reflection.TargetParameterCountException> .</span><span class="sxs-lookup"><span data-stu-id="7f069-171">When the argument count is wrong and the type of one of the arguments is incorrect, .NET Native throws an <xref:System.ArgumentException> instead of a <xref:System.Reflection.TargetParameterCountException>.</span></span>

- <span data-ttu-id="7f069-172">Binäre Serialisierung von Ausnahmen wird in der Regel nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-172">Binary serialization of exceptions is generally not supported.</span></span> <span data-ttu-id="7f069-173">Daher können nicht serialisierbare Objekte zum <xref:System.Exception.Data%2A?displayProperty=nameWithType> -Wörterbuch hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-173">As a result, non-serializable objects can be added to the <xref:System.Exception.Data%2A?displayProperty=nameWithType> dictionary.</span></span>

<a name="Unsupported"></a>

## <a name="unsupported-scenarios-and-apis"></a><span data-ttu-id="7f069-174">Nicht unterstützte Szenarios und APIs</span><span class="sxs-lookup"><span data-stu-id="7f069-174">Unsupported scenarios and APIs</span></span>

<span data-ttu-id="7f069-175">In den folgenden Abschnitten werden nicht unterstützte Szenarios und APIs für allgemeine Entwicklung, Interop und Technologien wie HTTPClient und Windows Communication Foundation (WCF) aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="7f069-175">The following sections list unsupported scenarios and APIs for general development, interop, and technologies such as HTTPClient and Windows Communication Foundation (WCF):</span></span>

- [<span data-ttu-id="7f069-176">Allgemeine Entwicklung</span><span class="sxs-lookup"><span data-stu-id="7f069-176">General development</span></span>](#General)

- [<span data-ttu-id="7f069-177">HttpClient</span><span class="sxs-lookup"><span data-stu-id="7f069-177">HttpClient</span></span>](#HttpClient)

- [<span data-ttu-id="7f069-178">Interop</span><span class="sxs-lookup"><span data-stu-id="7f069-178">Interop</span></span>](#Interop)

- [<span data-ttu-id="7f069-179">Nicht unterstützte APIs</span><span class="sxs-lookup"><span data-stu-id="7f069-179">Unsupported APIs</span></span>](#APIs)

<a name="General"></a>

### <a name="general-development-differences"></a><span data-ttu-id="7f069-180">Allgemeine Entwicklungsunterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-180">General development differences</span></span>

<span data-ttu-id="7f069-181">**Werttypen**</span><span class="sxs-lookup"><span data-stu-id="7f069-181">**Value types**</span></span>

- <span data-ttu-id="7f069-182">Wenn Sie die <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> - und <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> -Methoden für einen Werttyp außer Kraft setzen, rufen Sie nicht die Implementierungen der Basisklasse auf.</span><span class="sxs-lookup"><span data-stu-id="7f069-182">If you override the <xref:System.ValueType.Equals%2A?displayProperty=nameWithType> and <xref:System.ValueType.GetHashCode%2A?displayProperty=nameWithType> methods for a value type, don't call the base class implementations.</span></span> <span data-ttu-id="7f069-183">In .NET für Windows Store-Apps sind diese Methoden auf Reflektion angewiesen.</span><span class="sxs-lookup"><span data-stu-id="7f069-183">In .NET for Windows Store apps, these methods rely on reflection.</span></span> <span data-ttu-id="7f069-184">Zum Zeitpunkt der Kompilierung generiert .net Native eine-Implementierung, die nicht auf die Lauf Zeit Reflektion angewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7f069-184">At compile time, .NET Native generates an implementation that doesn't rely on runtime reflection.</span></span> <span data-ttu-id="7f069-185">Dies bedeutet, dass Sie, wenn Sie diese beiden Methoden nicht außer Kraft setzen, wie erwartet funktionieren, da .net Native die Implementierung zum Zeitpunkt der Kompilierung generiert.</span><span class="sxs-lookup"><span data-stu-id="7f069-185">This means that if you don't override these two methods, they will work as expected, because .NET Native generates the implementation at compile time.</span></span> <span data-ttu-id="7f069-186">Allerdings wird durch das Außerkraftsetzen dieser Methoden und das Aufrufen der Basisklassenimplementierung eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7f069-186">However, overriding these methods but calling the base class implementation results in an exception.</span></span>

- <span data-ttu-id="7f069-187">Werttypen größer als 1 Megabyte werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-187">Value types larger than 1 megabyte aren't supported.</span></span>

- <span data-ttu-id="7f069-188">Werttypen dürfen in .net Native keinen Parameter losen Konstruktor aufweisen.</span><span class="sxs-lookup"><span data-stu-id="7f069-188">Value types can't have a parameterless constructor in .NET Native.</span></span> <span data-ttu-id="7f069-189">(In c# und Visual Basic werden Parameter lose Konstruktoren für Werttypen untersagt.</span><span class="sxs-lookup"><span data-stu-id="7f069-189">(C# and Visual Basic prohibit parameterless constructors on value types.</span></span> <span data-ttu-id="7f069-190">Allerdings können diese in IL erstellt werden.)</span><span class="sxs-lookup"><span data-stu-id="7f069-190">However, these can be created in IL.)</span></span>

<span data-ttu-id="7f069-191">**Arrays**</span><span class="sxs-lookup"><span data-stu-id="7f069-191">**Arrays**</span></span>

- <span data-ttu-id="7f069-192">Arrays mit einer unteren Grenze ungleich null werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-192">Arrays with a lower bound other than zero aren't supported.</span></span> <span data-ttu-id="7f069-193">Diese Arrays werden in der Regel durch Aufrufen der <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> -Überladung erstellt.</span><span class="sxs-lookup"><span data-stu-id="7f069-193">Typically, these arrays are created by calling the <xref:System.Array.CreateInstance%28System.Type%2CSystem.Int32%5B%5D%2CSystem.Int32%5B%5D%29?displayProperty=nameWithType> overload.</span></span>

- <span data-ttu-id="7f069-194">Die dynamische Erstellung von mehrdimensionalen Arrays wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-194">Dynamic creation of multidimensional arrays isn't supported.</span></span> <span data-ttu-id="7f069-195">Solche Arrays werden in der Regel durch Aufruf einer Überladung für die <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> -Methode erstellt, die einen `lengths` -Parameter enthält, oder durch Aufrufen der <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> -Methode.</span><span class="sxs-lookup"><span data-stu-id="7f069-195">Such arrays are typically created by calling an overload of the <xref:System.Array.CreateInstance%2A?displayProperty=nameWithType> method that includes a `lengths` parameter, or by calling the <xref:System.Type.MakeArrayType%28System.Int32%29?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="7f069-196">Mehrdimensionale Arrays mit vier oder mehr Dimensionen werden nicht unterstützt. Das heißt, der <xref:System.Array.Rank%2A?displayProperty=nameWithType> -Eigenschaftswert ist vier oder größer.</span><span class="sxs-lookup"><span data-stu-id="7f069-196">Multidimensional arrays that have four or more dimensions aren't supported; that is, their <xref:System.Array.Rank%2A?displayProperty=nameWithType> property value is four or greater.</span></span> <span data-ttu-id="7f069-197">Verwenden Sie stattdessen [verzweigte Arrays](../../csharp/programming-guide/arrays/jagged-arrays.md) (ein Array aus Arrays).</span><span class="sxs-lookup"><span data-stu-id="7f069-197">Use [jagged arrays](../../csharp/programming-guide/arrays/jagged-arrays.md) (an array of arrays) instead.</span></span> <span data-ttu-id="7f069-198">`array[x,y,z]` ist zum Beispiel ungültig, `array[x][y][z]` aber nicht.</span><span class="sxs-lookup"><span data-stu-id="7f069-198">For example, `array[x,y,z]` is invalid, but `array[x][y][z]` isn't.</span></span>

- <span data-ttu-id="7f069-199">Varianz für mehrdimensionale Arrays wird nicht unterstützt und verursacht eine <xref:System.InvalidCastException> -Ausnahme zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="7f069-199">Variance for multidimensional arrays isn't supported and causes an <xref:System.InvalidCastException> exception at run time.</span></span>

<span data-ttu-id="7f069-200">**Generics**</span><span class="sxs-lookup"><span data-stu-id="7f069-200">**Generics**</span></span>

- <span data-ttu-id="7f069-201">Unendliche generische Typerweiterung führt zu einem Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="7f069-201">Infinite generic type expansion results in a compiler error.</span></span> <span data-ttu-id="7f069-202">Dieser Code kann z. B. nicht kompiliert werden:</span><span class="sxs-lookup"><span data-stu-id="7f069-202">For example, this code fails to compile:</span></span>

  [!code-csharp[ProjectN#9](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat2.cs#9)]

<span data-ttu-id="7f069-203">**Zeiger**</span><span class="sxs-lookup"><span data-stu-id="7f069-203">**Pointers**</span></span>

- <span data-ttu-id="7f069-204">Arrays aus Zeigern werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-204">Arrays of pointers aren't supported.</span></span>

- <span data-ttu-id="7f069-205">Sie können mithilfe der Reflektion kein Zeigerfeld abrufen oder festlegen.</span><span class="sxs-lookup"><span data-stu-id="7f069-205">You can't use reflection to get or set a pointer field.</span></span>

<span data-ttu-id="7f069-206">**Serialisierung**</span><span class="sxs-lookup"><span data-stu-id="7f069-206">**Serialization**</span></span>

<span data-ttu-id="7f069-207">Die <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> -Attribut wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-207">The <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.String%29> attribute isn't supported.</span></span> <span data-ttu-id="7f069-208">Verwenden Sie stattdessen das <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> -Attribut.</span><span class="sxs-lookup"><span data-stu-id="7f069-208">Use the <xref:System.Runtime.Serialization.KnownTypeAttribute.%23ctor%28System.Type%29> attribute instead.</span></span>

<span data-ttu-id="7f069-209">**Ressourcen**</span><span class="sxs-lookup"><span data-stu-id="7f069-209">**Resources**</span></span>

<span data-ttu-id="7f069-210">Die Verwendung von lokalisierten Ressourcen mit der <xref:System.Diagnostics.Tracing.EventSource> -Klasse wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-210">The use of localized resources with the <xref:System.Diagnostics.Tracing.EventSource> class isn't supported.</span></span> <span data-ttu-id="7f069-211">Die <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> -Eigenschaft definiert keine lokalisierten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="7f069-211">The <xref:System.Diagnostics.Tracing.EventSourceAttribute.LocalizationResources%2A?displayProperty=nameWithType> property doesn't define localized resources.</span></span>

<span data-ttu-id="7f069-212">**Delegaten**</span><span class="sxs-lookup"><span data-stu-id="7f069-212">**Delegates**</span></span>

<span data-ttu-id="7f069-213">`Delegate.BeginInvoke` und `Delegate.EndInvoke` werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-213">`Delegate.BeginInvoke` and `Delegate.EndInvoke` aren't supported.</span></span>

<span data-ttu-id="7f069-214">**Verschiedene APIs**</span><span class="sxs-lookup"><span data-stu-id="7f069-214">**Miscellaneous APIs**</span></span>

- <span data-ttu-id="7f069-215">Die [typeInfo. GUID](xref:System.Type.GUID) -Eigenschaft löst eine- <xref:System.PlatformNotSupportedException> Ausnahme aus, wenn ein- <xref:System.Runtime.InteropServices.GuidAttribute> Attribut nicht auf den Typ angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="7f069-215">The [TypeInfo.GUID](xref:System.Type.GUID) property throws a <xref:System.PlatformNotSupportedException> exception if a <xref:System.Runtime.InteropServices.GuidAttribute> attribute isn't applied to the type.</span></span> <span data-ttu-id="7f069-216">Die GUID wird in erster Linie für die COM-Unterstützung verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f069-216">The GUID is used primarily for COM support.</span></span>

- <span data-ttu-id="7f069-217">Die- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> Methode analysiert ordnungsgemäß Zeichen folgen, die kurze Datumsangaben in .net Native enthalten.</span><span class="sxs-lookup"><span data-stu-id="7f069-217">The <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> method correctly parses strings that contain short dates in .NET Native.</span></span> <span data-ttu-id="7f069-218">Sie behält allerdings keine Kompatibilität mit den Änderungen der Datums- und Uhrzeitanalyse bei, die in den Microsoft Knowledge Base-Artikeln [KB2803771](https://support.microsoft.com/kb/2803771) und [KB2803755](https://support.microsoft.com/kb/2803755)beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-218">However, it doesn't maintain compatibility with the changes in date and time parsing described in the Microsoft Knowledge Base articles [KB2803771](https://support.microsoft.com/kb/2803771) and [KB2803755](https://support.microsoft.com/kb/2803755).</span></span>

- <span data-ttu-id="7f069-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType>`("E")`wird in .net Native ordnungsgemäß gerundet.</span><span class="sxs-lookup"><span data-stu-id="7f069-219"><xref:System.Numerics.BigInteger.ToString%2A?displayProperty=nameWithType> `("E")` is correctly rounded in .NET Native.</span></span> <span data-ttu-id="7f069-220">In einigen Versionen der CLR wird die resultierende Zeichenfolge abgeschnitten und nicht gerundet.</span><span class="sxs-lookup"><span data-stu-id="7f069-220">In some versions of the CLR, the result string is truncated instead of rounded.</span></span>

<a name="HttpClient"></a>

### <a name="httpclient-differences"></a><span data-ttu-id="7f069-221">HttpClient-Unterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-221">HttpClient differences</span></span>

<span data-ttu-id="7f069-222">In .net Native verwendet die <xref:System.Net.Http.HttpClientHandler> -Klasse intern WinInet (über die <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> -Klasse) anstelle der-Klasse und der-Klasse, die <xref:System.Net.WebRequest> <xref:System.Net.WebResponse> in den standardmäßigen .net für Windows Store-Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-222">In .NET Native, the <xref:System.Net.Http.HttpClientHandler> class internally uses WinINet (through the <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class) instead of the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes used in the standard .NET for Windows Store apps.</span></span>  <span data-ttu-id="7f069-223">WinINet unterstützt nicht alle Konfigurationsoptionen, die die <xref:System.Net.Http.HttpClientHandler> -Klasse unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-223">WinINet doesn't support all the configuration options that the <xref:System.Net.Http.HttpClientHandler> class supports.</span></span>  <span data-ttu-id="7f069-224">Infolgedessen:</span><span class="sxs-lookup"><span data-stu-id="7f069-224">As a result:</span></span>

- <span data-ttu-id="7f069-225">Einige der Funktionseigenschaften bei <xref:System.Net.Http.HttpClientHandler> der Rückgabe `false` .net Native, während Sie `true` in den standardmäßigen .net für Windows Store-Apps zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7f069-225">Some of the capability properties on <xref:System.Net.Http.HttpClientHandler> return `false` on .NET Native, whereas they return `true` in the standard .NET for Windows Store apps.</span></span>

- <span data-ttu-id="7f069-226">Einige der Accessoren der Konfigurations Eigenschaft `get` geben immer einen festgelegten Wert für .net Native zurück, der sich vom konfigurierbaren Standardwert in .net für Windows Store-Apps unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="7f069-226">Some of the configuration property `get` accessors always return a fixed value on .NET Native that is different than the default configurable value in .NET for Windows Store apps.</span></span>

<span data-ttu-id="7f069-227">In den folgenden Abschnitten werden einige zusätzliche Verhaltensunterschiede behandelt.</span><span class="sxs-lookup"><span data-stu-id="7f069-227">Some additional behavior differences are covered in the following subsections.</span></span>

<span data-ttu-id="7f069-228">**Proxy**</span><span class="sxs-lookup"><span data-stu-id="7f069-228">**Proxy**</span></span>

<span data-ttu-id="7f069-229">Die- <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> Klasse unterstützt nicht das Konfigurieren oder Überschreiben des Proxys auf Anforderungs Basis.</span><span class="sxs-lookup"><span data-stu-id="7f069-229">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn’t support configuring or overriding the proxy on a per-request basis.</span></span>  <span data-ttu-id="7f069-230">Dies bedeutet, dass alle Anforderungen auf .net Native den vom System konfigurierten Proxy Server oder keinen Proxy Server verwenden, je nach Wert der- <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7f069-230">This means that all requests on .NET Native use the system-configured proxy server or no proxy server, depending on the value of the <xref:System.Net.Http.HttpClientHandler.UseProxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="7f069-231">In .NET für Windows Store-Apps wird der Proxyserver durch die <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> -Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="7f069-231">In .NET for Windows Store apps, the proxy server is defined by the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> property.</span></span>  <span data-ttu-id="7f069-232">Bei .net Native wird durch das Festlegen von <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> auf einen anderen Wert als `null` eine-Ausnahme ausgelöst <xref:System.PlatformNotSupportedException> .</span><span class="sxs-lookup"><span data-stu-id="7f069-232">On .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.Proxy%2A?displayProperty=nameWithType> to a value other than `null` throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="7f069-233">Die- <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> Eigenschaft gibt `false` auf .net Native zurück, während Sie `true` in der Standard .NET Framework für Windows Store-Apps zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7f069-233">The <xref:System.Net.Http.HttpClientHandler.SupportsProxy%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in the standard .NET Framework for Windows Store apps.</span></span>

<span data-ttu-id="7f069-234">**Automatische Umleitung**</span><span class="sxs-lookup"><span data-stu-id="7f069-234">**Automatic redirection**</span></span>

<span data-ttu-id="7f069-235">Die- <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> Klasse lässt nicht zu, dass die maximale Anzahl automatischer Umleitungen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="7f069-235">The <xref:Windows.Web.Http.Filters.HttpBaseProtocolFilter> class doesn't allow the maximum number of automatic redirections to be configured.</span></span>  <span data-ttu-id="7f069-236">Der Wert der <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> -Eigenschaft ist in den standardmäßigen .NET für Windows Store-Apps standardmäßig 50 und kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-236">The value of the <xref:System.Net.Http.HttpClientHandler.MaxAutomaticRedirections%2A?displayProperty=nameWithType> property is 50 by default in the standard .NET for Windows Store apps and can be modified.</span></span> <span data-ttu-id="7f069-237">Auf .net Native lautet der Wert dieser Eigenschaft 10. Wenn Sie versuchen, Sie zu ändern, wird eine- <xref:System.PlatformNotSupportedException> Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7f069-237">On .NET Native, the value of this property is 10, and trying to modify it throws a <xref:System.PlatformNotSupportedException> exception.</span></span>  <span data-ttu-id="7f069-238">Die- <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> Eigenschaft gibt `false` auf .net Native zurück, während Sie `true` in .net für Windows Store-Apps zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7f069-238">The <xref:System.Net.Http.HttpClientHandler.SupportsRedirectConfiguration%2A?displayProperty=nameWithType> property returns `false` on .NET Native, whereas it returns `true` in .NET for Windows Store apps.</span></span>

<span data-ttu-id="7f069-239">**Automatische Dekomprimierung**</span><span class="sxs-lookup"><span data-stu-id="7f069-239">**Automatic decompression**</span></span>

<span data-ttu-id="7f069-240">.NET für Windows Store-Apps ermöglichen Ihnen das Festlegen der <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> -Eigenschaft auf <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, beides <xref:System.Net.DecompressionMethods.Deflate> und <xref:System.Net.DecompressionMethods.GZip>oder <xref:System.Net.DecompressionMethods.None>.</span><span class="sxs-lookup"><span data-stu-id="7f069-240">.NET for Windows Store apps allows you to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A?displayProperty=nameWithType> property to <xref:System.Net.DecompressionMethods.Deflate>, <xref:System.Net.DecompressionMethods.GZip>, both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="7f069-241">.Net Native unterstützt nur <xref:System.Net.DecompressionMethods.Deflate> in Verbindung mit <xref:System.Net.DecompressionMethods.GZip> , oder <xref:System.Net.DecompressionMethods.None> .</span><span class="sxs-lookup"><span data-stu-id="7f069-241">.NET Native only supports <xref:System.Net.DecompressionMethods.Deflate> together with <xref:System.Net.DecompressionMethods.GZip>, or <xref:System.Net.DecompressionMethods.None>.</span></span>  <span data-ttu-id="7f069-242">Wenn Sie versuchen, die <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> -Eigenschaft im Hintergrund auf <xref:System.Net.DecompressionMethods.Deflate> oder <xref:System.Net.DecompressionMethods.GZip> festzulegen, wird sie auf <xref:System.Net.DecompressionMethods.Deflate> und <xref:System.Net.DecompressionMethods.GZip>festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7f069-242">Trying to set the <xref:System.Net.Http.HttpClientHandler.AutomaticDecompression%2A> property to either <xref:System.Net.DecompressionMethods.Deflate> or <xref:System.Net.DecompressionMethods.GZip> alone silently sets it to both <xref:System.Net.DecompressionMethods.Deflate> and <xref:System.Net.DecompressionMethods.GZip>.</span></span>

<span data-ttu-id="7f069-243">**Cookies**</span><span class="sxs-lookup"><span data-stu-id="7f069-243">**Cookies**</span></span>

<span data-ttu-id="7f069-244">Cookieverarbeitung erfolgt gleichzeitig durch <xref:System.Net.Http.HttpClient> und WinINet.</span><span class="sxs-lookup"><span data-stu-id="7f069-244">Cookie handling is performed simultaneously by <xref:System.Net.Http.HttpClient> and WinINet.</span></span>  <span data-ttu-id="7f069-245">Cookies aus dem <xref:System.Net.CookieContainer> werden mit Cookies im WinINet-Cookiecache kombiniert.</span><span class="sxs-lookup"><span data-stu-id="7f069-245">Cookies from the <xref:System.Net.CookieContainer> are combined with cookies in the WinINet cookie cache.</span></span>  <span data-ttu-id="7f069-246">Durch das Entfernen eines Cookies aus <xref:System.Net.CookieContainer> wird <xref:System.Net.Http.HttpClient> am Senden des Cookies gehindert. Wenn der Cookie aber schon von WinINet erkannt wurde und Cookies nicht vom Benutzer gelöscht wurden, wird er durch WinINet gesendet.</span><span class="sxs-lookup"><span data-stu-id="7f069-246">Removing a cookie from <xref:System.Net.CookieContainer> prevents <xref:System.Net.Http.HttpClient> from sending the cookie, but if the cookie was already seen by WinINet, and cookies weren't deleted by the user, WinINet sends it.</span></span>  <span data-ttu-id="7f069-247">Es ist nicht möglich, einen Cookie programmgesteuert aus WinINet mithilfe der <xref:System.Net.Http.HttpClient>-, <xref:System.Net.Http.HttpClientHandler>- oder <xref:System.Net.CookieContainer> -API zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="7f069-247">It isn't possible to programmatically remove a cookie from WinINet by using the <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.HttpClientHandler>, or <xref:System.Net.CookieContainer> API.</span></span>  <span data-ttu-id="7f069-248">Durch das Festlegen der <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> -Eigenschaft auf `false` sendet <xref:System.Net.Http.HttpClient> keine Cookies mehr; WinINet kann die Cookies immer noch in der Anforderung einschließen.</span><span class="sxs-lookup"><span data-stu-id="7f069-248">Setting the <xref:System.Net.Http.HttpClientHandler.UseCookies%2A?displayProperty=nameWithType> property to `false` causes only <xref:System.Net.Http.HttpClient> to stop sending cookies; WinINet might still include its cookies in the request.</span></span>

<span data-ttu-id="7f069-249">**Anmeldeinformationen**</span><span class="sxs-lookup"><span data-stu-id="7f069-249">**Credentials**</span></span>

<span data-ttu-id="7f069-250">In .NET für Windows Store-Apps funktionieren die Eigenschaften <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> und <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> unabhängig voneinander.</span><span class="sxs-lookup"><span data-stu-id="7f069-250">In .NET for Windows Store apps, the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A?displayProperty=nameWithType> and <xref:System.Net.Http.HttpClientHandler.Credentials%2A?displayProperty=nameWithType> properties work independently.</span></span>  <span data-ttu-id="7f069-251">Darüber hinaus akzeptiert die <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft jedes Objekt, das die <xref:System.Net.ICredentials> -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="7f069-251">Additionally, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property accepts any object that implements the <xref:System.Net.ICredentials> interface.</span></span>  <span data-ttu-id="7f069-252">In .net Native bewirkt das Festlegen der- <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> Eigenschaft auf `true` die- <xref:System.Net.Http.HttpClientHandler.Credentials%2A> Eigenschaft `null` .</span><span class="sxs-lookup"><span data-stu-id="7f069-252">In .NET Native, setting the <xref:System.Net.Http.HttpClientHandler.UseDefaultCredentials%2A> property to `true` causes the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property to become `null`.</span></span>  <span data-ttu-id="7f069-253">Außerdem kann die <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft nur auf `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>oder ein Objekt vom Typ <xref:System.Net.NetworkCredential>festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-253">In addition, the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property can be set only to `null`, <xref:System.Net.CredentialCache.DefaultCredentials%2A>, or an object of type <xref:System.Net.NetworkCredential>.</span></span>  <span data-ttu-id="7f069-254">Wenn ein beliebiges anderes <xref:System.Net.ICredentials> -Objekt, zum Beispiel das sehr beliebte <xref:System.Net.CredentialCache>-Objekt, der <xref:System.Net.Http.HttpClientHandler.Credentials%2A> -Eigenschaft zugeweisen wird, wird eine <xref:System.PlatformNotSupportedException>ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7f069-254">Assigning any other <xref:System.Net.ICredentials> object, the most popular of which is <xref:System.Net.CredentialCache>, to the <xref:System.Net.Http.HttpClientHandler.Credentials%2A> property throws a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="7f069-255">**Andere nicht unterstützte oder nicht konfigurierbare Features**</span><span class="sxs-lookup"><span data-stu-id="7f069-255">**Other unsupported or unconfigurable features**</span></span>

<span data-ttu-id="7f069-256">In .net Native:</span><span class="sxs-lookup"><span data-stu-id="7f069-256">In .NET Native:</span></span>

- <span data-ttu-id="7f069-257">Der Wert der <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> -Eigenschaft ist immer <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span><span class="sxs-lookup"><span data-stu-id="7f069-257">The value of the <xref:System.Net.Http.HttpClientHandler.ClientCertificateOptions%2A?displayProperty=nameWithType> property is always <xref:System.Net.Http.ClientCertificateOption.Automatic>.</span></span>  <span data-ttu-id="7f069-258">In .NET für Windows Store-Apps ist der Standardwert <xref:System.Net.Http.ClientCertificateOption.Manual>.</span><span class="sxs-lookup"><span data-stu-id="7f069-258">In .NET for Windows Store apps, the default is <xref:System.Net.Http.ClientCertificateOption.Manual>.</span></span>

- <span data-ttu-id="7f069-259">Die <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> -Eigenschaft ist nicht konfigurierbar.</span><span class="sxs-lookup"><span data-stu-id="7f069-259">The <xref:System.Net.Http.HttpClientHandler.MaxRequestContentBufferSize%2A?displayProperty=nameWithType> property isn't configurable.</span></span>

- <span data-ttu-id="7f069-260">Die <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> -Eigenschaft ist immer `true`.</span><span class="sxs-lookup"><span data-stu-id="7f069-260">The <xref:System.Net.Http.HttpClientHandler.PreAuthenticate%2A?displayProperty=nameWithType> property is always `true`.</span></span>  <span data-ttu-id="7f069-261">In .NET für Windows Store-Apps ist der Standardwert `false`.</span><span class="sxs-lookup"><span data-stu-id="7f069-261">In .NET for Windows Store apps, the default is `false`.</span></span>

- <span data-ttu-id="7f069-262">Der `SetCookie2` -Header in Antworten wird als veraltet ignoriert.</span><span class="sxs-lookup"><span data-stu-id="7f069-262">The `SetCookie2` header in responses is ignored as obsolete.</span></span>

<a name="Interop"></a>
### <a name="interop-differences"></a><span data-ttu-id="7f069-263">Interop-Unterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-263">Interop differences</span></span>
 <span data-ttu-id="7f069-264">**Nicht mehr unterstützte APIs**</span><span class="sxs-lookup"><span data-stu-id="7f069-264">**Deprecated APIs**</span></span>

 <span data-ttu-id="7f069-265">Eine Reihe von selten verwendeten APIs für die Interoperabilität mit verwaltetem Code werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-265">A number of infrequently used APIs for interoperability with managed code have been deprecated.</span></span> <span data-ttu-id="7f069-266">Bei Verwendung mit .net Native können diese APIs eine- <xref:System.NotImplementedException> oder- <xref:System.PlatformNotSupportedException> Ausnahme auslösen oder einen Compilerfehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="7f069-266">When used with .NET Native, these APIs may throw a <xref:System.NotImplementedException> or <xref:System.PlatformNotSupportedException> exception, or result in a compiler error.</span></span> <span data-ttu-id="7f069-267">Diese APIs sind in .NET für Windows Store-Apps als veraltet gekennzeichnet, obwohl beim Aufruf kein Compilerfehler sondern eine Compilerwarnung generiert wird.</span><span class="sxs-lookup"><span data-stu-id="7f069-267">In .NET for Windows Store apps, these APIs are marked as obsolete, although calling them generates a compiler warning rather than a compiler error.</span></span>

 <span data-ttu-id="7f069-268">Als veraltet markierte APIs für das Marshalling `VARIANT` gehören:</span><span class="sxs-lookup"><span data-stu-id="7f069-268">Deprecated APIs for `VARIANT` marshaling include:</span></span>

- <xref:System.Runtime.InteropServices.BStrWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.CurrencyWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.DispatchWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ErrorWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnknownWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VariantWrapper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.VarEnum?displayProperty=nameWithType>

 <span data-ttu-id="7f069-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType>wird unterstützt, löst aber in einigen Szenarien eine Ausnahme aus, z. b. bei der Verwendung mit [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) oder `byref` Varianten.</span><span class="sxs-lookup"><span data-stu-id="7f069-269"><xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> is supported, but it throws an exception in some scenarios, such as when it is used with [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) or `byref` variants.</span></span>

 <span data-ttu-id="7f069-270">Als veraltet markierte APIs für die [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) -Unterstützung gehören:</span><span class="sxs-lookup"><span data-stu-id="7f069-270">Deprecated APIs for [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) support include:</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType>

<span data-ttu-id="7f069-271">Als veraltet markierte APIs für klassische COM-Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="7f069-271">Deprecated APIs for classic COM events include:</span></span>

- <xref:System.Runtime.InteropServices.ComEventsHelper?displayProperty=nameWithType>
- <xref:System.Runtime.InteropServices.ComSourceInterfacesAttribute>

<span data-ttu-id="7f069-272">Als veraltet markierte APIs in der- <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> Schnittstelle, die in .net Native nicht unterstützt werden, umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7f069-272">Deprecated APIs in the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface, which isn't supported in .NET Native, include:</span></span>

- <span data-ttu-id="7f069-273"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="7f069-273"><xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="7f069-274"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="7f069-274"><xref:System.Runtime.InteropServices.CustomQueryInterfaceMode?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="7f069-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="7f069-275"><xref:System.Runtime.InteropServices.CustomQueryInterfaceResult?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.Marshal.GetComInterfaceForObject%28System.Object%2CSystem.Type%2CSystem.Runtime.InteropServices.CustomQueryInterfaceMode%29?displayProperty=fullName>

<span data-ttu-id="7f069-276">Andere nicht unterstützte Interop-Features sind:</span><span class="sxs-lookup"><span data-stu-id="7f069-276">Other unsupported interop features include:</span></span>

- <span data-ttu-id="7f069-277"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="7f069-277"><xref:System.Runtime.InteropServices.ICustomAdapter?displayProperty=nameWithType> (all members)</span></span>
- <span data-ttu-id="7f069-278"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (alle Member)</span><span class="sxs-lookup"><span data-stu-id="7f069-278"><xref:System.Runtime.InteropServices.SafeBuffer?displayProperty=nameWithType> (all members)</span></span>
- <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.VBByRefStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AnsiBStr?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.AsAny?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.UnmanagedType.CustomMarshaler?displayProperty=fullName>

 <span data-ttu-id="7f069-279">Selten verwendete Marshalling-APIs:</span><span class="sxs-lookup"><span data-stu-id="7f069-279">Rarely used marshaling APIs:</span></span>

- <xref:System.Runtime.InteropServices.Marshal.ReadByte%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt16%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt32%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadInt64%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.ReadIntPtr%28System.Object%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteByte%28System.Object%2CSystem.Int32%2CSystem.Byte%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt16%28System.Object%2CSystem.Int32%2CSystem.Int16%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt32%28System.Object%2CSystem.Int32%2CSystem.Int32%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteInt64%28System.Object%2CSystem.Int32%2CSystem.Int64%29?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.Marshal.WriteIntPtr%28System.Object%2CSystem.Int32%2CSystem.IntPtr%29?displayProperty=fullName>

 <span data-ttu-id="7f069-280">**Plattformaufruf und COM-Interop-Kompatibilität**</span><span class="sxs-lookup"><span data-stu-id="7f069-280">**Platform invoke and COM interop compatibility**</span></span>

 <span data-ttu-id="7f069-281">Die meisten Platt Form Aufrufe und COM-Interop-Szenarien werden in .net Native weiterhin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-281">Most platform invoke and COM interop scenarios are still supported in .NET Native.</span></span> <span data-ttu-id="7f069-282">Insbesondere werden die gesamte Interoperabilität mit WinRT-APIs (Windows-Runtime) und das gesamte Marshalling unterstützt, das für Windows-Runtime erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7f069-282">In particular, all interoperability with Windows Runtime (WinRT) APIs and all marshaling required for the Windows Runtime is supported.</span></span> <span data-ttu-id="7f069-283">Dazu gehört die Marshallingunterstützung für:</span><span class="sxs-lookup"><span data-stu-id="7f069-283">This includes marshaling support for:</span></span>

- <span data-ttu-id="7f069-284">Arrays (einschließlich <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span><span class="sxs-lookup"><span data-stu-id="7f069-284">Arrays (including <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType>)</span></span>

- `BStr`

- <span data-ttu-id="7f069-285">Delegaten</span><span class="sxs-lookup"><span data-stu-id="7f069-285">Delegates</span></span>

- <span data-ttu-id="7f069-286">Zeichenfolgen (Unicode, Ansi und HSTRING)</span><span class="sxs-lookup"><span data-stu-id="7f069-286">Strings (Unicode, Ansi, and HSTRING)</span></span>

- <span data-ttu-id="7f069-287">Strukturen (`byref` und `byval`)</span><span class="sxs-lookup"><span data-stu-id="7f069-287">Structs (`byref` and `byval`)</span></span>

- <span data-ttu-id="7f069-288">Unions</span><span class="sxs-lookup"><span data-stu-id="7f069-288">Unions</span></span>

- <span data-ttu-id="7f069-289">Win32-Handles</span><span class="sxs-lookup"><span data-stu-id="7f069-289">Win32 handles</span></span>

- <span data-ttu-id="7f069-290">Alle WinRT-Konstrukte</span><span class="sxs-lookup"><span data-stu-id="7f069-290">All WinRT constructs</span></span>

- <span data-ttu-id="7f069-291">Teilweise Unterstützung für das Marshalling von "variant"-Typen.</span><span class="sxs-lookup"><span data-stu-id="7f069-291">Partial support for marshaling variant types.</span></span> <span data-ttu-id="7f069-292">Folgende werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7f069-292">The following are supported:</span></span>

  - <xref:System.Boolean>

  - <xref:System.Byte>

  - <xref:System.Decimal>

  - <xref:System.Double>

  - <xref:System.Int16>

  - <xref:System.Int32>

  - <xref:System.Int64>

  - <xref:System.SByte>

  - <xref:System.Single>

  - <xref:System.UInt16>

  - <xref:System.UInt32>

  - <xref:System.UInt64>

  - `BStr`

  - [<span data-ttu-id="7f069-293">IUnknown</span><span class="sxs-lookup"><span data-stu-id="7f069-293">IUnknown</span></span>](/windows/desktop/api/unknwn/nn-unknwn-iunknown)

<span data-ttu-id="7f069-294">Die folgenden .net Native werden jedoch nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="7f069-294">However, .NET Native doesn't support the following:</span></span>

- <span data-ttu-id="7f069-295">Verwenden von klassischen COM-Ereignissen</span><span class="sxs-lookup"><span data-stu-id="7f069-295">Using classic COM events</span></span>

- <span data-ttu-id="7f069-296">Implementieren der <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> -Schnittstelle für einen verwalteten Typ</span><span class="sxs-lookup"><span data-stu-id="7f069-296">Implementing the <xref:System.Runtime.InteropServices.ICustomQueryInterface?displayProperty=nameWithType> interface on a managed type</span></span>

- <span data-ttu-id="7f069-297">Implementieren der [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) -Schnittstelle für einen verwalteten Typ über das <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> -Attribut</span><span class="sxs-lookup"><span data-stu-id="7f069-297">Implementing the [IDispatch](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/nn-oaidl-idispatch) interface on a managed type through the <xref:System.Runtime.InteropServices.ComDefaultInterfaceAttribute?displayProperty=nameWithType> attribute.</span></span> <span data-ttu-id="7f069-298">Es ist jedoch nicht möglich, com-Objekte mithilfe von aufzurufen `IDispatch` , und das verwaltete Objekt kann nicht implementieren `IDispatch` .</span><span class="sxs-lookup"><span data-stu-id="7f069-298">However, you can't call COM objects through `IDispatch`, and your managed object can't implement `IDispatch`.</span></span>

<span data-ttu-id="7f069-299">Das Verwenden von Reflektion zum Aufrufen einer Plattformaufrufmethode wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-299">Using reflection to invoke a platform invoke method isn't supported.</span></span> <span data-ttu-id="7f069-300">Sie können diese Einschränkung umgehen, indem Sie den Methodenaufruf in eine andere Methode einschließen und den Wrapper stattdessen mithilfe von Reflektion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7f069-300">You can work around this limitation by wrapping the method call in another method and using reflection to call the wrapper instead.</span></span>

<a name="APIs"></a>

### <a name="other-differences-from-net-apis-for-windows-store-apps"></a><span data-ttu-id="7f069-301">Andere Unterschiede zu .NET-APIs für Windows Store-Apps</span><span class="sxs-lookup"><span data-stu-id="7f069-301">Other differences from .NET APIs for Windows Store apps</span></span>

<span data-ttu-id="7f069-302">In diesem Abschnitt werden die verbleibenden APIs aufgelistet, die in .net Native nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-302">This section lists the remaining APIs that aren't supported in .NET Native.</span></span> <span data-ttu-id="7f069-303">Die größte Gruppe von nicht unterstützten APIs sind die Windows Communication Foundation (WCF)-APIs.</span><span class="sxs-lookup"><span data-stu-id="7f069-303">The largest set of the unsupported APIs is the Windows Communication Foundation (WCF) APIs.</span></span>

<span data-ttu-id="7f069-304">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span><span class="sxs-lookup"><span data-stu-id="7f069-304">**DataAnnotations (System.ComponentModel.DataAnnotations)**</span></span>

<span data-ttu-id="7f069-305">Die Typen in den <xref:System.ComponentModel.DataAnnotations> -und- <xref:System.ComponentModel.DataAnnotations.Schema> Namespaces werden in .net Native nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-305">The types in the <xref:System.ComponentModel.DataAnnotations> and <xref:System.ComponentModel.DataAnnotations.Schema> namespaces aren't supported in .NET Native.</span></span> <span data-ttu-id="7f069-306">Hierzu gehören die folgenden Typen, die in .net für Windows Store-Apps für Windows 8 vorhanden sind:</span><span class="sxs-lookup"><span data-stu-id="7f069-306">These include the following types that are present in .NET for Windows Store apps for Windows 8:</span></span>

- <xref:System.ComponentModel.DataAnnotations.AssociationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ConcurrencyCheckAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.CustomValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataType?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DataTypeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayColumnAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.DisplayFormatAttribute>
- <xref:System.ComponentModel.DataAnnotations.EditableAttribute>
- <xref:System.ComponentModel.DataAnnotations.EnumDataTypeAttribute>
- <xref:System.ComponentModel.DataAnnotations.FilterUIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.KeyAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RangeAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RegularExpressionAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.RequiredAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.StringLengthAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.TimestampAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.UIHintAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationContext?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationException?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.ValidationResult?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Validator?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedAttribute?displayProperty=nameWithType>
- <xref:System.ComponentModel.DataAnnotations.Schema.DatabaseGeneratedOption?displayProperty=nameWithType>

 <span data-ttu-id="7f069-307">**Visual Basic**</span><span class="sxs-lookup"><span data-stu-id="7f069-307">**Visual Basic**</span></span>

<span data-ttu-id="7f069-308">Visual Basic wird derzeit in .net Native nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-308">Visual Basic isn't currently supported in .NET Native.</span></span> <span data-ttu-id="7f069-309">Die folgenden Typen in den <xref:Microsoft.VisualBasic> -und- <xref:Microsoft.VisualBasic.CompilerServices> Namespaces sind in .net Native nicht verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7f069-309">The following types in the <xref:Microsoft.VisualBasic> and <xref:Microsoft.VisualBasic.CompilerServices> namespaces aren't available in .NET Native:</span></span>

- <xref:Microsoft.VisualBasic.CallType?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Constants?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.HideModuleNameAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Strings?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Conversions?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.IncompleteInitialization?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.NewLateBinding?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ObjectFlowControl.ForLoopControl?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Operators?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionCompareAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.OptionTextAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.ProjectData?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StandardModuleAttribute?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.StaticLocalInitFlag?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.CompilerServices.Utils?displayProperty=nameWithType>

<span data-ttu-id="7f069-310">**Reflection Context (System.Reflection.Context-Namespace)**</span><span class="sxs-lookup"><span data-stu-id="7f069-310">**Reflection Context (System.Reflection.Context namespace)**</span></span>

<span data-ttu-id="7f069-311">Die- <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> Klasse wird in .net Native nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-311">The <xref:System.Reflection.Context.CustomReflectionContext?displayProperty=nameWithType> class isn't supported in .NET Native.</span></span>

<span data-ttu-id="7f069-312">**RTC (System.Net.Http.Rtc)**</span><span class="sxs-lookup"><span data-stu-id="7f069-312">**RTC (System.Net.Http.Rtc)**</span></span>

<span data-ttu-id="7f069-313">Die- `System.Net.Http.RtcRequestFactory` Klasse wird in .net Native nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-313">The `System.Net.Http.RtcRequestFactory` class isn't supported in .NET Native.</span></span>

<span data-ttu-id="7f069-314">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span><span class="sxs-lookup"><span data-stu-id="7f069-314">**Windows Communication Foundation (WCF) (System.ServiceModel.\*)**</span></span>

<span data-ttu-id="7f069-315">Die Typen in den [System. Service Model. \*-Namespaces](xref:System.ServiceModel) werden in .net Native nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7f069-315">The types in the [System.ServiceModel.\* namespaces](xref:System.ServiceModel) aren't supported in .NET Native.</span></span> <span data-ttu-id="7f069-316">Hierzu gehören die folgenden Typen:</span><span class="sxs-lookup"><span data-stu-id="7f069-316">These include the following types:</span></span>

- <xref:System.ServiceModel.ActionNotSupportedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpMessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.BasicHttpSecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.BeginOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.ChannelBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.EndOperationDelegate?displayProperty=nameWithType>
- <xref:System.ServiceModel.ClientBase%601.InvokeAsyncCompletedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectAbortedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationObjectFaultedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.CommunicationState?displayProperty=nameWithType>
- <xref:System.ServiceModel.DataContractFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.DnsEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.DuplexClientBase%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddress?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointAddressBuilder?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.EndpointNotFoundException?displayProperty=nameWithType>
- <xref:System.ServiceModel.EnvelopeVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.ExceptionDetail?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultCode?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReason?displayProperty=nameWithType>
- <xref:System.ServiceModel.FaultReasonText?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpBindingBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.HttpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.ICommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.IContextChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.IDefaultCommunicationTimeouts?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensibleObject%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtension%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.IExtensionCollection%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.InvalidMessageContractException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageBodyMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageContractMemberAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeader%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageHeaderException?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageParameterAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityOverTcp?displayProperty=nameWithType>
- <xref:System.ServiceModel.MessageSecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetHttpMessageEncoding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.NetTcpSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContextScope?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.OperationFormatStyle?displayProperty=nameWithType>
- <xref:System.ServiceModel.ProtocolException?displayProperty=nameWithType>
- <xref:System.ServiceModel.QuotaExceededException?displayProperty=nameWithType>
- <xref:System.ServiceModel.SecurityMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServerTooBusyException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceActivationException?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceKnownTypeAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.SpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpClientCredentialType?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity?displayProperty=nameWithType>
- <xref:System.ServiceModel.TransferMode?displayProperty=nameWithType>
- <xref:System.ServiceModel.UnknownMessageReceivedEventArgs?displayProperty=nameWithType>
- <xref:System.ServiceModel.UpnEndpointIdentity?displayProperty=nameWithType>
- <xref:System.ServiceModel.XmlSerializerFormatAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.AddressingVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelManagerBase?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ChannelParameterCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CommunicationObject?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CompressionFormat?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.FaultConverter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpRequestMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpResponseMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.HttpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IChannelFactory%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IDuplexSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IHttpCookieContainerManager?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IInputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IMessageProperty?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IOutputSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.IRequestSessionChannel?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISession?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.ISessionChannel%601?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.Message?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageBuffer?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoder?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncoderFactory?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageFault?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeader?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaderInfo?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageHeaders?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageProperties?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageState?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.MessageVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.RequestContext?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SecurityHeaderLayout?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.TransportSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportSettings?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WebSocketTransportUsage?displayProperty=nameWithType>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ClientCredentials?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ContractDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.FaultDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.IOperationBehavior?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageBodyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageDirection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessageHeaderDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePartDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.MessagePropertyDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescription?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.OperationDescriptionCollection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Description.ServiceEndpoint?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.ClientRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchOperation?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.DispatchRuntime?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.EndpointDispatcher?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageFormatter?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IClientOperationSelector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IParameterInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.BasicSecurityProfileVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.HttpDigestClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.MessageSecurityException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecureConversationVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityAccessDeniedException?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityPolicyVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.SecurityVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.TrustVersion?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.UserNamePasswordClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.WindowsClientCredential?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SecurityTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.SupportingTokenParameters?displayProperty=nameWithType>
- <xref:System.ServiceModel.Security.Tokens.UserNameSecurityTokenParameters?displayProperty=nameWithType>

### <a name="differences-in-serializers"></a><span data-ttu-id="7f069-317">Unterschiede in den Serialisierungsprogrammen</span><span class="sxs-lookup"><span data-stu-id="7f069-317">Differences in serializers</span></span>

<span data-ttu-id="7f069-318">Die folgenden Unterschiede betreffen die Serialisierung und Deserialisierung mit den Klassen <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>und <xref:System.Xml.Serialization.XmlSerializer> :</span><span class="sxs-lookup"><span data-stu-id="7f069-318">The following differences concern serialization and deserialization with the <xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer> classes:</span></span>

- <span data-ttu-id="7f069-319">In .net Native können <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> eine abgeleitete Klasse, die über ein Basisklassenmember verfügt, dessen Typ kein stammserialisierungstyp ist, serialisieren oder deserialisieren.</span><span class="sxs-lookup"><span data-stu-id="7f069-319">In .NET Native, <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize or deserialize a derived class that has a base class member whose type isn't a root serialization type.</span></span> <span data-ttu-id="7f069-320">Im folgenden Code führt das Serialisieren bzw. Deserialisieren von `Y` beispielsweise zu einem Fehler:</span><span class="sxs-lookup"><span data-stu-id="7f069-320">For example, in the following code, trying to serialize or deserialize `Y` results in an error:</span></span>

  [!code-csharp[ProjectN#10](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn/cs/compat3.cs#10)]

  <span data-ttu-id="7f069-321">Typ `InnerType` ist dem Serialisierungsprogramm nicht bekannt, da die Member der Basisklasse während der Serialisierung nicht durchlaufen werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-321">Type `InnerType` isn't known to the serializer, because the members of the base class aren't traversed during serialization.</span></span>

- <span data-ttu-id="7f069-322"><xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> können keine Klasse oder Struktur serialisieren, die die <xref:System.Collections.Generic.IEnumerable%601> -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="7f069-322"><xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> fail to serialize a class or structure that implements the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="7f069-323">Für folgende Typen schlägt das Serialisieren oder Deserialisieren beispielsweise fehl:</span><span class="sxs-lookup"><span data-stu-id="7f069-323">For example, the following types fail to serialize or deserialize:</span></span>

- <span data-ttu-id="7f069-324"><xref:System.Xml.Serialization.XmlSerializer> kann den folgenden Objektwert nicht serialisieren, da der genaue Typ des zu serialisierenden Objekts unbekannt ist:</span><span class="sxs-lookup"><span data-stu-id="7f069-324"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize the following object value, because it doesn't know the exact type of the object to be serialized:</span></span>

- <span data-ttu-id="7f069-325"><xref:System.Xml.Serialization.XmlSerializer> kann nicht serialisieren oder deserialisieren, wenn der Typ des serialisierten Objekts <xref:System.Xml.XmlQualifiedName>ist.</span><span class="sxs-lookup"><span data-stu-id="7f069-325"><xref:System.Xml.Serialization.XmlSerializer> fails to serialize or deserialize if the type of the serialized object is <xref:System.Xml.XmlQualifiedName>.</span></span>

- <span data-ttu-id="7f069-326">Alle Serialisierungsprogramme (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>und <xref:System.Xml.Serialization.XmlSerializer>) können keinen Serialisierungscode für den Typ <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> oder für einen Typ generieren, der <xref:System.Xml.Linq.XElement>enthält.</span><span class="sxs-lookup"><span data-stu-id="7f069-326">All serializers (<xref:System.Runtime.Serialization.DataContractSerializer>, <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, and <xref:System.Xml.Serialization.XmlSerializer>) fail to generate serialization code for type <xref:System.Xml.Linq.XElement?displayProperty=nameWithType> or for a type that contains <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="7f069-327">Sie zeigen stattdessen Buildfehler an.</span><span class="sxs-lookup"><span data-stu-id="7f069-327">They display build-time errors instead.</span></span>

- <span data-ttu-id="7f069-328">Die folgenden Konstruktoren der Serialisierungstypen funktionieren möglicherweise nicht wie erwartet:</span><span class="sxs-lookup"><span data-stu-id="7f069-328">The following constructors of the serialization types aren't guaranteed to work as expected:</span></span>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.DataContractSerializerSettings%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.DataContractSerializer.%23ctor%28System.Type%2CSystem.Xml.XmlDictionaryString%2CSystem.Xml.XmlDictionaryString%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Runtime.Serialization.Json.DataContractJsonSerializerSettings%29>

  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.%23ctor%28System.Type%2CSystem.Collections.Generic.IEnumerable%7BSystem.Type%7D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.String%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Type%5B%5D%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlRootAttribute%29>

  - <xref:System.Xml.Serialization.XmlSerializer.%23ctor%28System.Type%2CSystem.Xml.Serialization.XmlAttributeOverrides%2CSystem.Type%5B%5D%2CSystem.Xml.Serialization.XmlRootAttribute%2CSystem.String%29>

- <span data-ttu-id="7f069-329"><xref:System.Xml.Serialization.XmlSerializer> kann keinen Code für einen Typ generieren, der über Methoden mit einem der folgenden Attribute verfügt:</span><span class="sxs-lookup"><span data-stu-id="7f069-329"><xref:System.Xml.Serialization.XmlSerializer> fails to generate code for a type that has methods attributed with any of the following attributes:</span></span>

  - <xref:System.Runtime.Serialization.OnSerializingAttribute>

  - <xref:System.Runtime.Serialization.OnSerializedAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializingAttribute>

  - <xref:System.Runtime.Serialization.OnDeserializedAttribute>

- <span data-ttu-id="7f069-330"><xref:System.Xml.Serialization.XmlSerializer> berücksichtigt nicht die benutzerdefinierte <xref:System.Xml.Serialization.IXmlSerializable> -Serialisierungsschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7f069-330"><xref:System.Xml.Serialization.XmlSerializer> doesn't honor the <xref:System.Xml.Serialization.IXmlSerializable> custom serialization interface.</span></span> <span data-ttu-id="7f069-331">Wenn Sie eine Klasse haben, die diese Schnittstelle implementiert, berücksichtigt <xref:System.Xml.Serialization.XmlSerializer> den Typ als veralteten CLR-Objekttyp (POCO) und serialisiert nur die öffentlichen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="7f069-331">If you have a class that implements this interface, <xref:System.Xml.Serialization.XmlSerializer> considers the type a plain old CLR object (POCO) type and serializes only its public properties.</span></span>

- <span data-ttu-id="7f069-332">Das Serialisieren eines einfachen <xref:System.Exception> Objekts funktioniert nicht gut mit <xref:System.Runtime.Serialization.DataContractSerializer> und <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> .</span><span class="sxs-lookup"><span data-stu-id="7f069-332">Serializing a plain <xref:System.Exception> object doesn't work well with <xref:System.Runtime.Serialization.DataContractSerializer> and <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>

<a name="VS"></a>

## <a name="visual-studio-differences"></a><span data-ttu-id="7f069-333">Visual Studio-Unterschiede</span><span class="sxs-lookup"><span data-stu-id="7f069-333">Visual Studio differences</span></span>

<span data-ttu-id="7f069-334">**Ausnahmen und Debuggen**</span><span class="sxs-lookup"><span data-stu-id="7f069-334">**Exceptions and debugging**</span></span>

<span data-ttu-id="7f069-335">Beim Ausführen von apps, die mit .net Native im Debugger kompiliert werden, werden Ausnahmen der ersten Chance für die folgenden Ausnahme Typen aktiviert:</span><span class="sxs-lookup"><span data-stu-id="7f069-335">When you're running apps compiled by using .NET Native in the debugger, first-chance exceptions are enabled for the following exception types:</span></span>

- <xref:System.MemberAccessException>

- <xref:System.TypeAccessException>

<span data-ttu-id="7f069-336">**Entwickeln von apps**</span><span class="sxs-lookup"><span data-stu-id="7f069-336">**Building apps**</span></span>

<span data-ttu-id="7f069-337">Verwenden Sie die x86-Buildtools, die standardmäßig von Visual Studio verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f069-337">Use the x86 build tools that are used by default by Visual Studio.</span></span> <span data-ttu-id="7f069-338">Sie sollten nicht die AMD64-MSBuild-Tools unter "C:\Program Files (x86)\MSBuild\12.0\bin\amd64" verwenden. Diese können Buildprobleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="7f069-338">We don't recommend using the AMD64 MSBuild tools, which are found in C:\Program Files (x86)\MSBuild\12.0\bin\amd64; these may create build problems.</span></span>

<span data-ttu-id="7f069-339">**Profiler**</span><span class="sxs-lookup"><span data-stu-id="7f069-339">**Profilers**</span></span>

- <span data-ttu-id="7f069-340">Der Visual Studio-CPU-Profiler und der XAML-Arbeitsspeicherprofiler zeigen "Nur mein Code" nicht ordnungsgemäß an.</span><span class="sxs-lookup"><span data-stu-id="7f069-340">The Visual Studio CPU Profiler and XAML Memory Profiler don't display Just-My-Code correctly.</span></span>

- <span data-ttu-id="7f069-341">Der XAML-Arbeitsspeicherprofiler zeigt verwaltete Heapdaten nicht ordnungsgemäß an.</span><span class="sxs-lookup"><span data-stu-id="7f069-341">The XAML Memory Profiler doesn't accurately display managed heap data.</span></span>

- <span data-ttu-id="7f069-342">Der CPU-Profiler identifiziert Module nicht ordnungsgemäß und zeigt Funktionsnamen mit Präfix an.</span><span class="sxs-lookup"><span data-stu-id="7f069-342">The CPU Profiler doesn't correctly identify modules, and displays prefixed function names.</span></span>

<span data-ttu-id="7f069-343">**Komponententest-Bibliotheksprojekte**</span><span class="sxs-lookup"><span data-stu-id="7f069-343">**Unit Test Library projects**</span></span>

<span data-ttu-id="7f069-344">Das Aktivieren von .net Native in einer Komponenten Test Bibliothek für ein Windows Store-App-Projekt wird nicht unterstützt und bewirkt, dass das Projekt nicht erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7f069-344">Enabling .NET Native on a Unit Test Library for a Windows Store apps project isn't supported and causes the project to fail to build.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f069-345">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f069-345">See also</span></span>

- [<span data-ttu-id="7f069-346">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="7f069-346">Getting Started</span></span>](getting-started-with-net-native.md)
- [<span data-ttu-id="7f069-347">Laufzeitanweisungs-Konfigurationsdatei (rd.xml) Referenz</span><span class="sxs-lookup"><span data-stu-id="7f069-347">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="7f069-348">Übersicht über .net für Windows Store-Apps</span><span class="sxs-lookup"><span data-stu-id="7f069-348">.NET For Windows Store apps overview</span></span>](https://docs.microsoft.com/previous-versions/windows/apps/br230302%28v=vs.140%29)
- [<span data-ttu-id="7f069-349">.NET Framework-Unterstützung für Windows Store-Apps und Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="7f069-349">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)
