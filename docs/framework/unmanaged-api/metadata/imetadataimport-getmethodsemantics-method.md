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
ms.openlocfilehash: 65bc4bc74e06368e6c7be9b742a8f311ecadc7fc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782319"
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="4564a-102">IMetaDataImport::GetMethodSemantics-Methode</span><span class="sxs-lookup"><span data-stu-id="4564a-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="4564a-103">Ruft Flags, die die Beziehung zwischen dem-Methode auf, die vom angegebenen MethodDef-Token und der gepaarten Eigenschaft verwiesen wird und ein Ereignis, die auf die verwiesen wird vom angegebenen EventProp-token ab.</span><span class="sxs-lookup"><span data-stu-id="4564a-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4564a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4564a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4564a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4564a-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="4564a-106">[in] Ein MethodDef-Token, die die semantische Informationen für die abzurufenden Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="4564a-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="4564a-107">[in] Ein Token, das darstellt, die gepaarten Eigenschaft und das Ereignis für den die Rolle der Methode abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4564a-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="4564a-108">[out] Ein Zeiger auf die zugeordnete Semantik-Flags.</span><span class="sxs-lookup"><span data-stu-id="4564a-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="4564a-109">Dieser Wert ist eine Bitmaske aus der [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="4564a-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4564a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4564a-110">Remarks</span></span>  
 <span data-ttu-id="4564a-111">Die [IMetaDataEmit:: DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) Methode wird von einer Methode Semantikflags.</span><span class="sxs-lookup"><span data-stu-id="4564a-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4564a-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4564a-112">Requirements</span></span>  
 <span data-ttu-id="4564a-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4564a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4564a-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4564a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4564a-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4564a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4564a-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4564a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4564a-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4564a-117">See also</span></span>

- [<span data-ttu-id="4564a-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4564a-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4564a-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4564a-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
