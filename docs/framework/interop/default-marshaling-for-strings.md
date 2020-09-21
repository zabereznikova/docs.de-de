---
title: Standardmäßiges Marshalling für Zeichenfolgen
description: Überprüfen Sie das standardmäßige Marshallingverhalten für Zeichenfolgen bei Schnittstellen, Plattformaufrufen, Strukturen und Zeichenfolgenpuffern mit fester Länge in .NET.
ms.date: 03/20/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
ms.openlocfilehash: 81df2dcc132c8ce057fa3e0e7d0ad04832f7a48b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555054"
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="f9640-103">Standardmäßiges Marshalling für Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f9640-103">Default Marshaling for Strings</span></span>

<span data-ttu-id="f9640-104">Die <xref:System.String?displayProperty=nameWithType>-Klasse und die <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Klasse weisen ein ähnliches Marshallingverhalten auf.</span><span class="sxs-lookup"><span data-stu-id="f9640-104">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>

<span data-ttu-id="f9640-105">Zeichenfolgen werden als `BSTR`-Typ im COM-Format oder als eine auf NULL endende Zeichenfolge (ein Zeichenarray, das mit dem Zeichen NULL endet) gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="f9640-105">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="f9640-106">Die Zeichen innerhalb der Zeichenfolge können als Unicode (Standardeinstellung auf Windows-Systemen) oder ANSI gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-106">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="f9640-107">In Schnittstellen verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f9640-107">Strings Used in Interfaces</span></span>

<span data-ttu-id="f9640-108">In der folgenden Tabelle werden die Marshallingoptionen für den String-Datentyp aufgelistet, wenn dieser als Methodenargument an nicht verwalteten Code gemarshallt wird.</span><span class="sxs-lookup"><span data-stu-id="f9640-108">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="f9640-109">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen an COM-Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="f9640-109">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>

|<span data-ttu-id="f9640-110">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="f9640-110">Enumeration type</span></span>|<span data-ttu-id="f9640-111">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="f9640-111">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|<span data-ttu-id="f9640-112">`UnmanagedType.BStr` (Standard)</span><span class="sxs-lookup"><span data-stu-id="f9640-112">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="f9640-113">`BSTR` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-113">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|`UnmanagedType.LPStr`|<span data-ttu-id="f9640-114">Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-114">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="f9640-115">Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-115">A pointer to a null-terminated array of Unicode characters.</span></span>|

<span data-ttu-id="f9640-116">Diese Tabelle gilt für <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f9640-116">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="f9640-117">Für <xref:System.Text.StringBuilder> sind nur die Optionen `UnmanagedType.LPStr` und `UnmanagedType.LPWStr` zulässig.</span><span class="sxs-lookup"><span data-stu-id="f9640-117">For <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>

<span data-ttu-id="f9640-118">Im folgenden Beispiel werden in der `IStringWorker`Schnittstelle deklarierte Zeichenfolgen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9640-118">The following example shows strings declared in the `IStringWorker` interface.</span></span>

```csharp
public interface IStringWorker
{
    void PassString1(string s);
    void PassString2([MarshalAs(UnmanagedType.BStr)] string s);
    void PassString3([MarshalAs(UnmanagedType.LPStr)] string s);
    void PassString4([MarshalAs(UnmanagedType.LPWStr)] string s);
    void PassStringRef1(ref string s);
    void PassStringRef2([MarshalAs(UnmanagedType.BStr)] ref string s);
    void PassStringRef3([MarshalAs(UnmanagedType.LPStr)] ref string s);
    void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)] ref string s);
}
```

```vb
Public Interface IStringWorker
    Sub PassString1(s As String)
    Sub PassString2(<MarshalAs(UnmanagedType.BStr)> s As String)
    Sub PassString3(<MarshalAs(UnmanagedType.LPStr)> s As String)
    Sub PassString4(<MarshalAs(UnmanagedType.LPWStr)> s As String)
    Sub PassStringRef1(ByRef s As String)
    Sub PassStringRef2(<MarshalAs(UnmanagedType.BStr)> ByRef s As String)
    Sub PassStringRef3(<MarshalAs(UnmanagedType.LPStr)> ByRef s As String)
    Sub PassStringRef4(<MarshalAs(UnmanagedType.LPWStr)> ByRef s As String)
End Interface
```

<span data-ttu-id="f9640-119">Im folgenden Beispiel ist die entsprechende Schnittstelle dargestellt, die in einer Typbibliothek beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="f9640-119">The following example shows the corresponding interface described in a type library.</span></span>

```cpp
interface IStringWorker : IDispatch
{
    HRESULT PassString1([in] BSTR s);
    HRESULT PassString2([in] BSTR s);
    HRESULT PassString3([in] LPStr s);
    HRESULT PassString4([in] LPWStr s);
    HRESULT PassStringRef1([in, out] BSTR *s);
    HRESULT PassStringRef2([in, out] BSTR *s);
    HRESULT PassStringRef3([in, out] LPStr *s);
    HRESULT PassStringRef4([in, out] LPWStr *s);
};
```

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="f9640-120">Im Plattformaufruf verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f9640-120">Strings Used in Platform Invoke</span></span>

<span data-ttu-id="f9640-121">Der Plattformaufruf kopiert Zeichenfolgenargumente, wobei das .NET Framework-Format (Unicode) in das nicht verwaltete Plattformformat konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="f9640-121">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="f9640-122">Zeichenfolgen sind unveränderlich und werden bei Rückgabe des Aufrufs nicht aus dem nicht verwalteten Speicher in den verwalteten Speicher zurückkopiert.</span><span class="sxs-lookup"><span data-stu-id="f9640-122">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>

<span data-ttu-id="f9640-123">In der folgenden Tabelle werden die Marshallingoptionen für Zeichenfolgen aufgelistet, wenn die Zeichenfolgen als Methodenargumente eines Plattformaufrufs gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-123">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="f9640-124">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen bereit.</span><span class="sxs-lookup"><span data-stu-id="f9640-124">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>

|<span data-ttu-id="f9640-125">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="f9640-125">Enumeration type</span></span>|<span data-ttu-id="f9640-126">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="f9640-126">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="f9640-127">`BSTR` im COM-Format mit vorangestellter Länge und ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-127">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|
|`UnmanagedType.BStr`|<span data-ttu-id="f9640-128">`BSTR` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-128">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="f9640-129">`UnmanagedType.LPStr` (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="f9640-129">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="f9640-130">Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-130">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="f9640-131">Ein Zeiger auf ein mit NULL endendes Array von plattformabhängigen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-131">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="f9640-132">Ein Zeiger auf ein mit Null endendes Array von UTF-8-codierten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-132">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="f9640-133">Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-133">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.TBStr`|<span data-ttu-id="f9640-134">`BSTR` im COM-Format mit vorangestellter Länge und plattformabhängigen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-134">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|
|`VBByRefStr`|<span data-ttu-id="f9640-135">Ein Wert, der es Visual Basic .NET ermöglicht, eine Zeichenfolge in nicht verwaltetem Code zu ändern und die Ergebnisse in verwaltetem Code wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="f9640-135">A value that enables Visual Basic .NET to change a string in unmanaged code and have the results reflected in managed code.</span></span> <span data-ttu-id="f9640-136">Dieser Wert wird nur für Plattformaufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9640-136">This value is supported only for platform invoke.</span></span> <span data-ttu-id="f9640-137">Das ist der Standardwert in Visual Basic für `ByVal`-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="f9640-137">This is the default value in Visual Basic for `ByVal` strings.</span></span>|

<span data-ttu-id="f9640-138">Diese Tabelle gilt für <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f9640-138">This table applies to <xref:System.String>.</span></span> <span data-ttu-id="f9640-139">Für <xref:System.Text.StringBuilder> sind nur die Optionen `LPStr`, `LPTStr` und `LPWStr` zulässig.</span><span class="sxs-lookup"><span data-stu-id="f9640-139">For <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>

<span data-ttu-id="f9640-140">In der folgenden Typdefinition ist die richtige Verwendung von `MarshalAsAttribute` für Plattformaufrufe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f9640-140">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>

```csharp
class StringLibAPI
{
    [DllImport("StringLib.dll")]
    public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPWStr([MarshalAs(UnmanagedType.LPWStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPTStr([MarshalAs(UnmanagedType.LPTStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassLPUTF8Str([MarshalAs(UnmanagedType.LPUTF8Str)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)] string s);
    [DllImport("StringLib.dll")]
    public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)] string s);
}
```

```vb
Class StringLibAPI
    Public Declare Auto Sub PassLPStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPStr)> s As String)
    Public Declare Auto Sub PassLPWStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPWStr)> s As String)
    Public Declare Auto Sub PassLPTStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPTStr)> s As String)
    Public Declare Auto Sub PassLPUTF8Str Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.LPUTF8Str)> s As String)
    Public Declare Auto Sub PassBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.BStr)> s As String)
    Public Declare Auto Sub PassAnsiBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.AnsiBStr)> s As String)
    Public Declare Auto Sub PassTBStr Lib "StringLib.dll" (
        <MarshalAs(UnmanagedType.TBStr)> s As String)
End Class
```

## <a name="strings-used-in-structures"></a><span data-ttu-id="f9640-141">In Strukturen verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f9640-141">Strings Used in Structures</span></span>

<span data-ttu-id="f9640-142">Zeichenfolgen sind gültige Member von Strukturen. <xref:System.Text.StringBuilder>-Puffer sind jedoch in Strukturen ungültig.</span><span class="sxs-lookup"><span data-stu-id="f9640-142">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="f9640-143">In der folgenden Tabelle werden die Marshallingoptionen für den <xref:System.String>-Datentyp aufgelistet, wenn der Typ als Feld gemarshallt wird.</span><span class="sxs-lookup"><span data-stu-id="f9640-143">The following table shows the marshaling options for the <xref:System.String> data type when the type is marshaled as a field.</span></span> <span data-ttu-id="f9640-144">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen an ein Feld bereit.</span><span class="sxs-lookup"><span data-stu-id="f9640-144">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>

|<span data-ttu-id="f9640-145">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="f9640-145">Enumeration type</span></span>|<span data-ttu-id="f9640-146">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="f9640-146">Description of unmanaged format</span></span>|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|<span data-ttu-id="f9640-147">`BSTR` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-147">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|
|<span data-ttu-id="f9640-148">`UnmanagedType.LPStr` (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="f9640-148">`UnmanagedType.LPStr` (default)</span></span>|<span data-ttu-id="f9640-149">Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-149">A pointer to a null-terminated array of ANSI characters.</span></span>|
|`UnmanagedType.LPTStr`|<span data-ttu-id="f9640-150">Ein Zeiger auf ein mit NULL endendes Array von plattformabhängigen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-150">A pointer to a null-terminated array of platform-dependent characters.</span></span>|
|`UnmanagedType.LPUTF8Str`|<span data-ttu-id="f9640-151">Ein Zeiger auf ein mit Null endendes Array von UTF-8-codierten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-151">A pointer to a null-terminated array of UTF-8 encoded characters.</span></span>|
|`UnmanagedType.LPWStr`|<span data-ttu-id="f9640-152">Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-152">A pointer to a null-terminated array of Unicode characters.</span></span>|
|`UnmanagedType.ByValTStr`|<span data-ttu-id="f9640-153">Ein Zeichenarray mit fester Länge. Der Typ des Arrays wird durch den Zeichensatz der enthaltenden Struktur bestimmt.</span><span class="sxs-lookup"><span data-stu-id="f9640-153">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|

<span data-ttu-id="f9640-154">Der `ByValTStr`-Typ wird für Inlinearrays mit Zeichen fester Länge verwendet, die in einer Struktur dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-154">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="f9640-155">Andere Typen gelten für Zeichenfolgenverweise, die in Strukturen enthalten sind, die Zeiger auf Zeichenfolgen enthalten.</span><span class="sxs-lookup"><span data-stu-id="f9640-155">Other types apply to string references contained within structures that contain pointers to strings.</span></span>

<span data-ttu-id="f9640-156">Das `CharSet`-Argument des <xref:System.Runtime.InteropServices.StructLayoutAttribute>, das auf die enthaltende Struktur angewendet wird, bestimmt das Zeichenformat von Zeichenfolgen in Strukturen.</span><span class="sxs-lookup"><span data-stu-id="f9640-156">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="f9640-157">Die folgenden Beispielstrukturen enthalten Zeichenfolgenverweise und Inlinezeichenfolgen sowie ANSI-, Unicode- und plattformabhängige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="f9640-157">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span> <span data-ttu-id="f9640-158">Die Darstellung dieser Strukturen in einer Typbibliothek ist im folgenden Code in C++ dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f9640-158">The representation of these structures in a type library is shown in the following C++ code:</span></span>

```cpp
struct StringInfoA
{
    char *  f1;
    char    f2[256];
};

struct StringInfoW
{
    WCHAR * f1;
    WCHAR   f2[256];
    BSTR    f3;
};

struct StringInfoT
{
    TCHAR * f1;
    TCHAR   f2[256];
};
```

<span data-ttu-id="f9640-159">Im folgenden Beispiel wird veranschaulicht, wie das <xref:System.Runtime.InteropServices.MarshalAsAttribute> zum Definieren derselben Struktur in unterschiedlichen Formaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f9640-159">The following example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> to define the same structure in different formats.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Ansi)]
struct StringInfoA
{
    [MarshalAs(UnmanagedType.LPStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Unicode)]
struct StringInfoW
{
    [MarshalAs(UnmanagedType.LPWStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
    [MarshalAs(UnmanagedType.BStr)] public string f3;
}

[StructLayout(LayoutKind.Sequential, CharSet = CharSet.Auto)]
struct StringInfoT
{
    [MarshalAs(UnmanagedType.LPTStr)] public string f1;
    [MarshalAs(UnmanagedType.ByValTStr, SizeConst = 256)] public string f2;
}
```

```vb
<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Ansi)> _
Structure StringInfoA
    <MarshalAs(UnmanagedType.LPStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Unicode)> _
Structure StringInfoW
    <MarshalAs(UnmanagedType.LPWStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
<MarshalAs(UnmanagedType.BStr)> Public f3 As String
End Structure

<StructLayout(LayoutKind.Sequential, CharSet := CharSet.Auto)> _
Structure StringInfoT
    <MarshalAs(UnmanagedType.LPTStr)> Public f1 As String
    <MarshalAs(UnmanagedType.ByValTStr, SizeConst := 256)> _
    Public f2 As String
End Structure
```

## <a name="fixed-length-string-buffers"></a><span data-ttu-id="f9640-160">Zeichenfolgenpuffer mit fester Länge</span><span class="sxs-lookup"><span data-stu-id="f9640-160">Fixed-Length String Buffers</span></span>

<span data-ttu-id="f9640-161">Unter bestimmten Umständen müssen Zeichenpuffer mit fester Länge zur Bearbeitung an nicht verwalteten Code übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-161">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="f9640-162">In diesem Fall ist es nicht möglich, die Zeichenfolge einfach zu übergeben, weil der Aufgerufene den Inhalt des übergebenen Puffers nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="f9640-162">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="f9640-163">Auch wenn die Zeichenfolge als Verweis übergeben wird, kann der Puffer nicht mit einer bestimmten Größe initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-163">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>

<span data-ttu-id="f9640-164">Die Lösung besteht darin, anstelle einer <xref:System.String> einen <xref:System.Text.StringBuilder>-Puffer als Argument zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="f9640-164">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a <xref:System.String>.</span></span> <span data-ttu-id="f9640-165">Ein `StringBuilder` kann durch den Aufrufer dereferenziert und geändert werden, sofern die Kapazität von `StringBuilder` nicht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="f9640-165">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="f9640-166">Er kann auch mit einer festen Länge initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9640-166">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="f9640-167">Wenn Sie beispielsweise einen `StringBuilder`-Puffer mit einer Kapazität von `N` initialisieren, stellt der Marshaller einen Puffer mit einer Größe von (`N`+1) Zeichen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f9640-167">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="f9640-168">Durch +1 wird der Tatsache Rechnung getragen, dass die nicht verwaltete Zeichenfolge (im Gegensatz zu `StringBuilder`) über einen NULL-Terminator verfügt.</span><span class="sxs-lookup"><span data-stu-id="f9640-168">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>

<span data-ttu-id="f9640-169">Zum Beispiel ist es bei der [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw)-API-Funktion von Windows (definiert in *winuser.h*) erforderlich, dass der Aufrufer einen Zeichenpuffer fester Länge übergibt, in den die Funktion den Text des Fensters schreibt.</span><span class="sxs-lookup"><span data-stu-id="f9640-169">For example, the Windows [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw) API function (defined in *winuser.h*) requires that the caller pass a fixed-length character buffer to which the function writes the window's text.</span></span> <span data-ttu-id="f9640-170">`LpString` zeigt auf einen vom Aufrufer reservierten Puffer der Größe `nMaxCount`.</span><span class="sxs-lookup"><span data-stu-id="f9640-170">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="f9640-171">Der Aufrufer soll den Puffer reservieren und das `nMaxCount`-Argument auf die Größe des reservierten Puffers festlegen.</span><span class="sxs-lookup"><span data-stu-id="f9640-171">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="f9640-172">Das folgende Beispiel stellt die `GetWindowText`-Funktionsdeklaration entsprechend der Definition in *winuser.h* dar.</span><span class="sxs-lookup"><span data-stu-id="f9640-172">The following example shows the `GetWindowText` function declaration as defined in *winuser.h*.</span></span>

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

<span data-ttu-id="f9640-173">Ein `StringBuilder` kann durch den Aufrufer dereferenziert und geändert werden, sofern die Kapazität von `StringBuilder` nicht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="f9640-173">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="f9640-174">Im folgenden Codebeispiel wird veranschaulicht, wie `StringBuilder` mit einer festen Länge initialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f9640-174">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;
using System.Text;

internal static class NativeMethods
{
    [DllImport("User32.dll")]
    internal static extern void GetWindowText(IntPtr hWnd, StringBuilder lpString, int nMaxCount);
}

public class Window
{
    internal IntPtr h;        // Internal handle to Window.
    public String GetText()
    {
        StringBuilder sb = new StringBuilder(256);
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1);
        return sb.ToString();
    }
}
```

```vb
Imports System.Text

Friend Class NativeMethods
    Friend Declare Auto Sub GetWindowText Lib "User32.dll" _
        (hWnd As IntPtr, lpString As StringBuilder, nMaxCount As Integer)
End Class

Public Class Window
    Friend h As IntPtr ' Friend handle to Window.
    Public Function GetText() As String
        Dim sb As New StringBuilder(256)
        NativeMethods.GetWindowText(h, sb, sb.Capacity + 1)
        Return sb.ToString()
   End Function
End Class
```

## <a name="see-also"></a><span data-ttu-id="f9640-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9640-175">See also</span></span>

- [<span data-ttu-id="f9640-176">Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)</span><span class="sxs-lookup"><span data-stu-id="f9640-176">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="f9640-177">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f9640-177">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="f9640-178">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="f9640-178">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="f9640-179">[Direktionale Attribute](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f9640-179">[Directional Attributes](/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="f9640-180">Kopieren und Fixieren</span><span class="sxs-lookup"><span data-stu-id="f9640-180">Copying and Pinning</span></span>](copying-and-pinning.md)
