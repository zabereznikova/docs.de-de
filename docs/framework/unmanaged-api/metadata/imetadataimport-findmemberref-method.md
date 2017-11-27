---
title: IMetaDataImport::FindMemberRef-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.FindMemberRef
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: efb8a3a74997c6894eff6fafb87e933a6d2cf7bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="f9210-102">IMetaDataImport::FindMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="f9210-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="f9210-103">Ruft ein Zeiger auf das MemberRef-Token für das Element verweisen, d. h. durch das angegebene eingeschlossen <xref:System.Type> und den angegebenen Namen und Metadaten aufweist.</span><span class="sxs-lookup"><span data-stu-id="f9210-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9210-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9210-104">Syntax</span></span>  
  
```  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9210-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9210-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="f9210-106">[in] Das TypeRef-Token für die Klasse oder Schnittstelle, die den Parameterverweis zu suchende einschließt.</span><span class="sxs-lookup"><span data-stu-id="f9210-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="f9210-107">Wenn dieser Wert ist `mdTokenNil`, die Suche für eine globale Variable oder eine globale Funktion Verweis erfolgt.</span><span class="sxs-lookup"><span data-stu-id="f9210-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="f9210-108">[in] Der Name des zu suchenden den Parameterverweis.</span><span class="sxs-lookup"><span data-stu-id="f9210-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f9210-109">[in] Ein Zeiger auf die binäre Metadatensignatur der den Parameterverweis.</span><span class="sxs-lookup"><span data-stu-id="f9210-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="f9210-110">[in] Die Größe in Bytes des `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="f9210-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="f9210-111">[out] Ein Zeiger auf das übereinstimmende MemberRef-Token.</span><span class="sxs-lookup"><span data-stu-id="f9210-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9210-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9210-112">Remarks</span></span>  
 <span data-ttu-id="f9210-113">Geben Sie die Member, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="f9210-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="f9210-114">Die Signatur zu übergeben, um `FindMemberRef` muss wurden im aktuellen Bereich generiert wurde, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="f9210-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="f9210-115">Eine Signatur kann ein Token einbetten, die die einschließende Klasse oder der angegebene Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f9210-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="f9210-116">Das Token ist ein Index in die lokale TypeDef-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f9210-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="f9210-117">Sie können keine Laufzeit-Signatur im Kontext des aktuellen Gültigkeitsbereichs erstellen und verwenden Sie diese Signatur als Eingabe für `FindMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="f9210-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="f9210-118">`FindMemberRef`Sucht nur Elementverweise, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbten Member verweisen.</span><span class="sxs-lookup"><span data-stu-id="f9210-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9210-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9210-119">Requirements</span></span>  
 <span data-ttu-id="f9210-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9210-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9210-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f9210-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f9210-122">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f9210-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9210-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9210-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9210-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9210-124">See Also</span></span>  
 [<span data-ttu-id="f9210-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9210-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f9210-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9210-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
