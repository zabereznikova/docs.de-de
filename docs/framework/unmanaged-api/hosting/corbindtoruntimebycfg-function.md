---
title: CorBindToRuntimeByCfg-Funktion
ms.date: 03/30/2017
api_name:
- CorBindToRuntimeByCfg
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorBindToRuntimeByCfg
helpviewer_keywords:
- CorBindToRuntimeByCfg function [.NET Framework hosting]
ms.assetid: ded1e492-a782-4185-9c66-709e421c1782
topic_type:
- apiref
ms.openlocfilehash: 4fbc6e7ea531f65a6b1cd0ec93f4847ab8e4fe83
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178243"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="43829-102">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="43829-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="43829-103">Lädt die Common Language Runtime (CLR) mithilfe von Versionsinformationen, die aus einer XML-Datei gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="43829-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="43829-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="43829-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43829-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="43829-105">Syntax</span></span>  
  
```cpp  
HRESULT CorBindToRuntimeByCfg (  
    [in]  IStream     *pCfgStream,  
    [in]  DWORD        reserved,  
    [in]  DWORD        startupFlags,  
    [in]  REFCLSID     rclsid,  
    [in]  REFIID       riid,
    [out] LPVOID FAR*  ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43829-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="43829-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="43829-107">[in] Ein Zeiger auf `IStream` ein Objekt, das die XML-Datei liest.</span><span class="sxs-lookup"><span data-stu-id="43829-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="43829-108">[in] Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="43829-108">[in] Reserved for future use.</span></span> <span data-ttu-id="43829-109">Verwenden Sie 0 (Null) als Wert.</span><span class="sxs-lookup"><span data-stu-id="43829-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="43829-110">[in] Ein Wert [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) der STARTUP_FLAGS-Enumeration, die das Startverhalten der CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="43829-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="43829-111">[in] Die `CLSID` der coclass, die entweder den [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) oder die [ICLRRuntimeHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) implementiert.</span><span class="sxs-lookup"><span data-stu-id="43829-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="43829-112">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="43829-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="43829-113">[in] Die `IID` der `ICorRuntimeHost` oder `ICLRRuntimeHost` der Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="43829-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="43829-114">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="43829-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="43829-115">[out] Ein Zeiger auf die Adresse der zurückgegebenen Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="43829-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43829-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="43829-116">Remarks</span></span>  
 <span data-ttu-id="43829-117">Das Format der XML-Datei wird nach der Standardanwendungskonfigurationsdatei modelliert.</span><span class="sxs-lookup"><span data-stu-id="43829-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="43829-118">Weitere Informationen zu XML-Dateien finden Sie unter [Konfigurationsdateischema](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="43829-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43829-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="43829-119">Requirements</span></span>  
 <span data-ttu-id="43829-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43829-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43829-121">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="43829-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43829-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43829-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43829-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43829-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43829-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43829-124">See also</span></span>

- [<span data-ttu-id="43829-125">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="43829-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="43829-126">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="43829-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="43829-127">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="43829-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="43829-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="43829-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="43829-129">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43829-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="43829-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="43829-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
