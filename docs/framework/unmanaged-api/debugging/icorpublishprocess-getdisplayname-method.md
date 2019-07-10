---
title: ICorPublishProcess::GetDisplayName-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetDisplayName
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetDisplayName
helpviewer_keywords:
- ICorPublishProcess::GetDisplayName method [.NET Framework debugging]
- GetDisplayName method, ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 7c0af9e9-a73f-41aa-a685-b21c439e059d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 354e1b0dad942534068d5fb07071ed4ac695fb49
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764885"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="30c8b-102">ICorPublishProcess::GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="30c8b-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="30c8b-103">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess, der auf die dieses [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span><span class="sxs-lookup"><span data-stu-id="30c8b-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30c8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30c8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30c8b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="30c8b-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="30c8b-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="30c8b-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="30c8b-107">[out] Die Anzahl der Breitzeichen zurückgegeben, die der `szName` Array.</span><span class="sxs-lookup"><span data-stu-id="30c8b-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="30c8b-108">[out] Ein Array, das den Namen, einschließlich des vollständigen Pfads, der die ausführbare Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="30c8b-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="30c8b-109">Der Name ist, Null-terminiert.</span><span class="sxs-lookup"><span data-stu-id="30c8b-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30c8b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30c8b-110">Requirements</span></span>  
 <span data-ttu-id="30c8b-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30c8b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c8b-112">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="30c8b-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="30c8b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30c8b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30c8b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c8b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c8b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30c8b-115">See also</span></span>

- [<span data-ttu-id="30c8b-116">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30c8b-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
