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
ms.openlocfilehash: 21b01156afceb24ab5c132894fae6922d7b97e59
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733294"
---
# <a name="getcorsystemdirectory-function"></a><span data-ttu-id="44eed-102">GetCORSystemDirectory-Funktion</span><span class="sxs-lookup"><span data-stu-id="44eed-102">GetCORSystemDirectory Function</span></span>

<span data-ttu-id="44eed-103">Gibt das Installationsverzeichnis des Common Language Runtime (CLR) zurück, das in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="44eed-103">Returns the installation directory of the common language runtime (CLR) that is loaded into the process.</span></span> <span data-ttu-id="44eed-104">Das Installationsverzeichnis ist voll qualifiziert, z. b. "c:\WINDOWS\Microsoft.NET\Framework\v1.0.3705".</span><span class="sxs-lookup"><span data-stu-id="44eed-104">The installation directory is fully qualified, for example, "c:\windows\microsoft.net\framework\v1.0.3705".</span></span>  
  
 <span data-ttu-id="44eed-105">Diese Funktion ist als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="44eed-105">This function is deprecated.</span></span> <span data-ttu-id="44eed-106">Sie wird durch die [iclrruntimumfo:: getruntimedirectory](iclrruntimeinfo-getruntimedirectory-method.md) -Methode abgelöst, die in der .NET Framework 4 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="44eed-106">It is superseded by the [ICLRRuntimeInfo::GetRuntimeDirectory](iclrruntimeinfo-getruntimedirectory-method.md) method provided in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44eed-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="44eed-107">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (
    [out] LPWSTR  pbuffer,
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="44eed-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="44eed-108">Parameters</span></span>  

 `pbuffer`  
 <span data-ttu-id="44eed-109">vorgenommen Ein Puffer, in dem die Laufzeit eine Zeichenfolge zurückgibt, die den voll qualifizierten Namen des Installationsverzeichnisses für die Laufzeit enthält, die in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="44eed-109">[out] A buffer in which the runtime returns a string that contains the fully qualified name of the installation directory for the runtime that is loaded into the process.</span></span> <span data-ttu-id="44eed-110">Wenn die Laufzeit noch nicht in den Prozess geladen wurde, gibt die Funktion die entsprechenden Verzeichnisinformationen für die aktuelle Version der Laufzeit zurück, die auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="44eed-110">If the runtime has not yet been loaded into the process, the function returns the appropriate directory information for the latest version of the runtime installed on the computer.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="44eed-111">in Die Größe von in Bytes `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="44eed-111">[in] The size, in bytes, of `pbuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="44eed-112">vorgenommen Die Anzahl der Zeichen, die in zurückgegeben werden `pbuffer` .</span><span class="sxs-lookup"><span data-stu-id="44eed-112">[out] The number of characters returned in `pbuffer`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44eed-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44eed-113">Remarks</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="44eed-114">Verwenden Sie diese Funktion nicht in Prozessen, in denen Version 4 der CLR ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="44eed-114">Do not use this function in processes that are running version 4 of the CLR.</span></span> <span data-ttu-id="44eed-115">Wenn eine frühere Version der CLR auf dem Computer installiert ist, gibt diese Funktion das Installationsverzeichnis für diese Version zurück.</span><span class="sxs-lookup"><span data-stu-id="44eed-115">If an earlier version of the CLR is installed on the computer, this function returns the installation directory for that version.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44eed-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="44eed-116">Requirements</span></span>  

 <span data-ttu-id="44eed-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44eed-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44eed-118">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="44eed-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="44eed-119">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="44eed-119">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="44eed-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44eed-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44eed-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44eed-121">See also</span></span>

- [<span data-ttu-id="44eed-122">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="44eed-122">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
