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
ms.openlocfilehash: 068014732cee91147edaec29fa0f954a741d8b5c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491653"
---
# <a name="imetadataimportfindmemberref-method"></a><span data-ttu-id="794e1-102">IMetaDataImport::FindMemberRef-Methode</span><span class="sxs-lookup"><span data-stu-id="794e1-102">IMetaDataImport::FindMemberRef Method</span></span>
<span data-ttu-id="794e1-103">Ruft einen Zeiger auf das Mitgliedschaft Verweis Token für den Element Verweis ab, der durch den angegebenen eingeschlossen ist <xref:System.Type> und den angegebenen Namen und die angegebene Metadatensignatur aufweist.</span><span class="sxs-lookup"><span data-stu-id="794e1-103">Gets a pointer to the MemberRef token for the member reference that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="794e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="794e1-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="794e1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="794e1-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="794e1-106">in Das TypeRef-Token für die Klasse oder Schnittstelle, die den zu suchenden Element Verweis einschließt.</span><span class="sxs-lookup"><span data-stu-id="794e1-106">[in] The TypeRef token for the class or interface that encloses the member reference to search for.</span></span> <span data-ttu-id="794e1-107">Wenn dieser Wert ist `mdTokenNil` , erfolgt die Suche für eine globale Variable oder einen globalen Funktions Verweis.</span><span class="sxs-lookup"><span data-stu-id="794e1-107">If this value is `mdTokenNil`, the lookup is done for a global variable or a global-function reference.</span></span>  
  
 `szName`  
 <span data-ttu-id="794e1-108">in Der Name des Element Verweises, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="794e1-108">[in] The name of the member reference to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="794e1-109">in Ein Zeiger auf die binäre Metadatensignatur des Element Verweises.</span><span class="sxs-lookup"><span data-stu-id="794e1-109">[in] A pointer to the binary metadata signature of the member reference.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="794e1-110">in Die Größe von in Bytes `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="794e1-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="794e1-111">vorgenommen Ein Zeiger auf das übereinstimmende mitgliedlinienref-Token.</span><span class="sxs-lookup"><span data-stu-id="794e1-111">[out] A pointer to the matching MemberRef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="794e1-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="794e1-112">Remarks</span></span>  
 <span data-ttu-id="794e1-113">Sie geben den Member mit der einschließenden Klasse oder Schnittstelle ( `td` ), dem Namen ( `szName` ) und optional der Signatur ( `pvSigBlob` ) an.</span><span class="sxs-lookup"><span data-stu-id="794e1-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="794e1-114">Die an über gegebene Signatur `FindMemberRef` muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="794e1-114">The signature passed to `FindMemberRef` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="794e1-115">Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="794e1-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="794e1-116">Das Token ist ein Index in der lokalen Tabelle "Typedef".</span><span class="sxs-lookup"><span data-stu-id="794e1-116">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="794e1-117">Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Bereichs erstellen und diese Signatur als Eingabe für verwenden `FindMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="794e1-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindMemberRef`.</span></span>  
  
 <span data-ttu-id="794e1-118">`FindMemberRef`sucht nur Member-Verweise, die direkt in der Klasse oder Schnittstelle definiert wurden. vererbte Element Verweise werden nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="794e1-118">`FindMemberRef` finds only member references that were defined directly in the class or interface; it does not find inherited member references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="794e1-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="794e1-119">Requirements</span></span>  
 <span data-ttu-id="794e1-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="794e1-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="794e1-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="794e1-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="794e1-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="794e1-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="794e1-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="794e1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="794e1-124">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="794e1-124">See also</span></span>

- [<span data-ttu-id="794e1-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="794e1-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="794e1-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="794e1-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
