---
title: CertFreeAuthenticodeTimestamperInfo-Funktion
ms.date: 03/30/2017
api_name:
- CertFreeAuthenticodeTimestamperInfo
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 3eb14c49-68c2-4516-ac89-e5bd7473831c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8ecada29528b065ddad0abc80a850ee0f347f6b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787003"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="22887-102">CertFreeAuthenticodeTimestamperInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="22887-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="22887-103">Gibt Ressourcen frei, die der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) -Struktur zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="22887-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22887-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="22887-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="22887-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="22887-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="22887-106">[in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="22887-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="22887-107">Siehe [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) -Struktur.</span><span class="sxs-lookup"><span data-stu-id="22887-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22887-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="22887-108">Return Value</span></span>  
 <span data-ttu-id="22887-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="22887-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="22887-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="22887-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22887-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22887-111">See also</span></span>

- [<span data-ttu-id="22887-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="22887-112">Authenticode</span></span>](index.md)
