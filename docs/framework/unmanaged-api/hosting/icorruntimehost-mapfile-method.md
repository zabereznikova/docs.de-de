---
title: ICorRuntimeHost::MapFile-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.MapFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::MapFile
helpviewer_keywords:
- ICorRuntimeHost::MapFile method [.NET Framework hosting]
- MapFile method [.NET Framework hosting]
ms.assetid: 45ae0502-0a31-4342-b7e3-f36e1cf738f3
topic_type:
- apiref
ms.openlocfilehash: bcf1b49f0576f5dbd73c001f8edff7a9ab29af22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139502"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="9dc7c-102">ICorRuntimeHost::MapFile-Methode</span><span class="sxs-lookup"><span data-stu-id="9dc7c-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="9dc7c-103">Ordnet die angegebene Datei dem Arbeitsspeicher zu.</span><span class="sxs-lookup"><span data-stu-id="9dc7c-103">Maps the specified file into memory.</span></span> <span data-ttu-id="9dc7c-104">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="9dc7c-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc7c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dc7c-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dc7c-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="9dc7c-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="9dc7c-107">in Das Handle der Datei, die zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9dc7c-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="9dc7c-108">vorgenommen Die Start Speicheradresse, an der mit der Zuordnung der Datei begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="9dc7c-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dc7c-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9dc7c-109">Requirements</span></span>  
 <span data-ttu-id="9dc7c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dc7c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dc7c-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="9dc7c-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9dc7c-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9dc7c-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9dc7c-113">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="9dc7c-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc7c-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dc7c-114">See also</span></span>

- [<span data-ttu-id="9dc7c-115">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9dc7c-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
