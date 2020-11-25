---
title: GetVersionFromProcess-Funktion
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
ms.openlocfilehash: da0d159da6eef7745c1fa7f7320d5e1355f6e413
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721880"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="4b220-102">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="4b220-102">GetVersionFromProcess Function</span></span>

<span data-ttu-id="4b220-103">Ruft die Versionsnummer der Common Language Runtime (CLR) ab, die dem angegebenen Prozess Handle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4b220-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="4b220-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="4b220-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b220-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4b220-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b220-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4b220-106">Parameters</span></span>  

 `hProcess`  
 <span data-ttu-id="4b220-107">in Ein Handle für einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="4b220-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="4b220-108">vorgenommen Ein Puffer, der die Versionsnummern Zeichenfolge nach erfolgreichem Abschluss der Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="4b220-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4b220-109">in Die Länge des Versions Puffers.</span><span class="sxs-lookup"><span data-stu-id="4b220-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="4b220-110">vorgenommen Ein Zeiger auf die Länge der Versionsnummern Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4b220-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b220-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4b220-111">Return Value</span></span>  

 <span data-ttu-id="4b220-112">Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="4b220-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="4b220-113">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="4b220-113">Return code</span></span>|<span data-ttu-id="4b220-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4b220-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4b220-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4b220-115">S_OK</span></span>|<span data-ttu-id="4b220-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4b220-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="4b220-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4b220-117">E_INVALIDARG</span></span>|<span data-ttu-id="4b220-118">`pVersion` ist NULL und `cchBuffer` ist nicht NULL (oder umgekehrt).</span><span class="sxs-lookup"><span data-stu-id="4b220-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="4b220-119">- oder -</span><span class="sxs-lookup"><span data-stu-id="4b220-119">-or-</span></span><br /><br /> <span data-ttu-id="4b220-120">`hProcess` ist kein gültiges Handle für einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="4b220-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="4b220-121">- oder -</span><span class="sxs-lookup"><span data-stu-id="4b220-121">-or-</span></span><br /><br /> <span data-ttu-id="4b220-122">Die CLR ist nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="4b220-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="4b220-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4b220-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4b220-124">`cchBuffer` ist NULL oder kleiner als die Länge der Versions Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4b220-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="4b220-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="4b220-125">E_NOTIMPL</span></span>|<span data-ttu-id="4b220-126">Diese Methode ist nicht im Betriebssystem Microsoft Windows 95, Microsoft Windows 98 oder Microsoft Windows Millennium Edition verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4b220-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b220-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4b220-127">Requirements</span></span>  

 <span data-ttu-id="4b220-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b220-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b220-129">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="4b220-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b220-130">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b220-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b220-131">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b220-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b220-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b220-132">See also</span></span>

- [<span data-ttu-id="4b220-133">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="4b220-133">GetRequestedRuntimeInfo Function</span></span>](getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="4b220-134">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="4b220-134">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="4b220-135">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="4b220-135">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
