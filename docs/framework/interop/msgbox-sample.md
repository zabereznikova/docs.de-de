---
title: MsgBox-Beispiel
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 26c72ee918db48bcbdf0ce912e12d20a0719f85b
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="msgbox-sample"></a><span data-ttu-id="880ff-102">MsgBox-Beispiel</span><span class="sxs-lookup"><span data-stu-id="880ff-102">MsgBox Sample</span></span>
<span data-ttu-id="880ff-103">Dieses Beispiel demonstriert, wie Zeichenfolgentypen durch einen Wert als In-Parameter übergeben werden und wann das <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>-Feld, das <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>-Feld und das <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling>-Feld zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="880ff-103">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="880ff-104">Das MsgBox-Beispiel verwendet die folgende nicht verwaltete Funktion, die zusammen mit ihrer ursprünglichen Funktionsdeklaration aufgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="880ff-104">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="880ff-105">**MessageBox** aus „User32.dll“ exportiert.</span><span class="sxs-lookup"><span data-stu-id="880ff-105">**MessageBox** exported from User32.dll.</span></span>  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 <span data-ttu-id="880ff-106">In diesem Beispiel enthält die `LibWrap`-Klasse einen verwalteten Prototyp für jede nicht verwaltete Funktion, die durch die `MsgBoxSample`-Klasse aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="880ff-106">In this sample, the `LibWrap` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="880ff-107">Die verwalteten Prototypmethoden `MsgBox`, `MsgBox2` und `MsgBox3` verfügen über unterschiedliche Deklarationen für ein und dieselbe nicht verwaltete Funktion.</span><span class="sxs-lookup"><span data-stu-id="880ff-107">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="880ff-108">Die Deklaration für `MsgBox2` erzeugt eine falsche Ausgabe im Meldungsfeld, da der als ANSI angegebene Zeichentyp nicht mit dem Einstiegspunkt `MessageBoxW` übereinstimmt, der dem Namen der Unicode-Funktion entspricht.</span><span class="sxs-lookup"><span data-stu-id="880ff-108">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="880ff-109">Die Deklaration für `MsgBox3` erzeugt einen Übereinstimmungsfehler zwischen den Feldern **EntryPoint**, **CharSet** und **ExactSpelling**.</span><span class="sxs-lookup"><span data-stu-id="880ff-109">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="880ff-110">Die `MsgBox3` -Methode löst bei ihrem Aufruf eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="880ff-110">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="880ff-111">Ausführliche Informationen zur Benennung von Zeichenfolgen und zum Namensmarshallen finden Sie unter [Specifying a Character Set (Angeben eines Zeichensatzes)](specifying-a-character-set.md).</span><span class="sxs-lookup"><span data-stu-id="880ff-111">For detailed information on string naming and name marshaling, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="880ff-112">Deklarieren von Prototypen</span><span class="sxs-lookup"><span data-stu-id="880ff-112">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a><span data-ttu-id="880ff-113">Aufrufen von Funktionen</span><span class="sxs-lookup"><span data-stu-id="880ff-113">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="880ff-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="880ff-114">See Also</span></span>  
 [<span data-ttu-id="880ff-115">Marshallen von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="880ff-115">Marshaling Strings</span></span>](marshaling-strings.md)  
 <span data-ttu-id="880ff-116">[Datentypen für Plattformaufruf](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="880ff-116">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="880ff-117">Standardmäßiges Marshalling für Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="880ff-117">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)  
 [<span data-ttu-id="880ff-118">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="880ff-118">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)  
 [<span data-ttu-id="880ff-119">Specifying a Character Set (Angeben eines Zeichensatzes)</span><span class="sxs-lookup"><span data-stu-id="880ff-119">Specifying a Character Set</span></span>](specifying-a-character-set.md)
