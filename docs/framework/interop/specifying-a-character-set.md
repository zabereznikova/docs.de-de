---
title: Angeben eines Zeichensatzes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- platform invoke, attribute fields
- attribute fields in platform invoke, CharSet
- CharSet field
ms.assetid: a8347eb1-295f-46b9-8a78-63331f9ecc50
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: afb2ae519b4a3d52c590f050ba728286898373ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="specifying-a-character-set"></a><span data-ttu-id="20176-102">Angeben eines Zeichensatzes</span><span class="sxs-lookup"><span data-stu-id="20176-102">Specifying a Character Set</span></span>
<span data-ttu-id="20176-103">Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld steuert das Marshallen von Zeichenfolgen und bestimmt, wie Plattformaufrufe Funktionsnamen in einer DLL finden.</span><span class="sxs-lookup"><span data-stu-id="20176-103">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field controls string marshaling and determines how platform invoke finds function names in a DLL.</span></span> <span data-ttu-id="20176-104">In diesem Abschnitt werden beide Verhaltensweisen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="20176-104">This topic describes both behaviors.</span></span>  
  
 <span data-ttu-id="20176-105">Einige APIs exportieren zwei Versionen von Funktionen, die Zeichenfolgenargumente verwenden: schmal (ANSI) und breit (Unicode).</span><span class="sxs-lookup"><span data-stu-id="20176-105">Some APIs export two versions of functions that take string arguments: narrow (ANSI) and wide (Unicode).</span></span> <span data-ttu-id="20176-106">Die Win32-API enthält z.B. die folgenden Einstiegspunktnamen für die **MessageBox**-Funktion:</span><span class="sxs-lookup"><span data-stu-id="20176-106">The Win32 API, for instance, includes the following entry-point names for the **MessageBox** function:</span></span>  
  
-   <span data-ttu-id="20176-107">**MessageBoxA**</span><span class="sxs-lookup"><span data-stu-id="20176-107">**MessageBoxA**</span></span>  
  
     <span data-ttu-id="20176-108">Stellt einen 1-Byte-Zeichensatz im ANSI-Format zur Verfügung, der durch ein zum Namen des Einstiegspunkts hinzugefügten „A“ unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="20176-108">Provides 1-byte character ANSI formatting, distinguished by an "A" appended to the entry-point name.</span></span> <span data-ttu-id="20176-109">Aufrufe von **MessageBoxA** marshallen Zeichenfolgen immer im ANSI-Format, was auf Windows 95- und Windows 98-Plattformen üblich ist.</span><span class="sxs-lookup"><span data-stu-id="20176-109">Calls to **MessageBoxA** always marshal strings in ANSI format, as is common on Windows 95 and Windows 98 platforms.</span></span>  
  
-   <span data-ttu-id="20176-110">**MessageBoxW**</span><span class="sxs-lookup"><span data-stu-id="20176-110">**MessageBoxW**</span></span>  
  
     <span data-ttu-id="20176-111">Stellt einen 2-Byte-Zeichensatz im Unicode-Format zur Verfügung, der durch ein zum Namen des Einstiegspunkts hinzugefügten „W“ unterschieden wird.</span><span class="sxs-lookup"><span data-stu-id="20176-111">Provides 2-byte character Unicode formatting, distinguished by a "W" appended to the entry-point name.</span></span> <span data-ttu-id="20176-112">Aufrufe von **MessageBoxA** marshallen Zeichenfolgen immer im Unicode-Format, was auf Windows NT-, Windows 2000- und Windows XP-Plattformen üblich ist.</span><span class="sxs-lookup"><span data-stu-id="20176-112">Calls to **MessageBoxW** always marshal strings in Unicode format, as is common on Windows NT, Windows 2000, and Windows XP platforms.</span></span>  
  
## <a name="string-marshaling-and-name-matching"></a><span data-ttu-id="20176-113">Marshallen von Zeichenfolgen und Namensübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="20176-113">String Marshaling and Name Matching</span></span>  
 <span data-ttu-id="20176-114">Das **CharSet**-Feld akzeptiert die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="20176-114">The **CharSet** field accepts the following values:</span></span>  
  
 <span data-ttu-id="20176-115">**CharSet.Ansi** (Standardwert)</span><span class="sxs-lookup"><span data-stu-id="20176-115">**CharSet.Ansi** (default value)</span></span>  
  
-   <span data-ttu-id="20176-116">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="20176-116">String marshaling</span></span>  
  
     <span data-ttu-id="20176-117">Plattformaufruf marshallt Zeichenfolgen aus dem verwalteten Format (Unicode) in das ANSI-Format.</span><span class="sxs-lookup"><span data-stu-id="20176-117">Platform invoke marshals strings from their managed format (Unicode) to ANSI format.</span></span>  
  
-   <span data-ttu-id="20176-118">Namensübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="20176-118">Name matching</span></span>  
  
     <span data-ttu-id="20176-119">Wenn das <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType>-Feld **TRUE**entspricht, wie es standardmäßig in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] der Fall ist, sucht der Plattformaufruf nur nach dem von Ihnen angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="20176-119">When the <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling?displayProperty=nameWithType> field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="20176-120">Wenn Sie z.B. **MessageBox** angeben, sucht der Plattformaufruf nach **MessageBox** und schlägt fehl, wenn er die exakte Schreibweise nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="20176-120">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails when it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="20176-121">Wenn das **ExactSpelling**-Feld **FALSE** ist, wie es standardmäßig in C++ und C# der Fall ist, sucht der Plattformaufruf zunächst nach dem zerlegten Alias (**MessageBox**), und dann nach dem ergänzten Namen (**MessageBoxA**), wenn der zerlegte Alias nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="20176-121">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the unmangled alias first (**MessageBox**), then the mangled name (**MessageBoxA**) if the unmangled alias is not found.</span></span> <span data-ttu-id="20176-122">Beachten Sie, dass die Namensübereinstimmung des ANSI-Verhaltens sich von der Namensübereinstimmung des Unicode-Verhaltens unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="20176-122">Notice that ANSI name-matching behavior differs from Unicode name-matching behavior.</span></span>  
  
 <span data-ttu-id="20176-123">**CharSet.Unicode**</span><span class="sxs-lookup"><span data-stu-id="20176-123">**CharSet.Unicode**</span></span>  
  
-   <span data-ttu-id="20176-124">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="20176-124">String marshaling</span></span>  
  
     <span data-ttu-id="20176-125">Der Plattformaufruf kopiert Zeichenfolgen aus dem verwalteten Format (Unicode) in Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="20176-125">Platform invoke copies strings from their managed format (Unicode) to Unicode format.</span></span>  
  
-   <span data-ttu-id="20176-126">Namensübereinstimmung</span><span class="sxs-lookup"><span data-stu-id="20176-126">Name matching</span></span>  
  
     <span data-ttu-id="20176-127">Wenn das Feld **ExactSpelling** **TRUE** ist, wie es standardmäßig in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] der Fall ist, sucht der Plattformaufruf nur nach dem von Ihnen angegebenen Namen.</span><span class="sxs-lookup"><span data-stu-id="20176-127">When the **ExactSpelling** field is **true**, as it is by default in [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], platform invoke searches only for the name you specify.</span></span> <span data-ttu-id="20176-128">Wenn Sie z.B. **MessageBox** angeben, sucht der Plattformaufruf nach **MessageBox** und schlägt fehl, wenn er die exakte Schreibweise nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="20176-128">For example, if you specify **MessageBox**, platform invoke searches for **MessageBox** and fails if it cannot locate the exact spelling.</span></span>  
  
     <span data-ttu-id="20176-129">Wenn das **ExactSpelling**-Feld **FALSE** ist, wie es standardmäßig in C++ und C# der Fall ist, sucht der Plattformaufruf zunächst nach dem ergänzten Namen (**MessageBoxW**), und dann nach dem zerlegten Alias (**MessageBox**), wenn der ergänzte Name nicht gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="20176-129">When the **ExactSpelling** field is **false**, as it is by default in C++ and C#, platform invoke searches for the mangled name first (**MessageBoxW**), then the unmangled alias (**MessageBox**) if the mangled name is not found.</span></span> <span data-ttu-id="20176-130">Beachten Sie, dass das Verhalten der Namensübereinstimmung von Unicode sich vom Verhalten der Namensübereinstimmung von ANSI unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="20176-130">Notice that Unicode name-matching behavior differs from ANSI name-matching behavior.</span></span>  
  
 <span data-ttu-id="20176-131">**CharSet.Auto**</span><span class="sxs-lookup"><span data-stu-id="20176-131">**CharSet.Auto**</span></span>  
  
-   <span data-ttu-id="20176-132">Der Plattformaufruf basierend auf der Zielplattform zur Laufzeit wählt zwischen ANSI- und Unicode-Formaten.</span><span class="sxs-lookup"><span data-stu-id="20176-132">Platform invoke chooses between ANSI and Unicode formats at run time, based on the target platform.</span></span>  
  
## <a name="specifying-a-character-set-in-visual-basic"></a><span data-ttu-id="20176-133">Festlegen eines Zeichensatzes in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20176-133">Specifying a Character Set in Visual Basic</span></span>  
 <span data-ttu-id="20176-134">Das folgende Beispiel deklariert die **MessageBox**-Funktion dreimal, wobei der Zeichensatz sich jedes Mal unterschiedlich verhält.</span><span class="sxs-lookup"><span data-stu-id="20176-134">The following example declares the **MessageBox** function three times, each time with different character-set behavior.</span></span> <span data-ttu-id="20176-135">Sie können das Verhalten des Zeichensatzes in Visual Basic angeben, indem Sie die Schlüsselwörter **Ansi**, **Unicode** oder **Auto** zur Deklarationsanweisung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="20176-135">You can specify character-set behavior in Visual Basic by adding the **Ansi**, **Unicode**, or **Auto** keyword to the declaration statement.</span></span>  
  
 <span data-ttu-id="20176-136">Wenn Sie das Zeichensatzschlüsselwort weglassen, wie es in der ersten Deklarationsanweisung der Fall ist, erfolgt das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld standardmäßig im ANSI-Zeichensatz.</span><span class="sxs-lookup"><span data-stu-id="20176-136">If you omit the character-set keyword, as is done in the first declaration statement, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field defaults to the ANSI character set.</span></span> <span data-ttu-id="20176-137">Die zweite und dritte Anweisung in diesem Beispiel geben einen Zeichensatz explizit mit einem Schlüsselwort an.</span><span class="sxs-lookup"><span data-stu-id="20176-137">The second and third statements in the example explicitly specify a character set with a keyword.</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
  
Public Class Win32  
   Declare Function MessageBoxA Lib "user32.dll"(ByVal hWnd As Integer, _  
       ByVal txt As String, ByVal caption As String, _  
       ByVal Typ As Integer) As Integer  
  
   Declare Unicode Function MessageBoxW Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
  
   Declare Auto Function MessageBox Lib "user32.dll" _  
       (ByVal hWnd As Integer, ByVal txt As String, _  
        ByVal caption As String, ByVal Typ As Integer) As Integer  
End Class  
```  
  
## <a name="specifying-a-character-set-in-c-and-c"></a><span data-ttu-id="20176-138">Festlegen eines Zeichensatzes in C# und C++</span><span class="sxs-lookup"><span data-stu-id="20176-138">Specifying a Character Set in C# and C++</span></span>  
 <span data-ttu-id="20176-139">Das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType>-Feld identifiziert den zugrunde liegenden Zeichensatz als ANSI oder Unicode.</span><span class="sxs-lookup"><span data-stu-id="20176-139">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field identifies the underlying character set as ANSI or Unicode.</span></span> <span data-ttu-id="20176-140">Der Zeichensatz steuert, wie die Zeichenfolgenargumente an eine Methode gemarshallt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20176-140">The character set controls how string arguments to a method should be marshaled.</span></span> <span data-ttu-id="20176-141">Verwenden Sie eines der folgenden Formate, um den Zeichensatz anzugeben:</span><span class="sxs-lookup"><span data-stu-id="20176-141">Use one of the following forms to indicate the character set:</span></span>  
  
```csharp  
[DllImport("dllname", CharSet=CharSet.Ansi)]  
[DllImport("dllname", CharSet=CharSet.Unicode)]  
[DllImport("dllname", CharSet=CharSet.Auto)]  
```  
  
```cpp  
[DllImport("dllname", CharSet=CharSet::Ansi)]  
[DllImport("dllname", CharSet=CharSet::Unicode)]  
[DllImport("dllname", CharSet=CharSet::Auto)]  
```  
  
 <span data-ttu-id="20176-142">Im folgenden Beispiel werden drei verwaltete Definitionen der **MessageBox**-Funktion angezeigt, die einen Zeichensatz anzeigen.</span><span class="sxs-lookup"><span data-stu-id="20176-142">The following example shows three managed definitions of the **MessageBox** function attributed to specify a character set.</span></span> <span data-ttu-id="20176-143">Durch die Auslassung wird das **CharSet**-Feld in der ersten Definition standardmäßig in ANSI-Zeichensatz verwandelt.</span><span class="sxs-lookup"><span data-stu-id="20176-143">In the first definition, by its omission, the **CharSet** field defaults to the ANSI character set.</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
    public static extern int MessageBoxA(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Unicode)]  
    public static extern int MessageBoxW(int hWnd, String text,   
        String caption, uint type);  
[DllImport("user32.dll", CharSet=CharSet.Auto)]  
    public static extern int MessageBox(int hWnd, String text,   
        String caption, uint type);  
```  
  
```cpp  
typedef void* HWND;  
  
//Can use MessageBox or MessageBoxA.  
[DllImport("user32")]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Can use MessageBox or MessageBoxW.  
[DllImport("user32", CharSet=CharSet::Unicode)]  
extern "C" int MessageBoxW(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
  
//Must use MessageBox.  
[DllImport("user32", CharSet=CharSet::Auto)]  
extern "C" int MessageBox(HWND hWnd,  
                          String* pText,  
                          String* pCaption,  
                          unsigned int uType);  
```  
  
## <a name="see-also"></a><span data-ttu-id="20176-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20176-144">See Also</span></span>  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [<span data-ttu-id="20176-145">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="20176-145">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="20176-146">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="20176-146">Platform Invoke Examples</span></span>](../../../docs/framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="20176-147">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="20176-147">Marshaling Data with Platform Invoke</span></span>](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md)
