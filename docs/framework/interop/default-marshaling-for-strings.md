---
title: Standardmäßiges Marshalling für Zeichenfolgen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings, interop marshaling
- interop marshaling, strings
ms.assetid: 9baea3ce-27b3-4b4f-af98-9ad0f9467e6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df65f54a9a7408a22f8b558f99ab42d6c37ae55b
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/13/2019
ms.locfileid: "56221068"
---
# <a name="default-marshaling-for-strings"></a><span data-ttu-id="55af4-102">Standardmäßiges Marshalling für Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="55af4-102">Default Marshaling for Strings</span></span>
<span data-ttu-id="55af4-103">Die <xref:System.String?displayProperty=nameWithType>-Klasse und die <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Klasse weisen ein ähnliches Marshallingverhalten auf.</span><span class="sxs-lookup"><span data-stu-id="55af4-103">Both the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes have similar marshaling behavior.</span></span>  
  
 <span data-ttu-id="55af4-104">Zeichenfolgen werden als `BSTR`-Typ im COM-Format oder als eine auf NULL endende Zeichenfolge (ein Zeichenarray, das mit dem Zeichen NULL endet) gemarshallt.</span><span class="sxs-lookup"><span data-stu-id="55af4-104">Strings are marshaled as a COM-style `BSTR` type or as a null-terminated string (a character array that ends with a null character).</span></span> <span data-ttu-id="55af4-105">Die Zeichen innerhalb der Zeichenfolge können als Unicode (Standardeinstellung auf Windows-Systemen) oder ANSI gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="55af4-105">The characters within the string can be marshaled as Unicode (the default on Windows systems) or ANSI.</span></span>  
  
 <span data-ttu-id="55af4-106">Dieses Thema enthält die folgenden Informationen zum Marshalling von Zeichenfolgentypen:</span><span class="sxs-lookup"><span data-stu-id="55af4-106">This topic provides the following information on marshaling string types:</span></span>  
  
-   [<span data-ttu-id="55af4-107">In Schnittstellen verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="55af4-107">Strings Used in Interfaces</span></span>](#cpcondefaultmarshalingforstringsanchor1)  
  
-   [<span data-ttu-id="55af4-108">Im Plattformaufruf verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="55af4-108">Strings Used in Platform Invoke</span></span>](#cpcondefaultmarshalingforstringsanchor5)  
  
-   [<span data-ttu-id="55af4-109">In Strukturen verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="55af4-109">Strings Used in Structures</span></span>](#cpcondefaultmarshalingforstringsanchor2)  
  
-   [<span data-ttu-id="55af4-110">Zeichenfolgenpuffer mit fester Länge</span><span class="sxs-lookup"><span data-stu-id="55af4-110">Fixed-Length String Buffers</span></span>](#cpcondefaultmarshalingforstringsanchor3)  
  
<a name="cpcondefaultmarshalingforstringsanchor1"></a>

## <a name="strings-used-in-interfaces"></a><span data-ttu-id="55af4-111">In Schnittstellen verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="55af4-111">Strings Used in Interfaces</span></span>  
 <span data-ttu-id="55af4-112">In der folgenden Tabelle werden die Marshallingoptionen für den String-Datentyp aufgelistet, wenn dieser als Methodenargument an nicht verwalteten Code gemarshallt wird.</span><span class="sxs-lookup"><span data-stu-id="55af4-112">The following table shows the marshaling options for the string data type when marshaled as a method argument to unmanaged code.</span></span> <span data-ttu-id="55af4-113">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen an COM-Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="55af4-113">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to COM interfaces.</span></span>  
  
|<span data-ttu-id="55af4-114">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="55af4-114">Enumeration type</span></span>|<span data-ttu-id="55af4-115">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="55af4-115">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|<span data-ttu-id="55af4-116">`UnmanagedType.BStr` (Standard)</span><span class="sxs-lookup"><span data-stu-id="55af4-116">`UnmanagedType.BStr` (default)</span></span>|<span data-ttu-id="55af4-117">
  `BSTR\` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-117">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="55af4-118">Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-118">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="55af4-119">Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-119">A pointer to a null-terminated array of Unicode characters.</span></span>|  
  
 <span data-ttu-id="55af4-120">Diese Tabelle gilt für Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="55af4-120">This table applies to strings.</span></span> <span data-ttu-id="55af4-121">Für <xref:System.Text.StringBuilder> sind jedoch nur die Optionen `UnmanagedType.LPStr` und `UnmanagedType.LPWStr` zulässig.</span><span class="sxs-lookup"><span data-stu-id="55af4-121">However, for <xref:System.Text.StringBuilder>, the only options allowed are `UnmanagedType.LPStr` and `UnmanagedType.LPWStr`.</span></span>  
  
 <span data-ttu-id="55af4-122">Im folgenden Beispiel werden in der `IStringWorker`Schnittstelle deklarierte Zeichenfolgen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="55af4-122">The following example shows strings declared in the `IStringWorker` interface.</span></span>  
  
```cpp  
public interface IStringWorker {  
void PassString1(String s);  
void PassString2([MarshalAs(UnmanagedType.BStr)]String s);  
void PassString3([MarshalAs(UnmanagedType.LPStr)]String s);  
void PassString4([MarshalAs(UnmanagedType.LPWStr)]String s);  
void PassStringRef1(ref String s);  
void PassStringRef2([MarshalAs(UnmanagedType.BStr)]ref String s);  
void PassStringRef3([MarshalAs(UnmanagedType.LPStr)]ref String s);  
void PassStringRef4([MarshalAs(UnmanagedType.LPWStr)]ref String s);  
);
```

<span data-ttu-id="55af4-123">Im folgenden Beispiel ist die entsprechende Schnittstelle dargestellt, die in einer Typbibliothek beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="55af4-123">The following example shows the corresponding interface described in a type library.</span></span>

```
[…]  
interface IStringWorker : IDispatch {  
HRESULT PassString1([in] BSTR s);  
HRESULT PassString2([in] BSTR s);  
HRESULT PassString3([in] LPStr s);  
HRESULT PassString4([in] LPWStr s);  
HRESULT PassStringRef1([in, out] BSTR *s);  
HRESULT PassStringRef2([in, out] BSTR *s);  
HRESULT PassStringRef3([in, out] LPStr *s);  
HRESULT PassStringRef4([in, out] LPWStr *s);  
);
```

<a name="cpcondefaultmarshalingforstringsanchor5"></a>

## <a name="strings-used-in-platform-invoke"></a><span data-ttu-id="55af4-124">Im Plattformaufruf verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="55af4-124">Strings Used in Platform Invoke</span></span>  
 <span data-ttu-id="55af4-125">Der Plattformaufruf kopiert Zeichenfolgenargumente, wobei das .NET Framework-Format (Unicode) in das nicht verwaltete Plattformformat konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="55af4-125">Platform invoke copies string arguments, converting from the .NET Framework format (Unicode) to the platform unmanaged format.</span></span> <span data-ttu-id="55af4-126">Zeichenfolgen sind unveränderlich und werden bei Rückgabe des Aufrufs nicht aus dem nicht verwalteten Speicher in den verwalteten Speicher zurückkopiert.</span><span class="sxs-lookup"><span data-stu-id="55af4-126">Strings are immutable and are not copied back from unmanaged memory to managed memory when the call returns.</span></span>  
  
 <span data-ttu-id="55af4-127">In der folgenden Tabelle werden die Marshallingoptionen für Zeichenfolgen aufgelistet, wenn die Zeichenfolgen als Methodenargumente eines Plattformaufrufs gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="55af4-127">The following table lists the marshaling options for strings when marshaled as a method argument of a platform invoke call.</span></span> <span data-ttu-id="55af4-128">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen bereit.</span><span class="sxs-lookup"><span data-stu-id="55af4-128">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings.</span></span>  
  
|<span data-ttu-id="55af4-129">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="55af4-129">Enumeration type</span></span>|<span data-ttu-id="55af4-130">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="55af4-130">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.AnsiBStr`|<span data-ttu-id="55af4-131">
  `BSTR\` im COM-Format mit vorangestellter Länge und ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-131">A COM-style `BSTR` with a prefixed length and ANSI characters.</span></span>|  
|`UnmanagedType.BStr`|<span data-ttu-id="55af4-132">
  `BSTR\` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-132">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="55af4-133">Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-133">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="55af4-134">Ein Zeiger auf ein mit NULL endendes Array von plattformabhängigen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-134">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="55af4-135">Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-135">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.TBStr`|<span data-ttu-id="55af4-136">
  `BSTR\` im COM-Format mit vorangestellter Länge und plattformabhängigen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-136">A COM-style `BSTR` with a prefixed length and platform-dependent characters.</span></span>|  
|`VBByRefStr`|<span data-ttu-id="55af4-137">Ein Wert, der es Visual Basic .NET ermöglicht, eine Zeichenfolge in nicht verwaltetem Code zu ändern und die Ergebnisse in verwaltetem Code wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="55af4-137">A value that enables Visual Basic .NET to change a string in unmanaged code, and have the results reflected in managed code.</span></span> <span data-ttu-id="55af4-138">Dieser Wert wird nur für Plattformaufrufe unterstützt.</span><span class="sxs-lookup"><span data-stu-id="55af4-138">This value is supported only for platform invoke.</span></span> <span data-ttu-id="55af4-139">Das ist der Standardwert in Visual Basic für `ByVal`-Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="55af4-139">This is default value in Visual Basic for `ByVal` strings.</span></span>|  
  
 <span data-ttu-id="55af4-140">Diese Tabelle gilt für Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="55af4-140">This table applies to strings.</span></span> <span data-ttu-id="55af4-141">Für <xref:System.Text.StringBuilder> sind jedoch nur die Optionen `LPStr`, `LPTStr` und `LPWStr` zulässig.</span><span class="sxs-lookup"><span data-stu-id="55af4-141">However, for <xref:System.Text.StringBuilder>, the only options allowed are `LPStr`, `LPTStr`, and `LPWStr`.</span></span>  
  
 <span data-ttu-id="55af4-142">In der folgenden Typdefinition ist die richtige Verwendung von `MarshalAsAttribute` für Plattformaufrufe dargestellt.</span><span class="sxs-lookup"><span data-stu-id="55af4-142">The following type definition shows the correct use of `MarshalAsAttribute` for platform invoke calls.</span></span>  
  
```vb  
Class StringLibAPI      
Public Declare Auto Sub PassLPStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPStr)> s As String)      
Public Declare Auto Sub PassLPWStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPWStr)> s As String)      
Public Declare Auto Sub PassLPTStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.LPTStr)> s As String)      
Public Declare Auto Sub PassBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.BStr)> s As String)      
Public Declare Auto Sub PassAnsiBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.AnsiBStr)> s As String)      
Public Declare Auto Sub PassTBStr Lib "StringLib.Dll" _  
(<MarshalAs(UnmanagedType.TBStr)> s As String)  
End Class  
```

```csharp
class StringLibAPI {  
[DllImport("StringLib.Dll")]  
public static extern void PassLPStr([MarshalAs(UnmanagedType.LPStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPWStr([MarshalAs(UnmanagedType.LPWStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassLPTStr([MarshalAs(UnmanagedType.LPTStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassBStr([MarshalAs(UnmanagedType.BStr)]  
String s);  
[DllImport("StringLib.Dll")]  
public static extern void   
PassAnsiBStr([MarshalAs(UnmanagedType.AnsiBStr)]String s);  
[DllImport("StringLib.Dll")]  
public static extern void PassTBStr([MarshalAs(UnmanagedType.TBStr)]  
String s);  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor2"></a>   
## <a name="strings-used-in-structures"></a><span data-ttu-id="55af4-143">In Strukturen verwendete Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="55af4-143">Strings Used in Structures</span></span>  
 <span data-ttu-id="55af4-144">Zeichenfolgen sind gültige Member von Strukturen. <xref:System.Text.StringBuilder>-Puffer sind jedoch in Strukturen ungültig.</span><span class="sxs-lookup"><span data-stu-id="55af4-144">Strings are valid members of structures; however, <xref:System.Text.StringBuilder> buffers are invalid in structures.</span></span> <span data-ttu-id="55af4-145">In der folgenden Tabelle werden die Marshallingoptionen für den String-Datentyp aufgelistet, wenn der Typ als Feld gemarshallt wird.</span><span class="sxs-lookup"><span data-stu-id="55af4-145">The following table shows the marshaling options for the string data type when the type is marshaled as a field.</span></span> <span data-ttu-id="55af4-146">Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen an ein Feld bereit.</span><span class="sxs-lookup"><span data-stu-id="55af4-146">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute provides several <xref:System.Runtime.InteropServices.UnmanagedType> enumeration values to marshal strings to a field.</span></span>  
  
|<span data-ttu-id="55af4-147">Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="55af4-147">Enumeration type</span></span>|<span data-ttu-id="55af4-148">Beschreibung des nicht verwalteten Formats</span><span class="sxs-lookup"><span data-stu-id="55af4-148">Description of unmanaged format</span></span>|  
|----------------------|-------------------------------------|  
|`UnmanagedType.BStr`|<span data-ttu-id="55af4-149">
  `BSTR\` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-149">A COM-style `BSTR` with a prefixed length and Unicode characters.</span></span>|  
|`UnmanagedType.LPStr`|<span data-ttu-id="55af4-150">Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-150">A pointer to a null-terminated array of ANSI characters.</span></span>|  
|`UnmanagedType.LPTStr`|<span data-ttu-id="55af4-151">Ein Zeiger auf ein mit NULL endendes Array von plattformabhängigen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-151">A pointer to a null-terminated array of platform-dependent characters.</span></span>|  
|`UnmanagedType.LPWStr`|<span data-ttu-id="55af4-152">Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-152">A pointer to a null-terminated array of Unicode characters.</span></span>|  
|`UnmanagedType.ByValTStr`|<span data-ttu-id="55af4-153">Ein Zeichenarray mit fester Länge. Der Typ des Arrays wird durch den Zeichensatz der enthaltenden Struktur bestimmt.</span><span class="sxs-lookup"><span data-stu-id="55af4-153">A fixed-length array of characters; the array's type is determined by the character set of the containing structure.</span></span>|  
  
 <span data-ttu-id="55af4-154">Der `ByValTStr`-Typ wird für Inlinearrays mit Zeichen fester Länge verwendet, die in einer Struktur dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="55af4-154">The `ByValTStr` type is used for inline, fixed-length character arrays that appear within a structure.</span></span> <span data-ttu-id="55af4-155">Andere Typen gelten für Zeichenfolgenverweise, die in Strukturen enthalten sind, die Zeiger auf Zeichenfolgen enthalten.</span><span class="sxs-lookup"><span data-stu-id="55af4-155">Other types apply to string references contained within structures that contain pointers to strings.</span></span>  
  
 <span data-ttu-id="55af4-156">Das `CharSet`-Argument des <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attributs, das auf die enthaltende Struktur angewendet wird, bestimmt das Zeichenformat von Zeichenfolgen in Strukturen.</span><span class="sxs-lookup"><span data-stu-id="55af4-156">The `CharSet` argument of the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute that is applied to the containing structure determines the character format of strings in structures.</span></span> <span data-ttu-id="55af4-157">Die folgenden Beispielstrukturen enthalten Zeichenfolgenverweise und Inlinezeichenfolgen sowie ANSI-, Unicode- und plattformabhängige Zeichen.</span><span class="sxs-lookup"><span data-stu-id="55af4-157">The following example structures contain string references and inline strings, as well as ANSI, Unicode, and platform-dependent characters.</span></span>  
  
### <a name="type-library-representation"></a><span data-ttu-id="55af4-158">Darstellung der Typbibliothek</span><span class="sxs-lookup"><span data-stu-id="55af4-158">Type Library Representation</span></span>  
  
```
struct StringInfoA {  
   char *    f1;  
   char      f2[256];  
};  
struct StringInfoW {  
   WCHAR *   f1;  
   WCHAR     f2[256];  
   BSTR      f3;  
};  
struct StringInfoT {  
   TCHAR *   f1;  
   TCHAR     f2[256];  
};  
```  
  
 <span data-ttu-id="55af4-159">Im folgenden Codebeispiel wird veranschaulicht, wie das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut zum Definieren derselben Struktur in unterschiedlichen Formaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="55af4-159">The following code example shows how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to define the same structure in different formats.</span></span>  
  
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
  
```csharp  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Ansi)]  
struct StringInfoA {  
   [MarshalAs(UnmanagedType.LPStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Unicode)]  
struct StringInfoW {  
   [MarshalAs(UnmanagedType.LPWStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
   [MarshalAs(UnmanagedType.BStr)] public String f3;  
}  
[StructLayout(LayoutKind.Sequential, CharSet=CharSet.Auto)]  
struct StringInfoT {  
   [MarshalAs(UnmanagedType.LPTStr)] public String f1;  
   [MarshalAs(UnmanagedType.ByValTStr, SizeConst=256)] public String f2;  
}  
```  
  
<a name="cpcondefaultmarshalingforstringsanchor3"></a>   
## <a name="fixed-length-string-buffers"></a><span data-ttu-id="55af4-160">Zeichenfolgenpuffer mit fester Länge</span><span class="sxs-lookup"><span data-stu-id="55af4-160">Fixed-Length String Buffers</span></span>  
 <span data-ttu-id="55af4-161">Unter bestimmten Umständen müssen Zeichenpuffer mit fester Länge zur Bearbeitung an nicht verwalteten Code übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="55af4-161">In some circumstances, a fixed-length character buffer must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="55af4-162">In diesem Fall ist es nicht möglich, die Zeichenfolge einfach zu übergeben, weil der Aufgerufene den Inhalt des übergebenen Puffers nicht ändern kann.</span><span class="sxs-lookup"><span data-stu-id="55af4-162">Simply passing a string does not work in this case because the callee cannot modify the contents of the passed buffer.</span></span> <span data-ttu-id="55af4-163">Auch wenn die Zeichenfolge als Verweis übergeben wird, kann der Puffer nicht mit einer bestimmten Größe initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="55af4-163">Even if the string is passed by reference, there is no way to initialize the buffer to a given size.</span></span>  
  
 <span data-ttu-id="55af4-164">Die Lösung besteht darin, anstelle einer Zeichenfolge einen <xref:System.Text.StringBuilder>-Puffer als Argument zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="55af4-164">The solution is to pass a <xref:System.Text.StringBuilder> buffer as the argument instead of a string.</span></span> <span data-ttu-id="55af4-165">Ein `StringBuilder` kann durch den Aufrufer dereferenziert und geändert werden, sofern die Kapazität von `StringBuilder` nicht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="55af4-165">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="55af4-166">Er kann auch mit einer festen Länge initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="55af4-166">It can also be initialized to a fixed length.</span></span> <span data-ttu-id="55af4-167">Wenn Sie beispielsweise einen `StringBuilder`-Puffer mit einer Kapazität von `N` initialisieren, stellt der Marshaller einen Puffer mit einer Größe von (`N`+1) Zeichen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="55af4-167">For example, if you initialize a `StringBuilder` buffer to a capacity of `N`, the marshaler provides a buffer of size (`N`+1) characters.</span></span> <span data-ttu-id="55af4-168">Durch +1 wird der Tatsache Rechnung getragen, dass die nicht verwaltete Zeichenfolge (im Gegensatz zu `StringBuilder`) über einen NULL-Terminator verfügt.</span><span class="sxs-lookup"><span data-stu-id="55af4-168">The +1 accounts for the fact that the unmanaged string has a null terminator while `StringBuilder` does not.</span></span>  
  
 <span data-ttu-id="55af4-169">Die `GetWindowText`-Funktion der Microsoft Win32-API (in Windows.h definiert) ist beispielsweise ein Zeichenpuffer mit fester Länge, der zur Bearbeitung an nicht verwalteten Code übergeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="55af4-169">For example, the Microsoft Win32 API `GetWindowText` function (defined in Windows.h) is a fixed-length character buffer that must be passed into unmanaged code to be manipulated.</span></span> <span data-ttu-id="55af4-170">`LpString` zeigt auf einen vom Aufrufer reservierten Puffer der Größe `nMaxCount`.</span><span class="sxs-lookup"><span data-stu-id="55af4-170">`LpString` points to a caller-allocated buffer of size `nMaxCount`.</span></span> <span data-ttu-id="55af4-171">Der Aufrufer soll den Puffer reservieren und das `nMaxCount`-Argument auf die Größe des reservierten Puffers festlegen.</span><span class="sxs-lookup"><span data-stu-id="55af4-171">The caller is expected to allocate the buffer and set the `nMaxCount` argument to the size of the allocated buffer.</span></span> <span data-ttu-id="55af4-172">Der folgende Code stellt die Deklaration der `GetWindowText`-Funktion entsprechend der Definition in Windows.h dar.</span><span class="sxs-lookup"><span data-stu-id="55af4-172">The following code shows the `GetWindowText` function declaration as defined in Windows.h.</span></span>  
  
```  
int GetWindowText(  
HWND hWnd,        // Handle to window or control.  
LPTStr lpString,  // Text buffer.  
int nMaxCount     // Maximum number of characters to copy.  
);  
```  
  
 <span data-ttu-id="55af4-173">Ein `StringBuilder` kann durch den Aufrufer dereferenziert und geändert werden, sofern die Kapazität von `StringBuilder` nicht überschritten wird.</span><span class="sxs-lookup"><span data-stu-id="55af4-173">A `StringBuilder` can be dereferenced and modified by the callee, provided it does not exceed the capacity of the `StringBuilder`.</span></span> <span data-ttu-id="55af4-174">Im folgenden Codebeispiel wird veranschaulicht, wie `StringBuilder` mit einer festen Länge initialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="55af4-174">The following code example demonstrates how `StringBuilder` can be initialized to a fixed length.</span></span>  
  
```vb  
Public Class Win32API  
Public Declare Auto Sub GetWindowText Lib "User32.Dll" _  
(h As Integer, s As StringBuilder, nMaxCount As Integer)  
End Class  
Public Class Window  
   Friend h As Integer ' Friend handle to Window.  
   Public Function GetText() As String  
      Dim sb As New StringBuilder(256)  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1)  
   Return sb.ToString()  
   End Function  
End Class  
```  
  
```csharp  
public class Win32API {  
[DllImport("User32.Dll")]  
public static extern void GetWindowText(int h, StringBuilder s,   
int nMaxCount);  
}  
public class Window {  
   internal int h;        // Internal handle to Window.  
   public String GetText() {  
      StringBuilder sb = new StringBuilder(256);  
      Win32API.GetWindowText(h, sb, sb.Capacity + 1);  
   return sb.ToString();  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="55af4-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55af4-175">See also</span></span>
- [<span data-ttu-id="55af4-176">Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)</span><span class="sxs-lookup"><span data-stu-id="55af4-176">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)
- [<span data-ttu-id="55af4-177">Blitfähige und nicht blitfähige Typen</span><span class="sxs-lookup"><span data-stu-id="55af4-177">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)
- <span data-ttu-id="55af4-178">[Direktionale Attribute](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="55af4-178">[Directional Attributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))</span></span>
- [<span data-ttu-id="55af4-179">Kopieren und Fixieren</span><span class="sxs-lookup"><span data-stu-id="55af4-179">Copying and Pinning</span></span>](copying-and-pinning.md)
