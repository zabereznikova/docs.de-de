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
ms.openlocfilehash: dae4a36537eeac58ffb17ebc1b78d935ec807cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175979"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="b7e12-102">IMetaDataAssemblyImport::GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="b7e12-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="b7e12-103">Ruft die Eigenschaften der Datei mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="b7e12-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7e12-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7e12-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b7e12-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b7e12-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="b7e12-106">[in] Das `mdFile` Metadatentoken, das die Datei darstellt, für die die Eigenschaften abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b7e12-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="b7e12-107">[out] Der einfache Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="b7e12-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="b7e12-108">[in] Die Größe, in breiten `szName`Zeichen, von .</span><span class="sxs-lookup"><span data-stu-id="b7e12-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="b7e12-109">[out] Die Anzahl der breiten Zeichen, die tatsächlich in `szName`zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="b7e12-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="b7e12-110">[out] Ein Zeiger auf den Hashwert.</span><span class="sxs-lookup"><span data-stu-id="b7e12-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="b7e12-111">Dies ist der Hash der Datei mit dem SHA-1-Algorithmus.</span><span class="sxs-lookup"><span data-stu-id="b7e12-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="b7e12-112">[out] Die Anzahl der breiten Zeichen im zurückgegebenen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="b7e12-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="b7e12-113">[out] Ein Zeiger auf die Flags, die die Metadaten beschreiben, die auf eine Datei angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b7e12-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="b7e12-114">Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorFileFlags-Werten.](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="b7e12-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7e12-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b7e12-115">Requirements</span></span>  
 <span data-ttu-id="b7e12-116">**Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7e12-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7e12-117">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b7e12-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b7e12-118">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="b7e12-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b7e12-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7e12-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7e12-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7e12-120">See also</span></span>

- [<span data-ttu-id="b7e12-121">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b7e12-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
