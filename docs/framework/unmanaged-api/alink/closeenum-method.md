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
ms.openlocfilehash: e5c3185dc6d488223d5882f543f0c690d82261b5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402443"
---
# <a name="closeenum-method"></a><span data-ttu-id="4dcc3-102">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="4dcc3-102">CloseEnum Method</span></span>
<span data-ttu-id="4dcc3-103">Schließt die angegebene Enumeration und gibt die zugeordnete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="4dcc3-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dcc3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4dcc3-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4dcc3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4dcc3-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="4dcc3-106">Handle der Enumeration, die geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4dcc3-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4dcc3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4dcc3-107">Return Value</span></span>  
 <span data-ttu-id="4dcc3-108">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4dcc3-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4dcc3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4dcc3-109">Requirements</span></span>  
 <span data-ttu-id="4dcc3-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="4dcc3-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dcc3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dcc3-111">See Also</span></span>  
 [<span data-ttu-id="4dcc3-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dcc3-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="4dcc3-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dcc3-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="4dcc3-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="4dcc3-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
