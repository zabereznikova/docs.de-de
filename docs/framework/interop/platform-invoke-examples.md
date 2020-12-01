---
title: Beispiele für Plattformaufrufe
description: Sehen Sie sich ein Beispiel für den Aufruf der Plattform an, das veranschaulicht, wie die MessageBox-Funktion in „User32.dll“ definiert und aufgerufen wird.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [.NET Framework], platform invoke
- unmanaged functions
- COM interop, platform invoke
- platform invoke, examples
- interoperation with unmanaged code, platform invoke
- DLL functions
ms.assetid: 15926806-f0b7-487e-93a6-4e9367ec689f
ms.openlocfilehash: 3b626061a579e089f92f2bf7de7f83f7db5bd184
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268884"
---
# <a name="platform-invoke-examples"></a><span data-ttu-id="fac8c-103">Beispiele für Plattformaufrufe</span><span class="sxs-lookup"><span data-stu-id="fac8c-103">Platform Invoke Examples</span></span>

<span data-ttu-id="fac8c-104">In den folgenden Beispielen erfahren Sie, wie Sie durch die Übergabe einer einfachen Zeichenfolge als Argument die Funktion **MessageBox** in der Datei „User32.dll“ definieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fac8c-104">The following examples demonstrate how to define and call the **MessageBox** function in User32.dll, passing a simple string as an argument.</span></span> <span data-ttu-id="fac8c-105">In den Beispielen ist das Feld <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> auf **Auto** (Automatisch) festgelegt, damit die Zielplattform die Zeichenbreite und das Marshalling von Zeichenfolgen festlegen kann.</span><span class="sxs-lookup"><span data-stu-id="fac8c-105">In the examples, the <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet?displayProperty=nameWithType> field is set to **Auto** to let the target platform determine the character width and string marshaling.</span></span>  
  
 [!code-cpp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cpp/Example.cpp#1)]
 [!code-csharp[Conceptual.Interop.PInvoke#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Conceptual.Interop.PInvoke/cs/Example1.cs#1)]
 [!code-vb[Conceptual.Interop.PInvoke#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Conceptual.Interop.PInvoke/vb/Example1.vb#1)]  
  
 <span data-ttu-id="fac8c-106">Weitere Beispiele finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mithilfe des Plattformaufrufs)](marshaling-data-with-platform-invoke.md).</span><span class="sxs-lookup"><span data-stu-id="fac8c-106">For additional examples, see [Marshaling Data with Platform Invoke](marshaling-data-with-platform-invoke.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac8c-107">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fac8c-107">See also</span></span>

- <xref:System.Runtime.InteropServices.DllImportAttribute>
- [<span data-ttu-id="fac8c-108">Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)</span><span class="sxs-lookup"><span data-stu-id="fac8c-108">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="fac8c-109">Specifying a Character Set (Angeben eines Zeichensatzes)</span><span class="sxs-lookup"><span data-stu-id="fac8c-109">Specifying a Character Set</span></span>](specifying-a-character-set.md)
