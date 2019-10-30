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
ms.openlocfilehash: 4f0806e0273b111e3398fb8f2884231b96cf1116
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099774"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="f2f86-102">CertFreeAuthenticodeTimestamperInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="f2f86-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>
<span data-ttu-id="f2f86-103">Gibt Ressourcen frei, die der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) -Struktur zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="f2f86-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2f86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2f86-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f2f86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2f86-105">Parameters</span></span>  
 `pTimestamperInfo`  
 <span data-ttu-id="f2f86-106">[in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f2f86-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="f2f86-107">Siehe [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) -Struktur.</span><span class="sxs-lookup"><span data-stu-id="f2f86-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2f86-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f2f86-108">Return Value</span></span>  
 <span data-ttu-id="f2f86-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f2f86-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="f2f86-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f2f86-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2f86-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2f86-111">See also</span></span>

- [<span data-ttu-id="f2f86-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="f2f86-112">Authenticode</span></span>](index.md)
