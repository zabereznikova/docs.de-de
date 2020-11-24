---
title: GetCORVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: e7ef3f300c8cfa0c275d15913e171abe09385eea
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681209"
---
# <a name="getcorversion-function"></a><span data-ttu-id="28bb8-102">GetCORVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="28bb8-102">GetCORVersion Function</span></span>

<span data-ttu-id="28bb8-103">Gibt die Versionsnummer der Common Language Runtime (CLR) zurück, die im aktuellen Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="28bb8-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="28bb8-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="28bb8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28bb8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="28bb8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="28bb8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="28bb8-106">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="28bb8-107">Ein Zeiger auf einen Puffer, in dem die CLR eine Zeichenfolge zurückgibt, die die Version der Laufzeit angibt, die gerade in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="28bb8-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="28bb8-108">Die zurückgegebene Zeichenfolge hat dieselbe Form wie Zeichen folgen, die an [corbindtoriuntimeex](corbindtoruntimeex-function.md)übermittelt werden, z. b. "v 1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="28bb8-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="28bb8-109">Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die aktuelle Version der Laufzeit zurück, die auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="28bb8-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="28bb8-110">Die Anzahl der Zeichen `WCHAR` , die in aufbewahrt werden können `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="28bb8-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="28bb8-111">Ein Zeiger auf die Anzahl von Zeichen, die tatsächlich in zurückgegeben werden `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="28bb8-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="28bb8-112">Wenn `pbuffer` ein NULL-Zeiger ist, gibt die Laufzeit E_POINTER zurück.</span><span class="sxs-lookup"><span data-stu-id="28bb8-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="28bb8-113">Wenn die Anzahl der Zeichen größer als die Länge von ist `pbuffer` , gibt die Laufzeit ERROR_INSUFFICIENT_BUFFER zurück.</span><span class="sxs-lookup"><span data-stu-id="28bb8-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28bb8-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="28bb8-114">Requirements</span></span>  

 <span data-ttu-id="28bb8-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28bb8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28bb8-116">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="28bb8-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28bb8-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28bb8-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="28bb8-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28bb8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28bb8-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28bb8-119">See also</span></span>

- [<span data-ttu-id="28bb8-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="28bb8-120">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
