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
ms.openlocfilehash: b8a65b0748fec0e474d8b3b5dc03473fbd716108
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177336"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="24511-102">IMetaDataImport::EnumMemberRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="24511-102">IMetaDataImport::EnumMemberRefs Method</span></span>
<span data-ttu-id="24511-103">Zählt MemberRef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="24511-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24511-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24511-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24511-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="24511-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="24511-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="24511-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="24511-107">[in] Ein TypeDef-, TypeRef-, MethodDef- oder ModuleRef-Token für den Typ, dessen Member aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="24511-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="24511-108">[out] Das Array, das zum Speichern von MemberRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="24511-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="24511-109">[in] Die maximale Größe des `rMemberRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="24511-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="24511-110">[out] Die tatsächliche Anzahl der In. `rMemberRefs`MemberRef-Token, die in zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="24511-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="24511-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="24511-111">Return Value</span></span>  
  
|<span data-ttu-id="24511-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="24511-112">HRESULT</span></span>|<span data-ttu-id="24511-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24511-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="24511-114">`EnumMemberRefs`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="24511-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="24511-115">Es sind keine MemberRef-Token zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="24511-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="24511-116">In diesem `pcTokens` Fall ist zu Null.</span><span class="sxs-lookup"><span data-stu-id="24511-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24511-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="24511-117">Requirements</span></span>  
 <span data-ttu-id="24511-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24511-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24511-119">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="24511-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24511-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="24511-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24511-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24511-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24511-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24511-122">See also</span></span>

- [<span data-ttu-id="24511-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24511-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="24511-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24511-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
