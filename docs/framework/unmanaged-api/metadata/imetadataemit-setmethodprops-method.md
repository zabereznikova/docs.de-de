---
title: IMetaDataEmit::SetMethodProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodProps
helpviewer_keywords:
- SetMethodProps method [.NET Framework metadata]
- IMetaDataEmit::SetMethodProps method [.NET Framework metadata]
ms.assetid: e0c6ac12-22ea-43f5-b799-8cda0faf3336
topic_type:
- apiref
ms.openlocfilehash: c461582cc22f7185ee2707db91be83bc1aa0ba4c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706836"
---
# <a name="imetadataemitsetmethodprops-method"></a><span data-ttu-id="b5866-102">IMetaDataEmit::SetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="b5866-102">IMetaDataEmit::SetMethodProps Method</span></span>

<span data-ttu-id="b5866-103">Legt die Funktion, die bei der angegebenen relativen virtuellen Adresse gespeichert ist, für eine Methode fest oder aktualisiert Sie, die durch einen früheren [IMetaDataEmit::D efinemethod](imetadataemit-definemethod-method.md)-aufzurufen ist.</span><span class="sxs-lookup"><span data-stu-id="b5866-103">Sets or updates the feature, stored at the specified relative virtual address, of a method defined by a prior call to [IMetaDataEmit::DefineMethod](imetadataemit-definemethod-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5866-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5866-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodProps (
    [in]  mdMethodDef md,
    [in]  DWORD       dwMethodFlags,  
    [in]  ULONG       ulCodeRVA,
    [in]  DWORD       dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5866-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5866-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="b5866-106">in Das Token für die zu ändernde Methode.</span><span class="sxs-lookup"><span data-stu-id="b5866-106">[in] The token for the method to be changed.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="b5866-107">in Die Element Attribute.</span><span class="sxs-lookup"><span data-stu-id="b5866-107">[in] The member attributes.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="b5866-108">in Die Adresse des Codes.</span><span class="sxs-lookup"><span data-stu-id="b5866-108">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="b5866-109">in Die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="b5866-109">[in] The implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5866-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b5866-110">Requirements</span></span>  

 <span data-ttu-id="b5866-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5866-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5866-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b5866-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b5866-113">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5866-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b5866-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5866-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5866-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5866-115">See also</span></span>

- [<span data-ttu-id="b5866-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5866-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b5866-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b5866-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
