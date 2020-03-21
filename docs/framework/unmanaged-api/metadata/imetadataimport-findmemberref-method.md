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
ms.openlocfilehash: d8b8bfd0e70e75c702f32555c10f433a1ff4ae10
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175420"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="8f7c2-102">IMetaDataImport::FindMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="8f7c2-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="8f7c2-103">Ruft einen Zeiger auf das MemberRef-Token für den Memberverweis ab, der von der angegebenen <xref:System.Type> Datei eingeschlossen ist und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f7c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f7c2-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f7c2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8f7c2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="8f7c2-106">[in] Das TypeRef-Token für die Klasse oder Schnittstelle, die den Memberverweis einschließt, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="8f7c2-107">Wenn dieser `mdTokenNil`Wert ist, erfolgt die Suche nach einer globalen Variablen oder einem verweis auf globale Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="8f7c2-108">[in] Der Name des Memberverweises, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="8f7c2-109">[in] Ein Zeiger auf die binäre Metadatensignatur des Memberverweises.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="8f7c2-110">[in] Die Größe in `pvSigBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="8f7c2-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="8f7c2-111">[out] Ein Zeiger auf das übereinstimmende MemberRef-Token.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f7c2-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8f7c2-112">Remarks</span></span>  
 <span data-ttu-id="8f7c2-113">Sie geben den Member mit seiner`td`einschließenden`szName`Klasse oder Schnittstelle (`pvSigBlob`), seinem Namen ( ) und optional seiner Signatur ( ) an.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="8f7c2-114">Die übergebene `FindMemberRef` Signatur muss im aktuellen Bereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="8f7c2-115">Eine Signatur kann ein Token einbetten, das die einschließende Klasse oder den Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="8f7c2-116">Das Token ist ein Index in der lokalen TypeDef-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="8f7c2-117">Sie können keine Laufzeitsignatur außerhalb des Kontexts des aktuellen Bereichs `FindMemberRef`erstellen und diese Signatur als Eingabe für verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="8f7c2-118">`FindMemberRef`findet nur Memberverweise, die direkt in der Klasse oder Schnittstelle definiert wurden; Es werden keine geerbten Memberverweise gefunden.</span><span class="sxs-lookup"><span data-stu-id="8f7c2-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f7c2-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8f7c2-119">Requirements</span></span>  
 <span data-ttu-id="8f7c2-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f7c2-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f7c2-121">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8f7c2-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f7c2-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8f7c2-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f7c2-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f7c2-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f7c2-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f7c2-124">See also</span></span>

- [<span data-ttu-id="8f7c2-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f7c2-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8f7c2-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8f7c2-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
