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
ms.openlocfilehash: 9b42f0f7c8e2878ee3ec140344f51517a24247c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729862"
---
# <a name="imetadataimportfindfield-method"></a><span data-ttu-id="edaaf-102">IMetaDataImport::FindField-Methode</span><span class="sxs-lookup"><span data-stu-id="edaaf-102">IMetaDataImport::FindField Method</span></span>

<span data-ttu-id="edaaf-103">Ruft einen Zeiger auf das FieldDef-Token für das Feld ab, das durch den angegebenen eingeschlossen ist <xref:System.Type> und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="edaaf-103">Gets a pointer to the FieldDef token for the field that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edaaf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="edaaf-104">Syntax</span></span>  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="edaaf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="edaaf-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="edaaf-106">in Das TypeDef-Token für die Klasse oder Schnittstelle, die das Feld einschließt, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="edaaf-106">[in] The TypeDef token for the class or interface that encloses the field to search for.</span></span> <span data-ttu-id="edaaf-107">Wenn dieser Wert ist `mdTokenNil` , wird die Suche für eine globale Variable durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="edaaf-107">If this value is `mdTokenNil`, the lookup is done for a global variable.</span></span>  
  
 `szName`  
 <span data-ttu-id="edaaf-108">in Der Name des Felds, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="edaaf-108">[in] The name of the field to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="edaaf-109">in Ein Zeiger auf die binäre Metadatensignatur des Felds.</span><span class="sxs-lookup"><span data-stu-id="edaaf-109">[in] A pointer to the binary metadata signature of the field.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="edaaf-110">in Die Größe von in Bytes `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="edaaf-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="edaaf-111">vorgenommen Ein Zeiger auf das übereinstimmende FieldDef-Token.</span><span class="sxs-lookup"><span data-stu-id="edaaf-111">[out] A pointer to the matching FieldDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="edaaf-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="edaaf-112">Remarks</span></span>  

 <span data-ttu-id="edaaf-113">Sie geben das Feld mit der einschließenden Klasse oder Schnittstelle ( `td` ), dem Namen ( `szName` ) und optional der Signatur ( `pvSigBlob` ) an.</span><span class="sxs-lookup"><span data-stu-id="edaaf-113">You specify the field using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span>  
  
 <span data-ttu-id="edaaf-114">Die an über gegebene Signatur `FindField` muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="edaaf-114">The signature passed to `FindField` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="edaaf-115">Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="edaaf-115">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="edaaf-116">(Das Token ist ein Index in der lokalen Tabelle "Typedef").</span><span class="sxs-lookup"><span data-stu-id="edaaf-116">(The token is an index into the local TypeDef table).</span></span> <span data-ttu-id="edaaf-117">Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Bereichs erstellen und diese Signatur als Eingabe für verwenden `FindField` .</span><span class="sxs-lookup"><span data-stu-id="edaaf-117">You cannot build a run-time signature outside the context of the current scope and use that signature as input to `FindField`.</span></span>  
  
 <span data-ttu-id="edaaf-118">`FindField` sucht nur Felder, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Felder werden nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="edaaf-118">`FindField` finds only fields that were defined directly in the class or interface; it does not find inherited fields.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edaaf-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="edaaf-119">Requirements</span></span>  

 <span data-ttu-id="edaaf-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edaaf-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edaaf-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="edaaf-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="edaaf-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="edaaf-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="edaaf-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edaaf-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edaaf-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="edaaf-124">See also</span></span>

- [<span data-ttu-id="edaaf-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edaaf-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="edaaf-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="edaaf-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
