---
title: IMetaDataImport::GetPropertyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPropertyProps
helpviewer_keywords:
- GetPropertyProps method [.NET Framework metadata]
- IMetaDataImport::GetPropertyProps method [.NET Framework metadata]
ms.assetid: dc0ff3e6-7e7d-4f6c-948d-52b28f5cb78c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08bd5beeb9fab1cd5b703c3afc4e82aaf71dbbc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122602"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="5e30c-102">IMetaDataImport::GetPropertyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5e30c-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="5e30c-103">Ruft die Metadaten für die Eigenschaft, die durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5e30c-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e30c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e30c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5e30c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5e30c-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="5e30c-106">[in] Ein Token, die die Metadaten für die zurückzugebende Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="5e30c-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="5e30c-107">[out] Ein Zeiger auf das TypeDef-Token, das den Typ darstellt, der der Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="5e30c-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="5e30c-108">[out] Ein Puffer, die Namen der Eigenschaft enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="5e30c-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="5e30c-109">[in] Die Größe in Breitzeichen `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="5e30c-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="5e30c-110">[out] Die Anzahl der Breitzeichen, die in zurückgegebenen `szProperty`.</span><span class="sxs-lookup"><span data-stu-id="5e30c-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="5e30c-111">[out] Ein Zeiger auf Attributflags auf die Eigenschaft angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5e30c-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="5e30c-112">Dieser Wert ist eine Bitmaske aus der [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5e30c-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="5e30c-113">[out] Ein Zeiger auf die Signatur für die Metadaten der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5e30c-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="5e30c-114">[out] Die Anzahl der Bytes, die in zurückgegebenen `ppvSig`.</span><span class="sxs-lookup"><span data-stu-id="5e30c-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="5e30c-115">[out] Ein Flag, das den Typ der Konstante, die der Standardwert der Eigenschaft angibt.</span><span class="sxs-lookup"><span data-stu-id="5e30c-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="5e30c-116">Dieser Wert liegt zwischen CorElementType-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="5e30c-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="5e30c-117">[out] Ein Zeiger auf die Bytes, die der Standardwert für diese Eigenschaft zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5e30c-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="5e30c-118">[out] Die Größe in Breitzeichen `ppDefaultValue`, wenn `pdwCPlusTypeFlag` ELEMENT_TYPE_STRING ist; andernfalls ist dieser Wert nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="5e30c-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="5e30c-119">In diesem Fall die Länge des `ppDefaultValue` wird aus der vom angegebenen Typ abgeleitet, `pdwCPlusTypeFlag`.</span><span class="sxs-lookup"><span data-stu-id="5e30c-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="5e30c-120">[out] Ein Zeiger auf das MethodDef-Token, das die Set-Accessor-Methode für die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="5e30c-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="5e30c-121">[out] Ein Zeiger auf das MethodDef-Token, das die Get-Accessor-Methode für die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="5e30c-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="5e30c-122">[out] Ein Array von MethodDef-Token, die andere Methoden, die mit der Eigenschaft verknüpften darstellen.</span><span class="sxs-lookup"><span data-stu-id="5e30c-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5e30c-123">[in] Die maximale Größe des `rmdOtherMethod`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="5e30c-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="5e30c-124">Wenn Sie ein Array, das groß genug für alle Methoden nicht angeben, werden sie ohne Warnung übersprungen.</span><span class="sxs-lookup"><span data-stu-id="5e30c-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="5e30c-125">[out] Die Anzahl der zurückgegebenen MethodDef-Token `rmdOtherMethod`.</span><span class="sxs-lookup"><span data-stu-id="5e30c-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e30c-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e30c-126">Requirements</span></span>  
 <span data-ttu-id="5e30c-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e30c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e30c-128">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5e30c-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5e30c-129">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5e30c-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5e30c-130">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5e30c-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5e30c-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e30c-131">See also</span></span>

- [<span data-ttu-id="5e30c-132">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e30c-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5e30c-133">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5e30c-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
