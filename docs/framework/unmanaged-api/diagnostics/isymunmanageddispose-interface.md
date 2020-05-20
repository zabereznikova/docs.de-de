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
ms.openlocfilehash: 85b0116edadbffdea8f141c3d20142e19b053321
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83440966"
---
# <a name="isymunmanageddispose-interface"></a><span data-ttu-id="480ae-102">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="480ae-102">ISymUnmanagedDispose Interface</span></span>
<span data-ttu-id="480ae-103">Gibt nicht verwaltete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="480ae-103">Disposes of unmanaged resources.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="480ae-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="480ae-104">Methods</span></span>  
  
|<span data-ttu-id="480ae-105">Methode</span><span class="sxs-lookup"><span data-stu-id="480ae-105">Method</span></span>|<span data-ttu-id="480ae-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="480ae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="480ae-107">Destroy-Methode</span><span class="sxs-lookup"><span data-stu-id="480ae-107">Destroy Method</span></span>](isymunmanageddispose-destroy-method.md)|<span data-ttu-id="480ae-108">Bewirkt, dass das zugrunde liegende-Objekt alle internen Verweise freigibt und bei allen nachfolgenden Methoden aufrufen einen Fehler zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="480ae-108">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="480ae-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="480ae-109">Requirements</span></span>  
 <span data-ttu-id="480ae-110">**Header:** Corsym. idl, corsym. h</span><span class="sxs-lookup"><span data-stu-id="480ae-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="480ae-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="480ae-111">See also</span></span>

- [<span data-ttu-id="480ae-112">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="480ae-112">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
