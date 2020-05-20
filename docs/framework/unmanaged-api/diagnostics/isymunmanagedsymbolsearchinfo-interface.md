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
ms.openlocfilehash: 308c501e17446719067d2dc0580d698c1770bf53
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610664"
---
# <a name="isymunmanagedsymbolsearchinfo-interface"></a><span data-ttu-id="63bff-102">ISymUnmanagedSymbolSearchInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63bff-102">ISymUnmanagedSymbolSearchInfo Interface</span></span>
<span data-ttu-id="63bff-103">Stellt Methoden bereit, die Informationen über den Suchpfad erhalten.</span><span class="sxs-lookup"><span data-stu-id="63bff-103">Provides methods that get information about the search path.</span></span> <span data-ttu-id="63bff-104">Rufen Sie diese Schnittstelle durch Aufrufen von `QueryInterface` für ein Objekt ab, das die [ISymUnmanagedReader](isymunmanagedreader-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="63bff-104">Obtain this interface by calling `QueryInterface` on an object that implements the [ISymUnmanagedReader](isymunmanagedreader-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="63bff-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="63bff-105">Methods</span></span>  
  
|<span data-ttu-id="63bff-106">Methode</span><span class="sxs-lookup"><span data-stu-id="63bff-106">Method</span></span>|<span data-ttu-id="63bff-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="63bff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="63bff-108">GetHRESULT-Methode</span><span class="sxs-lookup"><span data-stu-id="63bff-108">GetHRESULT Method</span></span>](isymunmanagedsymbolsearchinfo-gethresult-method.md)|<span data-ttu-id="63bff-109">Ruft das HRESULT ab.</span><span class="sxs-lookup"><span data-stu-id="63bff-109">Gets the HRESULT.</span></span>|  
|[<span data-ttu-id="63bff-110">GetSearchPath-Methode</span><span class="sxs-lookup"><span data-stu-id="63bff-110">GetSearchPath Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpath-method.md)|<span data-ttu-id="63bff-111">Ruft den Suchpfad ab.</span><span class="sxs-lookup"><span data-stu-id="63bff-111">Gets the search path.</span></span>|  
|[<span data-ttu-id="63bff-112">GetSearchPathLength-Methode</span><span class="sxs-lookup"><span data-stu-id="63bff-112">GetSearchPathLength Method</span></span>](isymunmanagedsymbolsearchinfo-getsearchpathlength-method.md)|<span data-ttu-id="63bff-113">Ruft die Länge des Suchpfads ab.</span><span class="sxs-lookup"><span data-stu-id="63bff-113">Gets the search path length.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63bff-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="63bff-114">Requirements</span></span>  
 <span data-ttu-id="63bff-115">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="63bff-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63bff-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63bff-116">See also</span></span>

- [<span data-ttu-id="63bff-117">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="63bff-117">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
