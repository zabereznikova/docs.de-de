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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57ddbd8c6935f2c0275c132e30ea175c6f198fac
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200089"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="0f2ab-102">IMetaDataImport::GetMethodSemantics-Methode</span><span class="sxs-lookup"><span data-stu-id="0f2ab-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="0f2ab-103">Ruft Flags, die die Beziehung zwischen dem-Methode auf, die vom angegebenen MethodDef-Token und der gepaarten Eigenschaft verwiesen wird und ein Ereignis, die auf die verwiesen wird vom angegebenen EventProp-token ab.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f2ab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f2ab-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f2ab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f2ab-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="0f2ab-106">[in] Ein MethodDef-Token, die die semantische Informationen für die abzurufenden Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="0f2ab-107">[in] Ein Token, das darstellt, die gepaarten Eigenschaft und das Ereignis für den die Rolle der Methode abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="0f2ab-108">[out] Ein Zeiger auf die zugeordnete Semantik-Flags.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="0f2ab-109">Dieser Wert ist eine Bitmaske aus der [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f2ab-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f2ab-110">Remarks</span></span>  
 <span data-ttu-id="0f2ab-111">Die [IMetaDataEmit:: DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) Methode wird von einer Methode Semantikflags.</span><span class="sxs-lookup"><span data-stu-id="0f2ab-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f2ab-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0f2ab-112">Requirements</span></span>  
 <span data-ttu-id="0f2ab-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f2ab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f2ab-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0f2ab-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f2ab-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0f2ab-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f2ab-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f2ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2ab-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f2ab-117">See also</span></span>

- [<span data-ttu-id="0f2ab-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f2ab-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0f2ab-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f2ab-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
