---
title: CloseEnum-Methode
ms.date: 03/30/2017
api_name:
- CloseEnum
- IALink.CloseEnum
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- CloseEnum
helpviewer_keywords:
- CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 009f7d20dfd6efc279b3187af8f5c95132ae51e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54525234"
---
# <a name="closeenum-method"></a><span data-ttu-id="218ca-102">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="218ca-102">CloseEnum Method</span></span>
<span data-ttu-id="218ca-103">Schließt die angegebene Enumeration und die zugeordneten Ressourcen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="218ca-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="218ca-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="218ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="218ca-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="218ca-106">Handle der Enumeration, die geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="218ca-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="218ca-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="218ca-107">Return Value</span></span>  
 <span data-ttu-id="218ca-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="218ca-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="218ca-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="218ca-109">Requirements</span></span>  
 <span data-ttu-id="218ca-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="218ca-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218ca-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="218ca-111">See also</span></span>
- [<span data-ttu-id="218ca-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="218ca-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="218ca-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="218ca-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="218ca-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="218ca-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
