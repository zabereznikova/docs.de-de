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
ms.openlocfilehash: f197c8802bd9e55391b3e3e20c64398736070a16
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136334"
---
# <a name="getfileversion-function"></a><span data-ttu-id="dfe2c-102">GetFileVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="dfe2c-102">GetFileVersion Function</span></span>
<span data-ttu-id="dfe2c-103">Ruft die Common Language Runtime (CLR)-Versionsinformationen der angegebenen Datei unter Verwendung des angegebenen Puffers ab.</span><span class="sxs-lookup"><span data-stu-id="dfe2c-103">Gets the common language runtime (CLR) version information of the specified file, using the specified buffer.</span></span>  
  
 <span data-ttu-id="dfe2c-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="dfe2c-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfe2c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="dfe2c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,   
    [in, out] LPWSTR   szBuffer,   
    [in]  DWORD        cchBuffer,   
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dfe2c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="dfe2c-106">Parameters</span></span>  
 `szFilename`  
 <span data-ttu-id="dfe2c-107">in Der Pfad der Datei, die überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="dfe2c-107">[in] The path of the file to be examined.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="dfe2c-108">[in, out] Der Puffer, der den zurückgegebenen Versionsinformationen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="dfe2c-108">[in, out] The buffer allocated for the version information that is returned.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="dfe2c-109">in Die Größe `szBuffer`in breit Zeichen.</span><span class="sxs-lookup"><span data-stu-id="dfe2c-109">[in] The size, in wide characters, of `szBuffer`.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="dfe2c-110">vorgenommen Die Größe (in Bytes) des zurückgegebenen `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="dfe2c-110">[out] The size, in bytes, of the returned `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfe2c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dfe2c-111">Requirements</span></span>  
 <span data-ttu-id="dfe2c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dfe2c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfe2c-113">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="dfe2c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dfe2c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfe2c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfe2c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfe2c-115">See also</span></span>

- [<span data-ttu-id="dfe2c-116">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="dfe2c-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
