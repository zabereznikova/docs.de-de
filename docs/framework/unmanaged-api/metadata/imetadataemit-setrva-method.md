---
title: IMetaDataEmit::SetRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
ms.openlocfilehash: fe0b4b7fef0d05c4acc06dad5bc8a4eaf0722c9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175576"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="63b26-102">IMetaDataEmit::SetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="63b26-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="63b26-103">Legt die relative virtuelle Adresse der angegebenen Methode fest.</span><span class="sxs-lookup"><span data-stu-id="63b26-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63b26-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="63b26-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,
    [in]  ULONG        ulRVA
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="63b26-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="63b26-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="63b26-106">[in] Das Token für die Zielmethode oder Methodenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="63b26-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="63b26-107">[in] Die Adresse des Codes oder Datenbereichs.</span><span class="sxs-lookup"><span data-stu-id="63b26-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63b26-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="63b26-108">Requirements</span></span>  
 <span data-ttu-id="63b26-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63b26-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63b26-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="63b26-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="63b26-111">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="63b26-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="63b26-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63b26-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63b26-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63b26-113">See also</span></span>

- [<span data-ttu-id="63b26-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63b26-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="63b26-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="63b26-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
