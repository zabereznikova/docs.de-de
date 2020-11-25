---
title: IMetaDataAssemblyImport::GetManifestResourceProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: 585a9e39f529294841cd11389f03d763968a0f5e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723817"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a><span data-ttu-id="ec602-102">IMetaDataAssemblyImport::GetManifestResourceProps-Methode</span><span class="sxs-lookup"><span data-stu-id="ec602-102">IMetaDataAssemblyImport::GetManifestResourceProps Method</span></span>

<span data-ttu-id="ec602-103">Ruft den Satz von Eigenschaften der Manifestressource mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="ec602-103">Gets the set of properties of the manifest resource with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec602-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec602-104">Syntax</span></span>  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec602-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec602-105">Parameters</span></span>  

 `mdmr`  
 <span data-ttu-id="ec602-106">in Ein `mdManifestResource` Token, das die Ressource darstellt, für die die Eigenschaften zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="ec602-106">[in] An `mdManifestResource` token that represents the resource for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="ec602-107">vorgenommen Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="ec602-107">[out] The name of the resource.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ec602-108">in Die Größe von in breit Zeichen `szName` .</span><span class="sxs-lookup"><span data-stu-id="ec602-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ec602-109">vorgenommen Ein Zeiger auf die Anzahl der breit Zeichen, die tatsächlich in zurückgegeben werden `szName` .</span><span class="sxs-lookup"><span data-stu-id="ec602-109">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `ptkImplementation`  
 <span data-ttu-id="ec602-110">vorgenommen Ein Zeiger auf ein `mdFile` Token oder ein `mdAssemblyRef` Token, das bzw. die bzw. die bzw. die bzw. die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="ec602-110">[out] A pointer to an `mdFile` token or an `mdAssemblyRef` token that represents the file or assembly, respectively, that contains the resource.</span></span>  
  
 `pdwOffset`  
 <span data-ttu-id="ec602-111">vorgenommen Ein Zeiger auf einen-Wert, der den Offset bis zum Anfang der Ressource innerhalb der Datei angibt.</span><span class="sxs-lookup"><span data-stu-id="ec602-111">[out] A pointer to a value that specifies the offset to the beginning of the resource within the file.</span></span>  
  
 `pdwResourceFlags`  
 <span data-ttu-id="ec602-112">vorgenommen Ein Zeiger auf Flags, die die auf eine Ressource angewendeten Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ec602-112">[out] A pointer to flags that describe the metadata applied to a resource.</span></span> <span data-ttu-id="ec602-113">Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) -Werten.</span><span class="sxs-lookup"><span data-stu-id="ec602-113">The flags value is a combination of one or more [CorManifestResourceFlags](cormanifestresourceflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec602-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ec602-114">Requirements</span></span>  

 <span data-ttu-id="ec602-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec602-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec602-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ec602-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec602-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec602-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ec602-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec602-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec602-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ec602-119">See also</span></span>

- [<span data-ttu-id="ec602-120">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec602-120">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
