---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan-Methode
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
ms.openlocfilehash: e4b09e6d89b3ba8ba3bf7e149d31a14a74b945b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723934"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="0c019-102">ISymUnmanagedWriter5::MapTokenToSourceSpan-Methode</span><span class="sxs-lookup"><span data-stu-id="0c019-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>

<span data-ttu-id="0c019-103">Ordnet das angegebene Metadatentoken der angegebenen Quellzeilen Spanne in der angegebenen Quelldatei zu.</span><span class="sxs-lookup"><span data-stu-id="0c019-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="0c019-104">Muss zwischen Aufrufen der [openmaptokenstosourcespans-Methode](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und der [closemaptokenstosourcespans-Methode](isymunmanagedwriter5-closemaptokenstosourcespans-method.md)aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0c019-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c019-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c019-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c019-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c019-106">Parameters</span></span>  
  
|<span data-ttu-id="0c019-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c019-107">Parameter</span></span>|<span data-ttu-id="0c019-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0c019-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="0c019-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0c019-109">Return Value</span></span>  

 <span data-ttu-id="0c019-110">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="0c019-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c019-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0c019-111">Requirements</span></span>  

 <span data-ttu-id="0c019-112">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="0c019-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c019-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c019-113">See also</span></span>

- [<span data-ttu-id="0c019-114">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c019-114">ISymUnmanagedWriter5 Interface</span></span>](isymunmanagedwriter5-interface.md)
