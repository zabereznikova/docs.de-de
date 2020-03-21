---
title: GetRequestedRuntimeVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 6be0bc5d08f612dcb8ed7d256711e0c4367b9274
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178136"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="a6e93-102">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="a6e93-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="a6e93-103">Ruft die Versionsnummer der Common Language Runtime (CLR) ab, die von der angegebenen Anwendung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="a6e93-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="a6e93-104">Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a6e93-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="a6e93-105">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="a6e93-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e93-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6e93-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6e93-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6e93-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="a6e93-108">[in] Der Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a6e93-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="a6e93-109">[out] Ein Puffer, der die Versionsnummernzeichenfolge nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="a6e93-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="a6e93-110">[in] Die Länge des Versionspuffers.</span><span class="sxs-lookup"><span data-stu-id="a6e93-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="a6e93-111">[out] Ein Zeiger auf die Länge der Versionsnummernzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6e93-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6e93-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a6e93-112">Return Value</span></span>  
 <span data-ttu-id="a6e93-113">Diese Methode gibt zusätzlich zu den folgenden Werten Com-Fehlercodes (Standard Component Object Model, COM) zurück, wie in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="a6e93-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="a6e93-114">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="a6e93-114">Return code</span></span>|<span data-ttu-id="a6e93-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6e93-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a6e93-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6e93-116">S_OK</span></span>|<span data-ttu-id="a6e93-117">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a6e93-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="a6e93-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a6e93-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a6e93-119">Der Versionspuffer ist nicht groß genug, um die Versionszeichenfolge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a6e93-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="a6e93-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a6e93-120">E_POINTER</span></span>|<span data-ttu-id="a6e93-121">`pdwLength` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="a6e93-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6e93-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a6e93-122">Requirements</span></span>  
 <span data-ttu-id="a6e93-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e93-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e93-124">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a6e93-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6e93-125">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6e93-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6e93-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e93-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e93-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a6e93-127">See also</span></span>

- [<span data-ttu-id="a6e93-128">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="a6e93-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="a6e93-129">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="a6e93-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="a6e93-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="a6e93-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
