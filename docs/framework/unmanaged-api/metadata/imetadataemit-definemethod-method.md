---
title: IMetaDataEmit::DefineMethod-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethod
helpviewer_keywords:
- DefineMethod method [.NET Framework metadata]
- IMetaDataEmit::DefineMethod method [.NET Framework metadata]
ms.assetid: 3e2102c5-48b7-4c0e-b805-7e2b5e156e3d
topic_type:
- apiref
ms.openlocfilehash: d4f3c95428d6f0f8807e284c5b54582428176511
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177668"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="6643e-102">IMetaDataEmit::DefineMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="6643e-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="6643e-103">Erstellt eine Definition für eine Methode oder globale Funktion mit der angegebenen Signatur und gibt ein Token an diese Methodendefinition zurück.</span><span class="sxs-lookup"><span data-stu-id="6643e-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6643e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6643e-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="6643e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6643e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6643e-106">[in] Das `mdTypedef` Token der übergeordneten Klasse oder übergeordneten Schnittstelle der Methode.</span><span class="sxs-lookup"><span data-stu-id="6643e-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="6643e-107">Legen Sie fest, `td` dass , wenn Sie eine globale Funktion definieren. `mdTokenNil`</span><span class="sxs-lookup"><span data-stu-id="6643e-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="6643e-108">[in] Der Membername in Unicode.</span><span class="sxs-lookup"><span data-stu-id="6643e-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="6643e-109">[in] Ein Wert der [CorMethodAttr-Enumeration,](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) der die Attribute der Methode oder globalen Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="6643e-109">[in] A value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="6643e-110">[in] Die Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="6643e-110">[in] The method signature.</span></span> <span data-ttu-id="6643e-111">Die Signatur wird wie angegeben beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6643e-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="6643e-112">Wenn Sie zusätzliche Informationen für Parameter angeben müssen, verwenden Sie die [IMetaDataEmit::SetParamProps-Methode.](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)</span><span class="sxs-lookup"><span data-stu-id="6643e-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="6643e-113">[in] Die Anzahl der `pvSigBlob`Bytes in .</span><span class="sxs-lookup"><span data-stu-id="6643e-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="6643e-114">[in] Die Adresse des Codes.</span><span class="sxs-lookup"><span data-stu-id="6643e-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="6643e-115">[in] Ein Wert der [CorMethodImpl-Enumeration,](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) der die Implementierungsfeatures der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="6643e-115">[in] A value of the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="6643e-116">[out] Das Membertoken.</span><span class="sxs-lookup"><span data-stu-id="6643e-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6643e-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6643e-117">Remarks</span></span>  
 <span data-ttu-id="6643e-118">Die Metadaten-API garantiert, dass Methoden in der gleichen Reihenfolge beibehalten werden, in der der Aufrufer sie für eine bestimmte einschließende Klasse oder Schnittstelle ausgibt, die im `td` Parameter angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="6643e-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="6643e-119">Weitere Informationen zur `DefineMethod` Verwendung und zu bestimmten Parametereinstellungen finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="6643e-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="6643e-120">Slots im V-Tisch</span><span class="sxs-lookup"><span data-stu-id="6643e-120">Slots in the V-table</span></span>  
 <span data-ttu-id="6643e-121">Die Laufzeit verwendet Methodendefinitionen, um v-Table-Slots einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6643e-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="6643e-122">In dem Fall, in dem ein oder mehrere Steckplätze übersprungen werden müssen, z. B. um die Parität mit einem COM-Schnittstellenlayout beizubehalten, wird eine Dummy-Methode definiert, um den Oder die Steckplätze in der v-Tabelle aufzunehmen. legen `dwMethodFlags` Sie `mdRTSpecialName` den Wert der [CorMethodAttr-Enumeration](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) fest, und geben Sie den Namen wie folgend:</span><span class="sxs-lookup"><span data-stu-id="6643e-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="6643e-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="6643e-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="6643e-124">wobei *SequenceNumber* die Sequenznummer der Methode und *CountOfSlots* die Anzahl der Steckplätze ist, die in der v-Tabelle übersprungen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6643e-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="6643e-125">Wenn *CountOfSlots* weggelassen wird, wird 1 angenommen.</span><span class="sxs-lookup"><span data-stu-id="6643e-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="6643e-126">Diese Dummy-Methoden können weder aus verwaltetem noch aus nicht verwaltetem Code aufrufen, und jeder Versuch, sie aufzurufen, entweder aus verwaltetem oder nicht verwaltetem Code, generiert eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="6643e-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="6643e-127">Ihr einziger Zweck besteht darin, Platz in der v-Tabelle einzunehmen, die die Laufzeit für die COM-Integration generiert.</span><span class="sxs-lookup"><span data-stu-id="6643e-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="6643e-128">Doppelte Methoden</span><span class="sxs-lookup"><span data-stu-id="6643e-128">Duplicate Methods</span></span>  
 <span data-ttu-id="6643e-129">Sie sollten keine doppelten Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="6643e-129">You should not define duplicate methods.</span></span> <span data-ttu-id="6643e-130">Das heißt, Sie `DefineMethod` sollten nicht mit einem `td`doppelten `wzName`Satz `pvSig` von Werten in , und Parameteraufrufen aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6643e-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="6643e-131">(Diese drei Parameter zusammen definieren die Methode eindeutig.).</span><span class="sxs-lookup"><span data-stu-id="6643e-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="6643e-132">Sie können jedoch ein doppeltes Triple verwenden, vorausgesetzt, dass Sie `mdPrivateScope` für `dwMethodFlags` eine der Methodendefinitionen das Bit im Parameter festlegen.</span><span class="sxs-lookup"><span data-stu-id="6643e-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="6643e-133">(Das `mdPrivateScope` Bit bedeutet, dass der Compiler keinen Verweis auf diese Methodendefinition ausgibt.)</span><span class="sxs-lookup"><span data-stu-id="6643e-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="6643e-134">Informationen zur Methodenimplementierung</span><span class="sxs-lookup"><span data-stu-id="6643e-134">Method Implementation Information</span></span>  
 <span data-ttu-id="6643e-135">Informationen über die Methodenimplementierung sind zum Zeitpunkt der Dekandieren der Methode oft nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="6643e-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="6643e-136">Daher müssen Sie beim Aufrufen keine `ulCodeRVA` `dwImplFlags` Werte in `DefineMethod`der und Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="6643e-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="6643e-137">Die Werte können später über [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) oder [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6643e-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="6643e-138">In einigen Situationen, z. B. Plattformaufruf (PInvoke) oder COM-Interop-Szenarien, wird der Methodentext nicht bereitgestellt und `ulCodeRVA` sollte auf Null gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="6643e-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="6643e-139">In diesen Situationen sollte die Methode nicht als abstrakt markiert werden, da die Laufzeit die Implementierung findet.</span><span class="sxs-lookup"><span data-stu-id="6643e-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="6643e-140">Definieren einer Methode für PInvoke</span><span class="sxs-lookup"><span data-stu-id="6643e-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="6643e-141">Für jede nicht verwaltete Funktion, die über PInvoke aufgerufen werden soll, müssen Sie eine verwaltete Methode definieren, die die nicht verwaltete Zielfunktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="6643e-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="6643e-142">Um die verwaltete `DefineMethod` Methode zu definieren, verwenden Sie einige der Parameter, die auf bestimmte Werte festgelegt sind, abhängig von der Art und Weise, in der PInvoke verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="6643e-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="6643e-143">True PInvoke - beinhaltet den Aufruf einer externen nicht verwalteten Methode, die sich in einer nicht verwalteten DLL befindet.</span><span class="sxs-lookup"><span data-stu-id="6643e-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="6643e-144">Lokaler PInvoke - umfasst den Aufruf einer systemeigenen nicht verwalteten Methode, die in das aktuelle verwaltete Modul eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="6643e-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="6643e-145">Die Parametereinstellungen sind in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="6643e-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="6643e-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="6643e-146">Parameter</span></span>|<span data-ttu-id="6643e-147">Werte für true PInvoke</span><span class="sxs-lookup"><span data-stu-id="6643e-147">Values for true PInvoke</span></span>|<span data-ttu-id="6643e-148">Werte für lokale PInvoke</span><span class="sxs-lookup"><span data-stu-id="6643e-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="6643e-149">Set `mdStatic`; klar `mdSynchronized` `mdAbstract`und .</span><span class="sxs-lookup"><span data-stu-id="6643e-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="6643e-150">Eine gültige CLR-Methodensignatur (Common Language Runtime) mit Parametern, die gültige verwaltete Typen sind.</span><span class="sxs-lookup"><span data-stu-id="6643e-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="6643e-151">Eine gültige CLR-Methodensignatur mit Parametern, die gültige verwaltete Typen sind.</span><span class="sxs-lookup"><span data-stu-id="6643e-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="6643e-152">0</span><span class="sxs-lookup"><span data-stu-id="6643e-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="6643e-153">Legen Sie `miCil` und `miManaged` fest.</span><span class="sxs-lookup"><span data-stu-id="6643e-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="6643e-154">Legen Sie `miNative` und `miUnmanaged` fest.</span><span class="sxs-lookup"><span data-stu-id="6643e-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6643e-155">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6643e-155">Requirements</span></span>  
 <span data-ttu-id="6643e-156">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6643e-156">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6643e-157">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6643e-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6643e-158">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6643e-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6643e-159">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6643e-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6643e-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6643e-160">See also</span></span>

- [<span data-ttu-id="6643e-161">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6643e-161">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6643e-162">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6643e-162">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
