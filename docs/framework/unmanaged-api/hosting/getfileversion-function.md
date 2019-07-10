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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b1f5508e9ee41d8670b43d5b219846237e11fc8f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778145"
---
# <a name="getfileversion-function"></a><span data-ttu-id="60363-102">GetFileVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="60363-102">GetFileVersion Function</span></span>
<span data-ttu-id="60363-103">Ruft die common Language Runtime (CLR) Versionsinformationen von der angegebenen Datei, die mithilfe des angegebenen Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="60363-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="60363-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="60363-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60363-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="60363-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60363-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="60363-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="60363-107">[in] Der Pfad der Datei, die untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="60363-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="60363-108">[in, out] Der Puffer zugeordnet werden, für die Versionsinformationen, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="60363-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="60363-109">[in] Die Größe in Breitzeichen, der `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="60363-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="60363-110">[out] Die Größe in Bytes, des zurückgegebenen `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="60363-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60363-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60363-111">Requirements</span></span>  
 <span data-ttu-id="60363-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60363-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60363-113">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="60363-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60363-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60363-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60363-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60363-115">See also</span></span>

- [<span data-ttu-id="60363-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="60363-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
