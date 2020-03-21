---
title: GetCORSystemDirectory-Funktion
ms.date: 03/30/2017
api_name:
- GetCORSystemDirectory
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORSystemDirectory
helpviewer_keywords:
- GetCORSystemDirectory function [.NET Framework hosting]
ms.assetid: 3dcd16a7-dafc-4ca8-b5cd-20ffb37db91d
topic_type:
- apiref
ms.openlocfilehash: bdafacfe52d678aacfcd44de1e924bcb88547424
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178203"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="ebd1f-102">GetCORSystemDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="ebd1f-102">GetCORSystemDirectory Function</span></span>
<span data-ttu-id="ebd1f-103">Gibt das Installationsverzeichnis der Common Language Runtime (CLR) zurück, die in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="ebd1f-104">Das Installationsverzeichnis ist voll qualifiziert, z. B. "c:'windows'microsoft.net'framework'v1.0.3705'.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="ebd1f-105">Diese Funktion ist als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-105">This function is deprecated.</span></span> <span data-ttu-id="ebd1f-106">Sie wird durch die [ICLRRuntimeInfo::GetRuntimeDirectory-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) ersetzt, die in .NET Framework 4 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebd1f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebd1f-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="ebd1f-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="ebd1f-108">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="ebd1f-109">[out] Ein Puffer, in dem die Laufzeit eine Zeichenfolge zurückgibt, die den vollqualifizierten Namen des Installationsverzeichnisses für die Laufzeit enthält, die in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="ebd1f-110">Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die neueste Version der auf dem Computer installierten Laufzeit zurück.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ebd1f-111">[in] Die Größe von in `pbuffer`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="ebd1f-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ebd1f-112">[out] Die Anzahl der `pbuffer`in zurückgegebenen Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebd1f-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ebd1f-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="ebd1f-114">Verwenden Sie diese Funktion nicht in Prozessen, in denen Version 4 der CLR ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="ebd1f-115">Wenn eine frühere Version der CLR auf dem Computer installiert ist, gibt diese Funktion das Installationsverzeichnis für diese Version zurück.</span><span class="sxs-lookup"><span data-stu-id="ebd1f-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebd1f-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ebd1f-116">Requirements</span></span>  
 <span data-ttu-id="ebd1f-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebd1f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebd1f-118">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ebd1f-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ebd1f-119">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebd1f-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebd1f-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebd1f-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd1f-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebd1f-121">See also</span></span>

- [<span data-ttu-id="ebd1f-122">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="ebd1f-122">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
