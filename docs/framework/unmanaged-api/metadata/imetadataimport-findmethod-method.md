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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b68d4e3d51fdb50290319de804a78c1a78a07a4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447387"
---
# <a name="imetadataimportfindmethod-method"></a><span data-ttu-id="e7654-102">IMetaDataImport::FindMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="e7654-102">IMetaDataImport::FindMethod Method</span></span>
<span data-ttu-id="e7654-103">Ruft einen Zeiger auf das MethodDef token für die Methode, die eingeschlossen ist durch das angegebene <xref:System.Type> und den angegebenen Namen und Metadaten aufweist.</span><span class="sxs-lookup"><span data-stu-id="e7654-103">Gets a pointer to the MethodDef token for the method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7654-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7654-104">Syntax</span></span>  
  
```  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,   
   [in]  PCCOR_SIGNATURE    pvSigBlob,   
   [in]  ULONG              cbSigBlob,   
   [out] mdMethodDef        *pmb  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7654-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7654-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e7654-106">[in] Die `mdTypeDef` token für den Typ (eine Klasse oder Schnittstelle), das der gesuchten Member enthält.</span><span class="sxs-lookup"><span data-stu-id="e7654-106">[in] The `mdTypeDef` token for the type (a class or interface) that encloses the member to search for.</span></span> <span data-ttu-id="e7654-107">Wenn dieser Wert ist `mdTokenNil`, und klicken Sie dann die Suche für eine globale Funktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7654-107">If this value is `mdTokenNil`, then the lookup is done for a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="e7654-108">[in] Der Name der zu suchenden Methode.</span><span class="sxs-lookup"><span data-stu-id="e7654-108">[in] The name of the method to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e7654-109">[in] Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="e7654-109">[in] A pointer to the binary metadata signature of the method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="e7654-110">[in] Die Größe in Bytes des `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="e7654-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="e7654-111">[out] Ein Zeiger auf das übereinstimmende MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="e7654-111">[out] A pointer to the matching MethodDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7654-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7654-112">Remarks</span></span>  
 <span data-ttu-id="e7654-113">Geben Sie die Methode, die mit der einschließenden Klasse oder Schnittstelle (`td`), seinen Namen (`szName`), und optional die Signatur (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="e7654-113">You specify the method using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="e7654-114">Es gibt möglicherweise mehrere Methoden mit demselben Namen in einer Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="e7654-114">There might be multiple methods with the same name in a class or interface.</span></span> <span data-ttu-id="e7654-115">Übergeben Sie in diesem Fall die Methodensignatur, um die eindeutige Übereinstimmung zu finden.</span><span class="sxs-lookup"><span data-stu-id="e7654-115">In that case, pass the method's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="e7654-116">Die Signatur zu übergeben, um `FindMethod` muss wurden im aktuellen Bereich generiert wurde, da Signaturen an einen bestimmten Bereich gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="e7654-116">The signature passed to `FindMethod` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="e7654-117">Eine Signatur kann ein Token einbetten, die die einschließende Klasse oder der angegebene Werttyp identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e7654-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="e7654-118">Das Token ist ein Index in die lokale TypeDef-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e7654-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="e7654-119">Sie erstellen eine Laufzeit-Signatur im Kontext des aktuellen Gültigkeitsbereichs und verwenden Sie diese Signatur als Eingabe können nicht `FindMethod`.</span><span class="sxs-lookup"><span data-stu-id="e7654-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMethod`.</span></span>  
  
 <span data-ttu-id="e7654-120">`FindMethod` Sucht nur Methoden, die direkt in der Klasse oder Schnittstelle definiert wurden. Es findet keine geerbte Methoden.</span><span class="sxs-lookup"><span data-stu-id="e7654-120">`FindMethod` finds only methods that were defined directly in the class or interface; it does not find inherited methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7654-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7654-121">Requirements</span></span>  
 <span data-ttu-id="e7654-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7654-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7654-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e7654-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e7654-124">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e7654-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e7654-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7654-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7654-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7654-126">See Also</span></span>  
 <xref:System.Reflection.MethodInfo>  
 [<span data-ttu-id="e7654-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7654-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e7654-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7654-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
