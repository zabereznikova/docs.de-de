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
ms.openlocfilehash: 32224431051b958a3f01ffeb15cdb6db1dae2657
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722101"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a><span data-ttu-id="2cb4b-102">IMetaDataAssemblyImport::GetExportedTypeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2cb4b-102">IMetaDataAssemblyImport::GetExportedTypeProps Method</span></span>

<span data-ttu-id="2cb4b-103">Ruft den Satz von Eigenschaften des exportierten Typs mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="2cb4b-103">Gets the set of properties of the exported type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cb4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cb4b-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2cb4b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2cb4b-105">Parameters</span></span>  

 `mdct`  
 <span data-ttu-id="2cb4b-106">in Ein `mdExportedType` Metadatentoken, das den exportierten Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="2cb4b-106">[in] An `mdExportedType` metadata token that represents the exported type.</span></span>  
  
 `szName`  
 <span data-ttu-id="2cb4b-107">vorgenommen Der Name des exportierten Typs.</span><span class="sxs-lookup"><span data-stu-id="2cb4b-107">[out] The name of the exported type.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2cb4b-108">in Die Größe von in breit Zeichen `szName` .</span><span class="sxs-lookup"><span data-stu-id="2cb4b-108">[in] The size, in wide characters, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="2cb4b-109">vorgenommen Die Anzahl der tatsächlich zurückgegebenen breit Zeichen. `szName`</span><span class="sxs-lookup"><span data-stu-id="2cb4b-109">[out] The number of wide characters actually returned in `szName`</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="2cb4b-110">vorgenommen Ein-,-oder-Metadatentoken, `mdFile` `mdAssemblyRef` `mdExportedType` das den Zugriff auf die Eigenschaften des exportierten Typs enthält oder zulässt.</span><span class="sxs-lookup"><span data-stu-id="2cb4b-110">[out] An `mdFile`, `mdAssemblyRef`, or `mdExportedType` metadata token that contains or allows access to the properties of the exported type.</span></span>  
  
 `ptkTypeDef`  
 <span data-ttu-id="2cb4b-111">vorgenommen Ein Zeiger auf ein `mdTypeDef` Token, das einen Typ in der Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="2cb4b-111">[out] A pointer to an `mdTypeDef` token that represents a type in the file.</span></span>  
  
 `pdwExportedTypeFlags`  
 <span data-ttu-id="2cb4b-112">vorgenommen Ein Zeiger auf die Flags, die die auf den exportierten Typ angewendeten Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="2cb4b-112">[out] A pointer to the flags that describe the metadata applied to the exported type.</span></span> <span data-ttu-id="2cb4b-113">Der Flags-Wert kann ein oder mehrere [CorTypeAttr](cortypeattr-enumeration.md) -Werte sein.</span><span class="sxs-lookup"><span data-stu-id="2cb4b-113">The flags value can be one or more [CorTypeAttr](cortypeattr-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cb4b-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2cb4b-114">Requirements</span></span>  

 <span data-ttu-id="2cb4b-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cb4b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cb4b-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2cb4b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2cb4b-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="2cb4b-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2cb4b-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cb4b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb4b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2cb4b-119">See also</span></span>

- [<span data-ttu-id="2cb4b-120">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cb4b-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
