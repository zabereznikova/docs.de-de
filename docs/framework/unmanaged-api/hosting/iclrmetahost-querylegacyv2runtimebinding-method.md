---
title: ICLRMetaHost::QueryLegacyV2RuntimeBinding-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::QueryLegacyV2RuntimeBinding
helpviewer_keywords:
- QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
- ICLRMetaHost::QueryLegacyV2RuntimeBinding method [.NET Framework hosting]
ms.assetid: 9929817e-acc9-40b7-960c-598664e04b60
topic_type:
- apiref
ms.openlocfilehash: d65191e515db9c302cef669a824ffd08327faf34
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713989"
---
# <a name="iclrmetahostquerylegacyv2runtimebinding-method"></a><span data-ttu-id="05396-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding-Methode</span><span class="sxs-lookup"><span data-stu-id="05396-102">ICLRMetaHost::QueryLegacyV2RuntimeBinding Method</span></span>

<span data-ttu-id="05396-103">Gibt eine-Schnittstelle zurück, die eine Laufzeit darstellt, an die die Legacy Aktivierungs Richtlinie gebunden wurde, z. b. durch die Verwendung des- `useLegacyV2RuntimeActivationPolicy` Attributs für den Eintrag der [ \<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) Konfigurationsdatei, durch direktes verwenden der Legacy-Aktivierungs-APIs oder durch Aufrufen der [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="05396-103">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05396-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05396-104">Syntax</span></span>  
  
```cpp  
HRESULT QueryLegacyV2RuntimeBinding (  
    [in] REFIID riid,  
    [out, iid_is(riid), retval] LPVOID *ppUnk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05396-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05396-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="05396-106">in Erforderlich. zurzeit ist der einzige gültige Wert für diesen Parameter `IID_ICLRRuntimeInfo` .</span><span class="sxs-lookup"><span data-stu-id="05396-106">[in] Required.Currently the only valid value for this parameter is `IID_ICLRRuntimeInfo`.</span></span>  
  
 `ppUnk`  
 <span data-ttu-id="05396-107">[out] erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05396-107">[out] Required.</span></span> <span data-ttu-id="05396-108">Diese Methode gibt einen Zeiger auf die [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zurück, die eine Laufzeit darstellt, die an die ältere Aktivierungs Richtlinie gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="05396-108">When this method returns, contains a pointer to the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that represents a runtime that has been bound to legacy activation policy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05396-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05396-109">Return Value</span></span>  

 <span data-ttu-id="05396-110">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="05396-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="05396-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05396-111">HRESULT</span></span>|<span data-ttu-id="05396-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="05396-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05396-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="05396-113">S_OK</span></span>|<span data-ttu-id="05396-114">Die Methode wurde erfolgreich abgeschlossen und hat eine Laufzeit zurückgegeben, die an eine ältere Aktivierungsrichtlinie gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="05396-114">The method completed successfully and returned a runtime that was bound to legacy activation policy.</span></span>|  
|<span data-ttu-id="05396-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="05396-115">S_FALSE</span></span>|<span data-ttu-id="05396-116">Die Methode wurde erfolgreich abgeschlossen, aber eine ältere Laufzeit wurde noch nicht gebunden.</span><span class="sxs-lookup"><span data-stu-id="05396-116">The method completed successfully, but a legacy runtime has not yet been bound.</span></span>|  
|<span data-ttu-id="05396-117">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="05396-117">E_NOINTERFACE</span></span>|<span data-ttu-id="05396-118">Die Methode hat eine Laufzeitumgebung gefunden, die an eine ältere Aktivierungsrichtlinie gebunden war, aber `riid` wird von dieser Laufzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="05396-118">The method found a runtime that was bound to legacy activation policy, but `riid` is not supported by that runtime.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05396-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="05396-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05396-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05396-120">Requirements</span></span>  

 <span data-ttu-id="05396-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05396-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05396-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="05396-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="05396-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="05396-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="05396-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05396-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05396-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05396-125">See also</span></span>

- [<span data-ttu-id="05396-126">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05396-126">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="05396-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="05396-127">Hosting</span></span>](index.md)
