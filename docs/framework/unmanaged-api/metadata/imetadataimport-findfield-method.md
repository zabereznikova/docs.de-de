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
ms.openlocfilehash: 842d6c0deb90bc45cb59454fb30fcc3544d742f1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437949"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="28505-102">IMetaDataImport::FindField-Methode</span><span class="sxs-lookup"><span data-stu-id="28505-102">IMetaDataImport::FindField Method</span></span>
<span data-ttu-id="28505-103">Ruft einen Zeiger auf das FieldDef-Token für das Feld ab, das durch die angegebene <xref:System.Type> eingeschlossen ist und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="28505-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28505-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28505-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="28505-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="28505-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="28505-106">in Das TypeDef-Token für die Klasse oder Schnittstelle, die das Feld einschließt, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="28505-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="28505-107">Wenn dieser Wert `mdTokenNil`ist, wird die Suche für eine globale Variable durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="28505-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="28505-108">in Der Name des Felds, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="28505-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="28505-109">in Ein Zeiger auf die binäre Metadatensignatur des Felds.</span><span class="sxs-lookup"><span data-stu-id="28505-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="28505-110">in Die Größe `pvSigBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="28505-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="28505-111">vorgenommen Ein Zeiger auf das übereinstimmende FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="28505-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28505-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="28505-112">Remarks</span></span>  
 <span data-ttu-id="28505-113">Sie geben das Feld mit der einschließenden Klasse oder Schnittstelle (`td`), dem Namen (`szName`) und optional der Signatur (`pvSigBlob`) an.</span><span class="sxs-lookup"><span data-stu-id="28505-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="28505-114">Die an `FindField` über gegebene Signatur muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="28505-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="28505-115">Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="28505-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="28505-116">(Das Token ist ein Index in der lokalen Tabelle "Typedef").</span><span class="sxs-lookup"><span data-stu-id="28505-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="28505-117">Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Bereichs erstellen und diese Signatur als Eingabe für `FindField`verwenden.</span><span class="sxs-lookup"><span data-stu-id="28505-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="28505-118">`FindField` findet nur Felder, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Felder werden nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="28505-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28505-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="28505-119">Requirements</span></span>  
 <span data-ttu-id="28505-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28505-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28505-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="28505-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="28505-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="28505-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="28505-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="28505-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28505-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28505-124">See also</span></span>

- [<span data-ttu-id="28505-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28505-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="28505-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="28505-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
