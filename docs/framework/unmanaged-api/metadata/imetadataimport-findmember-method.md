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
ms.openlocfilehash: bcd9499d0aef34fb34065ed58c0f0d69cc4ecedc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711441"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="902a2-102">IMetaDataImport::FindMember-Methode</span><span class="sxs-lookup"><span data-stu-id="902a2-102">IMetaDataImport::FindMember Method</span></span>

<span data-ttu-id="902a2-103">Ruft einen Zeiger auf das mitgliedtendef-Token für das Feld oder die Methode ab, das durch den angegebenen eingeschlossen ist <xref:System.Type> und den angegebenen Namen und die angegebene Metadatensignatur aufweist.</span><span class="sxs-lookup"><span data-stu-id="902a2-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="902a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="902a2-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,
   [in]  PCCOR_SIGNATURE   pvSigBlob,
   [in]  ULONG             cbSigBlob,
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="902a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="902a2-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="902a2-106">in Das TypeDef-Token für die Klasse oder Schnittstelle, die den Member einschließt, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="902a2-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="902a2-107">Wenn dieser Wert ist `mdTokenNil` , wird die Suche für eine globale Variable oder globale Funktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="902a2-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="902a2-108">in Der Name des zu suchenden Members.</span><span class="sxs-lookup"><span data-stu-id="902a2-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="902a2-109">in Ein Zeiger auf die binäre Metadatensignatur des Members.</span><span class="sxs-lookup"><span data-stu-id="902a2-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="902a2-110">in Die Größe von in Bytes `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="902a2-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="902a2-111">vorgenommen Ein Zeiger auf das übereinstimmende mitgliedtdef-Token.</span><span class="sxs-lookup"><span data-stu-id="902a2-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="902a2-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="902a2-112">Remarks</span></span>  

 <span data-ttu-id="902a2-113">Sie geben den Member mit der einschließenden Klasse oder Schnittstelle ( `td` ), dem Namen ( `szName` ) und optional der Signatur ( `pvSigBlob` ) an.</span><span class="sxs-lookup"><span data-stu-id="902a2-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="902a2-114">In einer Klasse oder Schnittstelle können mehrere Member mit demselben Namen vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="902a2-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="902a2-115">Übergeben Sie in diesem Fall die Signatur des Members, um die eindeutige Entsprechung zu finden.</span><span class="sxs-lookup"><span data-stu-id="902a2-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="902a2-116">Die an über gegebene Signatur `FindMember` muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="902a2-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="902a2-117">Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="902a2-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="902a2-118">Das Token ist ein Index in der lokalen Tabelle "Typedef".</span><span class="sxs-lookup"><span data-stu-id="902a2-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="902a2-119">Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Gültigkeits Bereichs erstellen und diese Signatur als Eingabe für die Eingabe verwenden `FindMember` .</span><span class="sxs-lookup"><span data-stu-id="902a2-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="902a2-120">`FindMember` sucht nur Elemente, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Member werden nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="902a2-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="902a2-121">`FindMember` ist eine Hilfsmethode.</span><span class="sxs-lookup"><span data-stu-id="902a2-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="902a2-122">Es wird [IMetaDataImport:: FindMethod](imetadataimport-findmethod-method.md); aufgerufen. Wenn dieser Aufruf keine Entsprechung findet, `FindMember` ruft [IMetaDataImport:: FindField](imetadataimport-findfield-method.md)auf.</span><span class="sxs-lookup"><span data-stu-id="902a2-122">It calls [IMetaDataImport::FindMethod](imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="902a2-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="902a2-123">Requirements</span></span>  

 <span data-ttu-id="902a2-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="902a2-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="902a2-125">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="902a2-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="902a2-126">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="902a2-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="902a2-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="902a2-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="902a2-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="902a2-128">See also</span></span>

- [<span data-ttu-id="902a2-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="902a2-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="902a2-130">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="902a2-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
