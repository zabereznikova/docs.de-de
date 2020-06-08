---
title: ISymUnmanagedWriter5-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
ms.openlocfilehash: d9204457b71b670e1c96ed228ad11116bdf41fe6
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493577"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="15dc4-102">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15dc4-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="15dc4-103">ISymUnmanagedWriter5-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="15dc4-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15dc4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="15dc4-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="15dc4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="15dc4-105">Methods</span></span>  
 <span data-ttu-id="15dc4-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="15dc4-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="15dc4-107">Methode</span><span class="sxs-lookup"><span data-stu-id="15dc4-107">Method</span></span>|<span data-ttu-id="15dc4-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="15dc4-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="15dc4-109">CloseMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="15dc4-109">CloseMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="15dc4-110">Schließen Sie den speziellen benutzerdefinierten Daten Abschnitt für die Übersetzung von Zuordnungsinformationen zwischen Token und Quelle.</span><span class="sxs-lookup"><span data-stu-id="15dc4-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="15dc4-111">Nachdem Sie geschlossen wurde, können keine weiteren Zuordnungsinformationen mehr hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="15dc4-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="15dc4-112">MapTokenToSourceSpan-Methode</span><span class="sxs-lookup"><span data-stu-id="15dc4-112">MapTokenToSourceSpan Method</span></span>](isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="15dc4-113">Ordnet das angegebene Metadatentoken der angegebenen Quellzeilen Spanne in der angegebenen Quelldatei zu.</span><span class="sxs-lookup"><span data-stu-id="15dc4-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="15dc4-114">Muss zwischen Aufrufen der [openmaptokenstosourcespans-Methode](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und der [closemaptokenstosourcespans-Methode](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="15dc4-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="15dc4-115">OpenMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="15dc4-115">OpenMapTokensToSourceSpans Method</span></span>](isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="15dc4-116">Öffnen Sie einen speziellen benutzerdefinierten Daten Abschnitt, um die Informationen zur Zuordnung von Token zu Quell Informationen in zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="15dc4-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="15dc4-117">Wenn Sie diesen Abschnitt öffnen, wenn eine Methode bereits geöffnet ist (oder umgekehrt), ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="15dc4-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15dc4-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="15dc4-118">Requirements</span></span>  
 <span data-ttu-id="15dc4-119">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="15dc4-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15dc4-120">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="15dc4-120">See also</span></span>

- [<span data-ttu-id="15dc4-121">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="15dc4-121">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="15dc4-122">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15dc4-122">ISymUnmanagedWriter4 Interface</span></span>](isymunmanagedwriter4-interface.md)
