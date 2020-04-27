---
title: Angeben eines Zeichensatzes
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
ms.openlocfilehash: 0db1cd8d75b45f6d718168793c873e5867028269
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125179"
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="dd95d-102">Angeben eines Zeichensatzes</span><span class="sxs-lookup"><span data-stu-id="dd95d-102">Specifying a Character Set</span></span>
<span data-ttu-id="dd95d-103">Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld steuert das Marshallen von Zeichenfolgen und bestimmt, wie Plattformaufrufe Funktionsnamen in einer DLL finden.</span><span class="sxs-lookup"><span data-stu-id="dd95d-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="dd95d-104">In diesem Abschnitt werden beide Verhaltensweisen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dd95d-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="dd95d-105">Einige APIs exportieren zwei Versionen von Funktionen, die Zeichenfolgenargumente verwenden: schmal (ANSI) und breit (Unicode).</span><span class="sxs-lookup"><span data-stu-id="dd95d-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="dd95d-106">Die Windows-API enthält z.B. die folgenden Einstiegspunktnamen für die **MessageBox**-Funktion:</span><span class="sxs-lookup"><span data-stu-id="dd95d-106">The Windows API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
- <span data-ttu-id="dd95d-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="dd95d-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="dd95d-108">Stellt einen 1-Byte-Zeichensatz im ANSI-Format zur Verfügung, der durch ein zum Namen des Einstiegspunkts hinzugefügten „A“ unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="dd95d-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="dd95d-109">Aufrufe von **MessageBoxA** marshallen Zeichenfolgen immer im ANSI-Format.</span><span class="sxs-lookup"><span data-stu-id="dd95d-109">Calls to **MessageBoxA** always marshal strings in ANSI format.</span></span>  
  
- <span data-ttu-id="dd95d-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="dd95d-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="dd95d-111">Stellt einen 2-Byte-Zeichensatz im Unicode-Format zur Verfügung, der durch ein zum Namen des Einstiegspunkts hinzugefügten „W“ unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="dd95d-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="dd95d-112">Aufrufe von **MessageBoxW** marshallen Zeichenfolgen immer im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="dd95d-112">Calls to **MessageBoxW** always marshal strings in Unicode format.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="dd95d-113">Marshallen von Zeichenfolgen und Namensübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="dd95d-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="dd95d-114">Das Feld `CharSet` akzeptiert die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="dd95d-114">The `CharSet` field accepts the following values:</span></span>  
  
 <span data-ttu-id="dd95d-115"><xref:System.Runtime.InteropServices.CharSet.Ansi> (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="dd95d-115"><xref:System.Runtime.InteropServices.CharSet.Ansi> (default value)</span></span>  
  
- <span data-ttu-id="dd95d-116">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="dd95d-116">String marshaling</span></span>  
  
     <span data-ttu-id="dd95d-117">Plattformaufruf marshallt Zeichenfolgen aus dem verwalteten Format (Unicode) in das ANSI-Format.</span><span class="sxs-lookup"><span data-stu-id="dd95d-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
- <span data-ttu-id="dd95d-118">Namensübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="dd95d-118">Name matching</span></span>  
  
     <span data-ttu-id="dd95d-119">Wenn das <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>-Feld `true` entspricht, wie es standardmäßig in Visual Basic der Fall ist, sucht der Plattformaufruf nur nach dem von Ihnen angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="dd95d-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="dd95d-120">Wenn Sie z.B. **MessageBox** angeben, sucht der Plattformaufruf nach **MessageBox** und schlägt fehl, wenn er die exakte Schreibweise nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="dd95d-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="dd95d-121">Wenn das Feld `ExactSpelling``false` ist, wie es standardmäßig in C++ und C# der Fall ist, sucht der Plattformaufruf zunächst nach dem unbeschädigten Alias (**MessageBox**) und dann nach dem beschädigten Namen (**MessageBoxA**), wenn der unbeschädigten Alias nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="dd95d-121">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="dd95d-122">Beachten Sie, dass die Namensübereinstimmung des ANSI-Verhaltens sich von der Namensübereinstimmung des Unicode-Verhaltens unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="dd95d-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Unicode>  
  
- <span data-ttu-id="dd95d-123">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="dd95d-123">String marshaling</span></span>  
  
     <span data-ttu-id="dd95d-124">Der Plattformaufruf kopiert Zeichenfolgen aus dem verwalteten Format (Unicode) in Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="dd95d-124">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
- <span data-ttu-id="dd95d-125">Namensübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="dd95d-125">Name matching</span></span>  
  
     <span data-ttu-id="dd95d-126">Wenn das `ExactSpelling`-Feld `true` entspricht, wie es standardmäßig in Visual Basic der Fall ist, sucht der Plattformaufruf nur nach dem von Ihnen angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="dd95d-126">When the `ExactSpelling` field is `true`, as it is by default in Visual Basic, platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="dd95d-127">Wenn Sie z.B. **MessageBox** angeben, sucht der Plattformaufruf nach **MessageBox** und schlägt fehl, wenn er die exakte Schreibweise nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="dd95d-127">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="dd95d-128">Wenn das Feld `ExactSpelling``false` ist, wie es standardmäßig in C++ und C# der Fall ist, sucht der Plattformaufruf zunächst nach dem beschädigten Namen (**MessageBoxW**) und dann nach dem unbeschädigten Alias (**MessageBox**), wenn der beschädigte Alias nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="dd95d-128">When the `ExactSpelling` field is `false`, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="dd95d-129">Beachten Sie, dass das Verhalten der Namensübereinstimmung von Unicode sich vom Verhalten der Namensübereinstimmung von ANSI unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="dd95d-129">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <xref:System.Runtime.InteropServices.CharSet.Auto>  
  
- <span data-ttu-id="dd95d-130">Der Plattformaufruf basierend auf der Zielplattform zur Laufzeit wählt zwischen ANSI- und Unicode-Formaten.</span><span class="sxs-lookup"><span data-stu-id="dd95d-130">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="dd95d-131">Festlegen eines Zeichensatzes in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dd95d-131">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="dd95d-132">Das folgende Beispiel deklariert die **MessageBox**-Funktion dreimal, wobei der Zeichensatz sich jedes Mal unterschiedlich verhält.</span><span class="sxs-lookup"><span data-stu-id="dd95d-132">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="dd95d-133">Sie können das Verhalten des Zeichensatzes in Visual Basic angeben, indem Sie die Schlüsselwörter **Ansi**, **Unicode** oder **Auto** zur Deklarationsanweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dd95d-133">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="dd95d-134">Wenn Sie das Zeichensatzschlüsselwort weglassen, wie es in der ersten Deklarationsanweisung der Fall ist, erfolgt das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld standardmäßig im ANSI-Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="dd95d-134">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="dd95d-135">Die zweite und dritte Anweisung in diesem Beispiel geben einen Zeichensatz explizit mit einem Schlüsselwort an.</span><span class="sxs-lookup"><span data-stu-id="dd95d-135">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Function MessageBoxA Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Unicode Function MessageBoxW Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer

    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="dd95d-136">Festlegen eines Zeichensatzes in C# und C++</span><span class="sxs-lookup"><span data-stu-id="dd95d-136">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="dd95d-137">Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld identifiziert den zugrunde liegenden Zeichensatz als ANSI oder Unicode.</span><span class="sxs-lookup"><span data-stu-id="dd95d-137">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="dd95d-138">Der Zeichensatz steuert, wie die Zeichenfolgenargumente an eine Methode gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dd95d-138">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="dd95d-139">Verwenden Sie eines der folgenden Formate, um den Zeichensatz anzugeben:</span><span class="sxs-lookup"><span data-stu-id="dd95d-139">Use one of the following forms to indicate the character set:</span></span>  
  
```csharp
[DllImport("DllName", CharSet = CharSet.Ansi)]
[DllImport("DllName", CharSet = CharSet.Unicode)]
[DllImport("DllName", CharSet = CharSet.Auto)]
```
  
```cpp
[DllImport("DllName", CharSet = CharSet::Ansi)]
[DllImport("DllName", CharSet = CharSet::Unicode)]
[DllImport("DllName", CharSet = CharSet::Auto)]
```
  
 <span data-ttu-id="dd95d-140">Im folgenden Beispiel werden drei verwaltete Definitionen der **MessageBox**-Funktion angezeigt, die einen Zeichensatz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd95d-140">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="dd95d-141">Durch die Auslassung wird das Feld `CharSet` in der ersten Definition standardmäßig in ANSI-Zeichensatz verwandelt.</span><span class="sxs-lookup"><span data-stu-id="dd95d-141">In the first definition, by its omission, the `CharSet` field defaults to the ANSI character set.</span></span>  
  
```csharp  
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll")]
    internal static extern int MessageBoxA(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Unicode)]
    internal static extern int MessageBoxW(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);

    [DllImport("user32.dll", CharSet = CharSet.Auto)]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```  
  
```cpp
typedef void* HWND;

// Can use MessageBox or MessageBoxA.
[DllImport("user32")]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Can use MessageBox or MessageBoxW.
[DllImport("user32", CharSet = CharSet::Unicode)]
extern "C" int MessageBoxW(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);

// Must use MessageBox.
[DllImport("user32", CharSet = CharSet::Auto)]
extern "C" int MessageBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a><span data-ttu-id="dd95d-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd95d-142">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="dd95d-143">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="dd95d-143">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="dd95d-144">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="dd95d-144">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="dd95d-145">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="dd95d-145">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
