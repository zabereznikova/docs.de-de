---
title: IMetaDataAssemblyImport::GetFileProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
ms.openlocfilehash: 0b9ff2716cc0bc32c81fe6fcdd4e6c367d4d835f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718175"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="d81e5-102">IMetaDataAssemblyImport::GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="d81e5-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>

<span data-ttu-id="d81e5-103">Ruft die Eigenschaften der Datei mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="d81e5-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81e5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d81e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,
    [out] LPWSTR      szName,
    [in]  ULONG       cchName,
    [out] ULONG       *pchName,
    [out] const void  **ppbHashValue,
    [out] ULONG       *pcbHashValue,
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d81e5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d81e5-105">Parameters</span></span>  

 `mdf`  
 <span data-ttu-id="d81e5-106">in Das `mdFile` Metadatentoken, das die Datei darstellt, für die die Eigenschaften zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="d81e5-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="d81e5-107">vorgenommen Der einfache Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="d81e5-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d81e5-108">in Die Größe von in breit Zeichen `szName` .</span><span class="sxs-lookup"><span data-stu-id="d81e5-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d81e5-109">vorgenommen Die Anzahl der breit Zeichen, die in tatsächlich zurückgegeben wurden `szName` .</span><span class="sxs-lookup"><span data-stu-id="d81e5-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="d81e5-110">vorgenommen Ein Zeiger auf den Hashwert.</span><span class="sxs-lookup"><span data-stu-id="d81e5-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="d81e5-111">Dies ist der Hash, der den SHA-1-Algorithmus der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="d81e5-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="d81e5-112">vorgenommen Die Anzahl der breiten Zeichen im zurückgegebenen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="d81e5-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="d81e5-113">vorgenommen Ein Zeiger auf die Flags, die die auf eine Datei angewendeten Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d81e5-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="d81e5-114">Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorFileFlags](corfileflags-enumeration.md) -Werten.</span><span class="sxs-lookup"><span data-stu-id="d81e5-114">The flags value is a combination of one or more [CorFileFlags](corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d81e5-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d81e5-115">Requirements</span></span>  

 <span data-ttu-id="d81e5-116">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d81e5-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d81e5-117">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d81e5-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d81e5-118">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d81e5-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d81e5-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d81e5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81e5-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d81e5-120">See also</span></span>

- [<span data-ttu-id="d81e5-121">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d81e5-121">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
