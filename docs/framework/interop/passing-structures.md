---
title: Übergeben von Strukturen
description: Erfahren Sie, wie Strukturen und Klassen an nicht verwaltete Funktionen übergeben werden können. Lernen Sie das Attribut StructLayoutAttribute kennen, das zum Definieren formatierter Typen dient.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform invoke, calling unmanaged functions
ms.assetid: 9b92ac73-32b7-4e1b-862e-6d8d950cf169
ms.openlocfilehash: ece5db8fdf803ce2f450ebeaaad66a379cfbf992
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268910"
---
# <a name="passing-structures"></a>Übergeben von Strukturen

Bei vielen nicht verwalteten Funktionen wird erwartet, dass Member von Strukturen (benutzerdefinierte Typen in Visual Basic) oder Member von Klassen, die in verwaltetem Code definiert werden, als Parameter an die Funktion übergeben werden. Wenn Sie Strukturen oder Klassen an nicht verwalteten Code mithilfe von Plattformaufruf übergeben, müssen Sie zusätzliche Informationen angeben, um das ursprüngliche Layout und die ursprüngliche Ausrichtung beizubehalten. Dieses Thema enthält eine Einführung in das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut, das Sie zum Definieren formatierter Typen verwenden. Sie können für verwaltete Strukturen und Klassen verschiedene vorhersagbare Layoutverhalten auswählen, die von der **LayoutKind**-Enumeration bereitgestellt werden.  
  
 Es gibt einen entscheidenden Unterschied zwischen Struktur- und Klassentypen, der für die im vorliegenden Thema dargestellten Konzepte eine Schlüsselposition einnimmt. Strukturen sind Werttypen und Klassen sind Referenztypen, wobei Klassen immer mindestens eine Speicherdereferenzierungsebene (einen Zeiger auf einen Wert) bereitstellen. Dieser Unterschied ist relevant, da nicht verwaltete Funktionen oftmals eine Dereferenzierung erfordern, wie durch die Signaturen in der ersten Spalte der folgenden Tabelle gezeigt. Die verwalteten Struktur- und Klassendeklarationen in den anderen Spalten geben an, in welchem Ausmaß die Dereferenzierungsebene in der Deklaration angepasst werden kann. Es werden Deklarationen für Visual Basic und Visual C# bereitgestellt.  
  
|Nicht verwaltete Signatur|Verwaltete Deklaration: <br />keine Dereferenzierung<br />`Structure MyType`<br />`struct MyType;`|Verwaltete Deklaration: <br />eine Dereferenzierungsebene<br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> Erfordert 0 Dereferenzierungsebenen.|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> Fügt 0 Dereferenzierungsebenen hinzu.|Nicht möglich, da bereits eine Dereferenzierungsebene besteht.|  
|`DoWork(MyType* x);`<br /><br /> Erfordert eine Dereferenzierungsebene.|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> Fügt eine Dereferenzierungsebene hinzu.|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> Fügt 0 Dereferenzierungsebenen hinzu.|  
|`DoWork(MyType** x);`<br /><br /> Erfordert zwei Dereferenzierungsebenen.|Nicht möglich, da **ByRef** **ByRef** oder `ref` `ref` nicht verwendet werden kann.|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> Fügt eine Dereferenzierungsebene hinzu.|  
  
 Die Tabelle beschreibt die folgenden Richtlinien für Plattformaufrufdeklarationen:  
  
- Verwenden Sie eine Struktur, die durch einen Wert übergeben wird, wenn die nicht verwaltete Funktion keine Dereferenzierung erfordert.  
  
- Verwenden Sie eine Struktur, die durch einen Verweis übergeben wird, oder verwenden Sie eine Klasse, die durch einen Wert übergeben wird, wenn die nicht verwaltete Funktion eine Dereferenzierungsebene erfordert.  
  
- Verwenden Sie eine Klasse, die durch einen Verweis übergeben wird, wenn die nicht verwaltete Funktion zwei Dereferenzierungsebenen erfordert.  
  
## <a name="declaring-and-passing-structures"></a>Deklarieren und Übergeben von Strukturen  

 Im folgenden Beispiel wird gezeigt, wie Sie `Point`-Strukturen und `Rect`-Strukturen in verwaltetem Code definieren und die Typen als Parameter an die **PtInRect**-Funktion in der Datei „User32.dll“ übergeben können. **PtInRect** hat folgende nicht verwaltete Signatur:  
  
```cpp
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 Hinweis: Sie müssen die Rect-Struktur durch Verweis übergeben, da von der Funktion ein Zeiger auf einen RECT-Typ erwartet wird.  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Structure Point  
    Public x As Integer  
    Public y As Integer  
End Structure  
  
Public Structure <StructLayout(LayoutKind.Explicit)> Rect  
    <FieldOffset(0)> Public left As Integer  
    <FieldOffset(4)> Public top As Integer  
    <FieldOffset(8)> Public right As Integer  
    <FieldOffset(12)> Public bottom As Integer  
End Structure  
  
Friend Class NativeMethods
    Friend Declare Auto Function PtInRect Lib "user32.dll" (
        ByRef r As Rect, p As Point) As Boolean  
End Class  
```  
  
```csharp  
using System.Runtime.InteropServices;  
  
[StructLayout(LayoutKind.Sequential)]  
public struct Point {  
    public int x;  
    public int y;  
}
  
[StructLayout(LayoutKind.Explicit)]  
public struct Rect {  
    [FieldOffset(0)] public int left;  
    [FieldOffset(4)] public int top;  
    [FieldOffset(8)] public int right;  
    [FieldOffset(12)] public int bottom;  
}
  
internal static class NativeMethods
{  
    [DllImport("User32.dll")]  
    internal static extern bool PtInRect(ref Rect r, Point p);  
}  
```  
  
## <a name="declaring-and-passing-classes"></a>Deklarieren und Übergeben von Klassen  

 Sie können Member einer Klasse an nicht verwaltete DLL-Funktionen übergeben, solange die Klasse ein festes Layout für Member hat. Das folgende Beispiel veranschaulicht, wie Sie Member der `MySystemTime`-Klasse, die sequenziell definiert sind, an **GetSystemTime** in der Datei „User32.dll“ übergeben können. **GetSystemTime** hat folgende nicht verwaltete Signatur:  
  
```cpp
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 Im Unterschied zu Werttypen besitzen Klassen immer mindestens eine Dereferenzierungsebene.  
  
```vb  
Imports System.Runtime.InteropServices  
  
<StructLayout(LayoutKind.Sequential)> Public Class MySystemTime  
    Public wYear As Short  
    Public wMonth As Short  
    Public wDayOfWeek As Short
    Public wDay As Short  
    Public wHour As Short  
    Public wMinute As Short  
    Public wSecond As Short  
    Public wMiliseconds As Short  
End Class  
  
Friend Class NativeMethods  
    Friend Declare Auto Sub GetSystemTime Lib "Kernel32.dll" (
        sysTime As MySystemTime)  
    Friend Declare Auto Function MessageBox Lib "User32.dll" (
        hWnd As IntPtr, lpText As String, lpCaption As String, uType As UInteger) As Integer  
End Class  
  
Public Class TestPlatformInvoke
    Public Shared Sub Main()  
        Dim sysTime As New MySystemTime()  
        NativeMethods.GetSystemTime(sysTime)  
  
        Dim dt As String  
        dt = "System time is:" & ControlChars.CrLf & _  
              "Year: " & sysTime.wYear & _  
              ControlChars.CrLf & "Month: " & sysTime.wMonth & _  
              ControlChars.CrLf & "DayOfWeek: " & sysTime.wDayOfWeek & _  
              ControlChars.CrLf & "Day: " & sysTime.wDay  
        NativeMethods.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0)
    End Sub  
End Class  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public class MySystemTime {  
    public ushort wYear;
    public ushort wMonth;  
    public ushort wDayOfWeek;
    public ushort wDay;
    public ushort wHour;
    public ushort wMinute;
    public ushort wSecond;
    public ushort wMilliseconds;
}  
internal static class NativeMethods
{  
    [DllImport("Kernel32.dll")]  
    internal static extern void GetSystemTime(MySystemTime st);  
  
    [DllImport("user32.dll", CharSet = CharSet.Auto)]  
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);  
}  
  
public class TestPlatformInvoke  
{  
    public static void Main()  
    {  
        MySystemTime sysTime = new MySystemTime();  
        NativeMethods.GetSystemTime(sysTime);  
  
        string dt;  
        dt = "System time is: \n" +  
              "Year: " + sysTime.wYear + "\n" +  
              "Month: " + sysTime.wMonth + "\n" +  
              "DayOfWeek: " + sysTime.wDayOfWeek + "\n" +  
              "Day: " + sysTime.wDay;  
        NativeMethods.MessageBox(IntPtr.Zero, dt, "Platform Invoke Sample", 0);  
    }  
}  
```  
  
## <a name="see-also"></a>Siehe auch

- [Calling a DLL Function (Aufrufen einer DLL-Funktion)](calling-a-dll-function.md)
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
