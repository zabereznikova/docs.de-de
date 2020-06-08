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
ms.openlocfilehash: 8b7dcdcc6d9d0106af1bb83ee591cff76239b416
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504432"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="e14e5-102">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="e14e5-102">CorBindToRuntimeByCfg Function</span></span>
<span data-ttu-id="e14e5-103">Lädt die Common Language Runtime (CLR) in einen Prozess, indem Versionsinformationen verwendet werden, die aus einer XML-Datei gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="e14e5-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="e14e5-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="e14e5-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e14e5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e14e5-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e14e5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e14e5-106">Parameters</span></span>  
 `pCfgStream`  
 <span data-ttu-id="e14e5-107">in Ein Zeiger auf ein `IStream` Objekt, das die XML-Datei liest.</span><span class="sxs-lookup"><span data-stu-id="e14e5-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="e14e5-108">[in] Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="e14e5-108">[in] Reserved for future use.</span></span> <span data-ttu-id="e14e5-109">0 (null) als Wert verwenden.</span><span class="sxs-lookup"><span data-stu-id="e14e5-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="e14e5-110">in Ein Wert der [STARTUP_FLAGS](startup-flags-enumeration.md) -Enumeration, die das Startverhalten der CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="e14e5-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="e14e5-111">in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="e14e5-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="e14e5-112">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="e14e5-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="e14e5-113">in Der der- `IID` `ICorRuntimeHost` Schnittstelle oder der- `ICLRRuntimeHost` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e14e5-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="e14e5-114">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="e14e5-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="e14e5-115">vorgenommen Ein Zeiger auf die Adresse der zurückgegebenen-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e14e5-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e14e5-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e14e5-116">Remarks</span></span>  
 <span data-ttu-id="e14e5-117">Das Format der XML-Datei wird nach der Standard Anwendungs Konfigurationsdatei modelliert.</span><span class="sxs-lookup"><span data-stu-id="e14e5-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="e14e5-118">Weitere Informationen zu XML-Dateien finden Sie unter [Schema der Konfigurationsdatei](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="e14e5-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e14e5-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e14e5-119">Requirements</span></span>  
 <span data-ttu-id="e14e5-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e14e5-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e14e5-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="e14e5-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e14e5-122">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="e14e5-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e14e5-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e14e5-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e14e5-124">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="e14e5-124">See also</span></span>

- [<span data-ttu-id="e14e5-125">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="e14e5-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="e14e5-126">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="e14e5-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="e14e5-127">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="e14e5-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="e14e5-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="e14e5-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="e14e5-129">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e14e5-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="e14e5-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="e14e5-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
