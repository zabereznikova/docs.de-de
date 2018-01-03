---
title: ISymUnmanagedWriter5-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 701b8de977d49a7d93f393b320bcb9d0d780c7bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="bc07c-102">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc07c-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="bc07c-103">ISymUnmanagedWriter5-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bc07c-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc07c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc07c-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="bc07c-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="bc07c-105">Methods</span></span>  
 <span data-ttu-id="bc07c-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="bc07c-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="bc07c-107">Methode</span><span class="sxs-lookup"><span data-stu-id="bc07c-107">Method</span></span>|<span data-ttu-id="bc07c-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bc07c-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bc07c-109">CloseMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="bc07c-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="bc07c-110">Schließen Sie die spezielle benutzerdefinierte Datenabschnitt für Token-Source-Spanne Zuordnungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="bc07c-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="bc07c-111">Nachdem sie geschlossen wurde, kann keine weiteren Zuordnungsinformationen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bc07c-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="bc07c-112">MapTokenToSourceSpan-Methode</span><span class="sxs-lookup"><span data-stu-id="bc07c-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="bc07c-113">Ordnet das angegebene Metadatentoken in die angegebene Quellcodezeile erstrecken sich über in der angegebenen Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="bc07c-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="bc07c-114">Muss aufgerufen werden, zwischen den Aufrufen [OpenMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und [CloseMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="bc07c-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="bc07c-115">OpenMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="bc07c-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="bc07c-116">Öffnen Sie eine spezielle benutzerdefinierte Datenabschnitt zum Ausgeben der Span-Token-Source--Zuordnungsinformationen in.</span><span class="sxs-lookup"><span data-stu-id="bc07c-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="bc07c-117">Öffnen in diesem Abschnitt aus, wenn eine Methode bereits geöffnet ist, oder umgekehrt, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="bc07c-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bc07c-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bc07c-118">Requirements</span></span>  
 <span data-ttu-id="bc07c-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="bc07c-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc07c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc07c-120">See Also</span></span>  
 [<span data-ttu-id="bc07c-121">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc07c-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="bc07c-122">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bc07c-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
