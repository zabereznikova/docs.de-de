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
ms.openlocfilehash: 60e1d5d49f6f8c6fec060d8751e94410986aa3fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671381"
---
# <a name="icorruntimehostmapfile-method"></a><span data-ttu-id="19faf-102">ICorRuntimeHost::MapFile-Methode</span><span class="sxs-lookup"><span data-stu-id="19faf-102">ICorRuntimeHost::MapFile Method</span></span>

<span data-ttu-id="19faf-103">Ordnet die angegebene Datei dem Arbeitsspeicher zu.</span><span class="sxs-lookup"><span data-stu-id="19faf-103">Maps the specified file into memory.</span></span> <span data-ttu-id="19faf-104">Diese Methode ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="19faf-104">This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19faf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="19faf-105">Syntax</span></span>  
  
```cpp  
HRESULT MapFile(  
    [in]  HANDLE    hFile,  
    [out] HMODULE*  hMapAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="19faf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="19faf-106">Parameters</span></span>  

 `hFile`  
 <span data-ttu-id="19faf-107">in Das Handle der Datei, die zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="19faf-107">[in] The handle of the file to be mapped.</span></span>  
  
 `hMapAddress`  
 <span data-ttu-id="19faf-108">vorgenommen Die Start Speicheradresse, an der mit der Zuordnung der Datei begonnen werden soll.</span><span class="sxs-lookup"><span data-stu-id="19faf-108">[out] The starting memory address at which to begin mapping the file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19faf-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="19faf-109">Requirements</span></span>  

 <span data-ttu-id="19faf-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19faf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19faf-111">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="19faf-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="19faf-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="19faf-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19faf-113">**.NET Framework Version:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="19faf-113">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19faf-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19faf-114">See also</span></span>

- [<span data-ttu-id="19faf-115">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19faf-115">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
