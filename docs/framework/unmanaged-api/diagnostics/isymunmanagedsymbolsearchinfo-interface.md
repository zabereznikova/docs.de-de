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
ms.openlocfilehash: 95ad3cbea4269173f22e662d15772ff97f7ee900
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705448"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="8184d-102">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8184d-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>

<span data-ttu-id="8184d-103">Stellt Methoden bereit, die Informationen über den Suchpfad erhalten.</span><span class="sxs-lookup"><span data-stu-id="8184d-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="8184d-104">Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="8184d-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8184d-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="8184d-105">Methods</span></span>  
  
|<span data-ttu-id="8184d-106">Methode</span><span class="sxs-lookup"><span data-stu-id="8184d-106">Method</span></span>|<span data-ttu-id="8184d-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8184d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8184d-108">GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="8184d-108">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="8184d-109">Ruft das HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="8184d-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="8184d-110">GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="8184d-110">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="8184d-111">Ruft den Suchpfad ab.</span><span class="sxs-lookup"><span data-stu-id="8184d-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="8184d-112">GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="8184d-112">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="8184d-113">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="8184d-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8184d-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8184d-114">Requirements</span></span>  

 <span data-ttu-id="8184d-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="8184d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8184d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8184d-116">See also</span></span>

- [<span data-ttu-id="8184d-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8184d-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
