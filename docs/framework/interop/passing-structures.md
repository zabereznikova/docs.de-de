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
ms.openlocfilehash: eae28d6746cd89d98b659b9eb957f158e1319190
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620819"
---
# <a name="passing-structures"></a><span data-ttu-id="dfe3c-104">Übergeben von Strukturen</span><span class="sxs-lookup"><span data-stu-id="dfe3c-104">Passing Structures</span></span>
<span data-ttu-id="dfe3c-105">Bei vielen nicht verwalteten Funktionen wird erwartet, dass Member von Strukturen (benutzerdefinierte Typen in Visual Basic) oder Member von Klassen, die in verwaltetem Code definiert werden, als Parameter an die Funktion übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-105">Many unmanaged functions expect you to pass, as a parameter to the function, members of structures (user-defined types in Visual Basic) or members of classes that are defined in managed code.</span></span> <span data-ttu-id="dfe3c-106">Wenn Sie Strukturen oder Klassen an nicht verwalteten Code mithilfe von Plattformaufruf übergeben, müssen Sie zusätzliche Informationen angeben, um das ursprüngliche Layout und die ursprüngliche Ausrichtung beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-106">When passing structures or classes to unmanaged code using platform invoke, you must provide additional information to preserve the original layout and alignment.</span></span> <span data-ttu-id="dfe3c-107">Dieses Thema enthält eine Einführung in das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut, das Sie zum Definieren formatierter Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-107">This topic introduces the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute, which you use to define formatted types.</span></span> <span data-ttu-id="dfe3c-108">Sie können für verwaltete Strukturen und Klassen verschiedene vorhersagbare Layoutverhalten auswählen, die von der **LayoutKind**-Enumeration bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-108">For managed structures and classes, you can select from several predictable layout behaviors supplied by the **LayoutKind** enumeration.</span></span>  
  
 <span data-ttu-id="dfe3c-109">Es gibt einen entscheidenden Unterschied zwischen Struktur- und Klassentypen, der für die im vorliegenden Thema dargestellten Konzepte eine Schlüsselposition einnimmt.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-109">Central to the concepts presented in this topic is an important difference between structure and class types.</span></span> <span data-ttu-id="dfe3c-110">Strukturen sind Werttypen und Klassen sind Referenztypen, wobei Klassen immer mindestens eine Speicherdereferenzierungsebene (einen Zeiger auf einen Wert) bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-110">Structures are value types and classes are reference types — classes always provide at least one level of memory indirection (a pointer to a value).</span></span> <span data-ttu-id="dfe3c-111">Dieser Unterschied ist relevant, da nicht verwaltete Funktionen oftmals eine Dereferenzierung erfordern, wie durch die Signaturen in der ersten Spalte der folgenden Tabelle gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-111">This difference is important because unmanaged functions often demand indirection, as shown by the signatures in the first column of the following table.</span></span> <span data-ttu-id="dfe3c-112">Die verwalteten Struktur- und Klassendeklarationen in den anderen Spalten geben an, in welchem Ausmaß die Dereferenzierungsebene in der Deklaration angepasst werden kann. Es werden Deklarationen für Visual Basic und Visual C# bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-112">The managed structure and class declarations in the remaining columns show the degree to which you can adjust the level of indirection in your declaration.Declarations are provided for both Visual Basic and Visual C#.</span></span>  
  
|<span data-ttu-id="dfe3c-113">Nicht verwaltete Signatur</span><span class="sxs-lookup"><span data-stu-id="dfe3c-113">Unmanaged signature</span></span>|<span data-ttu-id="dfe3c-114">Verwaltete Deklaration:</span><span class="sxs-lookup"><span data-stu-id="dfe3c-114">Managed declaration:</span></span> <br /><span data-ttu-id="dfe3c-115">keine Dereferenzierung</span><span class="sxs-lookup"><span data-stu-id="dfe3c-115">no indirection</span></span><br />`Structure MyType`<br />`struct MyType;`|<span data-ttu-id="dfe3c-116">Verwaltete Deklaration:</span><span class="sxs-lookup"><span data-stu-id="dfe3c-116">Managed declaration:</span></span> <br /><span data-ttu-id="dfe3c-117">eine Dereferenzierungsebene</span><span class="sxs-lookup"><span data-stu-id="dfe3c-117">one level of indirection</span></span><br />`Class MyType`<br />`class MyType;`|  
|-------------------------|---------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|  
|`DoWork(MyType x);`<br /><br /> <span data-ttu-id="dfe3c-118">Erfordert 0 Dereferenzierungsebenen.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-118">Demands zero levels of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="dfe3c-119">Fügt 0 Dereferenzierungsebenen hinzu.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-119">Adds zero levels of indirection.</span></span>|<span data-ttu-id="dfe3c-120">Nicht möglich, da bereits eine Dereferenzierungsebene besteht.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-120">Not possible because there is already one level of indirection.</span></span>|  
|`DoWork(MyType* x);`<br /><br /> <span data-ttu-id="dfe3c-121">Erfordert eine Dereferenzierungsebene.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-121">Demands one level of indirection.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="dfe3c-122">Fügt eine Dereferenzierungsebene hinzu.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-122">Adds one level of indirection.</span></span>|`DoWork(ByVal x As MyType)` <br /> `DoWork(MyType x)`<br /><br /> <span data-ttu-id="dfe3c-123">Fügt 0 Dereferenzierungsebenen hinzu.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-123">Adds zero levels of indirection.</span></span>|  
|`DoWork(MyType** x);`<br /><br /> <span data-ttu-id="dfe3c-124">Erfordert zwei Dereferenzierungsebenen.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-124">Demands two levels of indirection.</span></span>|<span data-ttu-id="dfe3c-125">Nicht möglich, da **ByRef** **ByRef** oder `ref` `ref` nicht verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-125">Not possible because **ByRef** **ByRef** or `ref` `ref` cannot be used.</span></span>|`DoWork(ByRef x As MyType)` <br /> `DoWork(ref MyType x)`<br /><br /> <span data-ttu-id="dfe3c-126">Fügt eine Dereferenzierungsebene hinzu.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-126">Adds one level of indirection.</span></span>|  
  
 <span data-ttu-id="dfe3c-127">Die Tabelle beschreibt die folgenden Richtlinien für Plattformaufrufdeklarationen:</span><span class="sxs-lookup"><span data-stu-id="dfe3c-127">The table describes the following guidelines for platform invoke declarations:</span></span>  
  
- <span data-ttu-id="dfe3c-128">Verwenden Sie eine Struktur, die durch einen Wert übergeben wird, wenn die nicht verwaltete Funktion keine Dereferenzierung erfordert.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-128">Use a structure passed by value when the unmanaged function demands no indirection.</span></span>  
  
- <span data-ttu-id="dfe3c-129">Verwenden Sie eine Struktur, die durch einen Verweis übergeben wird, oder verwenden Sie eine Klasse, die durch einen Wert übergeben wird, wenn die nicht verwaltete Funktion eine Dereferenzierungsebene erfordert.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-129">Use either a structure passed by reference or a class passed by value when the unmanaged function demands one level of indirection.</span></span>  
  
- <span data-ttu-id="dfe3c-130">Verwenden Sie eine Klasse, die durch einen Verweis übergeben wird, wenn die nicht verwaltete Funktion zwei Dereferenzierungsebenen erfordert.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-130">Use a class passed by reference when the unmanaged function demands two levels of indirection.</span></span>  
  
## <a name="declaring-and-passing-structures"></a><span data-ttu-id="dfe3c-131">Deklarieren und Übergeben von Strukturen</span><span class="sxs-lookup"><span data-stu-id="dfe3c-131">Declaring and Passing Structures</span></span>  
 <span data-ttu-id="dfe3c-132">Im folgenden Beispiel wird gezeigt, wie Sie `Point`-Strukturen und `Rect`-Strukturen in verwaltetem Code definieren und die Typen als Parameter an die **PtInRect**-Funktion in der Datei „User32.dll“ übergeben können.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-132">The following example shows how to define the `Point` and `Rect` structures in managed code, and pass the types as parameter to the **PtInRect** function in the User32.dll file.</span></span> <span data-ttu-id="dfe3c-133">**PtInRect** hat folgende nicht verwaltete Signatur:</span><span class="sxs-lookup"><span data-stu-id="dfe3c-133">**PtInRect** has the following unmanaged signature:</span></span>  
  
```cpp
BOOL PtInRect(const RECT *lprc, POINT pt);  
```  
  
 <span data-ttu-id="dfe3c-134">Hinweis: Sie müssen die Rect-Struktur durch Verweis übergeben, da von der Funktion ein Zeiger auf einen RECT-Typ erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-134">Notice that you must pass the Rect structure by reference, since the function expects a pointer to a RECT type.</span></span>  
  
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
  
## <a name="declaring-and-passing-classes"></a><span data-ttu-id="dfe3c-135">Deklarieren und Übergeben von Klassen</span><span class="sxs-lookup"><span data-stu-id="dfe3c-135">Declaring and Passing Classes</span></span>  
 <span data-ttu-id="dfe3c-136">Sie können Member einer Klasse an nicht verwaltete DLL-Funktionen übergeben, solange die Klasse ein festes Layout für Member hat.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-136">You can pass members of a class to an unmanaged DLL function, as long as the class has a fixed member layout.</span></span> <span data-ttu-id="dfe3c-137">Das folgende Beispiel veranschaulicht, wie Sie Member der `MySystemTime`-Klasse, die sequenziell definiert sind, an **GetSystemTime** in der Datei „User32.dll“ übergeben können.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-137">The following example demonstrates how to pass members of the `MySystemTime` class, which are defined in sequential order, to the **GetSystemTime** in the User32.dll file.</span></span> <span data-ttu-id="dfe3c-138">**GetSystemTime** hat folgende nicht verwaltete Signatur:</span><span class="sxs-lookup"><span data-stu-id="dfe3c-138">**GetSystemTime** has the following unmanaged signature:</span></span>  
  
```cpp
void GetSystemTime(SYSTEMTIME* SystemTime);  
```  
  
 <span data-ttu-id="dfe3c-139">Im Unterschied zu Werttypen besitzen Klassen immer mindestens eine Dereferenzierungsebene.</span><span class="sxs-lookup"><span data-stu-id="dfe3c-139">Unlike value types, classes always have at least one level of indirection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dfe3c-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfe3c-140">See also</span></span>

- [<span data-ttu-id="dfe3c-141">Calling a DLL Function (Aufrufen einer DLL-Funktion)</span><span class="sxs-lookup"><span data-stu-id="dfe3c-141">Calling a DLL Function</span></span>](calling-a-dll-function.md)
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- <xref:System.Runtime.InteropServices.FieldOffsetAttribute>
