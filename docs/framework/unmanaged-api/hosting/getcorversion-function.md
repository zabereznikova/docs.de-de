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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f66e00c3334aecdf8c653f57e28d1b327c4170e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628001"
---
# <a name="getcorversion-function"></a><span data-ttu-id="ff2c9-102">GetCORVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="ff2c9-102">GetCORVersion Function</span></span>
<span data-ttu-id="ff2c9-103">Gibt die Versionsnummer der die common Language Runtime (CLR), die im aktuellen Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff2c9-103">Returns the version number of the common language runtime (CLR) that is running in the current process.</span></span>  
  
 <span data-ttu-id="ff2c9-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="ff2c9-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff2c9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff2c9-105">Syntax</span></span>  
  
```  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,   
    [out] DWORD*  dwlength  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="ff2c9-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff2c9-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="ff2c9-107">Ein Zeiger auf einen Puffer, in dem die CLR zurückgegeben wird eine Zeichenfolge, die Angabe der Version der Laufzeit, die derzeit in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ff2c9-107">A pointer to a buffer in which the CLR returns a string specifying the version of the runtime that is currently loaded into the process.</span></span> <span data-ttu-id="ff2c9-108">Die zurückgegebene Zeichenfolge hat dieselbe Form wie Zeichenfolgen, die an [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), z. B. "v1.0.1216".</span><span class="sxs-lookup"><span data-stu-id="ff2c9-108">The returned string takes the same form as strings passed to [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), for example, "v1.0.1216".</span></span> <span data-ttu-id="ff2c9-109">Wenn die Runtime noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der Laufzeit auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ff2c9-109">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ff2c9-110">Die Anzahl der Zeichen (`WCHAR`s), die gespeichert werden können, im `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="ff2c9-110">The number of characters (`WCHAR`s) that can be held in `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ff2c9-111">Ein Zeiger auf die Anzahl der Zeichen im tatsächlich zurückgegebenen `pbuffer`.</span><span class="sxs-lookup"><span data-stu-id="ff2c9-111">A pointer to the number of characters actually returned in `pbuffer`.</span></span> <span data-ttu-id="ff2c9-112">Wenn `pbuffer` ist ein null-Zeiger der Common Language Runtime gibt E_POINTER zurück.</span><span class="sxs-lookup"><span data-stu-id="ff2c9-112">If `pbuffer` is a null pointer, the runtime returns E_POINTER.</span></span> <span data-ttu-id="ff2c9-113">Wenn die Anzahl der Zeichen größer ist. Klicken Sie dann die Länge des `pbuffer` , gibt die Laufzeit ERROR_INSUFFICIENT_BUFFER zurück.</span><span class="sxs-lookup"><span data-stu-id="ff2c9-113">If the number of characters is greater then the length of `pbuffer` , the runtime returns ERROR_INSUFFICIENT_BUFFER.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff2c9-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff2c9-114">Requirements</span></span>  
 <span data-ttu-id="ff2c9-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff2c9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff2c9-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ff2c9-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ff2c9-117">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff2c9-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff2c9-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff2c9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff2c9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff2c9-119">See also</span></span>

- [<span data-ttu-id="ff2c9-120">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="ff2c9-120">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
