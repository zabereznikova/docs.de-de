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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8f5fc951b629a3158fc2c2d6047234fb661f3741
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494898"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="5f9d5-102">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f9d5-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="5f9d5-103">Enthält Methoden, die Informationen zu den Suchpfad zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5f9d5-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="5f9d5-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5f9d5-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5f9d5-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5f9d5-105">Methods</span></span>  
  
|<span data-ttu-id="5f9d5-106">Methode</span><span class="sxs-lookup"><span data-stu-id="5f9d5-106">Method</span></span>|<span data-ttu-id="5f9d5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f9d5-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5f9d5-108">GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="5f9d5-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="5f9d5-109">Ruft HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="5f9d5-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="5f9d5-110">GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="5f9d5-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="5f9d5-111">Ruft den Pfad für die Suche.</span><span class="sxs-lookup"><span data-stu-id="5f9d5-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="5f9d5-112">GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="5f9d5-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="5f9d5-113">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="5f9d5-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5f9d5-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f9d5-114">Requirements</span></span>  
 <span data-ttu-id="5f9d5-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="5f9d5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f9d5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f9d5-116">See also</span></span>
- [<span data-ttu-id="5f9d5-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5f9d5-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
