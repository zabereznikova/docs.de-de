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
ms.openlocfilehash: d319382b577844a804c3e4562676491a15de5f63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673773"
---
# <a name="corbindtoruntimebycfg-function"></a><span data-ttu-id="65a2d-102">CorBindToRuntimeByCfg-Funktion</span><span class="sxs-lookup"><span data-stu-id="65a2d-102">CorBindToRuntimeByCfg Function</span></span>

<span data-ttu-id="65a2d-103">Lädt die Common Language Runtime (CLR) in einen Prozess, indem Versionsinformationen verwendet werden, die aus einer XML-Datei gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="65a2d-103">Loads the common language runtime (CLR) into a process by using version information that is read from an XML file.</span></span>  
  
 <span data-ttu-id="65a2d-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="65a2d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65a2d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="65a2d-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="65a2d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="65a2d-106">Parameters</span></span>  

 `pCfgStream`  
 <span data-ttu-id="65a2d-107">in Ein Zeiger auf ein `IStream` Objekt, das die XML-Datei liest.</span><span class="sxs-lookup"><span data-stu-id="65a2d-107">[in] A pointer to an `IStream` object that reads the XML file.</span></span>  
  
 `reserved`  
 <span data-ttu-id="65a2d-108">[in] Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="65a2d-108">[in] Reserved for future use.</span></span> <span data-ttu-id="65a2d-109">0 (null) als Wert verwenden.</span><span class="sxs-lookup"><span data-stu-id="65a2d-109">Use 0 (zero) as value.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="65a2d-110">in Ein Wert der [STARTUP_FLAGS](startup-flags-enumeration.md) -Enumeration, die das Startverhalten der CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="65a2d-110">[in] A value of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration that specifies the startup behavior of the CLR.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="65a2d-111">in Der `CLSID` der Co-Klasse, die entweder die [ICorRuntimeHost](icorruntimehost-interface.md) -oder die [ICLRRuntimeHost](iclrruntimehost-interface.md) -Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="65a2d-111">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](icorruntimehost-interface.md) or the [ICLRRuntimeHost](iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="65a2d-112">Unterstützte Werte sind "CLSID_CorRuntimeHost" oder "CLSID_CLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="65a2d-112">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="65a2d-113">in Der der- `IID` `ICorRuntimeHost` Schnittstelle oder der- `ICLRRuntimeHost` Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="65a2d-113">[in] The `IID` of either the `ICorRuntimeHost` or the `ICLRRuntimeHost` interface.</span></span> <span data-ttu-id="65a2d-114">Unterstützte Werte sind "IID_ICorRuntimeHost" oder "IID_ICLRRuntimeHost".</span><span class="sxs-lookup"><span data-stu-id="65a2d-114">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="65a2d-115">vorgenommen Ein Zeiger auf die Adresse der zurückgegebenen-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="65a2d-115">[out] A pointer to the address of the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65a2d-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="65a2d-116">Remarks</span></span>  

 <span data-ttu-id="65a2d-117">Das Format der XML-Datei wird nach der Standard Anwendungs Konfigurationsdatei modelliert.</span><span class="sxs-lookup"><span data-stu-id="65a2d-117">The format of the XML file is modeled after the standard application configuration file.</span></span> <span data-ttu-id="65a2d-118">Weitere Informationen zu XML-Dateien finden Sie unter [Schema der Konfigurationsdatei](../../configure-apps/file-schema/index.md).</span><span class="sxs-lookup"><span data-stu-id="65a2d-118">For more information about XML files, see [Configuration File Schema](../../configure-apps/file-schema/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65a2d-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="65a2d-119">Requirements</span></span>  

 <span data-ttu-id="65a2d-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65a2d-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65a2d-121">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="65a2d-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="65a2d-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="65a2d-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65a2d-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65a2d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65a2d-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65a2d-124">See also</span></span>

- [<span data-ttu-id="65a2d-125">CorBindToCurrentRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="65a2d-125">CorBindToCurrentRuntime Function</span></span>](corbindtocurrentruntime-function.md)
- [<span data-ttu-id="65a2d-126">CorBindToRuntime-Funktion</span><span class="sxs-lookup"><span data-stu-id="65a2d-126">CorBindToRuntime Function</span></span>](corbindtoruntime-function.md)
- [<span data-ttu-id="65a2d-127">CorBindToRuntimeEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="65a2d-127">CorBindToRuntimeEx Function</span></span>](corbindtoruntimeex-function.md)
- [<span data-ttu-id="65a2d-128">CorBindToRuntimeHost-Funktion</span><span class="sxs-lookup"><span data-stu-id="65a2d-128">CorBindToRuntimeHost Function</span></span>](corbindtoruntimehost-function.md)
- [<span data-ttu-id="65a2d-129">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65a2d-129">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
- [<span data-ttu-id="65a2d-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="65a2d-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
