---
title: Angeben eines Einstiegspunktes
description: Erfahren Sie, wie Sie einen Einstiegspunkt angeben, der den Speicherort einer Funktion in einer DLL identifiziert. Sie können die Funktion umbenennen, indem Sie den Einstiegspunkt einem anderen Namen zuordnen.
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
ms.openlocfilehash: 5628c54103410d127c2f9c4f56e1c6f897ada754
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86282020"
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="9e3bc-104">Angeben eines Einstiegspunktes</span><span class="sxs-lookup"><span data-stu-id="9e3bc-104">Specifying an Entry Point</span></span>

<span data-ttu-id="9e3bc-105">Ein Einstiegspunkt identifiziert die Position einer Funktion in einer DLL.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-105">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="9e3bc-106">In einem verwalteten Projekt wird diese Funktion vom ursprünglichen Namen oder vom Ordinaleinstiegspunkt einer Zielfunktion über die Grenzen der Interoperation hinaus identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-106">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="9e3bc-107">Außerdem können Sie dem Einstiegspunkt einen anderen Namen zuordnen und damit die Funktion umbenennen.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-107">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="9e3bc-108">Aus folgenden Gründen kann es sinnvoll sein, eine DLL-Funktion umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="9e3bc-108">The following is a list of possible reasons to rename a DLL function:</span></span>  
  
- <span data-ttu-id="9e3bc-109">Um keine API-Funktionsnamen zu verwenden, die zwischen Groß- und Kleinschreibung unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-109">To avoid using case-sensitive API function names</span></span>  
  
- <span data-ttu-id="9e3bc-110">Um die Konventionen vorhandener Namensstandards einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-110">To comply with existing naming standards</span></span>  
  
- <span data-ttu-id="9e3bc-111">Um Funktionen aufzunehmen, die verschiedene Datentypen verwenden (indem mehrere Versionen derselben DLL-Funktion deklariert werden).</span><span class="sxs-lookup"><span data-stu-id="9e3bc-111">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
- <span data-ttu-id="9e3bc-112">Um die Verwendung von APIs zu vereinfachen, die ANSI- und Unicode-Versionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-112">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="9e3bc-113">In diesem Abschnitt wird das Umbenennen einer DLL-Funktion in verwaltetem Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-113">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="9e3bc-114">Umbenennen einer Funktion in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="9e3bc-114">Renaming a Function in Visual Basic</span></span>  

<span data-ttu-id="9e3bc-115">Visual Basic verwendet das **Function**-Schlüsselwort in der **Declare**-Anweisung, um das<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>-Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-115">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="9e3bc-116">Das folgende Beispiel zeigt eine Basisdeklaration.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-116">The following example shows a basic declaration.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
<span data-ttu-id="9e3bc-117">Sie können den **MessageBox**-Einstiegspunkt durch **MsgBox** ersetzen, indem Sie das **Alias**-Schlüsselwort wie im folgenden Beispiel dargestellt in die Definition aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-117">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="9e3bc-118">In beiden Beispielen erübrigt sich aufgrund des **Auto**-Schlüsselwortes die Angabe der Zeichensatzversion des Einstiegspunktes.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-118">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="9e3bc-119">Weitere Informationen zum Auswählen eines Zeichensatzes finden Sie unter [Angeben eines Zeichensatzes](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="9e3bc-119">For more information about selecting a character set, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MsgBox _
        Lib "user32.dll" Alias "MessageBox" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="9e3bc-120">Umbenennen einer Funktion in C# und C++</span><span class="sxs-lookup"><span data-stu-id="9e3bc-120">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="9e3bc-121">Sie können das <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>-Feld verwenden, um eine DLL-Funktion nach Name oder Ordinalzahl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-121">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="9e3bc-122">Wenn der Name der Funktion in der Methodendefinition mit dem Einstiegspunkt in der DLL übereinstimmt, müssen Sie die Funktion nicht explizit mit dem **EntryPoint**-Feld identifizieren.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-122">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="9e3bc-123">Andernfalls verwenden Sie eine der folgenden Attributformen zur Angabe eines Namens oder einer Ordinalzahl:</span><span class="sxs-lookup"><span data-stu-id="9e3bc-123">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 <span data-ttu-id="9e3bc-124">Hinweis: Für eine Ordinalzahl müssen Sie das Pfundzeichen (#) als Präfix verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-124">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="9e3bc-125">Im folgenden Beispiel wird veranschaulicht, wie Sie im Code **MessageBoxA** mit **MsgBox** ersetzen, indem Sie das **EntryPoint**-Feld verwenden.</span><span class="sxs-lookup"><span data-stu-id="9e3bc-125">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp
using System;
using System.Runtime.InteropServices;

internal static class NativeMethods
{
    [DllImport("user32.dll", EntryPoint = "MessageBoxA")]
    internal static extern int MessageBox(
        IntPtr hWnd, string lpText, string lpCaption, uint uType);
}
```
  
```cpp
using namespace System;
using namespace System::Runtime::InteropServices;

typedef void* HWND;
[DllImport("user32", EntryPoint = "MessageBoxA")]
extern "C" int MsgBox(
    HWND hWnd, String* lpText, String* lpCaption, unsigned int uType);
```
  
## <a name="see-also"></a><span data-ttu-id="9e3bc-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e3bc-126">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="9e3bc-127">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="9e3bc-127">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="9e3bc-128">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="9e3bc-128">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="9e3bc-129">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="9e3bc-129">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
