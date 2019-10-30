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
ms.openlocfilehash: 3802354bf52cd2aab2a4149d565993b9965e8312
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138299"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="2ae37-102">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ae37-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="2ae37-103">Lädt die Common Language Runtime (CLR) in einen Prozess, indem Versionsinformationen verwendet werden, die aus einer XML-Datei gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="2ae37-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="2ae37-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="2ae37-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ae37-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ae37-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2ae37-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ae37-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="2ae37-107">in Ein Zeiger auf ein `IStream` Objekt, das die XML-Datei liest.</span><span class="sxs-lookup"><span data-stu-id="2ae37-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="2ae37-108">in Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="2ae37-108">[in] Reserved for future use.</span></span> <span data-ttu-id="2ae37-109">0 (null) als Wert verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ae37-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="2ae37-110">in Ein Wert der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) -Enumeration, der das Startverhalten der CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="2ae37-110">[in] A value of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="2ae37-111">in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="2ae37-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="2ae37-112">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="2ae37-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="2ae37-113">in Die `IID` der `ICorRuntimeHost` oder der `ICLRRuntimeHost`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2ae37-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="2ae37-114">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="2ae37-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2ae37-115">vorgenommen Ein Zeiger auf die Adresse der zurückgegebenen-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2ae37-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ae37-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2ae37-116">Remarks</span></span>  
 <span data-ttu-id="2ae37-117">Das Format der XML-Datei wird nach der Standard Anwendungs Konfigurationsdatei modelliert.</span><span class="sxs-lookup"><span data-stu-id="2ae37-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="2ae37-118">Weitere Informationen zu XML-Dateien finden Sie unter [Schema der Konfigurationsdatei](../../../../docs/framework/configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="2ae37-118">For more information about XML files, see [Configuration File Schema](../../../../docs/framework/configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ae37-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ae37-119">Requirements</span></span>  
 <span data-ttu-id="2ae37-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ae37-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ae37-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="2ae37-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2ae37-122">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="2ae37-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2ae37-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ae37-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ae37-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ae37-124">See also</span></span>

- [<span data-ttu-id="2ae37-125">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ae37-125">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)
- [<span data-ttu-id="2ae37-126">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ae37-126">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)
- [<span data-ttu-id="2ae37-127">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ae37-127">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)
- [<span data-ttu-id="2ae37-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="2ae37-128">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)
- [<span data-ttu-id="2ae37-129">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ae37-129">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
- [<span data-ttu-id="2ae37-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="2ae37-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
