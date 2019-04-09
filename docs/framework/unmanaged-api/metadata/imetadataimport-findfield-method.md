---
title: IMetaDataImport::FindField-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 88cd08b4290739808079bc8ecb713a5c5ea96584
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172561"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="9b558-102">IMetaDataImport::FindField-Methode</span><span class="sxs-lookup"><span data-stu-id="9b558-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="9b558-103">Ruft einen Zeiger auf das FieldDef token für das Feld, das eingeschlossen wird durch das angegebene <xref:System.Type> und dem angegebenen Namen und Metadaten aufweist.</span><span class="sxs-lookup"><span data-stu-id="9b558-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b558-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b558-104">Syntax</span></span>  
  
```  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b558-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b558-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9b558-106">[in] Die TypeDef-Token für die Klasse oder Schnittstelle, die zu suchenden Felds einschließt.</span><span class="sxs-lookup"><span data-stu-id="9b558-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="9b558-107">Wenn dieser Wert ist `mdTokenNil`, wird die Suche für eine globale Variable durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="9b558-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="9b558-108">[in] Der Name des zu suchenden Felds.</span><span class="sxs-lookup"><span data-stu-id="9b558-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9b558-109">[in] Ein Zeiger auf die binäre Metadatensignatur des Felds.</span><span class="sxs-lookup"><span data-stu-id="9b558-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="9b558-110">[in] Die Größe in Bytes der `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="9b558-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="9b558-111">[out] Ein Zeiger auf das entsprechende FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="9b558-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b558-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b558-112">Remarks</span></span>  
 <span data-ttu-id="9b558-113">Geben Sie das Feld mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="9b558-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="9b558-114">Die Signatur, die an `FindField` müssen wurden generiert im aktuellen Bereich, da die Signaturen für einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="9b558-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="9b558-115">Eine Signatur kann es sich um ein Token einbetten, die die einschließende Klasse oder eines Werttyps identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9b558-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="9b558-116">(Das Token ist ein Index in die lokale TypeDef-Tabelle).</span><span class="sxs-lookup"><span data-stu-id="9b558-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="9b558-117">Sie können keine Signatur zur Laufzeit im Kontext des aktuellen Bereichs und diese Signatur als Eingabe für `FindField`.</span><span class="sxs-lookup"><span data-stu-id="9b558-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 `FindField` <span data-ttu-id="9b558-118">Sucht nur die Felder, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbte Felder.</span><span class="sxs-lookup"><span data-stu-id="9b558-118">finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b558-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9b558-119">Requirements</span></span>  
 <span data-ttu-id="9b558-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b558-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b558-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9b558-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b558-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9b558-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="9b558-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="9b558-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9b558-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b558-124">See also</span></span>

- [<span data-ttu-id="9b558-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b558-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9b558-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b558-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
