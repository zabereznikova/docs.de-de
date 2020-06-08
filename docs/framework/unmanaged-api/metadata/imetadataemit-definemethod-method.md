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
ms.openlocfilehash: fbf6ce8c8c9628b08872058a794fb0e005764ab1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501299"
---
# <a name="imetadataemitdefinemethod-method"></a><span data-ttu-id="01d3d-102">IMetaDataEmit::DefineMethod-Methode</span><span class="sxs-lookup"><span data-stu-id="01d3d-102">IMetaDataEmit::DefineMethod Method</span></span>
<span data-ttu-id="01d3d-103">Erstellt eine Definition für eine Methode oder eine globale Funktion mit der angegebenen Signatur und gibt ein Token an diese Methoden Definition zurück.</span><span class="sxs-lookup"><span data-stu-id="01d3d-103">Creates a definition for a method or global function with the specified signature, and returns a token to that method definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01d3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="01d3d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="01d3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="01d3d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="01d3d-106">in Das `mdTypedef` Token der übergeordneten Klasse oder übergeordneten Schnittstelle der Methode.</span><span class="sxs-lookup"><span data-stu-id="01d3d-106">[in] The `mdTypedef` token of the parent class or parent interface of the method.</span></span> <span data-ttu-id="01d3d-107">Legen `td` Sie auf fest `mdTokenNil` , wenn Sie eine globale Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="01d3d-107">Set `td` to `mdTokenNil`, if you are defining a global function.</span></span>  
  
 `szName`  
 <span data-ttu-id="01d3d-108">in Der Elementname in Unicode.</span><span class="sxs-lookup"><span data-stu-id="01d3d-108">[in] The member name in Unicode.</span></span>  
  
 `dwMethodFlags`  
 <span data-ttu-id="01d3d-109">in Ein Wert der [CorMethodAttr](cormethodattr-enumeration.md) -Enumeration, der die Attribute der Methode oder globalen Funktion angibt.</span><span class="sxs-lookup"><span data-stu-id="01d3d-109">[in] A value of the [CorMethodAttr](cormethodattr-enumeration.md) enumeration that specifies the attributes of the method or global function.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="01d3d-110">in Die Methoden Signatur.</span><span class="sxs-lookup"><span data-stu-id="01d3d-110">[in] The method signature.</span></span> <span data-ttu-id="01d3d-111">Die Signatur wird wie angegeben beibehalten.</span><span class="sxs-lookup"><span data-stu-id="01d3d-111">The signature is persisted as supplied.</span></span> <span data-ttu-id="01d3d-112">Wenn Sie zusätzliche Informationen für Parameter angeben müssen, verwenden Sie die [IMetaDataEmit:: setparamrequismethode](imetadataemit-setparamprops-method.md) .</span><span class="sxs-lookup"><span data-stu-id="01d3d-112">If you need to specify additional information for any parameters, use the [IMetaDataEmit::SetParamProps](imetadataemit-setparamprops-method.md) method.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="01d3d-113">in Die Anzahl von Bytes in `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="01d3d-113">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `ulCodeRVA`  
 <span data-ttu-id="01d3d-114">in Die Adresse des Codes.</span><span class="sxs-lookup"><span data-stu-id="01d3d-114">[in] The address of the code.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="01d3d-115">in Ein Wert der [CorMethodImpl](cormethodimpl-enumeration.md) -Enumeration, der die Implementierungs Funktionen der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="01d3d-115">[in] A value of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the implementation features of the method.</span></span>  
  
 `pmd`  
 <span data-ttu-id="01d3d-116">vorgenommen Das Member-Token.</span><span class="sxs-lookup"><span data-stu-id="01d3d-116">[out] The member token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01d3d-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="01d3d-117">Remarks</span></span>  
 <span data-ttu-id="01d3d-118">Die metadatenapi garantiert, dass Methoden in derselben Reihenfolge wie der Aufrufer für eine bestimmte einschließende Klasse oder Schnittstelle, die im-Parameter angegeben ist, beibehalten wird `td` .</span><span class="sxs-lookup"><span data-stu-id="01d3d-118">The metadata API guarantees to persist methods in the same order as the caller emits them for a given enclosing class or interface, which is specified in the `td` parameter.</span></span>  
  
 <span data-ttu-id="01d3d-119">Weitere Informationen zur Verwendung von `DefineMethod` und bestimmten Parametereinstellungen finden Sie unten.</span><span class="sxs-lookup"><span data-stu-id="01d3d-119">Additional information regarding the use of `DefineMethod` and particular parameter settings is given below.</span></span>  
  
## <a name="slots-in-the-v-table"></a><span data-ttu-id="01d3d-120">Slots in der V-Tabelle</span><span class="sxs-lookup"><span data-stu-id="01d3d-120">Slots in the V-table</span></span>  
 <span data-ttu-id="01d3d-121">Die Laufzeit verwendet Methoden Definitionen zum Einrichten von v-Table-Slots.</span><span class="sxs-lookup"><span data-stu-id="01d3d-121">The runtime uses method definitions to set up v-table slots.</span></span> <span data-ttu-id="01d3d-122">Wenn ein oder mehrere Slots übersprungen werden müssen, z. b. um die Parität mit einem COM-Schnittstellen Layout beizubehalten, wird eine Pseudo Methode definiert, um den Slot oder die Einschub Fächer in der v-Tabelle zu nehmen. legen `dwMethodFlags` Sie auf den `mdRTSpecialName` Wert der [CorMethodAttr](cormethodattr-enumeration.md) -Enumeration fest, und geben Sie den Namen wie folgt an:</span><span class="sxs-lookup"><span data-stu-id="01d3d-122">In the case where one or more slots need to be skipped, such as to preserve parity with a COM interface layout, a dummy method is defined to take up the slot or slots in the v-table; set the `dwMethodFlags` to the `mdRTSpecialName` value of the [CorMethodAttr](cormethodattr-enumeration.md) enumeration and specify the name as:</span></span>  
  
 <span data-ttu-id="01d3d-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span><span class="sxs-lookup"><span data-stu-id="01d3d-123">_VtblGap\<*SequenceNumber*>\<\_*CountOfSlots*></span></span>
  
 <span data-ttu-id="01d3d-124">Dabei ist " *sequencenenumber* " die Sequenznummer der Methode, und " *zählslots* " ist die Anzahl der Slots, die in der v-Tabelle ausgelassen werden.</span><span class="sxs-lookup"><span data-stu-id="01d3d-124">where *SequenceNumber* is the sequence number of the method and *CountOfSlots* is the number of slots to skip in the v-table.</span></span> <span data-ttu-id="01d3d-125">Wenn " *zählslots* " weggelassen wird, wird 1 angenommen.</span><span class="sxs-lookup"><span data-stu-id="01d3d-125">If *CountOfSlots* is omitted, 1 is assumed.</span></span> <span data-ttu-id="01d3d-126">Diese Dummy-Methoden können nicht aus verwaltetem oder nicht verwaltetem Code aufgerufen werden, und jeder Versuch, Sie aus verwaltetem oder nicht verwaltetem Code aufzurufen, generiert eine Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="01d3d-126">These dummy methods are not callable from either managed or unmanaged code and any attempt to call them, from either managed or unmanaged code, generates an exception.</span></span> <span data-ttu-id="01d3d-127">Der einzige Zweck besteht darin, in der v-Tabelle, die die Common Language Runtime für die com-Integration generiert, Speicherplatz zu belegen.</span><span class="sxs-lookup"><span data-stu-id="01d3d-127">Their only purpose is to take up space in the v-table that the runtime generates for COM integration.</span></span>  
  
## <a name="duplicate-methods"></a><span data-ttu-id="01d3d-128">Doppelte Methoden</span><span class="sxs-lookup"><span data-stu-id="01d3d-128">Duplicate Methods</span></span>  
 <span data-ttu-id="01d3d-129">Sie sollten keine doppelten Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="01d3d-129">You should not define duplicate methods.</span></span> <span data-ttu-id="01d3d-130">Das heißt, Sie sollten nicht `DefineMethod` mit einem doppelten Satz von Werten in den `td` `wzName` Parametern, und Abrufen `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="01d3d-130">That is, you should not call `DefineMethod` with a duplicate set of values in the `td`, `wzName`, and `pvSig` parameters.</span></span> <span data-ttu-id="01d3d-131">(Mit diesen drei Parametern wird die Methode eindeutig definiert.)</span><span class="sxs-lookup"><span data-stu-id="01d3d-131">(These three parameters together uniquely define the method.).</span></span> <span data-ttu-id="01d3d-132">Sie können jedoch ein doppeltes Triple verwenden, vorausgesetzt, dass Sie für eine der Methoden Definitionen das `mdPrivateScope` Bit im-Parameter festlegen `dwMethodFlags` .</span><span class="sxs-lookup"><span data-stu-id="01d3d-132">However, you can use a duplicate triple provided that, for one of the method definitions, you set the `mdPrivateScope` bit in the `dwMethodFlags` parameter.</span></span> <span data-ttu-id="01d3d-133">(Das `mdPrivateScope` Bit bedeutet, dass der Compiler keinen Verweis auf diese Methoden Definition ausgibt.)</span><span class="sxs-lookup"><span data-stu-id="01d3d-133">(The `mdPrivateScope` bit means that the compiler will not emit a reference to this method definition.)</span></span>  
  
## <a name="method-implementation-information"></a><span data-ttu-id="01d3d-134">Methoden Implementierungs Informationen</span><span class="sxs-lookup"><span data-stu-id="01d3d-134">Method Implementation Information</span></span>  
 <span data-ttu-id="01d3d-135">Informationen zur Methoden Implementierung sind häufig nicht bekannt, wenn die-Methode deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="01d3d-135">Information about the method implementation is often not known at the time the method is declared.</span></span> <span data-ttu-id="01d3d-136">Daher müssen Sie beim Aufrufen von keine Werte im `ulCodeRVA` -Parameter und im- `dwImplFlags` Parameter übergeben `DefineMethod` .</span><span class="sxs-lookup"><span data-stu-id="01d3d-136">Therefore, you do not need to pass values in the `ulCodeRVA` and `dwImplFlags` parameters when calling `DefineMethod`.</span></span> <span data-ttu-id="01d3d-137">Die Werte können später über [IMetaDataEmit:: SetMethodImplFlags](imetadataemit-setmethodimplflags-method.md) oder [IMetaDataEmit:: SetRVA](imetadataemit-setrva-method.md)bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="01d3d-137">The values can be supplied later through [IMetaDataEmit::SetMethodImplFlags](imetadataemit-setmethodimplflags-method.md) or [IMetaDataEmit::SetRVA](imetadataemit-setrva-method.md), as appropriate.</span></span>  
  
 <span data-ttu-id="01d3d-138">In einigen Situationen, z. b. PInvoke-oder COM-Interop-Szenarien, wird der Methoden Text nicht bereitgestellt und `ulCodeRVA` sollte auf 0 (null) festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="01d3d-138">In some situations, such as platform invocation (PInvoke) or COM interop scenarios, the method body will not be supplied, and `ulCodeRVA` should be set to zero.</span></span> <span data-ttu-id="01d3d-139">In diesen Fällen sollte die-Methode nicht als abstrakt gekennzeichnet werden, da die-Laufzeit die-Implementierung findet.</span><span class="sxs-lookup"><span data-stu-id="01d3d-139">In these situations, the method should not be tagged as abstract, because the runtime will locate the implementation.</span></span>  
  
## <a name="defining-a-method-for-pinvoke"></a><span data-ttu-id="01d3d-140">Definieren einer Methode für PInvoke</span><span class="sxs-lookup"><span data-stu-id="01d3d-140">Defining a Method for PInvoke</span></span>  
 <span data-ttu-id="01d3d-141">Für jede nicht verwaltete Funktion, die über PInvoke aufgerufen werden soll, müssen Sie eine verwaltete Methode definieren, die die nicht verwaltete Zielfunktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="01d3d-141">For each unmanaged function to be called through PInvoke, you must define a managed method that represents the target unmanaged function.</span></span> <span data-ttu-id="01d3d-142">Um die verwaltete Methode zu definieren, verwenden Sie `DefineMethod` mit einigen Parametern, die auf bestimmte Werte festgelegt sind, abhängig von der Art und Weise, in der PInvoke verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="01d3d-142">To define the managed method, use `DefineMethod` with some of the parameters set to certain values, depending on the way in which PInvoke is used:</span></span>  
  
- <span data-ttu-id="01d3d-143">True PInvoke: umfasst den Aufruf einer externen nicht verwalteten Methode, die sich in einer nicht verwalteten DLL befindet.</span><span class="sxs-lookup"><span data-stu-id="01d3d-143">True PInvoke - involves invocation of an external unmanaged method that resides in an unmanaged DLL.</span></span>  
  
- <span data-ttu-id="01d3d-144">Local PInvoke: umfasst den Aufruf einer nativen, nicht verwalteten Methode, die in das aktuelle verwaltete Modul eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="01d3d-144">Local PInvoke - involves invocation of a native unmanaged method that is embedded in the current managed module.</span></span>  
  
 <span data-ttu-id="01d3d-145">Die Parametereinstellungen sind in der folgenden Tabelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="01d3d-145">The parameter settings are given in the following table.</span></span>  
  
|<span data-ttu-id="01d3d-146">Parameter</span><span class="sxs-lookup"><span data-stu-id="01d3d-146">Parameter</span></span>|<span data-ttu-id="01d3d-147">Werte für true PInvoke</span><span class="sxs-lookup"><span data-stu-id="01d3d-147">Values for true PInvoke</span></span>|<span data-ttu-id="01d3d-148">Werte für local PInvoke</span><span class="sxs-lookup"><span data-stu-id="01d3d-148">Values for local PInvoke</span></span>|  
|---------------|-----------------------------|------------------------------|  
|`dwMethodFlags`||<span data-ttu-id="01d3d-149">Festlegen `mdStatic` ; Löschen Sie `mdSynchronized` und `mdAbstract` .</span><span class="sxs-lookup"><span data-stu-id="01d3d-149">Set `mdStatic`; clear `mdSynchronized` and `mdAbstract`.</span></span>|  
|`pvSigBlob`|<span data-ttu-id="01d3d-150">Eine gültige common Language Runtime (CLR)-Methoden Signatur mit Parametern, die gültige verwaltete Typen sind.</span><span class="sxs-lookup"><span data-stu-id="01d3d-150">A valid common language runtime (CLR) method signature with parameters that are valid managed types.</span></span>|<span data-ttu-id="01d3d-151">Eine gültige CLR-Methoden Signatur mit Parametern, die gültige verwaltete Typen sind.</span><span class="sxs-lookup"><span data-stu-id="01d3d-151">A valid CLR method signature with parameters that are valid managed types.</span></span>|  
|`ulCodeRVA`||<span data-ttu-id="01d3d-152">0</span><span class="sxs-lookup"><span data-stu-id="01d3d-152">0</span></span>|  
|`dwImplFlags`|<span data-ttu-id="01d3d-153">Legen Sie `miCil` und `miManaged` fest.</span><span class="sxs-lookup"><span data-stu-id="01d3d-153">Set `miCil` and `miManaged`.</span></span>|<span data-ttu-id="01d3d-154">Legen Sie `miNative` und `miUnmanaged` fest.</span><span class="sxs-lookup"><span data-stu-id="01d3d-154">Set `miNative` and `miUnmanaged`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="01d3d-155">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="01d3d-155">Requirements</span></span>  
 <span data-ttu-id="01d3d-156">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="01d3d-156">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01d3d-157">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="01d3d-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="01d3d-158">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="01d3d-158">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01d3d-159">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01d3d-159">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01d3d-160">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="01d3d-160">See also</span></span>

- [<span data-ttu-id="01d3d-161">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01d3d-161">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="01d3d-162">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="01d3d-162">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
