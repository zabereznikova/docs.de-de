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
ms.openlocfilehash: 961db92c9ca9c713c38469a018ce8cde1fdefdc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556336"
---
# <a name="metahostconfigflags-enumeration"></a><span data-ttu-id="c0568-102">METAHOST_CONFIG_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c0568-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="c0568-103">Beschreibt die möglichen Flags, die zurückgegeben werden, der `pdwConfigFlags` Parameter der der [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode, gibt das Vorhandensein und die Einstellung des der `useLegacyV2RuntimeActivationPolicy` -Attribut in der [ \<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="c0568-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0568-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0568-104">Syntax</span></span>  
  
```  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="c0568-105">Member</span><span class="sxs-lookup"><span data-stu-id="c0568-105">Members</span></span>  
  
|<span data-ttu-id="c0568-106">Member</span><span class="sxs-lookup"><span data-stu-id="c0568-106">Member</span></span>|<span data-ttu-id="c0568-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0568-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="c0568-108">Die `useLegacyV2RuntimeActivationPolicy` Attribut wurde nicht im der [ \<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span><span class="sxs-lookup"><span data-stu-id="c0568-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="c0568-109">Die `useLegacyV2RuntimeActivationPolicy` Attribut war vorhanden und auf `true`.</span><span class="sxs-lookup"><span data-stu-id="c0568-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="c0568-110">Die `useLegacyV2RuntimeActivationPolicy` Attribut war vorhanden und auf `false`.</span><span class="sxs-lookup"><span data-stu-id="c0568-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="c0568-111">Übernehmen Sie auf den zurückgegebenen Wert diese Maske `pdwConfigFlags` um die Werte zu erhalten, die relevant für `useLegacyV2RuntimeActivationPolicy`.</span><span class="sxs-lookup"><span data-stu-id="c0568-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c0568-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c0568-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0568-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0568-113">Requirements</span></span>  
 <span data-ttu-id="c0568-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0568-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0568-115">**Header:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="c0568-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="c0568-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c0568-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0568-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0568-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0568-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0568-118">See also</span></span>
- [<span data-ttu-id="c0568-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="c0568-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="c0568-120">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="c0568-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="c0568-121">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="c0568-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
