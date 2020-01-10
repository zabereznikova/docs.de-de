---
title: Marshalling von Typen – .NET
description: Erfahren Sie, wie .NET Ihre Strukturen in eine native Darstellung marshallt.
ms.date: 01/18/2019
ms.openlocfilehash: 91b8f3d6cb53fd7a0adea7ea9669e7459e81445f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706265"
---
# <a name="type-marshaling"></a><span data-ttu-id="c2e00-103">Marshalling von Typen</span><span class="sxs-lookup"><span data-stu-id="c2e00-103">Type marshaling</span></span>

<span data-ttu-id="c2e00-104">Das **Marshallen** bezeichnet den Vorgang zum Umwandeln von Typen, wenn diese zwischen verwaltetem und nativem Code wechseln müssen.</span><span class="sxs-lookup"><span data-stu-id="c2e00-104">**Marshaling** is the process of transforming types when they need to cross between managed and native code.</span></span>

<span data-ttu-id="c2e00-105">Das Marshallen ist erforderlich, weil sich die Typen in verwaltetem und nicht verwaltetem Code unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c2e00-105">Marshaling is needed because the types in the managed and unmanaged code are different.</span></span> <span data-ttu-id="c2e00-106">In verwaltetem Code haben Sie z. b. eine `String`, während Zeichen folgen in der nicht verwalteten Welt Unicode ("Wide"), nicht-Unicode, mit NULL endend, ASCII usw. sein können. Standardmäßig versucht das P/aufrufen-Subsystem, das richtige zu tun, basierend auf dem Standardverhalten, das in diesem Artikel beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="c2e00-106">In managed code, for instance, you have a `String`, while in the unmanaged world strings can be Unicode ("wide"), non-Unicode, null-terminated, ASCII, etc. By default, the P/Invoke subsystem tries to do the right thing based on the default behavior, described on this article.</span></span> <span data-ttu-id="c2e00-107">In Situationen, in denen Sie zusätzliche Kontrolle benötigen, können Sie das [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute)-Attribut verwenden, um anzugeben, welcher Typ auf der nicht verwalteten Seite erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="c2e00-107">However, for those situations where you need extra control, you can employ the [MarshalAs](xref:System.Runtime.InteropServices.MarshalAsAttribute) attribute to specify what is the expected type on the unmanaged side.</span></span> <span data-ttu-id="c2e00-108">Wenn Sie beispielsweise die Zeichenfolge als nicht mit NULL endende ANSI-Zeichenfolge senden möchten, können Sie dies folgendermaßen erreichen:</span><span class="sxs-lookup"><span data-stu-id="c2e00-108">For instance, if you want the string to be sent as a null-terminated ANSI string, you could do it like this:</span></span>

```csharp
[DllImport("somenativelibrary.dll")]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);
```

## <a name="default-rules-for-marshaling-common-types"></a><span data-ttu-id="c2e00-109">Standardregeln für das Marshallen von häufig verwendeten Typen</span><span class="sxs-lookup"><span data-stu-id="c2e00-109">Default rules for marshaling common types</span></span>

<span data-ttu-id="c2e00-110">Allgemein versucht die Runtime, beim Marshallen das „Richtige“ zu tun, damit Sie möglichst wenig Arbeitsaufwand haben.</span><span class="sxs-lookup"><span data-stu-id="c2e00-110">Generally, the runtime tries to do the "right thing" when marshaling to require the least amount of work from you.</span></span> <span data-ttu-id="c2e00-111">Die folgenden Tabellen beschreiben das standardmäßige Marshallen der einzelnen Typen bei Verwendung in einem Parameter oder Feld.</span><span class="sxs-lookup"><span data-stu-id="c2e00-111">The following tables describe how each type is marshaled by default when used in a parameter or field.</span></span> <span data-ttu-id="c2e00-112">Die Integer- und Zeichentypen mit fester Breite von C99/C++11 werden verwendet, um sicherzustellen, dass die folgende Tabelle für alle Plattformen richtig ist.</span><span class="sxs-lookup"><span data-stu-id="c2e00-112">The C99/C++11 fixed-width integer and character types are used to ensure that the following table is correct for all platforms.</span></span> <span data-ttu-id="c2e00-113">Sie können jeden nativen Typen verwenden, der die gleichen Anforderungen an Ausrichtung und Größe aufweist wie diese Typen.</span><span class="sxs-lookup"><span data-stu-id="c2e00-113">You can use any native type that has the same alignment and size requirements as these types.</span></span>

<span data-ttu-id="c2e00-114">Die erste Tabelle beschreibt die Zuordnungen für verschiedene Typen, für die das Marshallen für P/Invoke und Feldmarshalling gleich ist.</span><span class="sxs-lookup"><span data-stu-id="c2e00-114">This first table describes the mappings for various types for whom the marshaling is the same for both P/Invoke and field marshaling.</span></span>

| <span data-ttu-id="c2e00-115">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-115">.NET Type</span></span> | <span data-ttu-id="c2e00-116">Nativer Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-116">Native Type</span></span>  |
|-----------|-------------------------|
| `byte`    | `uint8_t`               |
| `sbyte`   | `int8_t`                |
| `short`   | `int16_t`               |
| `ushort`  | `uint16_t`              |
| `int`     | `int32_t`               |
| `uint`    | `uint32_t`              |
| `long`    | `int64_t`               |
| `ulong`   | `uint64_t`              |
| `char`    | <span data-ttu-id="c2e00-117">Entweder `char` oder `char16_t`, je nach `CharSet` von P/Invoke oder der Struktur.</span><span class="sxs-lookup"><span data-stu-id="c2e00-117">Either `char` or `char16_t` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="c2e00-118">Informationen dazu finden Sie in der [Dokumentation zum Zeichensatz](charset.md).</span><span class="sxs-lookup"><span data-stu-id="c2e00-118">See the [charset documentation](charset.md).</span></span> |
| `string`  | <span data-ttu-id="c2e00-119">Entweder `char*` oder `char16_t*`, je nach `CharSet` von P/Invoke oder der Struktur.</span><span class="sxs-lookup"><span data-stu-id="c2e00-119">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke or structure.</span></span> <span data-ttu-id="c2e00-120">Informationen dazu finden Sie in der [Dokumentation zum Zeichensatz](charset.md).</span><span class="sxs-lookup"><span data-stu-id="c2e00-120">See the [charset documentation](charset.md).</span></span> |
| `System.IntPtr` | `intptr_t`        |
| `System.UIntPtr` | `uintptr_t`      |
| <span data-ttu-id="c2e00-121">.NET-Zeigertypen (z.B.</span><span class="sxs-lookup"><span data-stu-id="c2e00-121">.NET Pointer types (ex.</span></span> <span data-ttu-id="c2e00-122">`void*`)</span><span class="sxs-lookup"><span data-stu-id="c2e00-122">`void*`)</span></span>  | `void*` |
| <span data-ttu-id="c2e00-123">Von `System.Runtime.InteropServices.SafeHandle` abgeleiteter Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-123">Type derived from `System.Runtime.InteropServices.SafeHandle`</span></span> | `void*` |
| <span data-ttu-id="c2e00-124">Von `System.Runtime.InteropServices.CriticalHandle` abgeleiteter Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-124">Type derived from `System.Runtime.InteropServices.CriticalHandle`</span></span> | `void*`          |
| `bool`    | <span data-ttu-id="c2e00-125">Win32-`BOOL`-Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-125">Win32 `BOOL` type</span></span>       |
| `decimal` | <span data-ttu-id="c2e00-126">COM-`DECIMAL`-Struktur</span><span class="sxs-lookup"><span data-stu-id="c2e00-126">COM `DECIMAL` struct</span></span> |
| <span data-ttu-id="c2e00-127">.NET-Delegat</span><span class="sxs-lookup"><span data-stu-id="c2e00-127">.NET Delegate</span></span> | <span data-ttu-id="c2e00-128">Nativer Funktionszeiger</span><span class="sxs-lookup"><span data-stu-id="c2e00-128">Native function pointer</span></span> |
| `System.DateTime` | <span data-ttu-id="c2e00-129">Win32-`DATE`-Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-129">Win32 `DATE` type</span></span> |
| `System.Guid` | <span data-ttu-id="c2e00-130">Win32-`GUID`-Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-130">Win32 `GUID` type</span></span> |

<span data-ttu-id="c2e00-131">Einige Marshallingkategorien weisen unterschiedliche Standardwerte auf, wenn Sie das Marshalling als Parameter oder Struktur durchführen.</span><span class="sxs-lookup"><span data-stu-id="c2e00-131">A few categories of marshaling have different defaults if you're marshaling as a parameter or structure.</span></span>

| <span data-ttu-id="c2e00-132">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-132">.NET Type</span></span> | <span data-ttu-id="c2e00-133">Nativer Typ (Parameter)</span><span class="sxs-lookup"><span data-stu-id="c2e00-133">Native Type (Parameter)</span></span> | <span data-ttu-id="c2e00-134">Nativer Typ (Feld)</span><span class="sxs-lookup"><span data-stu-id="c2e00-134">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| <span data-ttu-id="c2e00-135">.NET-Array</span><span class="sxs-lookup"><span data-stu-id="c2e00-135">.NET array</span></span> | <span data-ttu-id="c2e00-136">Ein Zeiger auf den Anfang eines Arrays aus nativen Darstellungen der Arrayelemente</span><span class="sxs-lookup"><span data-stu-id="c2e00-136">A pointer to the start of an array of native representations of the array elements.</span></span> | <span data-ttu-id="c2e00-137">Ohne `[MarshalAs]`-Attribut nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="c2e00-137">Not allowed without a `[MarshalAs]` attribute</span></span>|
| <span data-ttu-id="c2e00-138">Eine Klasse mit einem `LayoutKind`-Wert vom Typ `Sequential` oder `Explicit`</span><span class="sxs-lookup"><span data-stu-id="c2e00-138">A class with a `LayoutKind` of `Sequential` or `Explicit`</span></span> | <span data-ttu-id="c2e00-139">Ein Zeiger auf die native Darstellung der Klasse</span><span class="sxs-lookup"><span data-stu-id="c2e00-139">A pointer to the native representation of the class</span></span> | <span data-ttu-id="c2e00-140">Die native Darstellung der Klasse</span><span class="sxs-lookup"><span data-stu-id="c2e00-140">The native representation of the class</span></span> |

<span data-ttu-id="c2e00-141">Die folgende Tabelle enthält die standardmäßigen Marshallingregeln, die nur für Windows gelten.</span><span class="sxs-lookup"><span data-stu-id="c2e00-141">The following table includes the default marshaling rules that are Windows-only.</span></span> <span data-ttu-id="c2e00-142">Auf Nicht-Windows-Plattformen können Sie diese Typen nicht marshallen.</span><span class="sxs-lookup"><span data-stu-id="c2e00-142">On non-Windows platforms, you cannot marshal these types.</span></span>

| <span data-ttu-id="c2e00-143">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-143">.NET Type</span></span> | <span data-ttu-id="c2e00-144">Nativer Typ (Parameter)</span><span class="sxs-lookup"><span data-stu-id="c2e00-144">Native Type (Parameter)</span></span> | <span data-ttu-id="c2e00-145">Nativer Typ (Feld)</span><span class="sxs-lookup"><span data-stu-id="c2e00-145">Native Type (Field)</span></span> |
|-----------|-------------------------|---------------------|
| `object`  | `VARIANT`               | `IUnknown*`         |
| `System.Array` | <span data-ttu-id="c2e00-146">COM-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2e00-146">COM interface</span></span> | <span data-ttu-id="c2e00-147">Ohne `[MarshalAs]`-Attribut nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="c2e00-147">Not allowed without a `[MarshalAs]` attribute</span></span> |
| `System.ArgIterator` | `va_list` | <span data-ttu-id="c2e00-148">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="c2e00-148">Not allowed</span></span> |
| `System.Collections.IEnumerator` | `IEnumVARIANT*` | <span data-ttu-id="c2e00-149">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="c2e00-149">Not allowed</span></span> |
| `System.Collections.IEnumerable` | `IDispatch*` | <span data-ttu-id="c2e00-150">Nicht zulässig</span><span class="sxs-lookup"><span data-stu-id="c2e00-150">Not allowed</span></span> |
| `System.DateTimeOffset` | <span data-ttu-id="c2e00-151">`int64_t` – repräsentiert die Anzahl von Takten seit dem 1. Januar 1601 um Mitternacht</span><span class="sxs-lookup"><span data-stu-id="c2e00-151">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> || <span data-ttu-id="c2e00-152">`int64_t` – repräsentiert die Anzahl von Takten seit dem 1. Januar 1601 um Mitternacht</span><span class="sxs-lookup"><span data-stu-id="c2e00-152">`int64_t` representing the number of ticks since midnight on January 1, 1601</span></span> |

<span data-ttu-id="c2e00-153">Für einige Typen ist das Marshalling nur als Parameter möglich, nicht als Felder.</span><span class="sxs-lookup"><span data-stu-id="c2e00-153">Some types can only be marshaled as parameters and not as fields.</span></span> <span data-ttu-id="c2e00-154">Diese Typen werden in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c2e00-154">These types are listed in the following table:</span></span>

| <span data-ttu-id="c2e00-155">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-155">.NET Type</span></span> | <span data-ttu-id="c2e00-156">Nativer Typ (nur Parameter)</span><span class="sxs-lookup"><span data-stu-id="c2e00-156">Native Type (Parameter Only)</span></span> |
|-----------|------------------------------|
| `System.Text.StringBuilder` | <span data-ttu-id="c2e00-157">Entweder `char*` oder `char16_t*`, je nach `CharSet` von P/Invoke.</span><span class="sxs-lookup"><span data-stu-id="c2e00-157">Either `char*` or `char16_t*` depending on the `CharSet` of the P/Invoke.</span></span>  <span data-ttu-id="c2e00-158">Informationen dazu finden Sie in der [Dokumentation zum Zeichensatz](charset.md).</span><span class="sxs-lookup"><span data-stu-id="c2e00-158">See the [charset documentation](charset.md).</span></span> |
| `System.ArgIterator` | <span data-ttu-id="c2e00-159">`va_list` (nur auf Windows x86/x64/arm64)</span><span class="sxs-lookup"><span data-stu-id="c2e00-159">`va_list` (on Windows x86/x64/arm64 only)</span></span> |
| `System.Runtime.InteropServices.ArrayWithOffset` | `void*` |
| `System.Runtime.InteropServices.HandleRef` | `void*` |

<span data-ttu-id="c2e00-160">Wenn diese Standardwerte nicht exakt Ihren Vorstellungen entsprechen, können Sie angeben, auf welche Weise das Marshalling von Parametern durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="c2e00-160">If these defaults don't do exactly what you want, you can customize how parameters are marshaled.</span></span> <span data-ttu-id="c2e00-161">Im Artikel [Marshallen von Parametern](customize-parameter-marshaling.md) erfahren Sie, wie Sie das Marshalling verschiedener Parametertypen anpassen.</span><span class="sxs-lookup"><span data-stu-id="c2e00-161">The [parameter marshaling](customize-parameter-marshaling.md) article walks you through how to customize how different parameter types are marshaled.</span></span>

## <a name="default-marshaling-in-com-scenarios"></a><span data-ttu-id="c2e00-162">Standardmarshalling in COM-Szenarien</span><span class="sxs-lookup"><span data-stu-id="c2e00-162">Default marshaling in COM scenarios</span></span>

<span data-ttu-id="c2e00-163">Wenn Sie Methoden in COM-Objekten in .NET aufrufen, ändert die .NET-Runtime die standardmäßigen Marshallingregeln, um der allgemeinen COM-Semantik zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c2e00-163">When you are calling methods on COM objects in .NET, the .NET runtime changes the default marshaling rules to match common COM semantics.</span></span> <span data-ttu-id="c2e00-164">In der folgenden Tabelle werden die Regeln aufgeführt, die die .NET-Runtime in COM-Szenarien verwendet:</span><span class="sxs-lookup"><span data-stu-id="c2e00-164">The following table lists the rules that .NET runtimes uses in COM scenarios:</span></span>

| <span data-ttu-id="c2e00-165">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="c2e00-165">.NET Type</span></span> | <span data-ttu-id="c2e00-166">Nativer Typ (COM-Methodenaufrufe)</span><span class="sxs-lookup"><span data-stu-id="c2e00-166">Native Type (COM method calls)</span></span> |
|-----------|--------------------------------|
| `bool`    | `VARIANT_BOOL`                 |
| `StringBuilder` | `LPWSTR`                 |
| `string`  | `BSTR`                         |
| <span data-ttu-id="c2e00-167">Delegattypen</span><span class="sxs-lookup"><span data-stu-id="c2e00-167">Delegate types</span></span> | <span data-ttu-id="c2e00-168">`_Delegate*` in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2e00-168">`_Delegate*` in .NET Framework.</span></span> <span data-ttu-id="c2e00-169">In .NET Core nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="c2e00-169">Disallowed in .NET Core.</span></span> |
| `System.Drawing.Color` | `OLECOLOR`        |
| <span data-ttu-id="c2e00-170">.NET-Array</span><span class="sxs-lookup"><span data-stu-id="c2e00-170">.NET array</span></span> | `SAFEARRAY`                   |
| `string[]` | <span data-ttu-id="c2e00-171">`SAFEARRAY` aus `BSTR`s</span><span class="sxs-lookup"><span data-stu-id="c2e00-171">`SAFEARRAY` of `BSTR`s</span></span>        |

## <a name="marshaling-classes-and-structs"></a><span data-ttu-id="c2e00-172">Marshallen von Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="c2e00-172">Marshaling classes and structs</span></span>

<span data-ttu-id="c2e00-173">Ein weiterer Aspekt des Marshallens von Typen ist die Übergabe einer Struktur an eine nicht verwaltete Methode.</span><span class="sxs-lookup"><span data-stu-id="c2e00-173">Another aspect of type marshaling is how to pass in a struct to an unmanaged method.</span></span> <span data-ttu-id="c2e00-174">Einige der nicht verwalteten Methoden erfordern beispielsweise eine Struktur als Parameter.</span><span class="sxs-lookup"><span data-stu-id="c2e00-174">For instance, some of the unmanaged methods require a struct as a parameter.</span></span> <span data-ttu-id="c2e00-175">In diesen Fällen müssen Sie eine entsprechende Struktur oder eine Klasse im verwalteten Bereich erstellen, um sie als Parameter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2e00-175">In these cases, you need to create a corresponding struct or a class in managed part of the world to use it as a parameter.</span></span> <span data-ttu-id="c2e00-176">Allerdings reicht das Definieren der Klasse nicht aus, Sie müssen dem Marshaller außerdem mitteilen, wie Felder in der Klasse der nicht verwalteten Struktur zuzuordnen sind.</span><span class="sxs-lookup"><span data-stu-id="c2e00-176">However, just defining the class isn't enough, you also need to instruct the marshaler how to map fields in the class to the unmanaged struct.</span></span> <span data-ttu-id="c2e00-177">Hierbei ist das `StructLayout`-Attribut nützlich.</span><span class="sxs-lookup"><span data-stu-id="c2e00-177">Here the `StructLayout` attribute becomes useful.</span></span>

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}
```

<span data-ttu-id="c2e00-178">Der obige Code zeigt ein einfaches Beispiel für einen Aufruf in der `GetSystemTime()`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="c2e00-178">The previous code shows a simple example of calling into `GetSystemTime()` function.</span></span> <span data-ttu-id="c2e00-179">Der interessante Teil befindet sich in Zeile 4.</span><span class="sxs-lookup"><span data-stu-id="c2e00-179">The interesting bit is on line 4.</span></span> <span data-ttu-id="c2e00-180">Das Attribut gibt an, dass die Felder der Klasse sequenziell der Struktur auf der anderen (nicht verwalteten) Seite zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c2e00-180">The attribute specifies that the fields of the class should be mapped sequentially to the struct on the other (unmanaged) side.</span></span> <span data-ttu-id="c2e00-181">Dies bedeutet, dass die Benennung der Felder nicht wichtig ist, sondern nur deren Reihenfolge, da diese der nicht verwalteten Struktur entsprechen muss, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c2e00-181">This means that the naming of the fields isn't important, only their order is important, as it needs to correspond to the unmanaged struct, shown in the following example:</span></span>

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME;
```

<span data-ttu-id="c2e00-182">Manchmal führt das standardmäßige Marshalling für Ihre Struktur nicht zum gewünschten Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="c2e00-182">Sometimes the default marshaling for your structure doesn't do what you need.</span></span> <span data-ttu-id="c2e00-183">Im Artikel [Anpassen des Marshallens für Strukturen](./customize-struct-marshaling.md) erfahren Sie, wie Sie das Marshalling für Ihre Struktur anpassen.</span><span class="sxs-lookup"><span data-stu-id="c2e00-183">The [Customizing structure marshaling](./customize-struct-marshaling.md) article teaches you how to customize how your structure is marshaled.</span></span>
