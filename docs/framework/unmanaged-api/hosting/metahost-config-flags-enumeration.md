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
ms.openlocfilehash: 07cab119810c4da25d16a4ad7c13f2d2bda16455
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140310"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="dd942-102">METAHOST_CONFIG_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="dd942-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>
<span data-ttu-id="dd942-103">Beschreibt die möglichen Flags, die im `pdwConfigFlags`-Parameter der [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) -Methode zurückgegeben werden, und gibt das vorhanden sein und das Festlegen des `useLegacyV2RuntimeActivationPolicy` Attributs im [\<Startup-> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dd942-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd942-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd942-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="dd942-105">Member</span><span class="sxs-lookup"><span data-stu-id="dd942-105">Members</span></span>  
  
|<span data-ttu-id="dd942-106">Member</span><span class="sxs-lookup"><span data-stu-id="dd942-106">Member</span></span>|<span data-ttu-id="dd942-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd942-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="dd942-108">Das `useLegacyV2RuntimeActivationPolicy`-Attribut war im [\<Startup >-Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="dd942-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="dd942-109">Das `useLegacyV2RuntimeActivationPolicy`-Attribut war vorhanden und auf `true`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dd942-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="dd942-110">Das `useLegacyV2RuntimeActivationPolicy`-Attribut war vorhanden und auf `false`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dd942-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="dd942-111">Wenden Sie diese Maske auf den in `pdwConfigFlags` zurückgegebenen Wert an, um die für `useLegacyV2RuntimeActivationPolicy`relevanten Werte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="dd942-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd942-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd942-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd942-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd942-113">Requirements</span></span>  
 <span data-ttu-id="dd942-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd942-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd942-115">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="dd942-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="dd942-116">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dd942-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd942-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd942-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd942-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd942-118">See also</span></span>

- [<span data-ttu-id="dd942-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="dd942-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="dd942-120">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="dd942-120">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="dd942-121">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="dd942-121">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
