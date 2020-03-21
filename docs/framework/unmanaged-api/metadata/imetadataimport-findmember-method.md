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
ms.openlocfilehash: dab155b82d87609b3d3f390133e6490502a43518
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177280"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="2d4cf-102">IMetaDataImport::FindMember-Methode</span><span class="sxs-lookup"><span data-stu-id="2d4cf-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="2d4cf-103">Ruft einen Zeiger auf das MemberDef-Token für das Feld <xref:System.Type> oder die Methode ab, das von der angegebenen Datei eingeschlossen ist und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d4cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d4cf-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d4cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d4cf-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2d4cf-106">[in] Das TypeDef-Token für die Klasse oder Schnittstelle, die den zu suchenden Member einschließt.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="2d4cf-107">Wenn dieser `mdTokenNil`Wert ist, erfolgt die Suche nach einer global-variablen oder globalen Funktion.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="2d4cf-108">[in] Der Name des Elements, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2d4cf-109">[in] Ein Zeiger auf die binäre Metadatensignatur des Members.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="2d4cf-110">[in] Die Größe in `pvSigBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="2d4cf-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="2d4cf-111">[out] Ein Zeiger auf das übereinstimmende MemberDef-Token.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d4cf-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2d4cf-112">Remarks</span></span>  
 <span data-ttu-id="2d4cf-113">Sie geben den Member mit seiner`td`einschließenden`szName`Klasse oder Schnittstelle (`pvSigBlob`), seinem Namen ( ) und optional seiner Signatur ( ) an.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="2d4cf-114">Möglicherweise gibt es mehrere Member mit demselben Namen in einer Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="2d4cf-115">Übergeben Sie in diesem Fall die Signatur des Mitglieds, um die eindeutige Übereinstimmung zu finden.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="2d4cf-116">Die übergebene `FindMember` Signatur muss im aktuellen Bereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="2d4cf-117">Eine Signatur kann ein Token einbetten, das die einschließende Klasse oder den Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="2d4cf-118">Das Token ist ein Index in der lokalen TypeDef-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="2d4cf-119">Sie können keine Laufzeitsignatur außerhalb des Kontexts des aktuellen Bereichs erstellen `FindMember`und diese Signatur als Eingabe für die Eingabe für verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="2d4cf-120">`FindMember`findet nur Member, die direkt in der Klasse oder Schnittstelle definiert wurden; Es werden keine geerbten Mitglieder gefunden.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2d4cf-121">`FindMember`ist eine Hilfsmethode.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="2d4cf-122">Es ruft [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); Wenn dieser Aufruf keine Übereinstimmung `FindMember` findet, ruft [iMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)auf.</span><span class="sxs-lookup"><span data-stu-id="2d4cf-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d4cf-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d4cf-123">Requirements</span></span>  
 <span data-ttu-id="2d4cf-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d4cf-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d4cf-125">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2d4cf-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2d4cf-126">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2d4cf-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2d4cf-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d4cf-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d4cf-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d4cf-128">See also</span></span>

- [<span data-ttu-id="2d4cf-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d4cf-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2d4cf-130">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d4cf-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
