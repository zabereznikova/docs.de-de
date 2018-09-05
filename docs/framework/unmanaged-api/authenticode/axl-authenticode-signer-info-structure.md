---
title: AXL_AUTHENTICODE_SIGNER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4b9f54c7c57d122ac1214b9f31cc4e1d1cddd71c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43670531"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="7a033-102">AXL_AUTHENTICODE_SIGNER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="7a033-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="7a033-103">Definiert Informationen zum Signaturgeber für Authenticode.</span><span class="sxs-lookup"><span data-stu-id="7a033-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a033-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a033-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    LPCWSTR pwszHash  
    LPCWSTR pwszDescription;  
    LPCWSTR pwszDescriptionUrl;  
    PCCERT_CHAIN_CONTEXT pChainContext  
} AXL_AUTHENTICODE_SIGNER_INFO, * PAXL_AUTHENTICODE_SIGNER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="7a033-105">Member</span><span class="sxs-lookup"><span data-stu-id="7a033-105">Members</span></span>  
  
|<span data-ttu-id="7a033-106">Member</span><span class="sxs-lookup"><span data-stu-id="7a033-106">Member</span></span>|<span data-ttu-id="7a033-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a033-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="7a033-108">Die Größe dieser Struktur.</span><span class="sxs-lookup"><span data-stu-id="7a033-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="7a033-109">Der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="7a033-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="7a033-110">Der hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="7a033-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="7a033-111">Der Hash.</span><span class="sxs-lookup"><span data-stu-id="7a033-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="7a033-112">Hierbei handelt es sich um die Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="7a033-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="7a033-113">Die URL der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="7a033-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="7a033-114">Der Chaincontext des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="7a033-114">The chain context of the signer.</span></span> <span data-ttu-id="7a033-115">Finden Sie unter den [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) Struktur.</span><span class="sxs-lookup"><span data-stu-id="7a033-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7a033-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a033-116">See Also</span></span>  
 [<span data-ttu-id="7a033-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="7a033-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
