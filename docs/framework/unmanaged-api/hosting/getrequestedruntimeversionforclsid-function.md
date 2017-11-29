---
title: GetRequestedRuntimeVersionForCLSID-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a5b9e4b186b6c9b91c1182e8700268f0e1c038f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="af745-102">GetRequestedRuntimeVersionForCLSID-Funktion</span><span class="sxs-lookup"><span data-stu-id="af745-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="af745-103">Ruft die entsprechende Version zur common Language Runtime (CLR) für die Klasse mit dem angegebenen `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="af745-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="af745-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="af745-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af745-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="af745-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af745-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="af745-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="af745-107">[in]  Die `CLSID` der Komponente.</span><span class="sxs-lookup"><span data-stu-id="af745-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="af745-108">[out]  Ein Puffer, der nach dem erfolgreichen Abschluss die Versionsnummernzeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="af745-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="af745-109">[in]  Die Größe in Breitzeichen, der die `pVersion` Puffer.</span><span class="sxs-lookup"><span data-stu-id="af745-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="af745-110">[out] Die Länge des zurückgegebenen Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="af745-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="af745-111">[in]  Einer der CLSID_RESOLUTION_FLAGS-Werte.</span><span class="sxs-lookup"><span data-stu-id="af745-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="af745-112">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="af745-112">The following values are supported:</span></span>  
  
-   <span data-ttu-id="af745-113">CLSID_RESOLUTION_DEFAULT: (0 x 0) gibt an, die das Interop-Standardverhalten sollten werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="af745-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
-   <span data-ttu-id="af745-114">CLSID_RESOLUTION_REGISTERED: (0 x 1) gibt an, dass die Registrierung durchsucht werden soll, und shim-Richtlinie sollte angewendet.</span><span class="sxs-lookup"><span data-stu-id="af745-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="af745-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="af745-115">Return Value</span></span>  
  
|<span data-ttu-id="af745-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="af745-116">HRESULT</span></span>|<span data-ttu-id="af745-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af745-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="af745-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="af745-118">S_OK</span></span>|<span data-ttu-id="af745-119">Die Funktion wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="af745-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="af745-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="af745-120">E_INVALIDARG</span></span>|<span data-ttu-id="af745-121">Einer der Parameter weist einen ungültigen Typ oder Format.</span><span class="sxs-lookup"><span data-stu-id="af745-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="af745-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="af745-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="af745-123">Die `pVersion` Puffer ist nicht groß genug für die gesamte Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="af745-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="af745-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="af745-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="af745-125">Es gibt keine Klasse, die mit dem angegebenen registriert `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="af745-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="af745-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="af745-126">E_POINTER</span></span>|<span data-ttu-id="af745-127">`dwLength`ist null, oder `cchBuffer` ist groß genug für die Versionszeichenfolge jedoch `pVersion` ist null.</span><span class="sxs-lookup"><span data-stu-id="af745-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="af745-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af745-128">Requirements</span></span>  
 <span data-ttu-id="af745-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af745-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af745-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af745-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af745-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af745-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af745-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af745-132">See Also</span></span>  
 [<span data-ttu-id="af745-133">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="af745-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
