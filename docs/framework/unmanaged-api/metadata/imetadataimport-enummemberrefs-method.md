---
title: IMetaDataImport::EnumMemberRefs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMemberRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMemberRefs
helpviewer_keywords:
- EnumMemberRefs method [.NET Framework metadata]
- IMetaDataImport::EnumMemberRefs method [.NET Framework metadata]
ms.assetid: e97c97a6-6e4f-41f5-9af1-9b3cf3bdbd6b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 34a6762618780b22bcd8be376209912390524578
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54592013"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="f6cbc-102">IMetaDataImport::EnumMemberRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="f6cbc-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="f6cbc-103">Zählt MemberRef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="f6cbc-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6cbc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6cbc-104">Syntax</span></span>  
  
```  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,   
   [in]   mdToken        tkParent,   
   [out]  mdMemberRef    rMemberRefs[],   
   [in]   ULONG          cMax,   
   [out]  ULONG          *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f6cbc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f6cbc-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f6cbc-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="f6cbc-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="f6cbc-107">[in] Eine TypeDef, TypeRef, MethodDef oder ModuleRef-Token für den Typ, dessen Member aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f6cbc-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="f6cbc-108">[out] Das Array zum Speichern von MemberRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f6cbc-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f6cbc-109">[in] Die maximale Größe des `rMemberRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="f6cbc-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f6cbc-110">[out] Die tatsächliche Anzahl der zurückgegebenen MemberRef-Token `rMemberRefs`.</span><span class="sxs-lookup"><span data-stu-id="f6cbc-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f6cbc-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f6cbc-111">Return Value</span></span>  
  
|<span data-ttu-id="f6cbc-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f6cbc-112">HRESULT</span></span>|<span data-ttu-id="f6cbc-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6cbc-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f6cbc-114">`EnumMemberRefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f6cbc-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f6cbc-115">Es sind keine MemberRef-Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="f6cbc-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="f6cbc-116">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="f6cbc-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f6cbc-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6cbc-117">Requirements</span></span>  
 <span data-ttu-id="f6cbc-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f6cbc-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f6cbc-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6cbc-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f6cbc-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f6cbc-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f6cbc-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f6cbc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6cbc-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6cbc-122">See also</span></span>
- [<span data-ttu-id="f6cbc-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6cbc-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f6cbc-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f6cbc-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
