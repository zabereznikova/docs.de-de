---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan-Methode
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 08c219dd033b39fc07159875b184cdf70e3aa3ed
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59181518"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="54717-102">ISymUnmanagedWriter5::MapTokenToSourceSpan-Methode</span><span class="sxs-lookup"><span data-stu-id="54717-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="54717-103">Zuordnungen in die Zeile für die angegebene Quelle das angegebene Metadatentoken umfassen, in der angegebenen Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="54717-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="54717-104">Muss aufgerufen werden, zwischen den Aufrufen [OpenMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und [CloseMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="54717-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54717-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="54717-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54717-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="54717-106">Parameters</span></span>  
  
|<span data-ttu-id="54717-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="54717-107">Parameter</span></span>|<span data-ttu-id="54717-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54717-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="54717-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="54717-109">Return Value</span></span>  
 <span data-ttu-id="54717-110">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="54717-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54717-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="54717-111">Requirements</span></span>  
 <span data-ttu-id="54717-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="54717-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54717-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54717-113">See also</span></span>

- [<span data-ttu-id="54717-114">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="54717-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
