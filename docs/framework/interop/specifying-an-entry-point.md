---
title: Angeben eines Einstiegspunktes
ms.date: 03/30/2017
helpviewer_keywords:
- EntryPoint field
- platform invoke, attribute fields
- attribute fields in platform invoke, EntryPoint
ms.assetid: d1247f08-0965-416a-b978-e0b50652dfe3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c278eca421020bea4f36f87eb6c8a9a8ba7d2a43
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658285"
---
# <a name="specifying-an-entry-point"></a><span data-ttu-id="4267a-102">Angeben eines Einstiegspunktes</span><span class="sxs-lookup"><span data-stu-id="4267a-102">Specifying an Entry Point</span></span>
<span data-ttu-id="4267a-103">Ein Einstiegspunkt identifiziert die Position einer Funktion in einer DLL.</span><span class="sxs-lookup"><span data-stu-id="4267a-103">An entry point identifies the location of a function in a DLL.</span></span> <span data-ttu-id="4267a-104">In einem verwalteten Projekt wird diese Funktion vom ursprünglichen Namen oder vom Ordinaleinstiegspunkt einer Zielfunktion über die Grenzen der Interoperation hinaus identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4267a-104">Within a managed project, the original name or ordinal entry point of a target function identifies that function across the interoperation boundary.</span></span> <span data-ttu-id="4267a-105">Außerdem können Sie dem Einstiegspunkt einen anderen Namen zuordnen und damit die Funktion umbenennen.</span><span class="sxs-lookup"><span data-stu-id="4267a-105">Further, you can map the entry point to a different name, effectively renaming the function.</span></span>  
  
 <span data-ttu-id="4267a-106">Aus folgenden Gründen kann es sinnvoll sein, eine DLL-Funktion umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="4267a-106">Following is a list of possible reasons to rename a DLL function:</span></span>  
  
-   <span data-ttu-id="4267a-107">Um keine API-Funktionsnamen zu verwenden, die zwischen Groß- und Kleinschreibung unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4267a-107">To avoid using case-sensitive API function names</span></span>  
  
-   <span data-ttu-id="4267a-108">Um die Konventionen vorhandener Namensstandards einzuhalten.</span><span class="sxs-lookup"><span data-stu-id="4267a-108">To comply with existing naming standards</span></span>  
  
-   <span data-ttu-id="4267a-109">Um Funktionen aufzunehmen, die verschiedene Datentypen verwenden (indem mehrere Versionen derselben DLL-Funktion deklariert werden).</span><span class="sxs-lookup"><span data-stu-id="4267a-109">To accommodate functions that take different data types (by declaring multiple versions of the same DLL function)</span></span>  
  
-   <span data-ttu-id="4267a-110">Um die Verwendung von APIs zu vereinfachen, die ANSI- und Unicode-Versionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4267a-110">To simplify using APIs that contain ANSI and Unicode versions</span></span>  
  
 <span data-ttu-id="4267a-111">In diesem Abschnitt wird das Umbenennen einer DLL-Funktion in verwaltetem Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="4267a-111">This topic demonstrates how to rename a DLL function in managed code.</span></span>  
  
## <a name="renaming-a-function-in-visual-basic"></a><span data-ttu-id="4267a-112">Umbenennen einer Funktion in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4267a-112">Renaming a Function in Visual Basic</span></span>  
 <span data-ttu-id="4267a-113">Visual Basic verwendet das **Function**-Schlüsselwort in der **Declare**-Anweisung, um das<xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>-Feld festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4267a-113">Visual Basic uses the **Function** keyword in the **Declare** statement to set the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field.</span></span> <span data-ttu-id="4267a-114">Das folgende Beispiel zeigt eine Basisdeklaration.</span><span class="sxs-lookup"><span data-stu-id="4267a-114">The following example shows a basic declaration.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
 <span data-ttu-id="4267a-115">Sie können den **MessageBox**-Einstiegspunkt durch **MsgBox** ersetzen, indem Sie das **Alias**-Schlüsselwort wie im folgenden Beispiel dargestellt in die Definition aufnehmen.</span><span class="sxs-lookup"><span data-stu-id="4267a-115">You can replace the **MessageBox** entry point with **MsgBox** by including the **Alias** keyword in your definition, as shown in the following example.</span></span> <span data-ttu-id="4267a-116">In beiden Beispielen erübrigt sich aufgrund des **Auto**-Schlüsselwortes die Angabe der Zeichensatzversion des Einstiegspunktes.</span><span class="sxs-lookup"><span data-stu-id="4267a-116">In both examples the **Auto** keyword eliminates the need to specify the character-set version of the entry point.</span></span> <span data-ttu-id="4267a-117">Weitere Informationen zum Auswählen eines Zeichensatzes finden Sie unter [Angeben eines Zeichensatzes](../../../docs/framework/interop/specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="4267a-117">For more information about selecting a character set, see [Specifying a Character Set](../../../docs/framework/interop/specifying-a-character-set.md).</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
    Declare Auto Function MsgBox Lib "user32.dll" _  
       Alias "MessageBox" (ByVal hWnd As Integer, ByVal txt As String,_  
       ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="renaming-a-function-in-c-and-c"></a><span data-ttu-id="4267a-118">Umbenennen einer Funktion in C# und C++</span><span class="sxs-lookup"><span data-stu-id="4267a-118">Renaming a Function in C# and C++</span></span>  
 <span data-ttu-id="4267a-119">Sie können das <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType>-Feld verwenden, um eine DLL-Funktion nach Name oder Ordinalzahl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4267a-119">You can use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint?displayProperty=nameWithType> field to specify a DLL function by name or ordinal.</span></span> <span data-ttu-id="4267a-120">Wenn der Name der Funktion in der Methodendefinition mit dem Einstiegspunkt in der DLL übereinstimmt, müssen Sie die Funktion nicht explizit mit dem **EntryPoint**-Feld identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4267a-120">If the name of the function in your method definition is the same as the entry point in the DLL, you do not have to explicitly identify the function with the **EntryPoint** field.</span></span> <span data-ttu-id="4267a-121">Andernfalls verwenden Sie eine der folgenden Attributformen zur Angabe eines Namens oder einer Ordinalzahl:</span><span class="sxs-lookup"><span data-stu-id="4267a-121">Otherwise, use one of the following attribute forms to indicate a name or ordinal:</span></span>  
  
```  
[DllImport("dllname", EntryPoint="Functionname")]  
[DllImport("dllname", EntryPoint="#123")]  
```  
  
 <span data-ttu-id="4267a-122">Hinweis: Für eine Ordinalzahl müssen Sie das Pfundzeichen (#) als Präfix verwenden.</span><span class="sxs-lookup"><span data-stu-id="4267a-122">Notice that you must prefix an ordinal with the pound sign (#).</span></span>  
  
 <span data-ttu-id="4267a-123">Im folgenden Beispiel wird veranschaulicht, wie Sie im Code **MessageBoxA** mit **MsgBox** ersetzen, indem Sie das **EntryPoint**-Feld verwenden.</span><span class="sxs-lookup"><span data-stu-id="4267a-123">The following example demonstrates how to replace **MessageBoxA** with **MsgBox** in your code by using the **EntryPoint** field.</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
  
public class Win32 {  
    [DllImport("user32.dll", EntryPoint="MessageBoxA")]  
    public static extern int MsgBox(int hWnd, String text, String caption,  
                                    uint type);  
}  
```  
  
```cpp  
using namespace System::Runtime::InteropServices;  
  
typedef void* HWND;  
[DllImport("user32", EntryPoint="MessageBoxA")]  
extern "C" int MsgBox(HWND hWnd,  
                      String*  pText,  
                      String*  pCaption,  
                      unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="4267a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4267a-124">See also</span></span>
- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="4267a-125">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="4267a-125">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="4267a-126">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="4267a-126">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)
- [<span data-ttu-id="4267a-127">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="4267a-127">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
