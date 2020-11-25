---
title: IMetaDataImport::GetModuleFromScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleFromScope
helpviewer_keywords:
- GetModuleFromScope method [.NET Framework metadata]
- IMetaDataImport::GetModuleFromScope method [.NET Framework metadata]
ms.assetid: add68d3f-45fd-4bef-af94-eb5273f26b11
topic_type:
- apiref
ms.openlocfilehash: 2eddd7a80c2b9c1b71f3e7fc5b1e4686ba11bccd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733164"
---
# <a name="imetadataimportgetmodulefromscope-method"></a><span data-ttu-id="346e6-102">IMetaDataImport::GetModuleFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="346e6-102">IMetaDataImport::GetModuleFromScope Method</span></span>

<span data-ttu-id="346e6-103">Ruft ein Metadatentoken für das Modul ab, auf das im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="346e6-103">Gets a metadata token for the module referenced in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="346e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="346e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleFromScope (  
   [out] mdModule    *pmd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="346e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="346e6-105">Parameters</span></span>  

 `pmd`  
 <span data-ttu-id="346e6-106">vorgenommen Ein Zeiger auf das Token, das das Modul darstellt, auf das im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="346e6-106">[out] A pointer to the token representing the module referenced in the current metadata scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="346e6-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="346e6-107">Requirements</span></span>  

 <span data-ttu-id="346e6-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="346e6-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="346e6-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="346e6-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="346e6-110">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="346e6-110">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="346e6-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="346e6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="346e6-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="346e6-112">See also</span></span>

- [<span data-ttu-id="346e6-113">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="346e6-113">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="346e6-114">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="346e6-114">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
