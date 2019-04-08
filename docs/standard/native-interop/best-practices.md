---
title: 'Bewährte Methoden für native Interoperabilität: .NET'
description: Erfahren Sie mehr über bewährte Methoden für die Einrichtung von Schnittstellen mit nativen Komponenten in .NET.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 5b65f80d3a81fab0d74ce26aec3b454c716a5d51
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412057"
---
# <a name="native-interoperability-best-practices"></a><span data-ttu-id="603c3-103">Bewährte Methoden für native Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="603c3-103">Native interoperability best practices</span></span>

<span data-ttu-id="603c3-104">.NET bietet verschiedene Möglichkeiten zum Anpassen Ihres Codes für die native Interoperabilität.</span><span class="sxs-lookup"><span data-stu-id="603c3-104">.NET gives you a variety of ways to customize your native interoperability code.</span></span> <span data-ttu-id="603c3-105">Dieser Artikel bietet einen Leitfaden, den die .NET-Teams von Microsoft in Bezug auf die native Interoperabilität befolgen.</span><span class="sxs-lookup"><span data-stu-id="603c3-105">This article includes the guidance that Microsoft's .NET teams follow for native interoperability.</span></span>

## <a name="general-guidance"></a><span data-ttu-id="603c3-106">Allgemeine Anleitung</span><span class="sxs-lookup"><span data-stu-id="603c3-106">General guidance</span></span>

<span data-ttu-id="603c3-107">Die Anleitungen in diesem Abschnitt gelten für alle Interoperabilitätsszenarien.</span><span class="sxs-lookup"><span data-stu-id="603c3-107">The guidance in this section applies to all interop scenarios.</span></span>

- <span data-ttu-id="603c3-108">**✔️ VERWENDEN** Sie die gleichen Benennungen und die gleiche Groß- und Kleinschreibung für Ihre Methoden und Parameter wie die native Methode, die Sie aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="603c3-108">**✔️ DO** use the same naming and capitalization for your methods and parameters as the native method you want to call.</span></span>
- <span data-ttu-id="603c3-109">**✔️ ERWÄGEN** Sie die Verwendung der gleichen Benennungen und der gleichen Groß- und Kleinschreibung für Werte von Konstanten.</span><span class="sxs-lookup"><span data-stu-id="603c3-109">**✔️ CONSIDER** using the same naming and capitalization for constant values.</span></span>
- <span data-ttu-id="603c3-110">**✔️ VERWENDEN** Sie .NET-Typen, die dem nativen Typ am ähnlichsten sind.</span><span class="sxs-lookup"><span data-stu-id="603c3-110">**✔️ DO** use .NET types that map closest to the native type.</span></span> <span data-ttu-id="603c3-111">Wenn z.B. der native Typ in C# `unsigned int` ist, verwenden Sie `uint`.</span><span class="sxs-lookup"><span data-stu-id="603c3-111">For example, in C#, use `uint` when the native type is `unsigned int`.</span></span>
- <span data-ttu-id="603c3-112">**✔️ VERWENDEN** Sie nur `[In]`- und `[Out]`-Attribute, wenn sich das gewünschte Verhalten vom Standardverhalten unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="603c3-112">**✔️ DO** only use `[In]` and `[Out]` attributes when the behavior you want differs from the default behavior.</span></span>
- <span data-ttu-id="603c3-113">**✔️ ERWÄGEN** Sie die Verwendung von <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType>, um Ihre nativen Arraypuffer in einem Pool zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="603c3-113">**✔️ CONSIDER** using <xref:System.Buffers.ArrayPool%601?displayProperty=nameWithType> to pool your native array buffers.</span></span>
- <span data-ttu-id="603c3-114">**✔️ ERWÄGEN** Sie eine Umschließung Ihrer P/Invoke-Deklarationen in einer Klasse mit dem gleichen Namen und der gleichen Groß- und Kleinschreibung wie in Ihrer nativen Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="603c3-114">**✔️ CONSIDER** wrapping your P/Invoke declarations in a class with the same name and capitalization as your native library.</span></span>
  - <span data-ttu-id="603c3-115">Damit können Ihre `[DllImport]`-Attribute das C#-Sprachfeature `nameof` verwenden, um den Namen der nativen Bibliothek zu übergeben, und so sicherstellen, dass der Name der nativen Bibliothek nicht falsch geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="603c3-115">This allows your `[DllImport]` attributes to use the C# `nameof` language feature to pass in the name of the native library and ensure that you didn't misspell the name of the native library.</span></span>

## <a name="dllimport-attribute-settings"></a><span data-ttu-id="603c3-116">Attributeinstellungen für „DllImport“</span><span class="sxs-lookup"><span data-stu-id="603c3-116">DllImport attribute settings</span></span>

| <span data-ttu-id="603c3-117">Einstellung</span><span class="sxs-lookup"><span data-stu-id="603c3-117">Setting</span></span> | <span data-ttu-id="603c3-118">Standard</span><span class="sxs-lookup"><span data-stu-id="603c3-118">Default</span></span> | <span data-ttu-id="603c3-119">Empfehlung</span><span class="sxs-lookup"><span data-stu-id="603c3-119">Recommendation</span></span> | <span data-ttu-id="603c3-120">Details</span><span class="sxs-lookup"><span data-stu-id="603c3-120">Details</span></span> |
|---------|---------|----------------|---------|
| <xref:System.Runtime.InteropServices.DllImportAttribute.PreserveSig>   | `true` |  <span data-ttu-id="603c3-121">Behalten Sie den Standardwert bei.</span><span class="sxs-lookup"><span data-stu-id="603c3-121">keep default</span></span>  | <span data-ttu-id="603c3-122">Wenn diese Einstellung explizit auf „false“ festgelegt wird, werden fehlerhafte HRESULT-Rückgabewerte zu Ausnahmen umgewandelt (und der Rückgabewert in der Definition wird dadurch NULL).</span><span class="sxs-lookup"><span data-stu-id="603c3-122">When this is explicitly set to false, failed HRESULT return values will be turned into exceptions (and the return value in the definition becomes null as a result).</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.SetLastError> | `false`  | <span data-ttu-id="603c3-123">Hängt von der API ab.</span><span class="sxs-lookup"><span data-stu-id="603c3-123">depends on the API</span></span>  | <span data-ttu-id="603c3-124">Legen Sie diese Einstellung auf „true“ fest, wenn die API „GetLastError“ verwendet, und verwenden Sie „Marshal.GetLastWin32Error“, um den Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="603c3-124">Set this to true if the API uses GetLastError and use Marshal.GetLastWin32Error to get the value.</span></span> <span data-ttu-id="603c3-125">Wenn die API eine Bedingung festlegt, die besagt, dass ein Fehler vorliegt, rufen Sie den Fehler ab, bevor Sie weitere Aufrufe senden, um ein versehentliches Überschreiben zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="603c3-125">If the API sets a condition that says it has an error, get the error before making other calls to avoid inadvertently having it overwritten.</span></span>|
| <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> | <span data-ttu-id="603c3-126">`CharSet.None` – Fallback auf das Verhalten `CharSet.Ansi`.</span><span class="sxs-lookup"><span data-stu-id="603c3-126">`CharSet.None`, which falls back to `CharSet.Ansi` behavior</span></span>  | <span data-ttu-id="603c3-127">Verwenden Sie explizit `CharSet.Unicode` oder `CharSet.Ansi`, wenn in der Definition Zeichenfolgen oder Zeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="603c3-127">Explicitly  use `CharSet.Unicode` or `CharSet.Ansi` when strings or characters are present in the definition</span></span> | <span data-ttu-id="603c3-128">Damit wird das Marshallingverhalten von Zeichenfolgen angegeben und festgelegt, was `ExactSpelling` bei `false` ausführt.</span><span class="sxs-lookup"><span data-stu-id="603c3-128">This specifies marshalling behavior of strings and what `ExactSpelling` does when `false`.</span></span> <span data-ttu-id="603c3-129">Beachten Sie, dass `CharSet.Ansi` tatsächlich UTF8 oder Unix ist.</span><span class="sxs-lookup"><span data-stu-id="603c3-129">Note that `CharSet.Ansi` is actually UTF8 on Unix.</span></span> <span data-ttu-id="603c3-130">_In den meisten Fällen_ verwendet Windows Unicode, Unix verwendet UTF8.</span><span class="sxs-lookup"><span data-stu-id="603c3-130">_Most_ of the time Windows uses Unicode while Unix uses UTF8.</span></span> <span data-ttu-id="603c3-131">Weitere Informationen finden Sie in der [Dokumentation zu Zeichensätzen](./charset.md).</span><span class="sxs-lookup"><span data-stu-id="603c3-131">See more information on the [documentation on charsets](./charset.md).</span></span> |
| <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> | `false` | `true`             | <span data-ttu-id="603c3-132">Legen Sie diesen Wert auf „true“ fest, um einen leichten Leistungsvorteil zu erzielen, da die Runtime nicht nach alternativen Funktionsnamen mit dem Suffix „A“ oder „W“ sucht, je nach Wert der Einstellung von `CharSet` („A“ für `CharSet.Ansi` und „W“ für `CharSet.Unicode`).</span><span class="sxs-lookup"><span data-stu-id="603c3-132">Set this to true and gain a slight perf benefit as the runtime will not look for alternate function names with either an "A" or "W" suffix depending on the value of the `CharSet` setting ("A" for `CharSet.Ansi` and "W" for `CharSet.Unicode`).</span></span> |

## <a name="string-parameters"></a><span data-ttu-id="603c3-133">Zeichenfolgenparameter</span><span class="sxs-lookup"><span data-stu-id="603c3-133">String parameters</span></span>

<span data-ttu-id="603c3-134">Wenn „CharSet“ auf „Unicode“ festgelegt oder das Argument explizit als `[MarshalAs(UnmanagedType.LPWSTR)]` gekennzeichnet ist _und_ die Zeichenfolge per Wert (nicht als `ref` oder `out`) übergeben wird, wird die Zeichenfolge angeheftet und vom nativen Code direkt verwendet (nicht kopiert).</span><span class="sxs-lookup"><span data-stu-id="603c3-134">When the CharSet is Unicode or the argument is explicitly marked as `[MarshalAs(UnmanagedType.LPWSTR)]` _and_ the string is passed by value (not `ref` or `out`), the string will be pinned and used directly by native code (rather than copied).</span></span>

<span data-ttu-id="603c3-135">Denken Sie daran, `[DllImport]` als `Charset.Unicode` zu kennzeichnen, es sei denn, Sie möchten explizit, dass Ihre Zeichenfolgen als ANSI verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-135">Remember to mark the `[DllImport]` as `Charset.Unicode` unless you explicitly want ANSI treatment of your strings.</span></span>

<span data-ttu-id="603c3-136">**❌ VERWENDEN SIE KEINE** `[Out] string`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="603c3-136">**❌ DO NOT** use `[Out] string` parameters.</span></span> <span data-ttu-id="603c3-137">Zeichenfolgenparameter, die per Wert mit dem `[Out]`-Attribut übergeben werden, können die Runtime destabilisieren, wenn die Zeichenfolge internalisiert ist.</span><span class="sxs-lookup"><span data-stu-id="603c3-137">String parameters passed by value with the `[Out]` attribute can destabilize the runtime if the string is an interned string.</span></span> <span data-ttu-id="603c3-138">Weitere Informationen zum Internalisieren von Zeichenfolgen finden Sie in der Dokumentation zu <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="603c3-138">See more information about string interning in the documentation for <xref:System.String.Intern%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="603c3-139">**❌ VERMEIDEN** Sie `StringBuilder`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="603c3-139">**❌ AVOID** `StringBuilder` parameters.</span></span> <span data-ttu-id="603c3-140">`StringBuilder` -Marshalling erzeugt *immer* eine native Pufferkopie.</span><span class="sxs-lookup"><span data-stu-id="603c3-140">`StringBuilder` marshalling *always* creates a native buffer copy.</span></span> <span data-ttu-id="603c3-141">Dies kann extrem ineffizient sein.</span><span class="sxs-lookup"><span data-stu-id="603c3-141">As such, it can be extremely inefficient.</span></span> <span data-ttu-id="603c3-142">Sehen Sie sich das folgende typische Szenario an, in dem eine Windows-API aufgerufen wird, die eine Zeichenfolge akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="603c3-142">Take the typical scenario of calling a Windows API that takes a string:</span></span>

1. <span data-ttu-id="603c3-143">Erstellen Sie einen StringBuilder mit der gewünschten Kapazität (ordnet die verwaltete Kapazität zu) **{1}**</span><span class="sxs-lookup"><span data-stu-id="603c3-143">Create a SB of the desired capacity (allocates managed capacity) **{1}**</span></span>
2. <span data-ttu-id="603c3-144">Aufrufen</span><span class="sxs-lookup"><span data-stu-id="603c3-144">Invoke</span></span>
   1. <span data-ttu-id="603c3-145">Ordnet einen nativen Puffer zu **{2}**</span><span class="sxs-lookup"><span data-stu-id="603c3-145">Allocates a native buffer **{2}**</span></span>  
   2. <span data-ttu-id="603c3-146">Kopiert den Inhalt im Fall von `[In]` _(Standard für einen`StringBuilder`-Parameter)_</span><span class="sxs-lookup"><span data-stu-id="603c3-146">Copies the contents if `[In]` _(the default for a `StringBuilder` parameter)_</span></span>  
   3. <span data-ttu-id="603c3-147">Kopiert den nativen Puffer in ein neu zugeordnetes verwaltetes Array im Fall von `[Out]` **{3}** _(ebenfalls Standard für `StringBuilder`)_</span><span class="sxs-lookup"><span data-stu-id="603c3-147">Copies the native buffer into a newly allocated managed array if `[Out]` **{3}** _(also the default for `StringBuilder`)_</span></span>  
3. <span data-ttu-id="603c3-148">`ToString()` ordnet ein weiteres verwaltetes Array zu **{4}**</span><span class="sxs-lookup"><span data-stu-id="603c3-148">`ToString()` allocates yet another managed array **{4}**</span></span>

<span data-ttu-id="603c3-149">Damit haben wir *{4}* Zuordnungen, um eine Zeichenfolge aus dem nativen Code abzurufen.</span><span class="sxs-lookup"><span data-stu-id="603c3-149">That is *{4}* allocations to get a string out of native code.</span></span> <span data-ttu-id="603c3-150">Die beste Möglichkeit, um dies zu beschränken, besteht darin, den `StringBuilder` in einem weiteren Aufruf wiederzuverwenden, damit wird aber dennoch nur *1* Zuordnung eingespart.</span><span class="sxs-lookup"><span data-stu-id="603c3-150">The best you can do to limit this is to reuse the `StringBuilder` in another call but this still only saves *1* allocation.</span></span> <span data-ttu-id="603c3-151">Es ist viel besser, einen Zeichenpuffer aus dem `ArrayPool` zu verwenden und zwischenzuspeichern – damit benötigen Sie in nachfolgenden Aufrufen nur die Zuordnung für `ToString()`.</span><span class="sxs-lookup"><span data-stu-id="603c3-151">It's much better to use and cache a character buffer from `ArrayPool`- you can then get down to just the allocation for the `ToString()` on subsequent calls.</span></span>

<span data-ttu-id="603c3-152">Ein weiteres Problem bei `StringBuilder` ist, dass immer der Rückgabepuffer bis zum ersten NULL-Zeichen zurückkopiert wird.</span><span class="sxs-lookup"><span data-stu-id="603c3-152">The other issue with `StringBuilder` is that it always copies the return buffer back up to the first null.</span></span> <span data-ttu-id="603c3-153">Wenn die zurückgegebene Zeichenfolge nicht beendet oder mit einem doppelten NULL-Zeichen beendet wird, ist „P/Invoke“ bestenfalls falsch.</span><span class="sxs-lookup"><span data-stu-id="603c3-153">If the passed back string isn't terminated or is a double-null-terminated string, your P/Invoke is incorrect at best.</span></span>

<span data-ttu-id="603c3-154">Wenn Sie `StringBuilder` *tatsächlich* verwenden, besteht eine weitere Besonderheit darin, dass die Kapazität **kein** verborgenes NULL-Zeichen umfasst, das bei der Interoperabilität immer berücksichtigt wird.</span><span class="sxs-lookup"><span data-stu-id="603c3-154">If you *do* use `StringBuilder`, one last gotcha is that the capacity does **not** include a hidden null, which is always accounted for in interop.</span></span> <span data-ttu-id="603c3-155">Das wird häufig falsch gemacht, da die meisten APIs die Größe des Puffers *einschließlich* des NULL-Zeichens erwarten.</span><span class="sxs-lookup"><span data-stu-id="603c3-155">It's common for people to get this wrong as most APIs want the size of the buffer *including* the null.</span></span> <span data-ttu-id="603c3-156">Dies kann zu unnötigen bzw. verschwendeten Zuordnungen führen.</span><span class="sxs-lookup"><span data-stu-id="603c3-156">This can result in wasted/unnecessary allocations.</span></span> <span data-ttu-id="603c3-157">Darüber hinaus verhindert diese Besonderheit, dass die Runtime das Marshallen von `StringBuilder` optimiert, um die Erstellung von Kopien zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="603c3-157">Additionally, this gotcha prevents the runtime from optimizing `StringBuilder` marshalling to minimize copies.</span></span>

<span data-ttu-id="603c3-158">**✔️ ERWÄGEN** Sie die Verwendung von `char[]`s aus einem `ArrayPool`.</span><span class="sxs-lookup"><span data-stu-id="603c3-158">**✔️ CONSIDER** using `char[]`s from an `ArrayPool`.</span></span>

<span data-ttu-id="603c3-159">Weitere Informationen zum Marshalling von Zeichenfolgen finden Sie unter [Standardmäßiges Marshalling für Zeichenfolgen](../../framework/interop/default-marshaling-for-strings.md) und [Anpassen des Zeichenfolgenmarshallings](customize-parameter-marshalling.md#customizing-string-parameters).</span><span class="sxs-lookup"><span data-stu-id="603c3-159">For more information on string marshalling, see [Default Marshalling for Strings](../../framework/interop/default-marshaling-for-strings.md) and [Customizing string marshalling](customize-parameter-marshalling.md#customizing-string-parameters).</span></span>

> <span data-ttu-id="603c3-160">__Windows-spezifisch__</span><span class="sxs-lookup"><span data-stu-id="603c3-160">__Windows Specific__</span></span>  
> <span data-ttu-id="603c3-161">Bei `[Out]`-Zeichenfolgen verwendet die CLR (Common Language Runtime) standardmäßig `CoTaskMemFree`, um Zeichenfolgen freizugeben, oder `SysStringFree` bei Zeichenfolgen, die als `UnmanagedType.BSTR` gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="603c3-161">For `[Out]` strings the CLR will use `CoTaskMemFree` by default to free strings or `SysStringFree` for strings that are marked as `UnmanagedType.BSTR`.</span></span>  
<span data-ttu-id="603c3-162">**Bei den meisten APIs mit Puffer für Ausgabezeichenfolgen gilt Folgendes**:</span><span class="sxs-lookup"><span data-stu-id="603c3-162">**For most APIs with an output string buffer:**</span></span>  
> <span data-ttu-id="603c3-163">Die übergebene Zeichenanzahl muss das NULL-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="603c3-163">The passed in character count must include the null.</span></span> <span data-ttu-id="603c3-164">Wenn der zurückgegebene Wert kleiner ist als die Zeichenanzahl, ist der Aufruf erfolgreich und der Wert ist die Anzahl der Zeichen *ohne* das nachgestellte NULL-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="603c3-164">If the returned value is less than the passed in character count the call has succeeded and the value is the number of characters *without* the trailing null.</span></span> <span data-ttu-id="603c3-165">Andernfalls ist die Anzahl die erforderliche Größe des Puffers *einschließlich* des NULL-Zeichens.</span><span class="sxs-lookup"><span data-stu-id="603c3-165">Otherwise the count is the required size of the buffer *including* the null character.</span></span>  
> - <span data-ttu-id="603c3-166">5 übergeben, 4 abrufen: Die Zeichenfolge ist 4 Zeichen lang und umfasst ein nachgestelltes NULL-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="603c3-166">Pass in 5, get 4: The string is 4 characters long with a trailing null.</span></span>
> - <span data-ttu-id="603c3-167">5 übergeben, 6 abrufen: Die Zeichenfolge ist 5 Zeichen lang und erfordert einen Puffer mit 6 Zeichen für das NULL-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="603c3-167">Pass in 5, get 6: The string is 5 characters long, need a 6 character buffer to hold the null.</span></span>  
> [<span data-ttu-id="603c3-168">Windows-Datentypen für Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="603c3-168">Windows Data Types for Strings</span></span>](/windows/desktop/Intl/windows-data-types-for-strings)

## <a name="boolean-parameters-and-fields"></a><span data-ttu-id="603c3-169">Boolesche Parameter und Felder</span><span class="sxs-lookup"><span data-stu-id="603c3-169">Boolean parameters and fields</span></span>

<span data-ttu-id="603c3-170">Bei booleschen Werten passieren leicht Fehler.</span><span class="sxs-lookup"><span data-stu-id="603c3-170">Booleans are easy to mess up.</span></span> <span data-ttu-id="603c3-171">Standardmäßig erfolgt für einen `bool`-Wert von .NET ein Marshalling in einen `BOOL`-Wert in Windows. Dort handelt es sich um einen 4 Byte langen Wert.</span><span class="sxs-lookup"><span data-stu-id="603c3-171">By default, a .NET `bool` is marshalled to a Windows `BOOL`, where it's a 4-byte value.</span></span> <span data-ttu-id="603c3-172">Die Typen `_Bool` und `bool` in C und C++ sind jedoch *Einzelbytewerte*.</span><span class="sxs-lookup"><span data-stu-id="603c3-172">However, the `_Bool`, and `bool` types in C and C++ are a *single* byte.</span></span> <span data-ttu-id="603c3-173">Dies kann zu Bugs führen, die sich nur sehr schwer auffinden lassen, da der halbe Rückgabewert verworfen wird, sich das Ergebnis aber nur *möglicherweise* ändert.</span><span class="sxs-lookup"><span data-stu-id="603c3-173">This can lead to hard to track down bugs as half the return value will be discarded, which will only *potentially* change the result.</span></span> <span data-ttu-id="603c3-174">Weitere Informationen zum Marshallen von `bool`-Werten aus .NET in `bool`-Typen in C oder C++ finden Sie in der Dokumentation zum [Anpassen des Marshallings von booleschen Feldern](customize-struct-marshalling.md#customizing-boolean-field-marshalling).</span><span class="sxs-lookup"><span data-stu-id="603c3-174">For more for information on marshalling .NET `bool` values to C or C++ `bool` types, see the documentation on [customizing boolean field marshalling](customize-struct-marshalling.md#customizing-boolean-field-marshalling).</span></span>

## <a name="guids"></a><span data-ttu-id="603c3-175">GUIDs</span><span class="sxs-lookup"><span data-stu-id="603c3-175">GUIDs</span></span>

<span data-ttu-id="603c3-176">GUIDs können direkt in Signaturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-176">GUIDs are usable directly in signatures.</span></span> <span data-ttu-id="603c3-177">Viele Windows-APIs akzeptieren `GUID&`-Typen wie `REFIID`.</span><span class="sxs-lookup"><span data-stu-id="603c3-177">Many Windows APIs take `GUID&` type aliases like `REFIID`.</span></span> <span data-ttu-id="603c3-178">Bei der Übergabe per Verweis können diese durch `ref` oder mit dem Attribut `[MarshalAs(UnmanagedType.LPStruct)]` übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-178">When passed by ref, they can either be passed by `ref` or with the `[MarshalAs(UnmanagedType.LPStruct)]` attribute.</span></span>

| <span data-ttu-id="603c3-179">GUID</span><span class="sxs-lookup"><span data-stu-id="603c3-179">GUID</span></span> | <span data-ttu-id="603c3-180">By-ref-GUID</span><span class="sxs-lookup"><span data-stu-id="603c3-180">By-ref GUID</span></span> |
|------|-------------|
| `KNOWNFOLDERID` | `REFKNOWNFOLDERID` |

<span data-ttu-id="603c3-181">**❌ VERWENDEN SIE `[MarshalAs(UnmanagedType.LPStruct)]` NICHT** für etwas anderes als `ref`-GUID-Parameter.</span><span class="sxs-lookup"><span data-stu-id="603c3-181">**❌ DO NOT** Use `[MarshalAs(UnmanagedType.LPStruct)]` for anything other than `ref` GUID parameters.</span></span>

## <a name="blittable-types"></a><span data-ttu-id="603c3-182">Für Blitting geeignete Typen</span><span class="sxs-lookup"><span data-stu-id="603c3-182">Blittable types</span></span>

<span data-ttu-id="603c3-183">Für Blitting geeignete Typen sind Typen, die in verwaltetem und nativem Code die gleiche Darstellung auf Bitebene aufweisen.</span><span class="sxs-lookup"><span data-stu-id="603c3-183">Blittable types are types that have the same bit-level representation in managed and native code.</span></span> <span data-ttu-id="603c3-184">Als solche müssen sie nicht in ein anderes Format konvertiert werden, um ein Marshalling in den und aus dem nativen Code zu ermöglichen. Da dies die Leistung verbessert, sind diese Typen zu bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="603c3-184">As such they do not need to be converted to another format to be marshalled to and from native code, and as this improves performance they should be preferred.</span></span>

<span data-ttu-id="603c3-185">**Für Blitting geeignete Typen**:</span><span class="sxs-lookup"><span data-stu-id="603c3-185">**Blittable types:**</span></span>

- <span data-ttu-id="603c3-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span><span class="sxs-lookup"><span data-stu-id="603c3-186">`byte`, `sbyte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `single`, `double`</span></span>
- <span data-ttu-id="603c3-187">Nicht geschachtelte eindimensionale Arrays aus für Blitting geeigneten Typen (z.B. `int[]`)</span><span class="sxs-lookup"><span data-stu-id="603c3-187">non-nested one-dimensional arrays of blittable types (for example, `int[]`)</span></span>
- <span data-ttu-id="603c3-188">Strukturen und Klassen mit festem Layout, die für Instanzfelder nur über für Blitting geeignete Typen verfügen</span><span class="sxs-lookup"><span data-stu-id="603c3-188">structs and classes with fixed layout that only have blittable value types for instance fields</span></span>
  - <span data-ttu-id="603c3-189">Ein festes Layout erfordert `[StructLayout(LayoutKind.Sequential)]` oder `[StructLayout(LayoutKind.Explicit)]`</span><span class="sxs-lookup"><span data-stu-id="603c3-189">fixed layout requires `[StructLayout(LayoutKind.Sequential)]` or `[StructLayout(LayoutKind.Explicit)]`</span></span>
  - <span data-ttu-id="603c3-190">Strukturen sind standardmäßig `LayoutKind.Sequential`, Klassen sind `LayoutKind.Auto`</span><span class="sxs-lookup"><span data-stu-id="603c3-190">structs are `LayoutKind.Sequential` by default, classes are `LayoutKind.Auto`</span></span>

<span data-ttu-id="603c3-191">**NICHT für Blitting geeignet**:</span><span class="sxs-lookup"><span data-stu-id="603c3-191">**NOT blittable:**</span></span>

- `bool`

<span data-ttu-id="603c3-192">**MANCHMAL für Blitting geeignet**:</span><span class="sxs-lookup"><span data-stu-id="603c3-192">**SOMETIMES blittable:**</span></span>

- <span data-ttu-id="603c3-193">`char`, `string`</span><span class="sxs-lookup"><span data-stu-id="603c3-193">`char`, `string`</span></span>

<span data-ttu-id="603c3-194">Wenn für Blitting geeignete Typen per Verweis übergeben werden, werden sie einfach vom Marshaller angeheftet, anstatt in einem temporären Puffer kopiert zu werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-194">When blittable types are passed by reference, they're simply pinned by the marshaller instead of being copied to an intermediate buffer.</span></span> <span data-ttu-id="603c3-195">(Klassen werden von Natur aus per Verweis übergeben, Strukturen werden per Verweis übergeben, wenn sie mit `ref` oder `out` verwendet werden.)</span><span class="sxs-lookup"><span data-stu-id="603c3-195">(Classes are inherently passed by reference, structs are passed by reference when used with `ref` or `out`.)</span></span>

<span data-ttu-id="603c3-196">`char` ist in einem eindimensionalen Array **oder** bei Verwendung in einem Typen für Blitting geeignet, der explizit mit `[StructLayout]` mit `CharSet = CharSet.Unicode` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="603c3-196">`char` is blittable in a one-dimensional array **or** if it's part of a type that contains it's explicitly marked with `[StructLayout]` with `CharSet = CharSet.Unicode`.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct UnicodeCharStruct
{
    public char c;
}
```

<span data-ttu-id="603c3-197">`string` ist für Blitting geeignet, wenn es nicht in einem anderen Typen enthalten ist und als Argument übergeben wird, das mit `[MarshalAs(UnmanagedType.LPWStr)]` gekennzeichnet ist oder in dem `CharSet = CharSet.Unicode` für `[DllImport]` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="603c3-197">`string` is blittable if it isn't contained in another type and it's being passed as an argument that is marked with `[MarshalAs(UnmanagedType.LPWStr)]` or the `[DllImport]` has `CharSet = CharSet.Unicode` set.</span></span>

<span data-ttu-id="603c3-198">Sie können feststellen, ob ein Typ für Blitting geeignet ist, indem Sie versuchen, ein angeheftetes `GCHandle` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="603c3-198">You can see if a type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="603c3-199">Wenn der Typ keine Zeichenfolge ist oder nicht als für Blitting geeignet betrachtet wird, löst `GCHandle.Alloc` eine `ArgumentException` aus.</span><span class="sxs-lookup"><span data-stu-id="603c3-199">If the type isn't a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="603c3-200">**✔️ LEGEN** Sie Ihre Strukturen nach Möglichkeit als für Blitting geeignet fest.</span><span class="sxs-lookup"><span data-stu-id="603c3-200">**✔️ DO** make your structures blittable when possible.</span></span>

<span data-ttu-id="603c3-201">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="603c3-201">For more information, see:</span></span>

- [<span data-ttu-id="603c3-202">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="603c3-202">Blittable and Non-Blittable Types</span></span>](../../framework/interop/blittable-and-non-blittable-types.md)  
- [<span data-ttu-id="603c3-203">Marshallen von Typen</span><span class="sxs-lookup"><span data-stu-id="603c3-203">Type Marshalling</span></span>](type-marshalling.md)

## <a name="keeping-managed-objects-alive"></a><span data-ttu-id="603c3-204">Beibehalten von verwalteten Objekten</span><span class="sxs-lookup"><span data-stu-id="603c3-204">Keeping managed objects alive</span></span>

<span data-ttu-id="603c3-205">`GC.KeepAlive()` stellt sicher, dass ein Objekt im Gültigkeitsbereich bleibt, bis die KeepAlive-Methode erreicht wird.</span><span class="sxs-lookup"><span data-stu-id="603c3-205">`GC.KeepAlive()` will ensure an object stays in scope until the KeepAlive method is hit.</span></span>

<span data-ttu-id="603c3-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) ermöglicht es dem Marshaller, ein Objekt während der Dauer eines P/Invoke beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="603c3-206">[`HandleRef`](xref:System.Runtime.InteropServices.HandleRef) allows the marshaller to keep an object alive for the duration of a P/Invoke.</span></span> <span data-ttu-id="603c3-207">Es kann statt `IntPtr` in Methodensignaturen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-207">It can be used instead of `IntPtr` in method signatures.</span></span> <span data-ttu-id="603c3-208">`SafeHandle` ersetzt diese Klasse und sollte stattdessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-208">`SafeHandle` effectively replaces this class and should be used instead.</span></span>

<span data-ttu-id="603c3-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) ermöglicht das Anheften eines verwalteten Objekts und Abrufen des nativen Zeigers auf das Objekt.</span><span class="sxs-lookup"><span data-stu-id="603c3-209">[`GCHandle`](xref:System.Runtime.InteropServices.GCHandle) allows pinning a managed object and getting the native pointer to it.</span></span> <span data-ttu-id="603c3-210">Das grundlegende Muster sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="603c3-210">The basic pattern is:</span></span>  

```csharp
GCHandle handle = GCHandle.Alloc(obj, GCHandleType.Pinned);
IntPtr ptr = handle.AddrOfPinnedObject();
handle.Free();
```

<span data-ttu-id="603c3-211">Anheften ist kein Standardvorgang für `GCHandle`.</span><span class="sxs-lookup"><span data-stu-id="603c3-211">Pinning isn't the default for `GCHandle`.</span></span> <span data-ttu-id="603c3-212">Das andere wichtige Muster sieht so aus: Ein Verweis wird über nativen Code an ein verwaltetes Objekt übergeben und, in der Regel über einen Rückruf, wieder zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="603c3-212">The other major pattern is for passing a reference to a managed object through native code and back to managed code, usually with a callback.</span></span> <span data-ttu-id="603c3-213">Hier sehen Sie das Muster:</span><span class="sxs-lookup"><span data-stu-id="603c3-213">Here is the pattern:</span></span>

```csharp
GCHandle handle = GCHandle.Alloc(obj);
SomeNativeEnumerator(callbackDelegate, GCHandle.ToIntPtr(handle));

// In the callback
GCHandle handle = GCHandle.FromIntPtr(param);
object managedObject = handle.Target;

// After the last callback
handle.Free();
```

<span data-ttu-id="603c3-214">Denken Sie daran, dass `GCHandle` explizit freigegeben werden muss, um Arbeitsspeicherverluste zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="603c3-214">Don't forget that `GCHandle` needs to be explicitly freed to avoid memory leaks.</span></span>

## <a name="common-windows-data-types"></a><span data-ttu-id="603c3-215">Allgemeine Windows-Datentypen</span><span class="sxs-lookup"><span data-stu-id="603c3-215">Common Windows data types</span></span>

<span data-ttu-id="603c3-216">Die folgende Liste enthält Datentypen, die in Windows-APIs häufig verwendet werden, sowie C#-Typen, die beim Aufrufen des Windows-Codes verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="603c3-216">Here is a list of data types commonly used in Windows APIs and which C# types to use when calling into the Windows code.</span></span>

<span data-ttu-id="603c3-217">Die folgenden Typen weisen trotz ihrer Namen die gleiche Größe wie 32- und 64-Bit-Typen für Windows auf.</span><span class="sxs-lookup"><span data-stu-id="603c3-217">The following types are the same size on 32-bit and 64-bit Windows, despite their names.</span></span>

| <span data-ttu-id="603c3-218">Breite</span><span class="sxs-lookup"><span data-stu-id="603c3-218">Width</span></span> | <span data-ttu-id="603c3-219">Windows</span><span class="sxs-lookup"><span data-stu-id="603c3-219">Windows</span></span>          | <span data-ttu-id="603c3-220">C (Windows)</span><span class="sxs-lookup"><span data-stu-id="603c3-220">C (Windows)</span></span>          | <span data-ttu-id="603c3-221">C#</span><span class="sxs-lookup"><span data-stu-id="603c3-221">C#</span></span>       | <span data-ttu-id="603c3-222">Alternative</span><span class="sxs-lookup"><span data-stu-id="603c3-222">Alternative</span></span>                          |
|:------|:-----------------|:---------------------|:---------|:-------------------------------------|
| <span data-ttu-id="603c3-223">32</span><span class="sxs-lookup"><span data-stu-id="603c3-223">32</span></span>    | `BOOL`           | `int`                | `int`    | `bool`                               |
| <span data-ttu-id="603c3-224">8</span><span class="sxs-lookup"><span data-stu-id="603c3-224">8</span></span>     | `BOOLEAN`        | `unsigned char`      | `byte`   | `[MarshalAs(UnmanagedType.U1)] bool` |
| <span data-ttu-id="603c3-225">8</span><span class="sxs-lookup"><span data-stu-id="603c3-225">8</span></span>     | `BYTE`           | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="603c3-226">8</span><span class="sxs-lookup"><span data-stu-id="603c3-226">8</span></span>     | `CHAR`           | `char`               | `sbyte`  |                                      |
| <span data-ttu-id="603c3-227">8</span><span class="sxs-lookup"><span data-stu-id="603c3-227">8</span></span>     | `UCHAR`          | `unsigned char`      | `byte`   |                                      |
| <span data-ttu-id="603c3-228">16</span><span class="sxs-lookup"><span data-stu-id="603c3-228">16</span></span>    | `SHORT`          | `short`              | `short`  |                                      |
| <span data-ttu-id="603c3-229">16</span><span class="sxs-lookup"><span data-stu-id="603c3-229">16</span></span>    | `CSHORT`         | `short`              | `short`  |                                      |
| <span data-ttu-id="603c3-230">16</span><span class="sxs-lookup"><span data-stu-id="603c3-230">16</span></span>    | `USHORT`         | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="603c3-231">16</span><span class="sxs-lookup"><span data-stu-id="603c3-231">16</span></span>    | `WORD`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="603c3-232">16</span><span class="sxs-lookup"><span data-stu-id="603c3-232">16</span></span>    | `ATOM`           | `unsigned short`     | `ushort` |                                      |
| <span data-ttu-id="603c3-233">32</span><span class="sxs-lookup"><span data-stu-id="603c3-233">32</span></span>    | `INT`            | `int`                | `int`    |                                      |
| <span data-ttu-id="603c3-234">32</span><span class="sxs-lookup"><span data-stu-id="603c3-234">32</span></span>    | `LONG`           | `long`               | `int`    |                                      |
| <span data-ttu-id="603c3-235">32</span><span class="sxs-lookup"><span data-stu-id="603c3-235">32</span></span>    | `ULONG`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="603c3-236">32</span><span class="sxs-lookup"><span data-stu-id="603c3-236">32</span></span>    | `DWORD`          | `unsigned long`      | `uint`   |                                      |
| <span data-ttu-id="603c3-237">64</span><span class="sxs-lookup"><span data-stu-id="603c3-237">64</span></span>    | `QWORD`          | `long long`          | `long`   |                                      |
| <span data-ttu-id="603c3-238">64</span><span class="sxs-lookup"><span data-stu-id="603c3-238">64</span></span>    | `LARGE_INTEGER`  | `long long`          | `long`   |                                      |
| <span data-ttu-id="603c3-239">64</span><span class="sxs-lookup"><span data-stu-id="603c3-239">64</span></span>    | `LONGLONG`       | `long long`          | `long`   |                                      |
| <span data-ttu-id="603c3-240">64</span><span class="sxs-lookup"><span data-stu-id="603c3-240">64</span></span>    | `ULONGLONG`      | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="603c3-241">64</span><span class="sxs-lookup"><span data-stu-id="603c3-241">64</span></span>    | `ULARGE_INTEGER` | `unsigned long long` | `ulong`  |                                      |
| <span data-ttu-id="603c3-242">32</span><span class="sxs-lookup"><span data-stu-id="603c3-242">32</span></span>    | `HRESULT`        | `long`               | `int`    |                                      |
| <span data-ttu-id="603c3-243">32</span><span class="sxs-lookup"><span data-stu-id="603c3-243">32</span></span>    | `NTSTATUS`       | `long`               | `int`    |                                      |


<span data-ttu-id="603c3-244">Die folgenden Typen sind Zeiger und entsprechen der Breite der Plattform.</span><span class="sxs-lookup"><span data-stu-id="603c3-244">The following types, being pointers, do follow the width of the platform.</span></span> <span data-ttu-id="603c3-245">Verwenden Sie `IntPtr`/`UIntPtr` für diese.</span><span class="sxs-lookup"><span data-stu-id="603c3-245">Use `IntPtr`/`UIntPtr` for these.</span></span>

| <span data-ttu-id="603c3-246">Signierte Zeigertypen (verwenden Sie `IntPtr`).</span><span class="sxs-lookup"><span data-stu-id="603c3-246">Signed Pointer Types (use `IntPtr`)</span></span> | <span data-ttu-id="603c3-247">Nicht signierte Zeigertypen (verwenden Sie `UIntPtr`).</span><span class="sxs-lookup"><span data-stu-id="603c3-247">Unsigned Pointer Types (use `UIntPtr`)</span></span> |
|:------------------------------------|:---------------------------------------|
| `HANDLE`                            | `WPARAM`                               |
| `HWND`                              | `UINT_PTR`                             |
| `HINSTANCE`                         | `ULONG_PTR`                            |
| `LPARAM`                            | `SIZE_T`                               |
| `LRESULT`                           |                                        |
| `LONG_PTR`                          |                                        |
| `INT_PTR`                           |                                        |

<span data-ttu-id="603c3-248">Für einen `PVOID`-Wert in Windows, der `void*` in C entspricht, kann ein Marshalling als `IntPtr` oder `UIntPtr` erfolgen. `void*` sollte jedoch nach Möglichkeit bevorzugt werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-248">A Windows `PVOID` which is a C `void*` can be marshaled as either `IntPtr` or `UIntPtr`, but prefer `void*` when possible.</span></span>

[<span data-ttu-id="603c3-249">Windows-Datentypen</span><span class="sxs-lookup"><span data-stu-id="603c3-249">Windows Data Types</span></span>](/windows/desktop/WinProg/windows-data-types)

[<span data-ttu-id="603c3-250">Datentypbereiche</span><span class="sxs-lookup"><span data-stu-id="603c3-250">Data Type Ranges</span></span>](/cpp/cpp/data-type-ranges)

## <a name="structs"></a><span data-ttu-id="603c3-251">Strukturen</span><span class="sxs-lookup"><span data-stu-id="603c3-251">Structs</span></span>

<span data-ttu-id="603c3-252">Verwaltete Strukturen werden im Stapel erstellt und erst dann entfernt, wenn die Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="603c3-252">Managed structs are created on the stack and aren't removed until the method returns.</span></span> <span data-ttu-id="603c3-253">Per Definition werden sie „angeheftet“ (also von der Garbage Collection nicht verschoben).</span><span class="sxs-lookup"><span data-stu-id="603c3-253">By definition then, they are "pinned" (it won't get moved by the GC).</span></span> <span data-ttu-id="603c3-254">Sie können auch einfach die Adresse in unsicheren Codeblöcken verwenden, wenn der native Code den Zeiger nicht über das Ende der aktuellen Methode hinaus verwendet.</span><span class="sxs-lookup"><span data-stu-id="603c3-254">You can also simply take the address in unsafe code blocks if native code won't use the pointer past the end of the current method.</span></span>

<span data-ttu-id="603c3-255">Für Blitting geeignete Strukturen sind wesentlich leistungsfähiger, da sie ganz einfach direkt von der Marshallingebene genutzt werden können.</span><span class="sxs-lookup"><span data-stu-id="603c3-255">Blittable structs are much more performant as they can simply be used directly by the marshalling layer.</span></span> <span data-ttu-id="603c3-256">Versuchen Sie, Typen blitfähig zu machen (vermeiden Sie z.B. `bool`).</span><span class="sxs-lookup"><span data-stu-id="603c3-256">Try to make structs blittable (for example, avoid `bool`).</span></span> <span data-ttu-id="603c3-257">Weitere Informationen finden Sie im Abschnitt [Für Blitting geeignete Typen](#blittable-types).</span><span class="sxs-lookup"><span data-stu-id="603c3-257">For more information, see the [Blittable Types](#blittable-types) section.</span></span>

<span data-ttu-id="603c3-258">*Wenn* eine Struktur für Blitting geeignet ist, verwenden Sie `sizeof()` statt `Marshal.SizeOf<MyStruct>()`, um eine bessere Leistung zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="603c3-258">*If* the struct is blittable, use `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for better performance.</span></span> <span data-ttu-id="603c3-259">Wie oben erwähnt, können Sie überprüfen, ob der Typ für Blitting geeignet ist, indem Sie versuchen, ein angeheftetes `GCHandle` zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="603c3-259">As mentioned above, you can validate that the type is blittable by attempting to create a pinned `GCHandle`.</span></span> <span data-ttu-id="603c3-260">Wenn der Typ keine Zeichenfolge ist oder nicht als für Blitting geeignet betrachtet wird, löst `GCHandle.Alloc` eine `ArgumentException` aus.</span><span class="sxs-lookup"><span data-stu-id="603c3-260">If the type is not a string or considered blittable, `GCHandle.Alloc` will throw an `ArgumentException`.</span></span>

<span data-ttu-id="603c3-261">Zeiger auf Strukturen in Definitionen müssen entweder von `ref` übergeben werden oder `unsafe` und `*` verwenden.</span><span class="sxs-lookup"><span data-stu-id="603c3-261">Pointers to structs in definitions must either be passed by `ref` or use `unsafe` and `*`.</span></span>

<span data-ttu-id="603c3-262">**✔️ PASSEN** Sie die verwaltete Struktur so eng wie möglich an die Form und die Namen an, die in der offiziellen Dokumentation zu Plattform oder im Header verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-262">**✔️ DO** match the managed struct as closely as possible to the shape and names that are used in the official platform documentation or header.</span></span>

<span data-ttu-id="603c3-263">**✔️ VERWENDEN** Sie `sizeof()` aus C# anstelle von `Marshal.SizeOf<MyStruct>()` für Strukturen, die für Blitting geeignet sind, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="603c3-263">**✔️ DO** use the C# `sizeof()` instead of `Marshal.SizeOf<MyStruct>()` for blittable structures to improve performance.</span></span>

<span data-ttu-id="603c3-264">Für ein Array wie `INT_PTR Reserved1[2]` muss ein Marshalling in zwei `IntPtr`-Felder durchgeführt werden: `Reserved1a` und `Reserved1b`.</span><span class="sxs-lookup"><span data-stu-id="603c3-264">An array like `INT_PTR Reserved1[2]` has to be marshaled to two `IntPtr` fields, `Reserved1a` and `Reserved1b`.</span></span> <span data-ttu-id="603c3-265">Wenn das native Array ein primitiver Typ ist, können wir das Schlüsselwort `fixed` verwenden, um es etwas übersichtlicher zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="603c3-265">When the native array is a primitive type, we can use the `fixed` keyword to write it a little more cleanly.</span></span> <span data-ttu-id="603c3-266">`SYSTEM_PROCESS_INFORMATION` sieht im nativen Header beispielsweise so aus:</span><span class="sxs-lookup"><span data-stu-id="603c3-266">For example, `SYSTEM_PROCESS_INFORMATION` looks like this in the native header:</span></span>

```c
typedef struct _SYSTEM_PROCESS_INFORMATION {
    ULONG NextEntryOffset;
    ULONG NumberOfThreads;
    BYTE Reserved1[48];
    UNICODE_STRING ImageName;
...
} SYSTEM_PROCESS_INFORMATION
```

<span data-ttu-id="603c3-267">In C# können wir es folgendermaßen schreiben:</span><span class="sxs-lookup"><span data-stu-id="603c3-267">In C#, we can write it like this:</span></span>

```csharp
internal unsafe struct SYSTEM_PROCESS_INFORMATION
{
    internal uint NextEntryOffset;
    internal uint NumberOfThreads;
    private fixed byte Reserved1[48];
    internal Interop.UNICODE_STRING ImageName;
    ...
}
```

<span data-ttu-id="603c3-268">Es gibt jedoch einige Besonderheiten bei festen Puffern.</span><span class="sxs-lookup"><span data-stu-id="603c3-268">However, there are some gotchas with fixed buffers.</span></span> <span data-ttu-id="603c3-269">Bei festen Puffer aus nicht für Blitting geeigneten Typen wird das Marshalling nicht ordnungsgemäß ausgeführt, daher muss das vorhandene Array auf mehrere einzelne Felder erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="603c3-269">Fixed buffers of non-blittable types won't be correctly marshalled, so the in-place array needs to be expanded out to multiple individual fields.</span></span> <span data-ttu-id="603c3-270">Darüber hinaus gilt für .NET Framework und .NET Core vor Version 3.0: Wenn eine Struktur, die ein festes Pufferfeld enthält, in einer nicht für Blitting geeigneten Struktur geschachtelt wird, erfolgt kein ordnungsgemäßes Marshalling des festen Pufferfelds zum nativen Code.</span><span class="sxs-lookup"><span data-stu-id="603c3-270">Additionally, in .NET Framework and .NET Core before 3.0, if a struct containing a fixed buffer field is nested within a non-blittable struct, the fixed buffer field won't be correctly marshalled to native code.</span></span>
