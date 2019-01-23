---
title: AXL_AUTHENTICODE_SIGNER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff50ee18dc3155bf784d6b752da8efc841aa6ce5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559436"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="33e5c-102">AXL_AUTHENTICODE_SIGNER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="33e5c-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="33e5c-103">Definiert Informationen zum Signaturgeber für Authenticode.</span><span class="sxs-lookup"><span data-stu-id="33e5c-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33e5c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33e5c-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="33e5c-105">Member</span><span class="sxs-lookup"><span data-stu-id="33e5c-105">Members</span></span>  
  
|<span data-ttu-id="33e5c-106">Member</span><span class="sxs-lookup"><span data-stu-id="33e5c-106">Member</span></span>|<span data-ttu-id="33e5c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33e5c-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="33e5c-108">Die Größe dieser Struktur.</span><span class="sxs-lookup"><span data-stu-id="33e5c-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="33e5c-109">Der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="33e5c-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="33e5c-110">Der hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="33e5c-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="33e5c-111">Der Hash.</span><span class="sxs-lookup"><span data-stu-id="33e5c-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="33e5c-112">Hierbei handelt es sich um die Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="33e5c-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="33e5c-113">Die URL der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="33e5c-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="33e5c-114">Der Chaincontext des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="33e5c-114">The chain context of the signer.</span></span> <span data-ttu-id="33e5c-115">Finden Sie unter den [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) Struktur.</span><span class="sxs-lookup"><span data-stu-id="33e5c-115">See the [CERT_CONTEXT](/windows/desktop/api/wincrypt/ns-wincrypt-_cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33e5c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33e5c-116">See also</span></span>
- [<span data-ttu-id="33e5c-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="33e5c-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
