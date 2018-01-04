---
title: IMetaDataImport::GetPropertyProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d838f43b500ac3dd0c3b44d9d84dd9fc039c6e16
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="a94a2-102">IMetaDataImport::GetPropertyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="a94a2-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="a94a2-103">Ruft die Metadaten für die Eigenschaft, die durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a94a2-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a94a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a94a2-104">Syntax</span></span>  
  
```  
HRESULT GetPropertyProps (  
   [in]  mdProperty        prop,  
   [out] mdTypeDef         *pClass,   
   [out] LPCWSTR           szProperty,   
   [in]  ULONG             cchProperty,   
   [out] ULONG             *pchProperty,   
   [out] DWORD             *pdwPropFlags,   
   [out] PCCOR_SIGNATURE   *ppvSig,   
   [out] ULONG             *pbSig,   
   [out] DWORD             *pdwCPlusTypeFlag,   
   [out] UVCP_CONSTANT     *ppDefaultValue,  
   [out] ULONG             *pcchDefaultValue,  
   [out] mdMethodDef       *pmdSetter,   
   [out] mdMethodDef       *pmdGetter,   
   [out] mdMethodDef       rmdOtherMethod[],  
   [in]  ULONG             cMax,   
   [out] ULONG             *pcOtherMethod   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a94a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a94a2-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="a94a2-106">[in] Ein Token, die die Metadaten für die zurückzugebende Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="a94a2-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="a94a2-107">[out] Ein Zeiger auf das TypeDef-Token, das den Typ darstellt, der die Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="a94a2-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="a94a2-108">[out] Ein Puffer, der den Eigenschaftennamen enthält.</span><span class="sxs-lookup"><span data-stu-id="a94a2-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="a94a2-109">[in] Die Größe in Breitzeichen `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="a94a2-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="a94a2-110">[out] Die Anzahl der Breitzeichen, die im zurückgegebenen `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="a94a2-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="a94a2-111">[out] Ein Zeiger auf Attributflags, die auf die Eigenschaft angewendet.</span><span class="sxs-lookup"><span data-stu-id="a94a2-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="a94a2-112">Dieser Wert ist eine Bitmaske aus der [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a94a2-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="a94a2-113">[out] Ein Zeiger auf die Metadatensignatur der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a94a2-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="a94a2-114">[out] Die Anzahl der Bytes im zurückgegebenen `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="a94a2-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="a94a2-115">[out] Ein Flag, das den Typ der Konstante, die der Standardwert der Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="a94a2-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="a94a2-116">Dieser Wert liegt zwischen CorElementType-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="a94a2-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="a94a2-117">[out] Ein Zeiger auf die Bytes, die den Standardwert für diese Eigenschaft zu speichern.</span><span class="sxs-lookup"><span data-stu-id="a94a2-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="a94a2-118">[out] Die Größe in Breitzeichen `ppDefaultValue`, wenn `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING ist; dieser Wert ist, andernfalls nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="a94a2-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="a94a2-119">In diesem Fall wird die Länge des `ppDefaultValue` wird aus der vom angegebenen Typ abgeleitet, `pdwCPlusTypeFlag`.</span><span class="sxs-lookup"><span data-stu-id="a94a2-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="a94a2-120">[out] Ein Zeiger auf das MethodDef-Token, das die Set-Zugriffsmethode für die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="a94a2-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="a94a2-121">[out] Ein Zeiger auf das MethodDef-Token, das die Get-Accessor-Methode für die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="a94a2-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="a94a2-122">[out] Ein Array von MethodDef-Token, die andere Methoden, die mit der Eigenschaft verknüpften darstellen.</span><span class="sxs-lookup"><span data-stu-id="a94a2-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a94a2-123">[in] Die maximale Größe des `rmdOtherMethod`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a94a2-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="a94a2-124">Wenn Sie ein Array, das groß genug für alle Methoden nicht angeben, werden sie ohne Warnung übersprungen.</span><span class="sxs-lookup"><span data-stu-id="a94a2-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="a94a2-125">[out] Die Anzahl der zurückgegebenen MethodDef-Token `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="a94a2-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a94a2-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a94a2-126">Requirements</span></span>  
 <span data-ttu-id="a94a2-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a94a2-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a94a2-128">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a94a2-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a94a2-129">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a94a2-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a94a2-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a94a2-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94a2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a94a2-131">See Also</span></span>  
 [<span data-ttu-id="a94a2-132">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a94a2-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a94a2-133">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a94a2-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
