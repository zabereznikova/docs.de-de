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
ms.openlocfilehash: 5fc71bf240b89afadbf8f2ba10906322921bdda2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175329"
---
# <a name="imetadataimportgetpropertyprops-method"></a><span data-ttu-id="0ddbd-102">IMetaDataImport::GetPropertyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="0ddbd-102">IMetaDataImport::GetPropertyProps Method</span></span>
<span data-ttu-id="0ddbd-103">Ruft die Metadaten für die Eigenschaft ab, die durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-103">Gets the metadata for the property represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ddbd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ddbd-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="0ddbd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ddbd-105">Parameters</span></span>  
 `prop`  
 <span data-ttu-id="0ddbd-106">[in] Ein Token, das die Eigenschaft darstellt, für die Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-106">[in] A token that represents the property to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="0ddbd-107">[out] Ein Zeiger auf das TypeDef-Token, das den Typ darstellt, der die Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-107">[out] A pointer to the TypeDef token that represents the type that implements the property.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="0ddbd-108">[out] Ein Puffer, der den Eigenschaftsnamen aufhält.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-108">[out] A buffer to hold the property name.</span></span>  
  
 `cchProperty`  
 <span data-ttu-id="0ddbd-109">[in] Die Größe in `szProperty`breiten Zeichen von .</span><span class="sxs-lookup"><span data-stu-id="0ddbd-109">[in] The size in wide characters of `szProperty`.</span></span>  
  
 `pchProperty`  
 <span data-ttu-id="0ddbd-110">[out] Die Anzahl der in `szProperty`zurückgegebenen breiten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-110">[out] The number of wide characters returned in `szProperty`.</span></span>  
  
 `pdwPropFlags`  
 <span data-ttu-id="0ddbd-111">[out] Ein Zeiger auf alle Attributflags, die auf die Eigenschaft angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-111">[out] A pointer to any attribute flags applied to the property.</span></span> <span data-ttu-id="0ddbd-112">Dieser Wert ist eine Bitmaske aus der [CorPropertyAttr-Enumeration.](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="0ddbd-112">This value is a bitmask from the [CorPropertyAttr](../../../../docs/framework/unmanaged-api/metadata/corpropertyattr-enumeration.md) enumeration.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="0ddbd-113">[out] Ein Zeiger auf die Metadatensignatur der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-113">[out] A pointer to the metadata signature of the property.</span></span>  
  
 `pbSig`  
 <span data-ttu-id="0ddbd-114">[out] Die Anzahl der `ppvSig`in zurückgegebenen Bytes.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-114">[out] The number of bytes returned in `ppvSig`.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="0ddbd-115">[out] Ein Flag, das den Typ der Konstante angibt, die der Standardwert der Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-115">[out] A flag specifying the type of the constant that is the default value of the property.</span></span> <span data-ttu-id="0ddbd-116">Dieser Wert stammt aus der CorElementType-Enumeration.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-116">This value is from the CorElementType enumeration.</span></span>  
  
 `ppDefaultValue`  
 <span data-ttu-id="0ddbd-117">[out] Ein Zeiger auf die Bytes, die den Standardwert für diese Eigenschaft speichern.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-117">[out] A pointer to the bytes that store the default value for this property.</span></span>  
  
 `pcchDefaultValue`  
 <span data-ttu-id="0ddbd-118">[out] Die Größe in `ppDefaultValue`breiten `pdwCPlusTypeFlag` Zeichen von , wenn ELEMENT_TYPE_STRING ist; andernfalls ist dieser Wert nicht relevant.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-118">[out] The size in wide characters of `ppDefaultValue`, if `pdwCPlusTypeFlag` is ELEMENT_TYPE_STRING; otherwise, this value is not relevant.</span></span> <span data-ttu-id="0ddbd-119">In diesem Fall wird `ppDefaultValue` die Länge von aus dem `pdwCPlusTypeFlag`Typ abgeleitet, der von angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-119">In that case, the length of `ppDefaultValue` is inferred from the type that is specified by `pdwCPlusTypeFlag`.</span></span>  
  
 `pmdSetter`  
 <span data-ttu-id="0ddbd-120">[out] Ein Zeiger auf das MethodDef-Token, das die Set-Accessor-Methode für die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-120">[out] A pointer to the MethodDef token that represents the set accessor method for the property.</span></span>  
  
 `pmdGetter`  
 <span data-ttu-id="0ddbd-121">[out] Ein Zeiger auf das MethodDef-Token, das die get-Accessor-Methode für die Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-121">[out] A pointer to the MethodDef token that represents the get accessor method for the property.</span></span>  
  
 `rmdOtherMethod`  
 <span data-ttu-id="0ddbd-122">[out] Ein Array von MethodDef-Token, die andere Methoden darstellen, die der Eigenschaft zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-122">[out] An array of MethodDef tokens that represent other methods associated with the property.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0ddbd-123">[in] Die maximale Größe des `rmdOtherMethod`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-123">[in] The maximum size of the `rmdOtherMethod` array.</span></span> <span data-ttu-id="0ddbd-124">Wenn Sie kein Array bereitstellen, das groß genug ist, um alle Methoden zu halten, werden diese ohne Warnung übersprungen.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-124">If you do not provide an array large enough to hold all the methods, they are skipped without warning.</span></span>  
  
 `pcOtherMethod`  
 <span data-ttu-id="0ddbd-125">[out] Die Anzahl der methodDef-Token, die in `rmdOtherMethod`zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0ddbd-125">[out] The number of MethodDef tokens returned in `rmdOtherMethod`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ddbd-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0ddbd-126">Requirements</span></span>  
 <span data-ttu-id="0ddbd-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ddbd-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ddbd-128">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ddbd-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ddbd-129">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0ddbd-129">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0ddbd-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ddbd-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ddbd-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ddbd-131">See also</span></span>

- [<span data-ttu-id="0ddbd-132">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ddbd-132">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0ddbd-133">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ddbd-133">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
