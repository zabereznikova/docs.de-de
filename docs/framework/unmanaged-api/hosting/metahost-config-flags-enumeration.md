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
ms.openlocfilehash: 01e55659bf2a348ec763f51112cbdcd706f27c84
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730005"
---
# <a name="metahost_config_flags-enumeration"></a><span data-ttu-id="a274e-102">METAHOST_CONFIG_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="a274e-102">METAHOST_CONFIG_FLAGS Enumeration</span></span>

<span data-ttu-id="a274e-103">Beschreibt die möglichen Flags, die im- `pdwConfigFlags` Parameter der [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) -Methode zurückgegeben werden, und gibt das vorhanden sein und das Festlegen des- `useLegacyV2RuntimeActivationPolicy` Attributs im- [ \<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) der Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="a274e-103">Describes the possible flags returned in the `pdwConfigFlags` parameter of the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method, indicating the presence and setting of the `useLegacyV2RuntimeActivationPolicy` attribute in the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) of the configuration file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a274e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a274e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET  = 0x00,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE   = 0x01,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE  = 0x02,  
    METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK   = 0x03  
} METAHOST_CONFIG_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="a274e-105">Member</span><span class="sxs-lookup"><span data-stu-id="a274e-105">Members</span></span>  
  
|<span data-ttu-id="a274e-106">Member</span><span class="sxs-lookup"><span data-stu-id="a274e-106">Member</span></span>|<span data-ttu-id="a274e-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a274e-107">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_UNSET`|<span data-ttu-id="a274e-108">Das- `useLegacyV2RuntimeActivationPolicy` Attribut war nicht im- [ \<startup> Element](../../configure-apps/file-schema/startup/startup-element.md)vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a274e-108">The `useLegacyV2RuntimeActivationPolicy` attribute was not present in the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md).</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_TRUE`|<span data-ttu-id="a274e-109">Das `useLegacyV2RuntimeActivationPolicy` -Attribut war vorhanden und auf festgelegt `true` .</span><span class="sxs-lookup"><span data-stu-id="a274e-109">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `true`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_FALSE`|<span data-ttu-id="a274e-110">Das `useLegacyV2RuntimeActivationPolicy` -Attribut war vorhanden und auf festgelegt `false` .</span><span class="sxs-lookup"><span data-stu-id="a274e-110">The `useLegacyV2RuntimeActivationPolicy` attribute was present and set to `false`.</span></span>|  
|`METAHOST_CONFIG_FLAGS_LEGACY_V2_ACTIVATION_POLICY_MASK`|<span data-ttu-id="a274e-111">Wenden Sie diese Maske auf den in zurückgegebenen Wert `pdwConfigFlags` an, um die für relevanten Werte zu erhalten `useLegacyV2RuntimeActivationPolicy` .</span><span class="sxs-lookup"><span data-stu-id="a274e-111">Apply this mask to the value returned in `pdwConfigFlags` to get the values relevant to `useLegacyV2RuntimeActivationPolicy`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a274e-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a274e-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a274e-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a274e-113">Requirements</span></span>  

 <span data-ttu-id="a274e-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a274e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a274e-115">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="a274e-115">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="a274e-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a274e-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a274e-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a274e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a274e-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a274e-118">See also</span></span>

- [<span data-ttu-id="a274e-119">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="a274e-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="a274e-120">GetRequestedRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="a274e-120">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
- [<span data-ttu-id="a274e-121">\<startup>-Element</span><span class="sxs-lookup"><span data-stu-id="a274e-121">\<startup> Element</span></span>](../../configure-apps/file-schema/startup/startup-element.md)
