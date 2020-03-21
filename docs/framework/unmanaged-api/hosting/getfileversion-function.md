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
ms.openlocfilehash: f3b51c1b376fa9c664de53aa76ec724ca305ae6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178182"
---
# <a name="getfileversion-function"></a><span data-ttu-id="a1e4b-102">GetFileVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="a1e4b-102">GetFileVersion Function</span></span>
<span data-ttu-id="a1e4b-103">Ruft die CLR-Versionsinformationen (Common Language Runtime) der angegebenen Datei mithilfe des angegebenen Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="a1e4b-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="a1e4b-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="a1e4b-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1e4b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1e4b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1e4b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1e4b-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="a1e4b-107">[in] Der Pfad der zu untersuchenden Datei.</span><span class="sxs-lookup"><span data-stu-id="a1e4b-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="a1e4b-108">[in, out] Der Puffer, der für die zurückgegebenen Versionsinformationen reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="a1e4b-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="a1e4b-109">[in] Die Größe von in `szBuffer`weiten Zeichen von .</span><span class="sxs-lookup"><span data-stu-id="a1e4b-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="a1e4b-110">[out] Die Größe der zurückgegebenen `szBuffer`in Bytes .</span><span class="sxs-lookup"><span data-stu-id="a1e4b-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1e4b-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a1e4b-111">Requirements</span></span>  
 <span data-ttu-id="a1e4b-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1e4b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1e4b-113">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a1e4b-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a1e4b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1e4b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1e4b-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1e4b-115">See also</span></span>

- [<span data-ttu-id="a1e4b-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="a1e4b-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
