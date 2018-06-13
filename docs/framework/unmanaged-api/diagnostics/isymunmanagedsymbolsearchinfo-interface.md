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
ms.openlocfilehash: 5dce9653d3fef534ac6567e36a4c8213e13ab231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429168"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="a1f0a-102">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1f0a-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="a1f0a-103">Enthält Methoden, die Informationen zu den Suchpfad abrufen.</span><span class="sxs-lookup"><span data-stu-id="a1f0a-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="a1f0a-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a1f0a-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1f0a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="a1f0a-105">Methods</span></span>  
  
|<span data-ttu-id="a1f0a-106">Methode</span><span class="sxs-lookup"><span data-stu-id="a1f0a-106">Method</span></span>|<span data-ttu-id="a1f0a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1f0a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1f0a-108">GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="a1f0a-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="a1f0a-109">Ruft HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="a1f0a-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="a1f0a-110">GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="a1f0a-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="a1f0a-111">Ruft den Suchpfad ab.</span><span class="sxs-lookup"><span data-stu-id="a1f0a-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="a1f0a-112">GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="a1f0a-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="a1f0a-113">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="a1f0a-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1f0a-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1f0a-114">Requirements</span></span>  
 <span data-ttu-id="a1f0a-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a1f0a-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1f0a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1f0a-116">See Also</span></span>  
 [<span data-ttu-id="a1f0a-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="a1f0a-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
