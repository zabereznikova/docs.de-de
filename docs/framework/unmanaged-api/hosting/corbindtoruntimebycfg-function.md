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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8f5e9a909a752dd8dc70bfc1c683b4611715f31
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767965"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="af1a7-102">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="af1a7-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="af1a7-103">Lädt die common Language Runtime (CLR) in einen Prozess mit Versionsinformationen, die aus einer XML-Datei gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="af1a7-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="af1a7-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="af1a7-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af1a7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="af1a7-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="af1a7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="af1a7-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="af1a7-107">[in] Ein Zeiger auf ein `IStream` Objekt, das die XML-Datei liest.</span><span class="sxs-lookup"><span data-stu-id="af1a7-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="af1a7-108">[in] Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="af1a7-108">[in] Reserved for future use.</span></span> <span data-ttu-id="af1a7-109">Verwenden Sie 0 (null) als Wert ein.</span><span class="sxs-lookup"><span data-stu-id="af1a7-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="af1a7-110">[in] Der Wert der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Enumeration, die das Startverhalten der CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="af1a7-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="af1a7-111">[in] Die `CLSID` der Co-Klasse, die entweder implementiert die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) oder [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="af1a7-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="af1a7-112">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="af1a7-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="af1a7-113">[in] Die `IID` entweder die `ICorRuntimeHost` oder `ICLRRuntimeHost` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="af1a7-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="af1a7-114">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="af1a7-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="af1a7-115">[out] Ein Zeiger auf die Adresse der zurückgegebenen Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="af1a7-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af1a7-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af1a7-116">Remarks</span></span>  
 <span data-ttu-id="af1a7-117">Das Format der XML-Datei ist der standard-Anwendungskonfigurationsdatei nachgebildet.</span><span class="sxs-lookup"><span data-stu-id="af1a7-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="af1a7-118">Weitere Informationen zu XML-Dateien, finden Sie unter [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="af1a7-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af1a7-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af1a7-119">Requirements</span></span>  
 <span data-ttu-id="af1a7-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af1a7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af1a7-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af1a7-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af1a7-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="af1a7-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af1a7-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af1a7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af1a7-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af1a7-124">See also</span></span>

- [<span data-ttu-id="af1a7-125">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="af1a7-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="af1a7-126">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="af1a7-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="af1a7-127">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="af1a7-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="af1a7-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="af1a7-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="af1a7-129">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af1a7-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="af1a7-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="af1a7-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
