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
ms.openlocfilehash: dc76274d3b0acbbe0b03eb141d2b3e6ff9063afb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421123"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="6f8a8-102">ICorPublishProcess::GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="6f8a8-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="6f8a8-103">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess ab, auf den von diesem [ICorPublishProcess](icorpublishprocess-interface.md)verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6f8a8-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f8a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f8a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f8a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f8a8-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6f8a8-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="6f8a8-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6f8a8-107">vorgenommen Die Anzahl der breit Zeichen, die im Array zurückgegeben werden `szName` .</span><span class="sxs-lookup"><span data-stu-id="6f8a8-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="6f8a8-108">vorgenommen Ein Array zum Speichern des Namens, einschließlich des vollständigen Pfads der ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="6f8a8-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="6f8a8-109">Der Name wird mit Null beendet.</span><span class="sxs-lookup"><span data-stu-id="6f8a8-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f8a8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6f8a8-110">Requirements</span></span>  
 <span data-ttu-id="6f8a8-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f8a8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f8a8-112">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="6f8a8-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6f8a8-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f8a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f8a8-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f8a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f8a8-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f8a8-115">See also</span></span>

- [<span data-ttu-id="6f8a8-116">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f8a8-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
