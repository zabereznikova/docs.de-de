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
ms.openlocfilehash: 6132e94544b30486b70ecfec49c1ddd5e3c0f50b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178117"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="05587-102">GetRequestedRuntimeVersionForCLSID-Funktion</span><span class="sxs-lookup"><span data-stu-id="05587-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="05587-103">Ruft die entsprechenden CLR-Versionsinformationen (Common Language Runtime) für die Klasse mit der angegebenen `CLSID`ab.</span><span class="sxs-lookup"><span data-stu-id="05587-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="05587-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="05587-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05587-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="05587-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05587-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="05587-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="05587-107">[in]  Die `CLSID` der Komponente.</span><span class="sxs-lookup"><span data-stu-id="05587-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="05587-108">[out]  Ein Puffer, der die Versionsnummernzeichenfolge nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="05587-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="05587-109">[in]  Die Größe des `pVersion` Puffers in weiten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="05587-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="05587-110">[out] Die Länge (in Bytes) des zurückgegebenen Puffers.</span><span class="sxs-lookup"><span data-stu-id="05587-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="05587-111">[in]  Einer der CLSID_RESOLUTION_FLAGS Werte.</span><span class="sxs-lookup"><span data-stu-id="05587-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="05587-112">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="05587-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="05587-113">CLSID_RESOLUTION_DEFAULT: (0x0) Gibt an, dass das standardmäßige Interopverhalten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="05587-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="05587-114">CLSID_RESOLUTION_REGISTERED: (0x1) Gibt an, dass die Registrierung durchsucht und die Shim-Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="05587-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05587-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05587-115">Return Value</span></span>  
  
|<span data-ttu-id="05587-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05587-116">HRESULT</span></span>|<span data-ttu-id="05587-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05587-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="05587-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="05587-118">S_OK</span></span>|<span data-ttu-id="05587-119">Die Funktion wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="05587-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="05587-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="05587-120">E_INVALIDARG</span></span>|<span data-ttu-id="05587-121">Einer der Parameter hat einen ungültigen Typ oder ein ungültiges Format.</span><span class="sxs-lookup"><span data-stu-id="05587-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="05587-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="05587-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="05587-123">Der `pVersion` Puffer ist nicht groß genug, um die gesamte Versionszeichenfolge zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="05587-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="05587-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="05587-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="05587-125">Es ist keine Klasse `CLSID`registriert, die für die angegebene klasse registriert ist.</span><span class="sxs-lookup"><span data-stu-id="05587-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="05587-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="05587-126">E_POINTER</span></span>|<span data-ttu-id="05587-127">`dwLength`ist null `cchBuffer` oder groß genug, um die `pVersion` Versionszeichenfolge zu halten, ist aber null.</span><span class="sxs-lookup"><span data-stu-id="05587-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05587-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05587-128">Requirements</span></span>  
 <span data-ttu-id="05587-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05587-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05587-130">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="05587-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="05587-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05587-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05587-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05587-132">See also</span></span>

- [<span data-ttu-id="05587-133">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="05587-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
