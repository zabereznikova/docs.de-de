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
ms.openlocfilehash: 967511238dceb752ab30ce10dcaba8b65f4dd9fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="98409-102">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98409-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="98409-103">Enthält Methoden, die Informationen zu den Suchpfad abrufen.</span><span class="sxs-lookup"><span data-stu-id="98409-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="98409-104">Rufen Sie diese Schnittstelle durch den Aufruf `QueryInterface` auf ein Objekt, implementiert die [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="98409-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98409-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="98409-105">Methods</span></span>  
  
|<span data-ttu-id="98409-106">Methode</span><span class="sxs-lookup"><span data-stu-id="98409-106">Method</span></span>|<span data-ttu-id="98409-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98409-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="98409-108">GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="98409-108">GetHRESULT Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="98409-109">Ruft HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="98409-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="98409-110">GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="98409-110">GetSearchPath Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="98409-111">Ruft den Suchpfad ab.</span><span class="sxs-lookup"><span data-stu-id="98409-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="98409-112">GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="98409-112">GetSearchPathLength Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="98409-113">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="98409-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98409-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98409-114">Requirements</span></span>  
 <span data-ttu-id="98409-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="98409-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98409-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98409-116">See Also</span></span>  
 [<span data-ttu-id="98409-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="98409-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
