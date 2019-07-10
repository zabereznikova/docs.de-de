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
ms.openlocfilehash: 9b6c839cc664105149f26b0d21d7ba7fb91b3e29
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742199"
---
# <a name="closeenum-method"></a><span data-ttu-id="57df8-102">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="57df8-102">CloseEnum Method</span></span>
<span data-ttu-id="57df8-103">Schließt die angegebene Enumeration und die zugeordneten Ressourcen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="57df8-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57df8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57df8-104">Syntax</span></span>  
  
```cpp  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="57df8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="57df8-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="57df8-106">Handle der Enumeration, die geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="57df8-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57df8-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="57df8-107">Return Value</span></span>  
 <span data-ttu-id="57df8-108">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="57df8-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57df8-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57df8-109">Requirements</span></span>  
 <span data-ttu-id="57df8-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="57df8-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57df8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57df8-111">See also</span></span>

- [<span data-ttu-id="57df8-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57df8-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="57df8-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57df8-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="57df8-114">Alink-API</span><span class="sxs-lookup"><span data-stu-id="57df8-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
