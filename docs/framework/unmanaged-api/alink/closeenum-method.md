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
ms.openlocfilehash: fd7d63596690e2a5d0bc26448884ec09ecd63231
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790077"
---
# <a name="closeenum-method"></a><span data-ttu-id="a7a6f-102">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="a7a6f-102">CloseEnum Method</span></span>
<span data-ttu-id="a7a6f-103">Schließt die angegebene Enumeration und die zugeordneten Ressourcen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a7a6f-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7a6f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7a6f-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7a6f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7a6f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="a7a6f-106">Handle der Enumeration, die geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a7a6f-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7a6f-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a7a6f-107">Return Value</span></span>  
 <span data-ttu-id="a7a6f-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a7a6f-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7a6f-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7a6f-109">Requirements</span></span>  
 <span data-ttu-id="a7a6f-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="a7a6f-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7a6f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7a6f-111">See also</span></span>

- [<span data-ttu-id="a7a6f-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7a6f-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a7a6f-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7a6f-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a7a6f-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="a7a6f-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
