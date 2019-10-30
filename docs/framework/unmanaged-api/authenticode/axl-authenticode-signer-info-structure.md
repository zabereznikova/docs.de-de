---
title: AXL_AUTHENTICODE_SIGNER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 00132bb378d69c0db9fe9d762407707346238917
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132510"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="72876-102">AXL_AUTHENTICODE_SIGNER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="72876-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="72876-103">Definiert die Authenticode-Informationen des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="72876-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72876-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72876-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="72876-105">Member</span><span class="sxs-lookup"><span data-stu-id="72876-105">Members</span></span>  
  
|<span data-ttu-id="72876-106">Member</span><span class="sxs-lookup"><span data-stu-id="72876-106">Member</span></span>|<span data-ttu-id="72876-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="72876-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="72876-108">Die Größe dieser Struktur.</span><span class="sxs-lookup"><span data-stu-id="72876-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="72876-109">Der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="72876-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="72876-110">Der hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="72876-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="72876-111">Der Hash.</span><span class="sxs-lookup"><span data-stu-id="72876-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="72876-112">Hierbei handelt es sich um die Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="72876-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="72876-113">Die URL der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="72876-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="72876-114">Der Chaincontext des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="72876-114">The chain context of the signer.</span></span> <span data-ttu-id="72876-115">Siehe [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) -Struktur.</span><span class="sxs-lookup"><span data-stu-id="72876-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="72876-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72876-116">See also</span></span>

- [<span data-ttu-id="72876-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="72876-117">Authenticode</span></span>](index.md)
