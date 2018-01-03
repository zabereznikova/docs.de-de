---
title: ISymUnmanagedSymbolSearchInfo-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo
helpviewer_keywords: ISymUnmanagedSymbolSearchInfo interface [.NET Framework debugging]
ms.assetid: 30817373-0a21-49c1-a0c4-8e8daeecb8db
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 441330471906a891646ad55eb73ec25b44800cbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="dbf29-102">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbf29-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="dbf29-103">Enthält Methoden, die Informationen zu den Suchpfad abrufen.</span><span class="sxs-lookup"><span data-stu-id="dbf29-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="dbf29-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="dbf29-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dbf29-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="dbf29-105">Methods</span></span>  
  
|<span data-ttu-id="dbf29-106">Methode</span><span class="sxs-lookup"><span data-stu-id="dbf29-106">Method</span></span>|<span data-ttu-id="dbf29-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dbf29-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbf29-108">GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="dbf29-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="dbf29-109">Ruft HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="dbf29-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="dbf29-110">GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="dbf29-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="dbf29-111">Ruft den Suchpfad ab.</span><span class="sxs-lookup"><span data-stu-id="dbf29-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="dbf29-112">GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="dbf29-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="dbf29-113">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="dbf29-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbf29-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dbf29-114">Requirements</span></span>  
 <span data-ttu-id="dbf29-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="dbf29-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf29-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbf29-116">See Also</span></span>  
 [<span data-ttu-id="dbf29-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dbf29-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
