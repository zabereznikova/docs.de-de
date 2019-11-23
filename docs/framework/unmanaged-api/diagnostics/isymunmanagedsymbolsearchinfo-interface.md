---
title: ISymUnmanagedSymbolSearchInfo-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo
helpviewer_keywords:
- ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type:
- apiref
ms.openlocfilehash: d7371361b074454e8aa359c49b964193c12f3034
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446147"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="397f6-102">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="397f6-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="397f6-103">Provides methods that get information about the search path.</span><span class="sxs-lookup"><span data-stu-id="397f6-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="397f6-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="397f6-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="397f6-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="397f6-105">Methods</span></span>  
  
|<span data-ttu-id="397f6-106">Methode</span><span class="sxs-lookup"><span data-stu-id="397f6-106">Method</span></span>|<span data-ttu-id="397f6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="397f6-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="397f6-108">GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="397f6-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="397f6-109">Gets the HRESULT.</span><span class="sxs-lookup"><span data-stu-id="397f6-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="397f6-110">GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="397f6-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="397f6-111">Gets the search path.</span><span class="sxs-lookup"><span data-stu-id="397f6-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="397f6-112">GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="397f6-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="397f6-113">Gets the search path length.</span><span class="sxs-lookup"><span data-stu-id="397f6-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="397f6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="397f6-114">Requirements</span></span>  
 <span data-ttu-id="397f6-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="397f6-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397f6-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="397f6-116">See also</span></span>

- [<span data-ttu-id="397f6-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="397f6-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
