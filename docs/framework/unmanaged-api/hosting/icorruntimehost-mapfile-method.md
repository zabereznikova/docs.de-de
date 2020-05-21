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
ms.openlocfilehash: 3b1a0cd9a1dfba6f33a20416f2a10c967f871a06
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762668"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="113ff-102">ICorRuntimeHost::MapFile-Methode</span><span class="sxs-lookup"><span data-stu-id="113ff-102">ICorRuntimeHost::MapFile Method</span></span>
<span data-ttu-id="113ff-103">Ordnet die angegebene Datei dem Arbeitsspeicher zu.</span><span class="sxs-lookup"><span data-stu-id="113ff-103">Maps the specified file into memory.</span></span> <span data-ttu-id="113ff-104">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="113ff-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="113ff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="113ff-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="113ff-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="113ff-106">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="113ff-107">in Das Handle der Datei, die zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="113ff-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="113ff-108">vorgenommen Die Start Speicheradresse, an der mit der Zuordnung der Datei begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="113ff-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="113ff-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="113ff-109">Requirements</span></span>  
 <span data-ttu-id="113ff-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="113ff-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="113ff-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="113ff-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="113ff-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="113ff-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="113ff-113">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="113ff-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="113ff-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="113ff-114">See also</span></span>

- [<span data-ttu-id="113ff-115">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="113ff-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
