---
title: AXL_AUTHENTICODE_SIGNER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
ms.openlocfilehash: 1bb6df4aa82f8dfc367083732af2065aba9d07b1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679987"
---
# <a name="axl_authenticode_signer_info-structure"></a><span data-ttu-id="54802-102">AXL_AUTHENTICODE_SIGNER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="54802-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>

<span data-ttu-id="54802-103">Definiert die Authenticode-Informationen des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="54802-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54802-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="54802-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="54802-105">Member</span><span class="sxs-lookup"><span data-stu-id="54802-105">Members</span></span>  
  
|<span data-ttu-id="54802-106">Member</span><span class="sxs-lookup"><span data-stu-id="54802-106">Member</span></span>|<span data-ttu-id="54802-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="54802-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="54802-108">Die Größe dieser Struktur.</span><span class="sxs-lookup"><span data-stu-id="54802-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="54802-109">Der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="54802-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="54802-110">Der hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="54802-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="54802-111">Der Hash.</span><span class="sxs-lookup"><span data-stu-id="54802-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="54802-112">Die Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="54802-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="54802-113">Die URL der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="54802-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="54802-114">Der Chaincontext des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="54802-114">The chain context of the signer.</span></span> <span data-ttu-id="54802-115">Siehe [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) Struktur.</span><span class="sxs-lookup"><span data-stu-id="54802-115">See the [CERT_CONTEXT](/windows/win32/api/wincrypt/ns-wincrypt-cert_context) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="54802-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54802-116">See also</span></span>

- [<span data-ttu-id="54802-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="54802-117">Authenticode</span></span>](index.md)
