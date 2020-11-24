---
title: AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
ms.openlocfilehash: b6852519da6cf4e12669aa2efa24862053adbc03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674241"
---
# <a name="axl_authenticode_timestamper_info-structure"></a><span data-ttu-id="8c03b-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="8c03b-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>

<span data-ttu-id="8c03b-103">Definiert die Authenticode-Informationen des Zeitstempelgebers.</span><span class="sxs-lookup"><span data-stu-id="8c03b-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c03b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c03b-104">Syntax</span></span>  
  
```cpp  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="8c03b-105">Member</span><span class="sxs-lookup"><span data-stu-id="8c03b-105">Members</span></span>  
  
|<span data-ttu-id="8c03b-106">Member</span><span class="sxs-lookup"><span data-stu-id="8c03b-106">Member</span></span>|<span data-ttu-id="8c03b-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c03b-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="8c03b-108">Die Größe dieser Struktur.</span><span class="sxs-lookup"><span data-stu-id="8c03b-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="8c03b-109">Der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="8c03b-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="8c03b-110">Der hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="8c03b-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="8c03b-111">Der Zeitpunkt des Zeitstempels.</span><span class="sxs-lookup"><span data-stu-id="8c03b-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="8c03b-112">Der Chaincontext des Erstellers des Zeitstempels.</span><span class="sxs-lookup"><span data-stu-id="8c03b-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="8c03b-113">Siehe [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) Struktur.</span><span class="sxs-lookup"><span data-stu-id="8c03b-113">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8c03b-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c03b-114">See also</span></span>

- [<span data-ttu-id="8c03b-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="8c03b-115">Authenticode</span></span>](index.md)
