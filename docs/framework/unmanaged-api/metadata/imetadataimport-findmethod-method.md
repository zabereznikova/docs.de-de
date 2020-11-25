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
ms.openlocfilehash: 111e42a6d8f413c616779bc44e0722ab38781588
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711337"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="82faa-102">IMetaDataImport::FindMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="82faa-102">IMetaDataImport::FindMethod Method</span></span>

<span data-ttu-id="82faa-103">Ruft einen Zeiger auf das MethodDef-Token für die Methode ab, die durch den angegebenen eingeschlossen ist <xref:System.Type> und den angegebenen Namen und die angegebene Metadatensignatur aufweist.</span><span class="sxs-lookup"><span data-stu-id="82faa-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82faa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="82faa-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82faa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="82faa-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="82faa-106">in Das `mdTypeDef` Token für den Typ (eine Klasse oder Schnittstelle), der den Member einschließt, nach dem gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="82faa-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="82faa-107">Wenn dieser Wert ist `mdTokenNil` , wird die Suche für eine globale Funktion durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="82faa-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="82faa-108">in Der Name der Methode, nach der gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="82faa-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="82faa-109">in Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="82faa-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="82faa-110">in Die Größe von in Bytes `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="82faa-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="82faa-111">vorgenommen Ein Zeiger auf das übereinstimmende MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="82faa-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82faa-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="82faa-112">Remarks</span></span>  

 <span data-ttu-id="82faa-113">Sie geben die Methode mithilfe der einschließenden Klasse oder Schnittstelle ( `td` ), des Namens ( `szName` ) und optional der Signatur ( `pvSigBlob` ) an.</span><span class="sxs-lookup"><span data-stu-id="82faa-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="82faa-114">Möglicherweise gibt es mehrere Methoden mit dem gleichen Namen in einer Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="82faa-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="82faa-115">Übergeben Sie in diesem Fall die Signatur der Methode, um die eindeutige Entsprechung zu finden.</span><span class="sxs-lookup"><span data-stu-id="82faa-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="82faa-116">Die an über gegebene Signatur `FindMethod` muss im aktuellen Gültigkeitsbereich generiert worden sein, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="82faa-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="82faa-117">Eine Signatur kann ein Token einbetten, das den einschließenden Klassen-oder Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="82faa-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="82faa-118">Das Token ist ein Index in der lokalen Tabelle "Typedef".</span><span class="sxs-lookup"><span data-stu-id="82faa-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="82faa-119">Sie können keine Lauf Zeit Signatur außerhalb des Kontexts des aktuellen Gültigkeits Bereichs erstellen und diese Signatur als Eingabe für die Eingabe verwenden `FindMethod` .</span><span class="sxs-lookup"><span data-stu-id="82faa-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="82faa-120">`FindMethod` sucht nur Methoden, die direkt in der Klasse oder Schnittstelle definiert wurden. geerbte Methoden werden nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="82faa-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82faa-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="82faa-121">Requirements</span></span>  

 <span data-ttu-id="82faa-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82faa-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82faa-123">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="82faa-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82faa-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="82faa-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82faa-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82faa-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82faa-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="82faa-126">See also</span></span>

- <xref:System.Reflection.MethodInfo>
- [<span data-ttu-id="82faa-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82faa-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="82faa-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82faa-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
