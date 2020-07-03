---
title: MsgBox-Beispiel
description: Hier finden Sie ein Beispiel der Übertragung von Zeichenfolgentypen durch Werte als In-Parameter mithilfe von MsgBox. Es zeigt, wann die Felder EntryPoint, CharSet und ExactSpelling in .NET verwendet werden sollen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
ms.openlocfilehash: ccf882e1f801dd18e5b65a4279fc580d927dd29d
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904090"
---
# <a name="msgbox-sample"></a><span data-ttu-id="841ca-104">MsgBox-Beispiel</span><span class="sxs-lookup"><span data-stu-id="841ca-104">MsgBox Sample</span></span>
<span data-ttu-id="841ca-105">Dieses Beispiel demonstriert, wie Zeichenfolgentypen durch einen Wert als In-Parameter übergeben werden und wann das <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>-Feld, das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld und das <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>-Feld zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="841ca-105">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="841ca-106">Das MsgBox-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="841ca-106">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
- <span data-ttu-id="841ca-107">**MessageBox** aus „User32.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="841ca-107">**MessageBox** exported from User32.dll.</span></span>  
  
    ```cpp
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,
       UINT uType);  
    ```  
  
 <span data-ttu-id="841ca-108">In diesem Beispiel enthält die `NativeMethods`-Klasse einen verwalteten Prototyp für jede nicht verwaltete Funktion, die durch die `MsgBoxSample`-Klasse aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="841ca-108">In this sample, the `NativeMethods` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="841ca-109">Die verwalteten Prototypmethoden `MsgBox`, `MsgBox2` und `MsgBox3` verfügen über unterschiedliche Deklarationen für ein und dieselbe nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="841ca-109">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="841ca-110">Die Deklaration für `MsgBox2` erzeugt eine falsche Ausgabe im Meldungsfeld, da der als ANSI angegebene Zeichentyp nicht mit dem Einstiegspunkt `MessageBoxW` übereinstimmt, der dem Namen der Unicode-Funktion entspricht.</span><span class="sxs-lookup"><span data-stu-id="841ca-110">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="841ca-111">Die Deklaration für `MsgBox3` erzeugt einen Übereinstimmungsfehler zwischen den Feldern **EntryPoint**, **CharSet** und **ExactSpelling**.</span><span class="sxs-lookup"><span data-stu-id="841ca-111">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="841ca-112">Die `MsgBox3` -Methode löst bei ihrem Aufruf eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="841ca-112">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="841ca-113">Ausführliche Informationen zur Benennung von Zeichenfolgen und zum Namensmarshallen finden Sie unter [Specifying a Character Set (Angeben eines Zeichensatzes)](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="841ca-113">For detailed information on string naming and name marshaling, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="841ca-114">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="841ca-114">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a><span data-ttu-id="841ca-115">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="841ca-115">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="841ca-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="841ca-116">See also</span></span>

- [<span data-ttu-id="841ca-117">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="841ca-117">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="841ca-118">Standardmäßiges Marshalling für Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="841ca-118">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
- [<span data-ttu-id="841ca-119">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="841ca-119">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="841ca-120">Specifying a Character Set (Angeben eines Zeichensatzes)</span><span class="sxs-lookup"><span data-stu-id="841ca-120">Specifying a Character Set</span></span>](specifying-a-character-set.md)
