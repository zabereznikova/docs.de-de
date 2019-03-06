---
title: IMetaDataImport::FindMember-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 777d7bf51db3e6984f30e31c46ac115301d13faf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478972"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="c78c5-102">IMetaDataImport::FindMember-Methode</span><span class="sxs-lookup"><span data-stu-id="c78c5-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="c78c5-103">Ruft einen Zeiger auf das MemberDef token für das Feld oder eine Methode, die eingeschlossen ist mit dem angegebenen <xref:System.Type> und dem angegebenen Namen und Metadaten aufweist.</span><span class="sxs-lookup"><span data-stu-id="c78c5-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c78c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c78c5-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c78c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c78c5-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c78c5-106">[in] Die TypeDef-Token für die Klasse oder Schnittstelle, die zu suchenden Member einschließt.</span><span class="sxs-lookup"><span data-stu-id="c78c5-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="c78c5-107">Wenn dieser Wert ist `mdTokenNil`, die Suche für eine globale Variable oder eine globale Funktion durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c78c5-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="c78c5-108">[in] Der Name des zu suchenden Members.</span><span class="sxs-lookup"><span data-stu-id="c78c5-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c78c5-109">[in] Ein Zeiger auf die binäre Metadatensignatur des Elements.</span><span class="sxs-lookup"><span data-stu-id="c78c5-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c78c5-110">[in] Die Größe in Bytes der `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="c78c5-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="c78c5-111">[out] Ein Zeiger auf das entsprechende MemberDef-Token.</span><span class="sxs-lookup"><span data-stu-id="c78c5-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c78c5-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c78c5-112">Remarks</span></span>  
 <span data-ttu-id="c78c5-113">Geben Sie den Member, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="c78c5-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="c78c5-114">Es gibt möglicherweise mehrere Member mit demselben Namen in einer Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="c78c5-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="c78c5-115">In diesem Fall übergeben Sie die Signatur des Members um die eindeutige Übereinstimmung zu finden.</span><span class="sxs-lookup"><span data-stu-id="c78c5-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="c78c5-116">Die Signatur, die an `FindMember` müssen wurden generiert im aktuellen Bereich, da die Signaturen für einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="c78c5-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="c78c5-117">Eine Signatur kann es sich um ein Token einbetten, die die einschließende Klasse oder eines Werttyps identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c78c5-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="c78c5-118">Das Token ist ein Index in die lokale TypeDef-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c78c5-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="c78c5-119">Sie erstellen eine Signatur zur Laufzeit im Kontext des aktuellen Bereichs und verwenden Sie diese Signatur als Eingabe können nicht `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="c78c5-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="c78c5-120">`FindMember` Sucht nur Member, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbte Member.</span><span class="sxs-lookup"><span data-stu-id="c78c5-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c78c5-121">`FindMember` ist eine Hilfsmethode.</span><span class="sxs-lookup"><span data-stu-id="c78c5-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="c78c5-122">Ruft [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Wenn dieser Aufruf keine Übereinstimmung findet `FindMember` ruft dann [IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="c78c5-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c78c5-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c78c5-123">Requirements</span></span>  
 <span data-ttu-id="c78c5-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c78c5-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c78c5-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c78c5-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c78c5-126">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c78c5-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c78c5-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c78c5-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78c5-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c78c5-128">See also</span></span>
- [<span data-ttu-id="c78c5-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c78c5-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c78c5-130">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c78c5-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
