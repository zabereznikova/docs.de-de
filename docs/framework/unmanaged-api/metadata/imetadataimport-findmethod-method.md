---
title: IMetaDataImport::FindMethod-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: 53b3d94e8b1e273fcbc041d25a5bf586a12735c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177249"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="b79d9-102">IMetaDataImport::FindMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="b79d9-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="b79d9-103">Ruft einen Zeiger auf das MethodDef-Token für die <xref:System.Type> Methode ab, die von der angegebenen Methode eingeschlossen wird und über den angegebenen Namen und die angegebene Metadatensignatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="b79d9-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b79d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b79d9-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b79d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b79d9-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="b79d9-106">[in] Das `mdTypeDef` Token für den Typ (eine Klasse oder Schnittstelle), das den zu suchenden Member einschließt.</span><span class="sxs-lookup"><span data-stu-id="b79d9-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="b79d9-107">Wenn dieser `mdTokenNil`Wert ist , wird die Suche für eine globale Funktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b79d9-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="b79d9-108">[in] Der Name der Methode, nach der gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="b79d9-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="b79d9-109">[in] Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="b79d9-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="b79d9-110">[in] Die Größe in `pvSigBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="b79d9-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="b79d9-111">[out] Ein Zeiger auf das übereinstimmende MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="b79d9-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b79d9-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b79d9-112">Remarks</span></span>  
 <span data-ttu-id="b79d9-113">Sie geben die Methode mit ihrer`td`einschließenden`szName`Klasse oder Schnittstelle (`pvSigBlob`), ihrem Namen ( ) und optional ihrer Signatur ( ) an.</span><span class="sxs-lookup"><span data-stu-id="b79d9-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="b79d9-114">Es können mehrere Methoden mit demselben Namen in einer Klasse oder Schnittstelle vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="b79d9-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="b79d9-115">Übergeben Sie in diesem Fall die Signatur der Methode, um die eindeutige Übereinstimmung zu finden.</span><span class="sxs-lookup"><span data-stu-id="b79d9-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="b79d9-116">Die übergebene `FindMethod` Signatur muss im aktuellen Bereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="b79d9-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="b79d9-117">Eine Signatur kann ein Token einbetten, das die einschließende Klasse oder den Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b79d9-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="b79d9-118">Das Token ist ein Index in der lokalen TypeDef-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b79d9-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="b79d9-119">Sie können keine Laufzeitsignatur außerhalb des Kontexts des aktuellen Bereichs erstellen `FindMethod`und diese Signatur als Eingabe für die Eingabe für verwenden.</span><span class="sxs-lookup"><span data-stu-id="b79d9-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="b79d9-120">`FindMethod`findet nur Methoden, die direkt in der Klasse oder Schnittstelle definiert wurden; Es werden keine geerbten Methoden gefunden.</span><span class="sxs-lookup"><span data-stu-id="b79d9-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b79d9-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b79d9-121">Requirements</span></span>  
 <span data-ttu-id="b79d9-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b79d9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b79d9-123">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b79d9-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b79d9-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b79d9-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b79d9-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b79d9-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b79d9-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b79d9-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="b79d9-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b79d9-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="b79d9-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b79d9-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
