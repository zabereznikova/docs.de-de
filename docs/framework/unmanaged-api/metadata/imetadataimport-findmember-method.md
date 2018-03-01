---
title: IMetaDataImport::FindMember-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a20930688aed210309a719de2c7187f1f5fd1f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="eec19-102">IMetaDataImport::FindMember-Methode</span><span class="sxs-lookup"><span data-stu-id="eec19-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="eec19-103">Ruft einen Zeiger auf das MemberDef token für das Feld oder eine Methode, die eingeschlossen ist durch das angegebene <xref:System.Type> und den angegebenen Namen und Metadaten aufweist.</span><span class="sxs-lookup"><span data-stu-id="eec19-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eec19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eec19-104">Syntax</span></span>  
  
```  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eec19-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eec19-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="eec19-106">[in] Das TypeDef-Token für die Klasse oder Schnittstelle, das der gesuchten Member enthält.</span><span class="sxs-lookup"><span data-stu-id="eec19-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="eec19-107">Wenn dieser Wert `mdTokenNil`, wird die Suche für eine globale Variable oder eine globale Funktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="eec19-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="eec19-108">[in] Der Name des zu suchenden Elements.</span><span class="sxs-lookup"><span data-stu-id="eec19-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="eec19-109">[in] Ein Zeiger auf die binäre Metadatensignatur des Members.</span><span class="sxs-lookup"><span data-stu-id="eec19-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="eec19-110">[in] Die Größe in Bytes des `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="eec19-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="eec19-111">[out] Ein Zeiger auf das übereinstimmende MemberDef-Token.</span><span class="sxs-lookup"><span data-stu-id="eec19-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eec19-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eec19-112">Remarks</span></span>  
 <span data-ttu-id="eec19-113">Geben Sie die Member, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="eec19-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="eec19-114">Es gibt möglicherweise mehrere Elemente mit dem gleichen Namen in einer Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="eec19-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="eec19-115">In diesem Fall übergeben Sie Signatur des Members, um die eindeutige Übereinstimmung zu finden.</span><span class="sxs-lookup"><span data-stu-id="eec19-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="eec19-116">Die Signatur zu übergeben, um `FindMember` muss wurden im aktuellen Bereich generiert wurde, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="eec19-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="eec19-117">Eine Signatur kann ein Token einbetten, die die einschließende Klasse oder der angegebene Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="eec19-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="eec19-118">Das Token ist ein Index in die lokale TypeDef-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="eec19-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="eec19-119">Sie erstellen eine Laufzeit-Signatur im Kontext des aktuellen Gültigkeitsbereichs und verwenden Sie diese Signatur als Eingabe können nicht `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="eec19-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="eec19-120">`FindMember`Sucht nur Member, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Member werden nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="eec19-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eec19-121">`FindMember`ist eine Hilfsmethode.</span><span class="sxs-lookup"><span data-stu-id="eec19-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="eec19-122">Sie ruft [IMetaDataImport:: FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Wenn dieser Aufruf keine Übereinstimmung findet `FindMember` ruft dann [IMetaDataImport:: FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="eec19-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eec19-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eec19-123">Requirements</span></span>  
 <span data-ttu-id="eec19-124">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eec19-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eec19-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eec19-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eec19-126">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eec19-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eec19-127">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eec19-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec19-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eec19-128">See Also</span></span>  
 [<span data-ttu-id="eec19-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eec19-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="eec19-130">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eec19-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
