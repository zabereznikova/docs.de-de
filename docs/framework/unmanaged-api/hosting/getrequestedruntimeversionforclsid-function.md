---
title: GetRequestedRuntimeVersionForCLSID-Funktion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63e6ec271634a52abe7c640bbbabdaedebd2a31d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471900"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="20564-102">GetRequestedRuntimeVersionForCLSID-Funktion</span><span class="sxs-lookup"><span data-stu-id="20564-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="20564-103">Ruft die entsprechende Version zur common Language Runtime (CLR) für die Klasse mit dem angegebenen `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="20564-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="20564-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="20564-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20564-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="20564-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20564-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="20564-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="20564-107">[in]  Die `CLSID` der Komponente.</span><span class="sxs-lookup"><span data-stu-id="20564-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="20564-108">[out]  Ein Puffer, der die Versionsnummer-Zeichenfolge nach dem erfolgreichen Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="20564-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="20564-109">[in]  Die Größe in Breitzeichen, der die `pVersion` Puffer.</span><span class="sxs-lookup"><span data-stu-id="20564-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="20564-110">[out] Die Länge des zurückgegebenen Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="20564-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="20564-111">[in]  Einer der CLSID_RESOLUTION_FLAGS-Werte.</span><span class="sxs-lookup"><span data-stu-id="20564-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="20564-112">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="20564-112">The following values are supported:</span></span>  
  
-   <span data-ttu-id="20564-113">CLSID_RESOLUTION_DEFAULT: (0 x 0) gibt an, dass die Interop-Standardverhalten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="20564-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
-   <span data-ttu-id="20564-114">CLSID_RESOLUTION_REGISTERED: (0 x 1) gibt an, die die Registrierung durchsucht werden soll, und Shimrichtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="20564-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20564-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="20564-115">Return Value</span></span>  
  
|<span data-ttu-id="20564-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="20564-116">HRESULT</span></span>|<span data-ttu-id="20564-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="20564-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="20564-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="20564-118">S_OK</span></span>|<span data-ttu-id="20564-119">Die Funktion wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20564-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="20564-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="20564-120">E_INVALIDARG</span></span>|<span data-ttu-id="20564-121">Einer der Parameter hat einen ungültigen Typ oder Format.</span><span class="sxs-lookup"><span data-stu-id="20564-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="20564-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="20564-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="20564-123">Die `pVersion` Puffer ist nicht groß genug für die gesamte Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="20564-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="20564-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="20564-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="20564-125">Es gibt keine Klasse, die mit dem angegebenen registriert `CLSID`.</span><span class="sxs-lookup"><span data-stu-id="20564-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="20564-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="20564-126">E_POINTER</span></span>|<span data-ttu-id="20564-127">`dwLength` null ist, oder `cchBuffer` ist groß genug für die Versionszeichenfolge, aber `pVersion` ist null.</span><span class="sxs-lookup"><span data-stu-id="20564-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="20564-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20564-128">Requirements</span></span>  
 <span data-ttu-id="20564-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20564-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20564-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20564-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20564-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20564-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20564-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20564-132">See also</span></span>
- [<span data-ttu-id="20564-133">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="20564-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
