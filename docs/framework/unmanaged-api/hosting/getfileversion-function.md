---
title: GetFileVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
ms.openlocfilehash: 57b30824c7849127f48d4da61872945366e7141e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733242"
---
# <a name="getfileversion-function"></a><span data-ttu-id="f9fd4-102">GetFileVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="f9fd4-102">GetFileVersion Function</span></span>

<span data-ttu-id="f9fd4-103">Ruft die Common Language Runtime (CLR)-Versionsinformationen der angegebenen Datei unter Verwendung des angegebenen Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="f9fd4-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="f9fd4-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="f9fd4-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9fd4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9fd4-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9fd4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9fd4-106">Parameters</span></span>  

 `szFilename`  
 <span data-ttu-id="f9fd4-107">in Der Pfad der Datei, die überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9fd4-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="f9fd4-108">[in, out] Der Puffer, der den zurückgegebenen Versionsinformationen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f9fd4-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f9fd4-109">in Die Größe von in breit Zeichen `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="f9fd4-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="f9fd4-110">vorgenommen Die Größe (in Bytes) des zurückgegebenen `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="f9fd4-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9fd4-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f9fd4-111">Requirements</span></span>  

 <span data-ttu-id="f9fd4-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9fd4-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9fd4-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f9fd4-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f9fd4-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9fd4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9fd4-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9fd4-115">See also</span></span>

- [<span data-ttu-id="f9fd4-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="f9fd4-116">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
