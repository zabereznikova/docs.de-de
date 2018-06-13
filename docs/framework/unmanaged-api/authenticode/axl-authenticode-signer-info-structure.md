---
title: AXL_AUTHENTICODE_SIGNER_INFO-Struktur
ms.date: 03/30/2017
ms.assetid: 81c0f8b4-ce35-4716-8651-b642d40648a2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd07707b5a80ec0980fc50b27caddf0a24398fd1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33400444"
---
# <a name="axlauthenticodesignerinfo-structure"></a><span data-ttu-id="78a2f-102">AXL_AUTHENTICODE_SIGNER_INFO-Struktur</span><span class="sxs-lookup"><span data-stu-id="78a2f-102">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>
<span data-ttu-id="78a2f-103">Definiert Informationen zum Signaturgeber für Authenticode.</span><span class="sxs-lookup"><span data-stu-id="78a2f-103">Defines the Authenticode signer information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78a2f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78a2f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="78a2f-105">Member</span><span class="sxs-lookup"><span data-stu-id="78a2f-105">Members</span></span>  
  
|<span data-ttu-id="78a2f-106">Member</span><span class="sxs-lookup"><span data-stu-id="78a2f-106">Member</span></span>|<span data-ttu-id="78a2f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="78a2f-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="78a2f-108">Die Größe dieser Struktur.</span><span class="sxs-lookup"><span data-stu-id="78a2f-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="78a2f-109">Der Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="78a2f-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="78a2f-110">Der hash-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="78a2f-110">The hash algorithm.</span></span>|  
|`pwszHash`|<span data-ttu-id="78a2f-111">Der Hash.</span><span class="sxs-lookup"><span data-stu-id="78a2f-111">The hash.</span></span>|  
|`pwszDescription`|<span data-ttu-id="78a2f-112">Hierbei handelt es sich um die Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="78a2f-112">The description.</span></span>|  
|`pwszDescriptionUrl`|<span data-ttu-id="78a2f-113">Die URL der Beschreibung.</span><span class="sxs-lookup"><span data-stu-id="78a2f-113">The URL of the description.</span></span>|  
|`pChainContext`|<span data-ttu-id="78a2f-114">Der Chaincontext des Signaturgebers.</span><span class="sxs-lookup"><span data-stu-id="78a2f-114">The chain context of the signer.</span></span> <span data-ttu-id="78a2f-115">Finden Sie unter der [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) Struktur.</span><span class="sxs-lookup"><span data-stu-id="78a2f-115">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="78a2f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78a2f-116">See Also</span></span>  
 [<span data-ttu-id="78a2f-117">Authenticode</span><span class="sxs-lookup"><span data-stu-id="78a2f-117">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
