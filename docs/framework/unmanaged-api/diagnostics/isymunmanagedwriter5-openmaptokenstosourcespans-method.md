---
title: ISymUnmanagedWriter5::OpenMapTokensToSourceSpans-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 93ad2517-b0dc-464c-8688-a58a30eda18d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb283198de5621748b37fe8e22f2fbc408754ad6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter5openmaptokenstosourcespans-method"></a><span data-ttu-id="69574-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="69574-102">ISymUnmanagedWriter5::OpenMapTokensToSourceSpans Method</span></span>
<span data-ttu-id="69574-103">Öffnen Sie eine spezielle benutzerdefinierte Datenabschnitt zum Ausgeben der Span-Token-Source--Zuordnungsinformationen in.</span><span class="sxs-lookup"><span data-stu-id="69574-103">Open a special custom data section to emit token-to-source span mapping information into.</span></span> <span data-ttu-id="69574-104">Öffnen in diesem Abschnitt aus, wenn eine Methode bereits geöffnet ist, oder umgekehrt, führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="69574-104">Opening this section when a method is already open, or vice versa, is an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69574-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="69574-105">Syntax</span></span>  
  
```idl  
HRESULT OpenMapTokensToSourceSpans();  
```  
  
## <a name="return-value"></a><span data-ttu-id="69574-106">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="69574-106">Return Value</span></span>  
 <span data-ttu-id="69574-107">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="69574-107">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69574-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="69574-108">Requirements</span></span>  
 <span data-ttu-id="69574-109">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="69574-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69574-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69574-110">See Also</span></span>  
 [<span data-ttu-id="69574-111">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="69574-111">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
