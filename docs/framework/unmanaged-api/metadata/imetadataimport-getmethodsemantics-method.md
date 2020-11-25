---
title: IMetaDataImport::GetMethodSemantics-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type:
- apiref
ms.openlocfilehash: cc01a417c3246ad2554c506f21e37a3cbbdeb991
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733184"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="e9638-102">IMetaDataImport::GetMethodSemantics-Methode</span><span class="sxs-lookup"><span data-stu-id="e9638-102">IMetaDataImport::GetMethodSemantics Method</span></span>

<span data-ttu-id="e9638-103">Ruft Flags ab, die die Beziehung zwischen der Methode angeben, auf die vom angegebenen MethodDef-Token verwiesen wird, und der gekoppelten Eigenschaft und dem Ereignis, auf die vom angegebenen EventProp</span><span class="sxs-lookup"><span data-stu-id="e9638-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9638-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9638-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9638-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9638-105">Parameters</span></span>  

 `mb`  
 <span data-ttu-id="e9638-106">in Ein MethodDef-Token, das die Methode darstellt, für die die semantischen Rollen Informationen zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="e9638-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="e9638-107">in Ein Token, das die gekoppelte Eigenschaft und das Ereignis darstellt, für das die Rolle der Methode angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e9638-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="e9638-108">vorgenommen Ein Zeiger auf die zugeordneten Semantik Flags.</span><span class="sxs-lookup"><span data-stu-id="e9638-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="e9638-109">Dieser Wert ist eine Bitmaske aus der [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e9638-109">This value is a bitmask from the [CorMethodSemanticsAttr](cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e9638-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e9638-110">Remarks</span></span>  

 <span data-ttu-id="e9638-111">Mit der [IMetaDataEmit::D efineproperty](imetadataemit-defineproperty-method.md) -Methode werden die Semantik Flags einer Methode festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e9638-111">The [IMetaDataEmit::DefineProperty](imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9638-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e9638-112">Requirements</span></span>  

 <span data-ttu-id="e9638-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9638-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9638-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e9638-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9638-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e9638-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9638-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9638-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9638-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e9638-117">See also</span></span>

- [<span data-ttu-id="e9638-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9638-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="e9638-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9638-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
