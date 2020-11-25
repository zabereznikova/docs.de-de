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
ms.openlocfilehash: d8b02e85efc2cd7364690dd42104a313ba6ec272
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711454"
---
# <a name="imetadataimportenummemberrefs-method"></a><span data-ttu-id="70eb3-102">IMetaDataImport::EnumMemberRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="70eb3-102">IMetaDataImport::EnumMemberRefs Method</span></span>

<span data-ttu-id="70eb3-103">Zählt MemberRef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="70eb3-103">Enumerates MemberRef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70eb3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70eb3-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemberRefs (  
   [in, out] HCORENUM    *phEnum,
   [in]   mdToken        tkParent,
   [out]  mdMemberRef    rMemberRefs[],
   [in]   ULONG          cMax,
   [out]  ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70eb3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="70eb3-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="70eb3-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="70eb3-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="70eb3-107">in Ein TypeDef-, TypeRef-, MethodDef-oder ModuleRef-Token für den Typ, dessen Member aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="70eb3-107">[in] A TypeDef, TypeRef, MethodDef, or ModuleRef token for the type whose members are to be enumerated.</span></span>  
  
 `rMemberRefs`  
 <span data-ttu-id="70eb3-108">vorgenommen Das Array, das zum Speichern von mitgliedverweis Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="70eb3-108">[out] The array used to store MemberRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="70eb3-109">[in] Die maximale Größe des `rMemberRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="70eb3-109">[in] The maximum size of the `rMemberRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="70eb3-110">vorgenommen Die tatsächliche Anzahl der in zurückgegebenen mitgliedungstokentoken `rMemberRefs` .</span><span class="sxs-lookup"><span data-stu-id="70eb3-110">[out] The actual number of MemberRef tokens returned in `rMemberRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="70eb3-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="70eb3-111">Return Value</span></span>  
  
|<span data-ttu-id="70eb3-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="70eb3-112">HRESULT</span></span>|<span data-ttu-id="70eb3-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="70eb3-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="70eb3-114">`EnumMemberRefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="70eb3-114">`EnumMemberRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="70eb3-115">Es sind keine mitgliedungstokentoken zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="70eb3-115">There are no MemberRef tokens to enumerate.</span></span> <span data-ttu-id="70eb3-116">In diesem Fall hat `pcTokens` den Wert 0 (null).</span><span class="sxs-lookup"><span data-stu-id="70eb3-116">In that case, `pcTokens` is to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70eb3-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="70eb3-117">Requirements</span></span>  

 <span data-ttu-id="70eb3-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70eb3-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70eb3-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="70eb3-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="70eb3-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="70eb3-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="70eb3-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70eb3-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70eb3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="70eb3-122">See also</span></span>

- [<span data-ttu-id="70eb3-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70eb3-123">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="70eb3-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70eb3-124">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
