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
ms.openlocfilehash: 470b6511366cef1680eaf97f9ab376736add55c4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437896"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="d8fc6-102">IMetaDataImport::FindMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="d8fc6-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="d8fc6-103">Ruft einen Zeiger auf das MethodDef-Token für die Methode ab, die durch den angegebenen <xref:System.Type> und den angegebenen Namen und die angegebene Metadatensignatur eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8fc6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8fc6-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8fc6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d8fc6-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d8fc6-106">in Das `mdTypeDef` Token für den Typ (eine Klasse oder Schnittstelle), der den Member einschließt, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="d8fc6-107">Wenn dieser Wert `mdTokenNil`ist, wird die Suche für eine globale Funktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="d8fc6-108">in Der Name der Methode, nach der gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d8fc6-109">in Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="d8fc6-110">in Die Größe `pvSigBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="d8fc6-111">vorgenommen Ein Zeiger auf das übereinstimmende MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8fc6-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8fc6-112">Remarks</span></span>  
 <span data-ttu-id="d8fc6-113">Sie geben die Methode mithilfe der einschließenden Klasse oder Schnittstelle (`td`), des Namens (`szName`) und optional der Signatur (`pvSigBlob`) an.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="d8fc6-114">Möglicherweise gibt es mehrere Methoden mit dem gleichen Namen in einer Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="d8fc6-115">Übergeben Sie in diesem Fall die Signatur der Methode, um die eindeutige Entsprechung zu finden.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="d8fc6-116">Die an `FindMethod` über gegebene Signatur muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="d8fc6-117">Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="d8fc6-118">Das Token ist ein Index in der lokalen Tabelle "Typedef".</span><span class="sxs-lookup"><span data-stu-id="d8fc6-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="d8fc6-119">Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Bereichs erstellen und diese Signatur als Eingabe für die Eingabe in `FindMethod`verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="d8fc6-120">`FindMethod` findet nur Methoden, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Methoden werden nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="d8fc6-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8fc6-121">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d8fc6-121">Requirements</span></span>  
 <span data-ttu-id="d8fc6-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8fc6-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8fc6-123">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d8fc6-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d8fc6-124">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d8fc6-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d8fc6-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8fc6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8fc6-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8fc6-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="d8fc6-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8fc6-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d8fc6-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d8fc6-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
