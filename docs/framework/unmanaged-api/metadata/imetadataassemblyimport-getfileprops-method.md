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
ms.openlocfilehash: beb697d80417b937876a0887e4376341185a47d9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447215"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="2bf11-102">IMetaDataAssemblyImport::GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2bf11-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="2bf11-103">Ruft die Eigenschaften der Datei mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="2bf11-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bf11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bf11-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2bf11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bf11-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="2bf11-106">in Das `mdFile` Metadatentoken, das die Datei darstellt, für die die Eigenschaften zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="2bf11-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="2bf11-107">vorgenommen Der einfache Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="2bf11-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="2bf11-108">in Die Größe `szName`in breiten Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2bf11-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="2bf11-109">vorgenommen Die Anzahl der breit Zeichen, die in `szName`tatsächlich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2bf11-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="2bf11-110">vorgenommen Ein Zeiger auf den Hashwert.</span><span class="sxs-lookup"><span data-stu-id="2bf11-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="2bf11-111">Dies ist der Hash, der den SHA-1-Algorithmus der Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="2bf11-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="2bf11-112">vorgenommen Die Anzahl der breiten Zeichen im zurückgegebenen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="2bf11-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="2bf11-113">vorgenommen Ein Zeiger auf die Flags, die die auf eine Datei angewendeten Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="2bf11-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="2bf11-114">Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) -Werten.</span><span class="sxs-lookup"><span data-stu-id="2bf11-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bf11-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2bf11-115">Requirements</span></span>  
 <span data-ttu-id="2bf11-116">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bf11-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bf11-117">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2bf11-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bf11-118">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="2bf11-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2bf11-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bf11-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bf11-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bf11-120">See also</span></span>

- [<span data-ttu-id="2bf11-121">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bf11-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
