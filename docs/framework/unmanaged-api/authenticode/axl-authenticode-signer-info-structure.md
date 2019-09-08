---
title: AXL_AUTHENTICODE_SIGNER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9aaa0258b53b6b39874c8c99c71ecf53cbdb8f97
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787082"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="182c7-102">AXL_AUTHENTICODE_SIGNER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="182c7-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="182c7-103">Definiert die Authenticode-Informationen des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="182c7-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="182c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="182c7-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="182c7-105">Member</span><span class="sxs-lookup"><span data-stu-id="182c7-105">Members</span></span>  
  
|<span data-ttu-id="182c7-106">Member</span><span class="sxs-lookup"><span data-stu-id="182c7-106">Member</span></span>|<span data-ttu-id="182c7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="182c7-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="182c7-108">Die Größe dieser Struktur.</span><span class="sxs-lookup"><span data-stu-id="182c7-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="182c7-109">Der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="182c7-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="182c7-110">Der hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="182c7-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="182c7-111">Der Hash.</span><span class="sxs-lookup"><span data-stu-id="182c7-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="182c7-112">Hierbei handelt es sich um die Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="182c7-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="182c7-113">Die URL der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="182c7-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="182c7-114">Der Chaincontext des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="182c7-114">The chain context of the signer.</span></span> <span data-ttu-id="182c7-115">Siehe [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) -Struktur.</span><span class="sxs-lookup"><span data-stu-id="182c7-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="182c7-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="182c7-116">See also</span></span>

- [<span data-ttu-id="182c7-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="182c7-117">Authenticode</span></span>](index.md)
