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
ms.openlocfilehash: 899d6e74902e47f1f41b849bd5c25048baa175f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617138"
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="5b0f9-102">GetRequestedRuntimeVersionForCLSID-Funktion</span><span class="sxs-lookup"><span data-stu-id="5b0f9-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="5b0f9-103">Ruft die entsprechenden Common Language Runtime (CLR)-Versionsinformationen für die-Klasse mit dem angegebenen ab `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="5b0f9-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="5b0f9-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0f9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b0f9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b0f9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b0f9-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="5b0f9-107">in  Der der `CLSID` Komponente.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="5b0f9-108">vorgenommen  Ein Puffer, der nach erfolgreichem Abschluss die Zeichenfolge der Versionsnummer enthält.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="5b0f9-109">in  Die Größe des Puffers in breit Zeichen `pVersion` .</span><span class="sxs-lookup"><span data-stu-id="5b0f9-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="5b0f9-110">vorgenommen Die Länge des zurückgegebenen Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="5b0f9-111">in  Einer der CLSID_RESOLUTION_FLAGS-Werte.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="5b0f9-112">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5b0f9-112">The following values are supported:</span></span>  
  
- <span data-ttu-id="5b0f9-113">CLSID_RESOLUTION_DEFAULT: (0x0) gibt an, dass das standardmäßige Interop-Verhalten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
- <span data-ttu-id="5b0f9-114">CLSID_RESOLUTION_REGISTERED: (0x1) gibt an, dass die Registrierung durchsucht werden soll und dass die Shim-Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5b0f9-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5b0f9-115">Return Value</span></span>  
  
|<span data-ttu-id="5b0f9-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5b0f9-116">HRESULT</span></span>|<span data-ttu-id="5b0f9-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5b0f9-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5b0f9-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="5b0f9-118">S_OK</span></span>|<span data-ttu-id="5b0f9-119">Die Funktion wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="5b0f9-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5b0f9-120">E_INVALIDARG</span></span>|<span data-ttu-id="5b0f9-121">Einer der Parameter weist einen ungültigen Typ oder ein ungültiges Format auf.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="5b0f9-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="5b0f9-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="5b0f9-123">Der `pVersion` Puffer ist nicht groß genug, um die gesamte Versions Zeichenfolge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="5b0f9-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="5b0f9-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="5b0f9-125">Es ist keine Klasse mit dem angegebenen registriert `CLSID` .</span><span class="sxs-lookup"><span data-stu-id="5b0f9-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="5b0f9-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5b0f9-126">E_POINTER</span></span>|<span data-ttu-id="5b0f9-127">`dwLength`ist NULL, oder `cchBuffer` ist groß genug, um die Versions Zeichenfolge aufzunehmen, aber `pVersion` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="5b0f9-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5b0f9-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b0f9-128">Requirements</span></span>  
 <span data-ttu-id="5b0f9-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b0f9-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b0f9-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5b0f9-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b0f9-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b0f9-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b0f9-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b0f9-132">See also</span></span>

- [<span data-ttu-id="5b0f9-133">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="5b0f9-133">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
