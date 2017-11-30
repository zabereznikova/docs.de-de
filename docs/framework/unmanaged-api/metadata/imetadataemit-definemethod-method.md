---
title: IMetaDataEmit::DefineMethod-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethod
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: de55ee714dcba512befae3d2311a9880a08ba29f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="95e34-102">IMetaDataEmit::DefineMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="95e34-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="95e34-103">Erstellt eine Definition für eine Methode oder globalen Funktion mit der angegebenen Signatur und gibt ein Token für diese Methodendefinition zurück.</span><span class="sxs-lookup"><span data-stu-id="95e34-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e34-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95e34-104">Syntax</span></span>  
  
```  
HRESULT DefineMethod (      
    [in]  mdTypeDef         td,   
    [in]  LPCWSTR           szName,   
    [in]  DWORD             dwMethodFlags,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [in]  ULONG             ulCodeRVA,   
    [in]  DWORD             dwImplFlags,   
    [out] mdMethodDef      *pmd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95e34-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95e34-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="95e34-106">[in] Die `mdTypedef` der übergeordneten Klasse oder übergeordneten Schnittstelle der Methode.</span><span class="sxs-lookup"><span data-stu-id="95e34-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="95e34-107">Legen Sie `td` zu `mdTokenNil`, wenn Sie eine globale Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="95e34-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="95e34-108">[in] Der Elementname im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="95e34-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="95e34-109">[in] Der Wert der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) -Enumeration, die die Attribute der Methode oder globalen Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="95e34-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="95e34-110">[in] Die Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="95e34-110">[in] The method signature.</span></span> <span data-ttu-id="95e34-111">Die Signatur wird beibehalten, wie angegeben.</span><span class="sxs-lookup"><span data-stu-id="95e34-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="95e34-112">Wenn Sie zusätzliche Informationen für alle Parameter angeben müssen, verwenden Sie die [IMetaDataEmit:: SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="95e34-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="95e34-113">[in] Die Anzahl der Bytes im `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="95e34-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="95e34-114">[in] Die Adresse des Codes.</span><span class="sxs-lookup"><span data-stu-id="95e34-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="95e34-115">[in] Der Wert der [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) -Enumeration, die Features zur Implementierung der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="95e34-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="95e34-116">[out] Das Membertoken.</span><span class="sxs-lookup"><span data-stu-id="95e34-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95e34-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="95e34-117">Remarks</span></span>  
 <span data-ttu-id="95e34-118">Die Metadaten-API-Methoden in der gleichen Reihenfolge beizubehalten, wie der Aufrufer sie für eine bestimmte einschließende Klasse oder Schnittstelle, die im angegebenen ausgibt garantiert, dass die `td` Parameter.</span><span class="sxs-lookup"><span data-stu-id="95e34-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="95e34-119">Weitere Informationen zur Verwendung von `DefineMethod` und bestimmten parametereinstellungen unten angegebenen ist.</span><span class="sxs-lookup"><span data-stu-id="95e34-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="95e34-120">Slots in der V-Tabelle</span><span class="sxs-lookup"><span data-stu-id="95e34-120">Slots in the V-table</span></span>  
 <span data-ttu-id="95e34-121">Die Laufzeit verwendet Methodendefinitionen Funktionstabelle Slots einrichten.</span><span class="sxs-lookup"><span data-stu-id="95e34-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="95e34-122">Im Fall, in denen eine oder mehrere Slots übersprungen werden, z. B. müssen, hinsichtlich Parität mit einem COM-Schnittstellenlayout beibehalten eine dummy-Methode definiert, um den oder die Slots in der Funktionstabelle auszufüllen klicken. Festlegen der `dwMethodFlags` auf die `mdRTSpecialName` Wert der [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) Enumeration und geben Sie den Namen als:</span><span class="sxs-lookup"><span data-stu-id="95e34-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="95e34-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="95e34-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>  
  
 <span data-ttu-id="95e34-124">wobei *SequenceNumber* ist die Sequenznummer der Methode und *CountOfSlots* ist die Anzahl der Slots in der Funktionstabelle übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="95e34-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="95e34-125">Wenn *CountOfSlots* wird weggelassen, wird 1 ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="95e34-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="95e34-126">Dieser dummy-Methoden sind nicht aus verwaltetem oder nicht verwaltetem Code aufgerufen werden kann, und jeder Versuch, aus verwaltetem oder nicht verwalteten Code aufrufen, wird eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="95e34-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="95e34-127">Ihre einzige dient in vtable-Platz einnehmen, die die Laufzeit für die COM-Integration generiert.</span><span class="sxs-lookup"><span data-stu-id="95e34-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="95e34-128">Doppelte Methoden</span><span class="sxs-lookup"><span data-stu-id="95e34-128">Duplicate Methods</span></span>  
 <span data-ttu-id="95e34-129">Sie sollten keine doppelten Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="95e34-129">You should not define duplicate methods.</span></span> <span data-ttu-id="95e34-130">D. h., Sie sollten nicht aufrufen `DefineMethod` mit einem doppelten Satz von Werten in der `td`, `wzName`, und `pvSig` Parameter.</span><span class="sxs-lookup"><span data-stu-id="95e34-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="95e34-131">(Diese drei Parameter zusammen definieren Sie die Methode eindeutig.).</span><span class="sxs-lookup"><span data-stu-id="95e34-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="95e34-132">Sie können jedoch ein doppeltes Tripel verwenden, vorausgesetzt, dass für eine der Methodendefinitionen, Sie legen die `mdPrivateScope` bit in der `dwMethodFlags` Parameter.</span><span class="sxs-lookup"><span data-stu-id="95e34-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="95e34-133">(Die `mdPrivateScope` Bit bedeutet, dass der Compiler einen Verweis auf die Methodendefinition ausgegeben wird.)</span><span class="sxs-lookup"><span data-stu-id="95e34-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="95e34-134">Informationen zur Implementierung</span><span class="sxs-lookup"><span data-stu-id="95e34-134">Method Implementation Information</span></span>  
 <span data-ttu-id="95e34-135">Informationen über die Implementierung der Methode wird häufig nicht zu dem Zeitpunkt bezeichnet, in der die Methode deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="95e34-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="95e34-136">Aus diesem Grund, Sie müssen nicht übergeben von Werten in der `ulCodeRVA` und `dwImplFlags` Parameter beim Aufrufen von `DefineMethod`.</span><span class="sxs-lookup"><span data-stu-id="95e34-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="95e34-137">Die Werte können später durch angegeben [IMetaDataEmit:: SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) oder [SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)je nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="95e34-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="95e34-138">In einigen Situationen, z. B. Platform-Aufruf (PInvoke) oder COM-Interop-Szenarios, Methodentext wird nicht bereitgestellt werden, und `ulCodeRVA` sollte auf 0 (null) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="95e34-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="95e34-139">In diesen Situationen sollte die Methode nicht als abstrakt markiert werden, da die Laufzeit die Implementierung suchen.</span><span class="sxs-lookup"><span data-stu-id="95e34-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="95e34-140">Definieren eine Methode für PInvoke</span><span class="sxs-lookup"><span data-stu-id="95e34-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="95e34-141">Für jede nicht verwaltete Funktion, die über PInvoke aufgerufen wird müssen Sie eine verwaltete Methode definieren, die das, die nicht verwaltete Zielfunktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="95e34-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="95e34-142">Verwenden Sie zum Definieren der verwalteten Methode `DefineMethod` mit einigen der Parameter auf bestimmte Werte abhängig von der Anzeigemethode in der PInvoke verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="95e34-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
-   <span data-ttu-id="95e34-143">"True" PInvoke - schließt den Aufruf einer externen nicht verwaltete Methode, die in einer nicht verwalteten DLL befindet.</span><span class="sxs-lookup"><span data-stu-id="95e34-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
-   <span data-ttu-id="95e34-144">Lokale PInvoke - schließt den Aufruf einer systemeigenen, nicht verwaltete Methode, die in der aktuellen verwalteten Modul eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="95e34-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="95e34-145">Die parametereinstellungen, werden in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="95e34-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="95e34-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="95e34-146">Parameter</span></span>|<span data-ttu-id="95e34-147">Werte für "true" PInvoke</span><span class="sxs-lookup"><span data-stu-id="95e34-147">Values for true PInvoke</span></span>|<span data-ttu-id="95e34-148">Werte für lokale PInvoke</span><span class="sxs-lookup"><span data-stu-id="95e34-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="95e34-149">Legen Sie `mdStatic`; clear `mdSynchronized` und `mdAbstract`.</span><span class="sxs-lookup"><span data-stu-id="95e34-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="95e34-150">Gültige common Language Runtime (CLR) Signatur einer Methode mit Parametern, die gültig sind von verwalteten Typen.</span><span class="sxs-lookup"><span data-stu-id="95e34-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="95e34-151">Eine gültige CLR-Methodensignatur mit Parametern, die gültig sind von verwalteten Typen.</span><span class="sxs-lookup"><span data-stu-id="95e34-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="95e34-152">0</span><span class="sxs-lookup"><span data-stu-id="95e34-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="95e34-153">Legen Sie `miCil` und `miManaged`.</span><span class="sxs-lookup"><span data-stu-id="95e34-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="95e34-154">Legen Sie `miNative` und `miUnmanaged`.</span><span class="sxs-lookup"><span data-stu-id="95e34-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95e34-155">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95e34-155">Requirements</span></span>  
 <span data-ttu-id="95e34-156">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95e34-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e34-157">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="95e34-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95e34-158">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="95e34-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95e34-159">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e34-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e34-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95e34-160">See Also</span></span>  
 [<span data-ttu-id="95e34-161">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95e34-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="95e34-162">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95e34-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
