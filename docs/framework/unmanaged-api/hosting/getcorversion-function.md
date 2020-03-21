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
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178193"
---
# <a name="getcorversion-function"></a><span data-ttu-id="c386e-102">GetCORVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="c386e-102">GetCORVersion Function</span></span>
<span data-ttu-id="c386e-103">Gibt die Versionsnummer der Common Language Runtime (CLR) zurück, die im aktuellen Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c386e-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="c386e-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="c386e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c386e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c386e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="c386e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c386e-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="c386e-107">Ein Zeiger auf einen Puffer, in dem die CLR eine Zeichenfolge zurückgibt, die die Version der Laufzeit angibt, die derzeit in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c386e-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="c386e-108">Die zurückgegebene Zeichenfolge hat dieselbe Form wie Zeichenfolgen, die an [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)übergeben werden, z. B. "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="c386e-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="c386e-109">Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der auf dem Computer installierten Laufzeit zurück.</span><span class="sxs-lookup"><span data-stu-id="c386e-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="c386e-110">Die Anzahl der`WCHAR`Zeichen (s), `pbuffer`die in gehalten werden können.</span><span class="sxs-lookup"><span data-stu-id="c386e-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="c386e-111">Ein Zeiger auf die Anzahl der `pbuffer`tatsächlich zurückgegebenen Zeichen in .</span><span class="sxs-lookup"><span data-stu-id="c386e-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="c386e-112">Wenn `pbuffer` es sich um einen Nullzeiger handelt, gibt die Laufzeit E_POINTER zurück.</span><span class="sxs-lookup"><span data-stu-id="c386e-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="c386e-113">Wenn die Anzahl der Zeichen größer `pbuffer` ist als die Länge von, gibt die Laufzeit ERROR_INSUFFICIENT_BUFFER zurück.</span><span class="sxs-lookup"><span data-stu-id="c386e-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c386e-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c386e-114">Requirements</span></span>  
 <span data-ttu-id="c386e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c386e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c386e-116">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c386e-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c386e-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c386e-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c386e-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c386e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c386e-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c386e-119">See also</span></span>

- [<span data-ttu-id="c386e-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="c386e-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
