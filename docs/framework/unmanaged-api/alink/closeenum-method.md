---
title: CloseEnum-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CloseEnum
- IALink.CloseEnum
api_location: alink.dll
api_type: COM
f1_keywords: CloseEnum
helpviewer_keywords: CloseEnum method
ms.assetid: aa4a091e-13fe-4264-91de-e12f1c767c87
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6ade939969069fb35221d83f8c7e4e380e903a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="closeenum-method"></a><span data-ttu-id="e8584-102">CloseEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="e8584-102">CloseEnum Method</span></span>
<span data-ttu-id="e8584-103">Schließt die angegebene Enumeration und gibt die zugeordnete Ressourcen frei.</span><span class="sxs-lookup"><span data-stu-id="e8584-103">Closes the indicated enumeration and frees associated resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8584-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8584-104">Syntax</span></span>  
  
```  
HRESULT CloseEnum(  
    HALINKENUM hEnum  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8584-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8584-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e8584-106">Handle der Enumeration, die geschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e8584-106">Handle of enumeration to be closed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8584-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8584-107">Return Value</span></span>  
 <span data-ttu-id="e8584-108">Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e8584-108">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8584-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e8584-109">Requirements</span></span>  
 <span data-ttu-id="e8584-110">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="e8584-110">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8584-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8584-111">See Also</span></span>  
 [<span data-ttu-id="e8584-112">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8584-112">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="e8584-113">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8584-113">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="e8584-114">ALink-API</span><span class="sxs-lookup"><span data-stu-id="e8584-114">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
