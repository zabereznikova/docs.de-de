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
ms.openlocfilehash: 440a49730f351b820cd68a741e79f94434f585c8
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904116"
---
# <a name="default-marshaling-for-strings"></a>Standardmäßiges Marshalling für Zeichenfolgen

Die <xref:System.String?displayProperty=nameWithType>-Klasse und die <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Klasse weisen ein ähnliches Marshallingverhalten auf.

Zeichenfolgen werden als `BSTR`-Typ im COM-Format oder als eine auf NULL endende Zeichenfolge (ein Zeichenarray, das mit dem Zeichen NULL endet) gemarshallt. Die Zeichen innerhalb der Zeichenfolge können als Unicode (Standardeinstellung auf Windows-Systemen) oder ANSI gemarshallt werden.

## <a name="strings-used-in-interfaces"></a>In Schnittstellen verwendete Zeichenfolgen

In der folgenden Tabelle werden die Marshallingoptionen für den String-Datentyp aufgelistet, wenn dieser als Methodenargument an nicht verwalteten Code gemarshallt wird. Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen an COM-Schnittstellen bereit.

|Enumerationstyp|Beschreibung des nicht verwalteten Formats|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr` (Standard)|`BSTR` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.|
|`UnmanagedType.LPStr`|Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.|
|`UnmanagedType.LPWStr`|Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.|

Diese Tabelle gilt für <xref:System.String>. Für <xref:System.Text.StringBuilder> sind nur die Optionen `UnmanagedType.LPStr` und `UnmanagedType.LPWStr` zulässig.

Im folgenden Beispiel werden in der `IStringWorker`Schnittstelle deklarierte Zeichenfolgen gezeigt.

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

Im folgenden Beispiel ist die entsprechende Schnittstelle dargestellt, die in einer Typbibliothek beschrieben wird.

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

## <a name="strings-used-in-platform-invoke"></a>Im Plattformaufruf verwendete Zeichenfolgen

Der Plattformaufruf kopiert Zeichenfolgenargumente, wobei das .NET Framework-Format (Unicode) in das nicht verwaltete Plattformformat konvertiert wird. Zeichenfolgen sind unveränderlich und werden bei Rückgabe des Aufrufs nicht aus dem nicht verwalteten Speicher in den verwalteten Speicher zurückkopiert.

In der folgenden Tabelle werden die Marshallingoptionen für Zeichenfolgen aufgelistet, wenn die Zeichenfolgen als Methodenargumente eines Plattformaufrufs gemarshallt werden. Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen bereit.

|Enumerationstyp|Beschreibung des nicht verwalteten Formats|
|----------------------|-------------------------------------|
|`UnmanagedType.AnsiBStr`|`BSTR` im COM-Format mit vorangestellter Länge und ANSI-Zeichen.|
|`UnmanagedType.BStr`|`BSTR` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.|
|`UnmanagedType.LPStr` (Standardwert)|Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.|
|`UnmanagedType.LPTStr`|Ein Zeiger auf ein mit NULL endendes Array von plattformabhängigen Zeichen.|
|`UnmanagedType.LPUTF8Str`|Ein Zeiger auf ein mit Null endendes Array von UTF-8-codierten Zeichen.|
|`UnmanagedType.LPWStr`|Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.|
|`UnmanagedType.TBStr`|`BSTR` im COM-Format mit vorangestellter Länge und plattformabhängigen Zeichen.|
|`VBByRefStr`|Ein Wert, der es Visual Basic .NET ermöglicht, eine Zeichenfolge in nicht verwaltetem Code zu ändern und die Ergebnisse in verwaltetem Code wiederzugeben. Dieser Wert wird nur für Plattformaufrufe unterstützt. Das ist der Standardwert in Visual Basic für `ByVal`-Zeichenfolgen.|

Diese Tabelle gilt für <xref:System.String>. Für <xref:System.Text.StringBuilder> sind nur die Optionen `LPStr`, `LPTStr` und `LPWStr` zulässig.

In der folgenden Typdefinition ist die richtige Verwendung von `MarshalAsAttribute` für Plattformaufrufe dargestellt.

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

## <a name="strings-used-in-structures"></a>In Strukturen verwendete Zeichenfolgen

Zeichenfolgen sind gültige Member von Strukturen. <xref:System.Text.StringBuilder>-Puffer sind jedoch in Strukturen ungültig. In der folgenden Tabelle werden die Marshallingoptionen für den <xref:System.String>-Datentyp aufgelistet, wenn der Typ als Feld gemarshallt wird. Das <xref:System.Runtime.InteropServices.MarshalAsAttribute>-Attribut stellt mehrere <xref:System.Runtime.InteropServices.UnmanagedType>-Enumerationswerte zum Marshallen von Zeichenfolgen an ein Feld bereit.

|Enumerationstyp|Beschreibung des nicht verwalteten Formats|
|----------------------|-------------------------------------|
|`UnmanagedType.BStr`|`BSTR` im COM-Format mit vorangestellter Länge und Unicode-Zeichen.|
|`UnmanagedType.LPStr` (Standardwert)|Ein Zeiger auf ein mit NULL endendes Array von ANSI-Zeichen.|
|`UnmanagedType.LPTStr`|Ein Zeiger auf ein mit NULL endendes Array von plattformabhängigen Zeichen.|
|`UnmanagedType.LPUTF8Str`|Ein Zeiger auf ein mit Null endendes Array von UTF-8-codierten Zeichen.|
|`UnmanagedType.LPWStr`|Ein Zeiger auf ein mit Null endendes Array von Unicode-Zeichen.|
|`UnmanagedType.ByValTStr`|Ein Zeichenarray mit fester Länge. Der Typ des Arrays wird durch den Zeichensatz der enthaltenden Struktur bestimmt.|

Der `ByValTStr`-Typ wird für Inlinearrays mit Zeichen fester Länge verwendet, die in einer Struktur dargestellt werden. Andere Typen gelten für Zeichenfolgenverweise, die in Strukturen enthalten sind, die Zeiger auf Zeichenfolgen enthalten.

Das `CharSet`-Argument des <xref:System.Runtime.InteropServices.StructLayoutAttribute>, das auf die enthaltende Struktur angewendet wird, bestimmt das Zeichenformat von Zeichenfolgen in Strukturen. Die folgenden Beispielstrukturen enthalten Zeichenfolgenverweise und Inlinezeichenfolgen sowie ANSI-, Unicode- und plattformabhängige Zeichen. Die Darstellung dieser Strukturen in einer Typbibliothek ist im folgenden Code in C++ dargestellt:

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

Im folgenden Beispiel wird veranschaulicht, wie das <xref:System.Runtime.InteropServices.MarshalAsAttribute> zum Definieren derselben Struktur in unterschiedlichen Formaten verwendet wird.

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

## <a name="fixed-length-string-buffers"></a>Zeichenfolgenpuffer mit fester Länge

Unter bestimmten Umständen müssen Zeichenpuffer mit fester Länge zur Bearbeitung an nicht verwalteten Code übergeben werden. In diesem Fall ist es nicht möglich, die Zeichenfolge einfach zu übergeben, weil der Aufgerufene den Inhalt des übergebenen Puffers nicht ändern kann. Auch wenn die Zeichenfolge als Verweis übergeben wird, kann der Puffer nicht mit einer bestimmten Größe initialisiert werden.

Die Lösung besteht darin, anstelle einer <xref:System.String> einen <xref:System.Text.StringBuilder>-Puffer als Argument zu übergeben. Ein `StringBuilder` kann durch den Aufrufer dereferenziert und geändert werden, sofern die Kapazität von `StringBuilder` nicht überschritten wird. Er kann auch mit einer festen Länge initialisiert werden. Wenn Sie beispielsweise einen `StringBuilder`-Puffer mit einer Kapazität von `N` initialisieren, stellt der Marshaller einen Puffer mit einer Größe von (`N`+1) Zeichen zur Verfügung. Durch +1 wird der Tatsache Rechnung getragen, dass die nicht verwaltete Zeichenfolge (im Gegensatz zu `StringBuilder`) über einen NULL-Terminator verfügt.

Zum Beispiel ist es bei der [`GetWindowText`](/windows/desktop/api/winuser/nf-winuser-getwindowtextw)-API-Funktion von Windows (definiert in *winuser.h*) erforderlich, dass der Aufrufer einen Zeichenpuffer fester Länge übergibt, in den die Funktion den Text des Fensters schreibt. `LpString` zeigt auf einen vom Aufrufer reservierten Puffer der Größe `nMaxCount`. Der Aufrufer soll den Puffer reservieren und das `nMaxCount`-Argument auf die Größe des reservierten Puffers festlegen. Das folgende Beispiel stellt die `GetWindowText`-Funktionsdeklaration entsprechend der Definition in *winuser.h* dar.

```cpp
int GetWindowText(
    HWND hWnd,        // Handle to window or control.
    LPTStr lpString,  // Text buffer.
    int nMaxCount     // Maximum number of characters to copy.
);
```

Ein `StringBuilder` kann durch den Aufrufer dereferenziert und geändert werden, sofern die Kapazität von `StringBuilder` nicht überschritten wird. Im folgenden Codebeispiel wird veranschaulicht, wie `StringBuilder` mit einer festen Länge initialisiert werden kann.

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

## <a name="see-also"></a>Siehe auch

- [Default Marshaling Behavior (Standardmäßiges Marshallingverhalten)](default-marshaling-behavior.md)
- [Marshallen von Zeichenfolgen](marshaling-strings.md)
- [Blitfähige und nicht blitfähige Typen](blittable-and-non-blittable-types.md)
- [Direktionale Attribute](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/77e6taeh(v=vs.100))
- [Kopieren und Fixieren](copying-and-pinning.md)
