---
title: ISymUnmanagedWriter5-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: bdc630c3c94c7d03b736efa0a95665f10aac7c6e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609429"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="ee746-102">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee746-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="ee746-103">ISymUnmanagedWriter5-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="ee746-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee746-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee746-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="ee746-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="ee746-105">Methods</span></span>  
 <span data-ttu-id="ee746-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="ee746-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="ee746-107">Methode</span><span class="sxs-lookup"><span data-stu-id="ee746-107">Method</span></span>|<span data-ttu-id="ee746-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ee746-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ee746-109">CloseMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="ee746-109">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="ee746-110">Schließen Sie den speziellen benutzerdefinierten Daten Abschnitt für die Übersetzung von Zuordnungsinformationen zwischen Token und Quelle.</span><span class="sxs-lookup"><span data-stu-id="ee746-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="ee746-111">Nachdem Sie geschlossen wurde, können keine weiteren Zuordnungsinformationen mehr hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="ee746-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="ee746-112">MapTokenToSourceSpan-Methode</span><span class="sxs-lookup"><span data-stu-id="ee746-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="ee746-113">Ordnet das angegebene Metadatentoken der angegebenen Quellzeilen Spanne in der angegebenen Quelldatei zu.</span><span class="sxs-lookup"><span data-stu-id="ee746-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="ee746-114">Muss zwischen Aufrufen der [openmaptokenstosourcespans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und der [closemaptokenstosourcespans-Methode](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ee746-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="ee746-115">OpenMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="ee746-115">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="ee746-116">Öffnen Sie einen speziellen benutzerdefinierten Daten Abschnitt, um die Informationen zur Zuordnung von Token zu Quell Informationen in zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="ee746-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="ee746-117">Wenn Sie diesen Abschnitt öffnen, wenn eine Methode bereits geöffnet ist (oder umgekehrt), ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ee746-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee746-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ee746-118">Requirements</span></span>  
 <span data-ttu-id="ee746-119">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="ee746-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee746-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee746-120">See also</span></span>

- [<span data-ttu-id="ee746-121">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ee746-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="ee746-122">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee746-122">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
