---
title: IMetaDataImport::FindMemberRef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0d446e2b78f41d43aa70f429e23f1f4be22fd799
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782505"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="12837-102">IMetaDataImport::FindMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="12837-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="12837-103">Ruft ein Zeiger auf das MemberRef-Token für das Element verweisen, eingeschlossen durch das angegebene <xref:System.Type> und dem angegebenen Namen und Metadaten aufweist.</span><span class="sxs-lookup"><span data-stu-id="12837-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12837-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="12837-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12837-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="12837-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="12837-106">[in] Die TypeRef-Token für die Klasse oder Schnittstelle, die den Parameterverweis zu suchende eingeschlossen werden soll.</span><span class="sxs-lookup"><span data-stu-id="12837-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="12837-107">Wenn dieser Wert ist `mdTokenNil`, die Suche für eine globale Variable oder einen Verweis für die globale Funktion durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="12837-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="12837-108">[in] Der Name des Verweises zu suchende Element.</span><span class="sxs-lookup"><span data-stu-id="12837-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="12837-109">[in] Ein Zeiger auf die binäre Metadatensignatur der den Parameterverweis.</span><span class="sxs-lookup"><span data-stu-id="12837-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="12837-110">[in] Die Größe in Bytes der `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="12837-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="12837-111">[out] Ein Zeiger auf das entsprechende MemberRef-Token.</span><span class="sxs-lookup"><span data-stu-id="12837-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="12837-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="12837-112">Remarks</span></span>  
 <span data-ttu-id="12837-113">Geben Sie den Member, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="12837-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="12837-114">Die Signatur, die an `FindMemberRef` müssen wurden generiert im aktuellen Bereich, da die Signaturen für einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="12837-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="12837-115">Eine Signatur kann es sich um ein Token einbetten, die die einschließende Klasse oder eines Werttyps identifiziert.</span><span class="sxs-lookup"><span data-stu-id="12837-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="12837-116">Das Token ist ein Index in die lokale TypeDef-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="12837-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="12837-117">Sie können keine Signatur zur Laufzeit im Kontext des aktuellen Bereichs und diese Signatur als Eingabe für `FindMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="12837-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="12837-118">`FindMemberRef` Sucht nur Memberverweise, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbte memberverweisen.</span><span class="sxs-lookup"><span data-stu-id="12837-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12837-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="12837-119">Requirements</span></span>  
 <span data-ttu-id="12837-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12837-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12837-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="12837-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="12837-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="12837-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="12837-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12837-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12837-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="12837-124">See also</span></span>

- [<span data-ttu-id="12837-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12837-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="12837-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="12837-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
