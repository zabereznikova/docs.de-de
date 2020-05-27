---
title: IMetaDataAssemblyImport::GetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
ms.openlocfilehash: a90deaf3e9ddf326c6fca558cbb4681fc40e022d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009053"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="d45b0-102">IMetaDataAssemblyImport::GetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="d45b0-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="d45b0-103">Ruft den Satz von Eigenschaften für die Assembly mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="d45b0-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d45b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d45b0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d45b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d45b0-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="d45b0-106">[in]</span><span class="sxs-lookup"><span data-stu-id="d45b0-106">[in].</span></span> <span data-ttu-id="d45b0-107">Das `mdAssembly` Metadatentoken, das die Assembly darstellt, für die die Eigenschaften zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="d45b0-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="d45b0-108">vorgenommen Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="d45b0-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="d45b0-109">vorgenommen Die Anzahl der Bytes im zurückgegebenen öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="d45b0-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="d45b0-110">vorgenommen Ein Zeiger auf den Algorithmus, der zum Hash der Dateien in der Assembly verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d45b0-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="d45b0-111">vorgenommen Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="d45b0-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d45b0-112">in Die Größe von in breit Zeichen `szName` .</span><span class="sxs-lookup"><span data-stu-id="d45b0-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d45b0-113">vorgenommen Die Anzahl der breit Zeichen, die in tatsächlich zurückgegeben wurden `szName` .</span><span class="sxs-lookup"><span data-stu-id="d45b0-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="d45b0-114">vorgenommen Ein Zeiger auf eine ASSEMBLYMETADATA-Struktur, die die Assemblymetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="d45b0-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="d45b0-115">vorgenommen Flags, die die auf eine Assembly angewendeten Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="d45b0-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="d45b0-116">Dieser Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](corassemblyflags-enumeration.md) -Werten.</span><span class="sxs-lookup"><span data-stu-id="d45b0-116">This value is a combination of one or more [CorAssemblyFlags](corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d45b0-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d45b0-117">Requirements</span></span>  
 <span data-ttu-id="d45b0-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d45b0-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d45b0-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d45b0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d45b0-120">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d45b0-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d45b0-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d45b0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45b0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d45b0-122">See also</span></span>

- [<span data-ttu-id="d45b0-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d45b0-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
