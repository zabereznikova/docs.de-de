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
ms.openlocfilehash: 1ef71b14faf66c179030dff2a7d953e27463c1f7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674163"
---
# <a name="certfreeauthenticodetimestamperinfo-function"></a><span data-ttu-id="4db52-102">CertFreeAuthenticodeTimestamperInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="4db52-102">CertFreeAuthenticodeTimestamperInfo Function</span></span>

<span data-ttu-id="4db52-103">Gibt Ressourcen frei, die der [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) Struktur zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4db52-103">Frees resources allocated for the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4db52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4db52-104">Syntax</span></span>  
  
```cpp  
HRESULT CertFreeAuthenticodeTimestamperInfo (  
    [in, out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO   pTimestamperInfo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4db52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4db52-105">Parameters</span></span>  

 `pTimestamperInfo`  
 <span data-ttu-id="4db52-106">[in, out] Informationen über den Ersteller des Zeitstempels, die veröffentlicht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4db52-106">[in, out] The time stamper information to be released.</span></span> <span data-ttu-id="4db52-107">Siehe [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) Struktur.</span><span class="sxs-lookup"><span data-stu-id="4db52-107">See the [AXL_AUTHENTICODE_TIMESTAMPER_INFO](axl-authenticode-timestamper-info-structure.md) structure.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4db52-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4db52-108">Return Value</span></span>  

 <span data-ttu-id="4db52-109">`S_OK`, wenn die Funktion erfolgreich ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="4db52-109">`S_OK` if the function succeeds.</span></span> <span data-ttu-id="4db52-110">Andernfalls wird ein Fehlercode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4db52-110">Otherwise, returns an error code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4db52-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4db52-111">See also</span></span>

- [<span data-ttu-id="4db52-112">Authenticode</span><span class="sxs-lookup"><span data-stu-id="4db52-112">Authenticode</span></span>](index.md)
