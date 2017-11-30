---
title: Behandeln von COM-Interop-Ausnahmen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: error-reference
helpviewer_keywords:
- unmanaged code, exceptions
- exceptions, unmanaged code
- HRESULTs
- exceptions, COM interop
- COM interop, exceptions
ms.assetid: e6104aa8-8e5f-4069-b864-def85579c96c
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bc3e01bc8ca463460ede9544d1d5c095c39a59d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="handling-com-interop-exceptions"></a><span data-ttu-id="53340-102">Behandeln von COM-Interop-Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="53340-102">Handling COM Interop Exceptions</span></span>
<span data-ttu-id="53340-103">Verwalteter und nicht verwalteter Code können zusammenarbeiten, um Ausnahmen zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="53340-103">Managed and unmanaged code can work together to handle exceptions.</span></span> <span data-ttu-id="53340-104">Wenn eine Methode in verwaltetem Code eine Ausnahme auslöst, kann die Common Language Runtime ein HRESULT an ein COM-Objekt übergeben.</span><span class="sxs-lookup"><span data-stu-id="53340-104">If a method throws an exception in managed code, the common language runtime can pass an HRESULT to a COM object.</span></span> <span data-ttu-id="53340-105">Wenn eine Methode in nicht verwaltetem Code fehlschlägt, indem ein Fehler-HRESULT zurückgegeben wird, löst die Common Language Runtime eine Ausnahme aus, die von verwaltetem Code abgefangen werden kann.</span><span class="sxs-lookup"><span data-stu-id="53340-105">If a method fails in unmanaged code by returning a failure HRESULT, the runtime throws an exception that can be caught by managed code.</span></span>  
  
 <span data-ttu-id="53340-106">Die Common Language Runtime ordnet das HRESULT von COM-Interop automatisch zu spezifischeren Ausnahmen zu.</span><span class="sxs-lookup"><span data-stu-id="53340-106">The runtime automatically maps the HRESULT from COM interop to more specific exceptions.</span></span> <span data-ttu-id="53340-107">So wird z. B. E_ACCESSDENIED zu <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY zu <xref:System.OutOfMemoryException> usw.</span><span class="sxs-lookup"><span data-stu-id="53340-107">For example, E_ACCESSDENIED becomes <xref:System.UnauthorizedAccessException>, E_OUTOFMEMORY becomes <xref:System.OutOfMemoryException>, and so on.</span></span>  
  
 <span data-ttu-id="53340-108">Wenn HRESULT ein benutzerdefiniertes Ergebnis wird oder es zur Laufzeit unbekannt ist, übergibt die Common Language Runtime ein generisches <xref:System.Runtime.InteropServices.COMException> an den Client.</span><span class="sxs-lookup"><span data-stu-id="53340-108">If the HRESULT is a custom result or if it is unknown to the runtime, the runtime passes a generic <xref:System.Runtime.InteropServices.COMException> to the client.</span></span> <span data-ttu-id="53340-109">Die **ErrorCode** Eigenschaft von der **COMException** enthält den HRESULT-Wert.</span><span class="sxs-lookup"><span data-stu-id="53340-109">The **ErrorCode** property of the **COMException** contains the HRESULT value.</span></span>  
  
## <a name="working-with-ierrorinfo"></a><span data-ttu-id="53340-110">Arbeiten mit IErrorInfo</span><span class="sxs-lookup"><span data-stu-id="53340-110">Working with IErrorInfo</span></span>  
 <span data-ttu-id="53340-111">Wenn ein Fehler von COM an verwalteten Code übergeben wird, füllt die Common Language Runtime das Ausnahmeobjekt mit Fehlerinformationen.</span><span class="sxs-lookup"><span data-stu-id="53340-111">When an error is passed from COM to managed code, the runtime populates the exception object with error information.</span></span> <span data-ttu-id="53340-112">COM-Objekte, die "IErrorInfo" unterstützen und HRESULTS zurückgeben, stellen diese Informationen für Ausnahmen in verwaltetem Code bereit.</span><span class="sxs-lookup"><span data-stu-id="53340-112">COM objects that support IErrorInfo and return HRESULTS provide this information to managed code exceptions.</span></span> <span data-ttu-id="53340-113">Die Common Language Runtime ordnet die Beschreibung des COM-Fehlers zur <xref:System.Exception.Message%2A>-Eigenschaft der Ausnahme zu.</span><span class="sxs-lookup"><span data-stu-id="53340-113">For example, the runtime maps the Description from the COM error to the exception's <xref:System.Exception.Message%2A> property.</span></span> <span data-ttu-id="53340-114">Wenn HRESULT keine weiteren Fehlerinformationen bereitstellt, füllt die Common Language Runtime viele Eigenschaften der Ausnahme mit Standardwerten.</span><span class="sxs-lookup"><span data-stu-id="53340-114">If the HRESULT provides no additional error information, the runtime fills many of the exception's properties with default values.</span></span>  
  
 <span data-ttu-id="53340-115">Wenn eine Methode in nicht verwaltetem Code fehlschlägt, kann eine Ausnahme an ein verwaltetes Codesegment übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="53340-115">If a method fails in unmanaged code, an exception can be passed to a managed code segment.</span></span> <span data-ttu-id="53340-116">Das Thema [HRESULTS und Ausnahmen](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) enthält eine Tabelle mit der Zuordnung von HRESULTS zu Ausnahmeobjekten der Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="53340-116">The topic [HRESULTS and Exceptions](../../../docs/framework/interop/how-to-map-hresults-and-exceptions.md) contains a table showing how HRESULTS map to runtime exception objects.</span></span>  

## <a name="see-also"></a><span data-ttu-id="53340-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53340-117">See Also</span></span>
[<span data-ttu-id="53340-118">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="53340-118">Exceptions</span></span>](index.md) 
