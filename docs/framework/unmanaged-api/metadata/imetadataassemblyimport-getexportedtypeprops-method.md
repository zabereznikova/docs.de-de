---
title: IMetaDataAssemblyImport::GetExportedTypeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
ms.openlocfilehash: 82302124828a2dab73b445128d7d847e112edd36
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448218"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="4734e-102">IMetaDataAssemblyImport::GetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4734e-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>
<span data-ttu-id="4734e-103">Ruft den Satz von Eigenschaften des exportierten Typs mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="4734e-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4734e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4734e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4734e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4734e-105">Parameters</span></span>  
 `mdct`  
 <span data-ttu-id="4734e-106">in Ein `mdExportedType` Metadatentoken, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="4734e-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="4734e-107">vorgenommen Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="4734e-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="4734e-108">in Die Größe `szName`in breit Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4734e-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="4734e-109">vorgenommen Die Anzahl der tatsächlich in `szName` zurückgegebenen breit Zeichen.</span><span class="sxs-lookup"><span data-stu-id="4734e-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="4734e-110">vorgenommen Ein `mdFile`-, `mdAssemblyRef`-oder `mdExportedType` Metadatentoken, das den Zugriff auf die Eigenschaften des exportierten Typs enthält bzw. zulässt.</span><span class="sxs-lookup"><span data-stu-id="4734e-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="4734e-111">vorgenommen Ein Zeiger auf ein `mdTypeDef` Token, das einen Typ in der Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="4734e-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="4734e-112">vorgenommen Ein Zeiger auf die Flags, die die auf den exportierten Typ angewendeten Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="4734e-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="4734e-113">Der Flags-Wert kann ein oder mehrere [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) -Werte sein.</span><span class="sxs-lookup"><span data-stu-id="4734e-113">The flags value can be one or more [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4734e-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4734e-114">Requirements</span></span>  
 <span data-ttu-id="4734e-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4734e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4734e-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4734e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4734e-117">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="4734e-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4734e-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4734e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4734e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4734e-119">See also</span></span>

- [<span data-ttu-id="4734e-120">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4734e-120">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
