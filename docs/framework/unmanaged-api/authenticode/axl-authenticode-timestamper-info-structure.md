---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d82ed3299f967457fe967d096a238da6143751a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219160"
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="3ce53-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="3ce53-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="3ce53-103">Definiert die Authenticode-Informationen des Zeitstempelgebers.</span><span class="sxs-lookup"><span data-stu-id="3ce53-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ce53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ce53-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="3ce53-105">Member</span><span class="sxs-lookup"><span data-stu-id="3ce53-105">Members</span></span>  
  
|<span data-ttu-id="3ce53-106">Member</span><span class="sxs-lookup"><span data-stu-id="3ce53-106">Member</span></span>|<span data-ttu-id="3ce53-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ce53-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="3ce53-108">Die Größe dieser Struktur.</span><span class="sxs-lookup"><span data-stu-id="3ce53-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="3ce53-109">Der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3ce53-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="3ce53-110">Der hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="3ce53-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="3ce53-111">Der Zeitpunkt des Zeitstempels.</span><span class="sxs-lookup"><span data-stu-id="3ce53-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="3ce53-112">Der Chaincontext des Erstellers des Zeitstempels.</span><span class="sxs-lookup"><span data-stu-id="3ce53-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="3ce53-113">Finden Sie unter den [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) Struktur.</span><span class="sxs-lookup"><span data-stu-id="3ce53-113">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3ce53-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ce53-114">See also</span></span>

- [<span data-ttu-id="3ce53-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="3ce53-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
