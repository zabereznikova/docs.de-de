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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a8a979e86dbe52577d0b58089015338e4a87750d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59193875"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="1538a-102">ICorRuntimeHost::MapFile-Methode</span><span class="sxs-lookup"><span data-stu-id="1538a-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="1538a-103">Ordnet die angegebene Datei in den Arbeitsspeicher an.</span><span class="sxs-lookup"><span data-stu-id="1538a-103">Maps the specified file into memory.</span></span> <span data-ttu-id="1538a-104">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="1538a-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1538a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1538a-105">Syntax</span></span>  
  
```  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1538a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1538a-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="1538a-107">[in] Das Handle der Datei zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="1538a-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="1538a-108">[out] Die Startspeicheradresse, ab der Zuordnungsdatei.</span><span class="sxs-lookup"><span data-stu-id="1538a-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1538a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1538a-109">Requirements</span></span>  
 <span data-ttu-id="1538a-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1538a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1538a-111">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1538a-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1538a-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1538a-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1538a-113">**.NET Framework Version:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="1538a-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1538a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1538a-114">See also</span></span>

- [<span data-ttu-id="1538a-115">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1538a-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
