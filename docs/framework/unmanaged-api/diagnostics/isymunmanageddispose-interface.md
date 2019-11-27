---
title: ISymUnmanagedDispose-Schnittstelle
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose
helpviewer_keywords:
- ISymUnmanagedDispose interface [.NET Framework debugging]
ms.assetid: b1d74e83-a200-4d00-8fbd-27918808616d
topic_type:
- apiref
ms.openlocfilehash: 08d9ba8f8c9a251bd0db0ffe256af7db0164ba2f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449224"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="03ffe-102">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="03ffe-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="03ffe-103">Gibt nicht verwaltete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="03ffe-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03ffe-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="03ffe-104">Methods</span></span>  
  
|<span data-ttu-id="03ffe-105">Methode</span><span class="sxs-lookup"><span data-stu-id="03ffe-105">Method</span></span>|<span data-ttu-id="03ffe-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="03ffe-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03ffe-107">Destroy-Methode</span><span class="sxs-lookup"><span data-stu-id="03ffe-107">Destroy Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-destroy-method.md)|<span data-ttu-id="03ffe-108">Bewirkt, dass das zugrunde liegende-Objekt alle internen Verweise freigibt und bei allen nachfolgenden Methoden aufrufen einen Fehler zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="03ffe-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03ffe-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="03ffe-109">Requirements</span></span>  
 <span data-ttu-id="03ffe-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="03ffe-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03ffe-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03ffe-111">See also</span></span>

- [<span data-ttu-id="03ffe-112">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="03ffe-112">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
