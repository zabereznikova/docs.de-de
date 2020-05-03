---
title: Angeben eines Einstiegspunktes
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
ms.openlocfilehash: c5f8f735dd3e8c359f88044a532c29303237acc8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181309"
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="76ced-102">Angeben eines Einstiegspunktes</span><span class="sxs-lookup"><span data-stu-id="76ced-102">Specifying an Entry Point</span></span>

<span data-ttu-id="76ced-103">Ein Einstiegspunkt identifiziert die Position einer Funktion in einer DLL.</span><span class="sxs-lookup"><span data-stu-id="76ced-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="76ced-104">In einem verwalteten Projekt wird diese Funktion vom ursprünglichen Namen oder vom Ordinaleinstiegspunkt einer Zielfunktion über die Grenzen der Interoperation hinaus identifiziert.</span><span class="sxs-lookup"><span data-stu-id="76ced-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="76ced-105">Außerdem können Sie dem Einstiegspunkt einen anderen Namen zuordnen und damit die Funktion umbenennen.</span><span class="sxs-lookup"><span data-stu-id="76ced-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="76ced-106">Aus folgenden Gründen kann es sinnvoll sein, eine DLL-Funktion umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="76ced-106">The following is a list of possible reasons to rename a DLL function:</span></span>  
  
- <span data-ttu-id="76ced-107">Um keine API-Funktionsnamen zu verwenden, die zwischen Groß- und Kleinschreibung unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="76ced-107">To avoid using case-sensitive API function names</span></span>  
  
- <span data-ttu-id="76ced-108">Um die Konventionen vorhandener Namensstandards einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="76ced-108">To comply with existing naming standards</span></span>  
  
- <span data-ttu-id="76ced-109">Um Funktionen aufzunehmen, die verschiedene Datentypen verwenden (indem mehrere Versionen derselben DLL-Funktion deklariert werden).</span><span class="sxs-lookup"><span data-stu-id="76ced-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
- <span data-ttu-id="76ced-110">Um die Verwendung von APIs zu vereinfachen, die ANSI- und Unicode-Versionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="76ced-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="76ced-111">In diesem Abschnitt wird das Umbenennen einer DLL-Funktion in verwaltetem Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="76ced-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="76ced-112">Umbenennen einer Funktion in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="76ced-112">Renaming a Function in Visual Basic</span></span>  

<span data-ttu-id="76ced-113">Visual Basic verwendet das **Function**-Schlüsselwort in der **Declare**-Anweisung, um das<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>-Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="76ced-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="76ced-114">Das folgende Beispiel zeigt eine Basisdeklaration.</span><span class="sxs-lookup"><span data-stu-id="76ced-114">The following example shows a basic declaration.</span></span>  
  
```vb
Friend Class NativeMethods
    Friend Declare Auto Function MessageBox Lib "user32.dll" (
        ByVal hWnd As IntPtr,
        ByVal lpText As String,
        ByVal lpCaption As String,
        ByVal uType As UInteger) As Integer
End Class
```
  
<span data-ttu-id="76ced-115">Sie können den **MessageBox**-Einstiegspunkt durch **MsgBox** ersetzen, indem Sie das **Alias**-Schlüsselwort wie im folgenden Beispiel dargestellt in die Definition aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="76ced-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="76ced-116">In beiden Beispielen erübrigt sich aufgrund des **Auto**-Schlüsselwortes die Angabe der Zeichensatzversion des Einstiegspunktes.</span><span class="sxs-lookup"><span data-stu-id="76ced-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="76ced-117">Weitere Informationen zum Auswählen eines Zeichensatzes finden Sie unter [Angeben eines Zeichensatzes](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="76ced-117">For more information about selecting a character set, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
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
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="76ced-118">Umbenennen einer Funktion in C# und C++</span><span class="sxs-lookup"><span data-stu-id="76ced-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="76ced-119">Sie können das <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>-Feld verwenden, um eine DLL-Funktion nach Name oder Ordinalzahl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="76ced-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="76ced-120">Wenn der Name der Funktion in der Methodendefinition mit dem Einstiegspunkt in der DLL übereinstimmt, müssen Sie die Funktion nicht explizit mit dem **EntryPoint**-Feld identifizieren.</span><span class="sxs-lookup"><span data-stu-id="76ced-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="76ced-121">Andernfalls verwenden Sie eine der folgenden Attributformen zur Angabe eines Namens oder einer Ordinalzahl:</span><span class="sxs-lookup"><span data-stu-id="76ced-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```csharp
[DllImport("DllName", EntryPoint = "Functionname")]
[DllImport("DllName", EntryPoint = "#123")]
```
  
 <span data-ttu-id="76ced-122">Hinweis: Für eine Ordinalzahl müssen Sie das Pfundzeichen (#) als Präfix verwenden.</span><span class="sxs-lookup"><span data-stu-id="76ced-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="76ced-123">Im folgenden Beispiel wird veranschaulicht, wie Sie im Code **MessageBoxA** mit **MsgBox** ersetzen, indem Sie das **EntryPoint**-Feld verwenden.</span><span class="sxs-lookup"><span data-stu-id="76ced-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="76ced-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76ced-124">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="76ced-125">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="76ced-125">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="76ced-126">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="76ced-126">Platform Invoke Examples</span></span>](platform-invoke-examples.md)
- [<span data-ttu-id="76ced-127">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="76ced-127">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)
