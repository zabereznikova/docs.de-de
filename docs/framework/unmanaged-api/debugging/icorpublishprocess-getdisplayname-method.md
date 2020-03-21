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
ms.openlocfilehash: 77e801b048709949c384f642fc0d0ecb5d7eb512
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178386"
---
# <a name="icorpublishprocessgetdisplayname-method"></a><span data-ttu-id="20bd9-102">ICorPublishProcess::GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="20bd9-102">ICorPublishProcess::GetDisplayName Method</span></span>
<span data-ttu-id="20bd9-103">Ruft den vollständigen Pfad der ausführbaren Datei für den Prozess ab, auf den von diesem [ICorPublishProcess](icorpublishprocess-interface.md)verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="20bd9-103">Gets the full path of the executable for the process referenced by this [ICorPublishProcess](icorpublishprocess-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20bd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20bd9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
    [in]  ULONG32                    cchName,
    [out] ULONG32                    *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]
        WCHAR                        *szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20bd9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="20bd9-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="20bd9-106">[in] Die Größe des `szName`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="20bd9-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="20bd9-107">[out] Die Anzahl der im `szName` Array zurückgegebenen breiten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="20bd9-107">[out] The number of wide characters returned in the `szName` array.</span></span>  
  
 `szName`  
 <span data-ttu-id="20bd9-108">[out] Ein Array zum Speichern des Namens, einschließlich des vollständigen Pfads, der ausführbaren Datei.</span><span class="sxs-lookup"><span data-stu-id="20bd9-108">[out] An array to store the name, including the full path, of the executable.</span></span> <span data-ttu-id="20bd9-109">Der Name ist null-terminated.</span><span class="sxs-lookup"><span data-stu-id="20bd9-109">The name is null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20bd9-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="20bd9-110">Requirements</span></span>  
 <span data-ttu-id="20bd9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20bd9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20bd9-112">**Kopfzeile:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="20bd9-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="20bd9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20bd9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20bd9-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20bd9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20bd9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20bd9-115">See also</span></span>

- [<span data-ttu-id="20bd9-116">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="20bd9-116">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
