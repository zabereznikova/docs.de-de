---
title: METAHOST_CONFIG_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- METAHOST_CONFIG_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_CONFIG_FLAGS
helpviewer_keywords:
- METAHOST_CONFIG_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 6f1e389f-ed99-4d6a-a0ba-72d7d869a01d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a13897f71bb675b982a84d57d310b799989c41aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442929"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="96c1d-102">METAHOST_CONFIG_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="96c1d-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="96c1d-103">Beschreibt die möglichen Flags, die zurückgegeben werden, der `pdwConfigFlags` Parameter von der [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) Methode, gibt das Vorhandensein und die Einstellung des der `useLegacyV2RuntimeActivationPolicy` Attribut in der [ \<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="96c1d-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96c1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="96c1d-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="96c1d-105">Member</span><span class="sxs-lookup"><span data-stu-id="96c1d-105">Members</span></span>  
  
|<span data-ttu-id="96c1d-106">Member</span><span class="sxs-lookup"><span data-stu-id="96c1d-106">Member</span></span>|<span data-ttu-id="96c1d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="96c1d-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="96c1d-108">Die `useLegacyV2RuntimeActivationPolicy` Attribut war nicht vorhanden, in der [ \<Startup > Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="96c1d-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="96c1d-109">Die `useLegacyV2RuntimeActivationPolicy` Attribut war vorhanden und auf `true`.</span><span class="sxs-lookup"><span data-stu-id="96c1d-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="96c1d-110">Die `useLegacyV2RuntimeActivationPolicy` Attribut war vorhanden und auf `false`.</span><span class="sxs-lookup"><span data-stu-id="96c1d-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="96c1d-111">Der zurückgegebene Wert in dieser Maske zuweisen `pdwConfigFlags` zum Abrufen der Werte relevant `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="96c1d-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96c1d-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="96c1d-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96c1d-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="96c1d-113">Requirements</span></span>  
 <span data-ttu-id="96c1d-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96c1d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96c1d-115">**Header:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="96c1d-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="96c1d-116">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="96c1d-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96c1d-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96c1d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96c1d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96c1d-118">See Also</span></span>  
 [<span data-ttu-id="96c1d-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="96c1d-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="96c1d-120">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="96c1d-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)  
 [<span data-ttu-id="96c1d-121">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="96c1d-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
