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
ms.openlocfilehash: 6c16b02a5ae323ba80d44937f322810022dfa9f5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711636"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="9b403-102">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b403-102">GetRequestedRuntimeVersion Function</span></span>

<span data-ttu-id="9b403-103">Ruft die Versionsnummer der von der angegebenen Anwendung angeforderten Common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="9b403-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="9b403-104">Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.</span><span class="sxs-lookup"><span data-stu-id="9b403-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="9b403-105">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="9b403-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b403-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b403-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b403-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b403-107">Parameters</span></span>  

 `pExe`  
 <span data-ttu-id="9b403-108">in Der Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9b403-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="9b403-109">vorgenommen Ein Puffer, der nach erfolgreichem Abschluss die Zeichenfolge der Versionsnummer enthält.</span><span class="sxs-lookup"><span data-stu-id="9b403-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="9b403-110">in Die Länge des Versions Puffers.</span><span class="sxs-lookup"><span data-stu-id="9b403-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="9b403-111">vorgenommen Ein Zeiger auf die Länge der Versionsnummern Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="9b403-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9b403-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9b403-112">Return Value</span></span>  

 <span data-ttu-id="9b403-113">Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="9b403-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="9b403-114">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="9b403-114">Return code</span></span>|<span data-ttu-id="9b403-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9b403-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="9b403-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="9b403-116">S_OK</span></span>|<span data-ttu-id="9b403-117">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9b403-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="9b403-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="9b403-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="9b403-119">Der Versions Puffer ist nicht groß genug, um die Versions Zeichenfolge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9b403-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="9b403-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9b403-120">E_POINTER</span></span>|<span data-ttu-id="9b403-121">`pdwLength` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="9b403-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9b403-122">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b403-122">Requirements</span></span>  

 <span data-ttu-id="9b403-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b403-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b403-124">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9b403-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9b403-125">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9b403-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9b403-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b403-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b403-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b403-127">See also</span></span>

- [<span data-ttu-id="9b403-128">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b403-128">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="9b403-129">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="9b403-129">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="9b403-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="9b403-130">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
