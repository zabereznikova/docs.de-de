---
title: EndMerge-Methode
ms.date: 03/30/2017
api_name:
- IALink.EndMerge
- EndMerge
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EndMerge
helpviewer_keywords:
- EndMerge method
ms.assetid: 1d03bb15-a2c8-4a04-8fc6-b126c89c3778
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9ba7c2d0c5ea29d5db429139f1831e8d71dd23f3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54739140"
---
# <a name="endmerge-method"></a><span data-ttu-id="3da56-102">EndMerge-Methode</span><span class="sxs-lookup"><span data-stu-id="3da56-102">EndMerge Method</span></span>
<span data-ttu-id="3da56-103">Gibt an, dass alle benutzerdefinierten Attribute mit dem Ausgabebereich zusammengeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="3da56-103">Indicates that all custom attributes have been merged into the emit scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3da56-104">Syntax</span></span>  
  
```  
HRESULT EndMerge(  
    mdAssembly AssemblyID  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3da56-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3da56-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3da56-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="3da56-106">ID of the assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3da56-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3da56-107">Return Value</span></span>  
 <span data-ttu-id="3da56-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3da56-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da56-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3da56-109">Requirements</span></span>  
 <span data-ttu-id="3da56-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="3da56-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da56-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3da56-111">See also</span></span>
- [<span data-ttu-id="3da56-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da56-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3da56-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3da56-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3da56-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="3da56-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
