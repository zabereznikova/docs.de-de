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
ms.openlocfilehash: df2750f082ddc40bbeee121116c3e877d037da84
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140431"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="eae93-102">ICorPublishProcess::GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="eae93-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="eae93-103">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess ab, auf den von diesem [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="eae93-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eae93-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,   
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eae93-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eae93-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="eae93-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="eae93-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="eae93-107">vorgenommen Die Anzahl der breit Zeichen, die im `szName` Array zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="eae93-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="eae93-108">vorgenommen Ein Array zum Speichern des Namens, einschließlich des vollständigen Pfads der ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="eae93-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="eae93-109">Der Name wird mit Null beendet.</span><span class="sxs-lookup"><span data-stu-id="eae93-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae93-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eae93-110">Requirements</span></span>  
 <span data-ttu-id="eae93-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae93-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae93-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="eae93-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="eae93-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eae93-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eae93-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eae93-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae93-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eae93-115">See also</span></span>

- [<span data-ttu-id="eae93-116">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eae93-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
