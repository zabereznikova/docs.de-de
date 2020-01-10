---
title: Anpassen des Marshallings für Strukturen – .NET
description: Erfahren Sie, wie Sie anpassen können, wie .NET Ihre Strukturen in eine native Darstellung marshallt.
ms.date: 01/18/2019
dev_langs:
- csharp
- cpp
ms.openlocfilehash: e69746e03cefa2444d4c34b582730824ff357858
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706347"
---
# <a name="customizing-structure-marshaling"></a><span data-ttu-id="3bd93-103">Anpassen des Marshallings für Strukturen</span><span class="sxs-lookup"><span data-stu-id="3bd93-103">Customizing structure marshaling</span></span>

<span data-ttu-id="3bd93-104">Manchmal entsprechen die Standardregeln für das Marshallen nicht genau Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-104">Sometimes the default marshaling rules for structures aren't exactly what you need.</span></span> <span data-ttu-id="3bd93-105">Die .NET-Runtimes bieten einige Erweiterungspunkte, mit denen Sie das Layout der Struktur und das Marshallen von Feldern anpassen können.</span><span class="sxs-lookup"><span data-stu-id="3bd93-105">The .NET runtimes provide a few extension points for you to customize your structure's layout and how fields are marshaled.</span></span>

## <a name="customizing-structure-layout"></a><span data-ttu-id="3bd93-106">Anpassen des Strukturlayouts</span><span class="sxs-lookup"><span data-stu-id="3bd93-106">Customizing structure layout</span></span>

<span data-ttu-id="3bd93-107">.NET bietet das <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>-Attribut und die <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType>-Enumeration, damit Sie anpassen können, wie Felder im Arbeitsspeicher abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="3bd93-107">.NET provides the <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> attribute and the <xref:System.Runtime.InteropServices.LayoutKind?displayProperty=nameWithType> enumeration to allow you to customize how fields are placed in memory.</span></span> <span data-ttu-id="3bd93-108">Die folgende Anleitung hilft Ihnen dabei, gängige Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3bd93-108">The following guidance will help you avoid common issues.</span></span>

<span data-ttu-id="3bd93-109">**✔️ ERWÄGEN SIE** nach Möglichkeit die Verwendung von `LayoutKind.Sequential`.</span><span class="sxs-lookup"><span data-stu-id="3bd93-109">**✔️ CONSIDER** using `LayoutKind.Sequential` whenever possible.</span></span>

<span data-ttu-id="3bd93-110">**✔️ VERWENDEN SIE**`LayoutKind.Explicit` beim Marshallen nur dann, wenn die native Struktur ebenfalls ein explizites Layout aufweist, beispielsweise eine Union.</span><span class="sxs-lookup"><span data-stu-id="3bd93-110">**✔️ DO** only use `LayoutKind.Explicit` in marshaling when your native struct is also has an explicit layout, such as a union.</span></span>

<span data-ttu-id="3bd93-111">**❌ vermeiden** Sie die Verwendung von `LayoutKind.Explicit` beim Marshalling von Strukturen auf nicht-Windows-Plattformen, wenn Sie Laufzeiten vor .net Core 3,0 ausrichten müssen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-111">**❌ AVOID** using `LayoutKind.Explicit` when marshaling structures on non-Windows platforms if you need to target runtimes before .NET Core 3.0.</span></span> <span data-ttu-id="3bd93-112">Die .net Core-Runtime vor 3,0 unterstützt nicht das Übergeben von expliziten Strukturen nach Wert an systemeigene Funktionen auf Intel-oder 64 AMD-nicht-Windows-Systemen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-112">The .NET Core runtime before 3.0 doesn't support passing explicit structures by value to native functions on Intel or AMD 64-bit non-Windows systems.</span></span> <span data-ttu-id="3bd93-113">Die Runtime unterstützt jedoch auf allen Plattformen die Übergabe expliziter Strukturen per Verweis.</span><span class="sxs-lookup"><span data-stu-id="3bd93-113">However, the runtime supports passing explicit structures by reference on all platforms.</span></span>

## <a name="customizing-boolean-field-marshaling"></a><span data-ttu-id="3bd93-114">Anpassen des Marshallens boolescher Felder</span><span class="sxs-lookup"><span data-stu-id="3bd93-114">Customizing boolean field marshaling</span></span>

<span data-ttu-id="3bd93-115">Für nativen Code gibt es viele verschiedene boolesche Darstellungen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-115">Native code has many different boolean representations.</span></span> <span data-ttu-id="3bd93-116">Allein unter Windows gibt es drei Möglichkeiten zur Darstellung boolescher Werte.</span><span class="sxs-lookup"><span data-stu-id="3bd93-116">On Windows alone, there are three ways to represent boolean values.</span></span> <span data-ttu-id="3bd93-117">Der Runtime ist die native Definition Ihrer Struktur nicht bekannt, daher kann sie allenfalls raten, wie Ihre booleschen Werte gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-117">The runtime doesn't know the native definition of your structure, so the best it can do is make a guess on how to marshal your boolean values.</span></span> <span data-ttu-id="3bd93-118">Die .NET-Runtime bietet eine Möglichkeit anzugeben, wie Ihr boolesches Feld gemarshallt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3bd93-118">The .NET runtime provides a way to indicate how to marshal your boolean field.</span></span> <span data-ttu-id="3bd93-119">Die folgenden Beispiele zeigen, wie .NET `bool` in andere native boolesche Typen gemarshallt wird.</span><span class="sxs-lookup"><span data-stu-id="3bd93-119">The following examples show how to marshal .NET `bool` to different native boolean types.</span></span>

<span data-ttu-id="3bd93-120">Boolesche Werte werden standardmäßig als nativer Win32-[`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL)-Wert mit 4 Byte gemarshallt, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="3bd93-120">Boolean values default to marshaling as a native 4-byte Win32 [`BOOL`](/windows/desktop/winprog/windows-data-types#BOOL) value as shown in the following example:</span></span>

```csharp
public struct WinBool
{
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

<span data-ttu-id="3bd93-121">Wenn Sie eine explizite Festlegung treffen möchten, können Sie mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType> dasselbe Verhalten wie oben erzielen:</span><span class="sxs-lookup"><span data-stu-id="3bd93-121">If you want to be explicit, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.Bool?displayProperty=nameWithType> value to get the same behavior as above:</span></span>

```csharp
public struct WinBool
{
    [MarshalAs(UnmanagedType.Bool)]
    public bool b;
}
```

```cpp
struct WinBool
{
    public BOOL b;
};
```

<span data-ttu-id="3bd93-122">Mit den unten gezeigten Werten `UnmanagedType.U1` oder `UnmanagedType.I1` können Sie die Runtime anweisen, das `b`-Feld als nativen 1-Byte-`bool`-Typ zu marshallen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-122">Using the `UnmanagedType.U1` or `UnmanagedType.I1` values below, you can tell the runtime to marshal the `b` field as a 1-byte native `bool` type.</span></span>

```csharp
public struct CBool
{
    [MarshalAs(UnmanagedType.U1)]
    public bool b;
}
```

```cpp
struct CBool
{
    public bool b;
};
```

<span data-ttu-id="3bd93-123">Unter Windows können Sie die Runtime mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType> anweisen, Ihren booleschen Wert in einen 2-Byte-`VARIANT_BOOL`-Wert zu marshallen:</span><span class="sxs-lookup"><span data-stu-id="3bd93-123">On Windows, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.VariantBool?displayProperty=nameWithType> value to tell the runtime to marshal your boolean value to a 2-byte `VARIANT_BOOL` value:</span></span>

```csharp
public struct VariantBool
{
    [MarshalAs(UnmanagedType.VariantBool)]
    public bool b;
}
```

```cpp
struct VariantBool
{
    public VARIANT_BOOL b;
};
```

> [!NOTE]
> <span data-ttu-id="3bd93-124">`VARIANT_BOOL` unterscheidet sich von den meisten booleschen Typen insofern als dass `VARIANT_TRUE = -1` und `VARIANT_FALSE = 0` sind.</span><span class="sxs-lookup"><span data-stu-id="3bd93-124">`VARIANT_BOOL` is different than most bool types in that `VARIANT_TRUE = -1` and `VARIANT_FALSE = 0`.</span></span> <span data-ttu-id="3bd93-125">Darüber hinaus werden alle Werte als FALSE betrachtet, die nicht gleich `VARIANT_TRUE` sind.</span><span class="sxs-lookup"><span data-stu-id="3bd93-125">Additionally, all values that aren't equal to `VARIANT_TRUE` are considered false.</span></span>

## <a name="customizing-array-field-marshaling"></a><span data-ttu-id="3bd93-126">Anpassen des Marshallens von Arrayfeldern</span><span class="sxs-lookup"><span data-stu-id="3bd93-126">Customizing array field marshaling</span></span>

<span data-ttu-id="3bd93-127">.NET umfasst auch einige Möglichkeiten zum Anpassen des Marshallens von Arrays.</span><span class="sxs-lookup"><span data-stu-id="3bd93-127">.NET also includes a few ways to customize array marshaling.</span></span>

<span data-ttu-id="3bd93-128">In der Standardeinstellung marshallt .NET Arrays als Zeiger auf eine zusammenhängende Liste der Elemente:</span><span class="sxs-lookup"><span data-stu-id="3bd93-128">By default, .NET marshals arrays as a pointer to a contiguous list of the elements:</span></span>

```csharp
public struct DefaultArray
{
    public int[] values;
}
```

```cpp
struct DefaultArray
{
    int* values;
};
```

<span data-ttu-id="3bd93-129">Wenn Sie mit COM-APIs arbeiten, müssen Sie Arrays möglicherweise als `SAFEARRAY*`-Objekte marshallen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-129">If you're interfacing with COM APIs, you may have to marshal arrays as `SAFEARRAY*` objects.</span></span> <span data-ttu-id="3bd93-130">Mit den Werten <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> können Sie die Runtime anweisen, ein Array als `SAFEARRAY*` zu marshallen:</span><span class="sxs-lookup"><span data-stu-id="3bd93-130">You can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> and the <xref:System.Runtime.InteropServices.UnmanagedType.SafeArray?displayProperty=nameWithType> value to tell the runtime to marshal an array as a `SAFEARRAY*`:</span></span>

```csharp
public struct SafeArrayExample
{
    [MarshalAs(UnmanagedType.SafeArray)]
    public int[] values;
}
```

```cpp
struct SafeArrayExample
{
    SAFEARRAY* values;
};
```

<span data-ttu-id="3bd93-131">Wenn Sie anpassen möchten, welche Art von Element in `SAFEARRAY` enthalten ist, können Sie mithilfe der Felder <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> und <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> den genauen Elementtyp von `SAFEARRAY` anpassen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-131">If you need to customize what type of element is in the `SAFEARRAY`, then you can use the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType?displayProperty=nameWithType> fields to customize the exact element type of the `SAFEARRAY`.</span></span>

<span data-ttu-id="3bd93-132">Wenn Sie das Array direkt marshallen möchten, können Sie den Marshaller über den Wert <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> entsprechend anweisen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-132">If you need to marshal the array in-place, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.ByValArray?displayProperty=nameWithType> value to tell the marshaler to marshal the array in-place.</span></span> <span data-ttu-id="3bd93-133">Wenn Sie diese Art des Marshallens einsetzen, müssen Sie dem Feld <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> auch einen Wert für die Anzahl von Elementen im Array angeben, damit die Runtime die richtige Speichermenge für die Struktur zuweisen kann.</span><span class="sxs-lookup"><span data-stu-id="3bd93-133">When you're using this marshaling, you also must supply a value to the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> field  for the number of elements in the array so the runtime can correctly allocate space for the structure.</span></span>

```csharp
public struct InPlaceArray
{
    [MarshalAs(UnmanagedType.ByValArray, SizeConst = 4)]
    public int[] values;
}
```

```cpp
struct InPlaceArray
{
    int values[4];
};
```

> [!NOTE]
> <span data-ttu-id="3bd93-134">.NET unterstützt nicht das Marshallen eines Arrayfelds mit variabler Länge als flexibles C99-Arraymember.</span><span class="sxs-lookup"><span data-stu-id="3bd93-134">.NET doesn't support marshaling a variable length array field as a C99 Flexible Array Member.</span></span>

## <a name="customizing-string-field-marshaling"></a><span data-ttu-id="3bd93-135">Anpassen des Marshallens von Zeichenfolgenfeldern</span><span class="sxs-lookup"><span data-stu-id="3bd93-135">Customizing string field marshaling</span></span>

<span data-ttu-id="3bd93-136">.NET bietet auch eine Vielzahl von Anpassungen für das Marshallen von Zeichenfolgenfeldern.</span><span class="sxs-lookup"><span data-stu-id="3bd93-136">.NET also provides a wide variety of customizations for marshaling string fields.</span></span>

<span data-ttu-id="3bd93-137">In der Standardeinstellung marshallt .NET eine Zeichenfolge als Zeiger auf eine mit NULL beendete Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="3bd93-137">By default, .NET marshals a string as a pointer to a null-terminated string.</span></span> <span data-ttu-id="3bd93-138">Die Codierung hängt von dem Wert des Felds <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> im <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType> ab.</span><span class="sxs-lookup"><span data-stu-id="3bd93-138">The encoding depends on the value of the <xref:System.Runtime.InteropServices.StructLayoutAttribute.CharSet?displayProperty=nameWithType> field in the <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3bd93-139">Wenn kein Attribut angegeben ist, wird als Codierung standardmäßig die ANSI-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3bd93-139">If no attribute is specified, the encoding defaults to an ANSI encoding.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char* str;
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

<span data-ttu-id="3bd93-140">Wenn Sie unterschiedliche Codierungen für verschiedene Felder verwenden oder Ihre Strukturdefinition einfach expliziter gestalten möchten, können Sie die Werte <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> oder <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> für ein <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType>-Attribut verwenden.</span><span class="sxs-lookup"><span data-stu-id="3bd93-140">If you need to use different encodings for different fields or just prefer to be more explicit in your struct definition, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.LPStr?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.UnmanagedType.LPWStr?displayProperty=nameWithType> values on a <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=nameWithType> attribute.</span></span>

```csharp
public struct AnsiString
{
    [MarshalAs(UnmanagedType.LPStr)]
    public string str;
}
```

```cpp
struct AnsiString
{
    char* str;
};
```

```csharp
public struct UnicodeString
{
    [MarshalAs(UnmanagedType.LPWStr)]
    public string str;
}
```

```cpp
struct UnicodeString
{
    char16_t* str; // Could also be wchar_t* on Windows.
};
```

<span data-ttu-id="3bd93-141">Wenn Sie Ihre Zeichenfolgen mit der UTF-8-Codierung marshallen möchten, können Sie den Wert <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> in Ihrem <xref:System.Runtime.InteropServices.MarshalAsAttribute> verwenden.</span><span class="sxs-lookup"><span data-stu-id="3bd93-141">If you want to marshal your strings using the UTF-8 encoding, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> value in your <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>

```csharp
public struct UTF8String
{
    [MarshalAs(UnmanagedType.LPUTF8Str)]
    public string str;
}
```

```cpp
struct UTF8String
{
    char* str;
};
```

> [!NOTE]
> <span data-ttu-id="3bd93-142">Für die Verwendung von <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> ist entweder .NET Framework 4.7 (oder höher) oder .NET Core 1.1 (oder höher) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3bd93-142">Using <xref:System.Runtime.InteropServices.UnmanagedType.LPUTF8Str?displayProperty=nameWithType> requires either .NET Framework 4.7 (or later versions) or .NET Core 1.1 (or later versions).</span></span> <span data-ttu-id="3bd93-143">In .NET Standard 2.0 ist diese Option nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3bd93-143">It isn't available in .NET Standard 2.0.</span></span>

<span data-ttu-id="3bd93-144">Wenn Sie mit COM-APIs arbeiten, müssen Sie eine Zeichenfolge möglicherweise als `BSTR` marshallen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-144">If you're working with COM APIs, you may need to marshal a string as a `BSTR`.</span></span> <span data-ttu-id="3bd93-145">Mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> können Sie eine Zeichenfolge als `BSTR` marshallen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-145">Using the <xref:System.Runtime.InteropServices.UnmanagedType.BStr?displayProperty=nameWithType> value, you can marshal a string as a `BSTR`.</span></span>

```csharp
public struct BString
{
    [MarshalAs(UnmanagedType.BStr)]
    public string str;
}
```

```cpp
struct BString
{
    BSTR str;
};
```

<span data-ttu-id="3bd93-146">Wenn Sie eine WinRT-basierte API verwenden, müssen Sie eine Zeichenfolge möglicherweise als `HSTRING` marshallen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-146">When using a WinRT-based API, you may need to marshal a string as an `HSTRING`.</span></span>  <span data-ttu-id="3bd93-147">Mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> können Sie eine Zeichenfolge als `HSTRING` marshallen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-147">Using the <xref:System.Runtime.InteropServices.UnmanagedType.HString?displayProperty=nameWithType> value, you can marshal a string as a `HSTRING`.</span></span>

```csharp
public struct HString
{
    [MarshalAs(UnmanagedType.HString)]
    public string str;
}
```

```cpp
struct BString
{
    HSTRING str;
};
```

<span data-ttu-id="3bd93-148">Wenn Ihre API verlangt, dass die Zeichenfolge direkt in der Struktur übergeben werden muss, können Sie den Wert <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType> verwenden.</span><span class="sxs-lookup"><span data-stu-id="3bd93-148">If your API requires you to pass the string in-place in the structure, you can use the <xref:System.Runtime.InteropServices.UnmanagedType.ByValTStr?displayProperty=nameWithType> value.</span></span> <span data-ttu-id="3bd93-149">Beachten Sie, dass die Codierung für eine Zeichenfolge, die mit `ByValTStr` gemarshallt wird, durch das Attribut `CharSet` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="3bd93-149">Do note that the encoding for a string marshaled by `ByValTStr` is determined from the `CharSet` attribute.</span></span> <span data-ttu-id="3bd93-150">Darüber hinaus muss über das Feld <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> eine Zeichenfolgenlänge übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="3bd93-150">Additionally, it requires that a string length is passed by the <xref:System.Runtime.InteropServices.MarshalAsAttribute.SizeConst?displayProperty=nameWithType> field.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char str[4];
};
```

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
public struct DefaultString
{
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 4)]
    public string str;
}
```

```cpp
struct DefaultString
{
    char16_t str[4]; // Could also be wchar_t[4] on Windows.
};
```

## <a name="customizing-decimal-field-marshaling"></a><span data-ttu-id="3bd93-151">Anpassen des Marshallens von Dezimalfeldern</span><span class="sxs-lookup"><span data-stu-id="3bd93-151">Customizing decimal field marshaling</span></span>

<span data-ttu-id="3bd93-152">Wenn Sie Windows verwenden, treffen Sie möglicherweise auf einige APIs, die die native [`CY`- oder `CURRENCY`](/windows/win32/api/wtypes/ns-wtypes-cy~r1)-Struktur verwenden.</span><span class="sxs-lookup"><span data-stu-id="3bd93-152">If you're working on Windows, you might encounter some APIs that use the native [`CY` or `CURRENCY`](/windows/win32/api/wtypes/ns-wtypes-cy~r1) structure.</span></span> <span data-ttu-id="3bd93-153">Standardmäßig marshallt der .NET-`decimal`-Typ in die native [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1)-Struktur.</span><span class="sxs-lookup"><span data-stu-id="3bd93-153">By default, the .NET `decimal` type marshals to the native [`DECIMAL`](/windows/win32/api/wtypes/ns-wtypes-decimal~r1) structure.</span></span> <span data-ttu-id="3bd93-154">Sie können jedoch ein <xref:System.Runtime.InteropServices.MarshalAsAttribute> mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType> verwenden, um den Marshaller zur Konvertierung eines `decimal`-Werts in einen nativen `CY`-Wert anzuweisen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-154">However, you can use a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.Currency?displayProperty=nameWithType> value to instruct the marshaler to convert a `decimal` value to a native `CY` value.</span></span>

```csharp
public struct Currency
{
    [MarshalAs(UnmanagedType.Currency)]
    public decimal dec;
}
```

```cpp
struct Currency
{
    CY dec;
};
```

## <a name="marshaling-systemobjects"></a><span data-ttu-id="3bd93-155">Marshalling von `System.Object`</span><span class="sxs-lookup"><span data-stu-id="3bd93-155">Marshaling `System.Object`s</span></span>

<span data-ttu-id="3bd93-156">Unter Windows können Sie Felder vom Typ `object` in nativen Code marshallen.</span><span class="sxs-lookup"><span data-stu-id="3bd93-156">On Windows, you can marshal `object`-typed fields to native code.</span></span> <span data-ttu-id="3bd93-157">Diese Felder können in einen der drei folgenden Typen gemarshallt werden:</span><span class="sxs-lookup"><span data-stu-id="3bd93-157">You can marshal these fields to one of three types:</span></span>

- [`VARIANT`](/windows/win32/api/oaidl/ns-oaidl-variant)
- [`IUnknown*`](/windows/desktop/api/unknwn/nn-unknwn-iunknown)
- [`IDispatch*`](/windows/desktop/api/oaidl/nn-oaidl-idispatch)

<span data-ttu-id="3bd93-158">Standardmäßig wird ein Feld vom Typ `object` in ein `IUnknown*`-Feld gemarshallt, das das Objekt umschließt.</span><span class="sxs-lookup"><span data-stu-id="3bd93-158">By default, an `object`-typed field will be marshaled to an `IUnknown*` that wraps the object.</span></span>

```csharp
public struct ObjectDefault
{
    public object obj;
}
```

```cpp
struct ObjectDefault
{
    IUnknown* obj;
};
```

<span data-ttu-id="3bd93-159">Wenn Sie ein Objektfeld in `IDispatch*` marshallen möchten, fügen Sie ein <xref:System.Runtime.InteropServices.MarshalAsAttribute> mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType> hinzu.</span><span class="sxs-lookup"><span data-stu-id="3bd93-159">If you want to marshal an object field to an `IDispatch*`, add a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.IDispatch?displayProperty=nameWithType> value.</span></span>

```csharp
public struct ObjectDispatch
{
    [MarshalAs(UnmanagedType.IDispatch)]
    public object obj;
}
```

```cpp
struct ObjectDispatch
{
    IDispatch* obj;
};
```

<span data-ttu-id="3bd93-160">Wenn Sie es als `VARIANT` marshallen möchten, fügen Sie ein <xref:System.Runtime.InteropServices.MarshalAsAttribute> mit dem Wert <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> hinzu.</span><span class="sxs-lookup"><span data-stu-id="3bd93-160">If you want to marshal it as a `VARIANT`, add a <xref:System.Runtime.InteropServices.MarshalAsAttribute> with the <xref:System.Runtime.InteropServices.UnmanagedType.Struct?displayProperty=nameWithType> value.</span></span>

```csharp
public struct ObjectVariant
{
    [MarshalAs(UnmanagedType.Struct)]
    public object obj;
}
```

```cpp
struct ObjectVariant
{
    VARIANT obj;
};
```

<span data-ttu-id="3bd93-161">In der folgenden Tabelle wird beschrieben, wie verschiedene Runtimetypen des Felds `obj` den verschiedenen Typen zugeordnet werden können, die in `VARIANT` gespeichert sind:</span><span class="sxs-lookup"><span data-stu-id="3bd93-161">The following table describes how different runtime types of the `obj` field map to the various types stored in a `VARIANT`:</span></span>

| <span data-ttu-id="3bd93-162">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="3bd93-162">.NET Type</span></span> | <span data-ttu-id="3bd93-163">VARIANT-Typ</span><span class="sxs-lookup"><span data-stu-id="3bd93-163">VARIANT Type</span></span> | | <span data-ttu-id="3bd93-164">.NET-Typ</span><span class="sxs-lookup"><span data-stu-id="3bd93-164">.NET Type</span></span> | <span data-ttu-id="3bd93-165">VARIANT-Typ</span><span class="sxs-lookup"><span data-stu-id="3bd93-165">VARIANT Type</span></span> |
|------------|--------------|-|----------|--------------|
|  `byte`  | `VT_UI1` |     | `System.Runtime.InteropServices.BStrWrapper` | `VT_BSTR` |
| `sbyte`  | `VT_I1`  |     | `object`  | `VT_DISPATCH` |
| `short`  | `VT_I2`  |     | `System.Runtime.InteropServices.UnknownWrapper` | `VT_UNKNOWN` |
| `ushort` | `VT_UI2` |     | `System.Runtime.InteropServices.DispatchWrapper` | `VT_DISPATCH` |
| `int`    | `VT_I4`  |     | `System.Reflection.Missing` | `VT_ERROR` |
| `uint`   | `VT_UI4` |     | `(object)null` | `VT_EMPTY` |
| `long`   | `VT_I8`  |     | `bool` | `VT_BOOL` |
| `ulong`  | `VT_UI8` |     | `System.DateTime` | `VT_DATE` |
| `float`  | `VT_R4`  |     | `decimal` | `VT_DECIMAL` |
| `double` | `VT_R8`  |     | `System.Runtime.InteropServices.CurrencyWrapper` | `VT_CURRENCY` |
| `char`   | `VT_UI2` |     | `System.DBNull` | `VT_NULL` |
| `string` | `VT_BSTR`|
