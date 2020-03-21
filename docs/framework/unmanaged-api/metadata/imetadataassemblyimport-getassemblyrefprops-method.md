---
title: IMetaDataAssemblyImport::GetAssemblyRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175966"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="e8dc1-102">IMetaDataAssemblyImport::GetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e8dc1-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="e8dc1-103">Ruft den Satz von Eigenschaften für den Assemblyverweis mit der angegebenen Metadatensignatur ab.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8dc1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8dc1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8dc1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8dc1-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="e8dc1-106">[in] Das `mdAssemblyRef` Metadatentoken, das den Assemblyverweis darstellt, für den die Eigenschaften abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="e8dc1-107">[out] Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="e8dc1-108">[out] Die Anzahl der Bytes im zurückgegebenen öffentlichen Schlüssel oder Token.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="e8dc1-109">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e8dc1-110">[in] Die Größe, in breiten `szName`Zeichen, von .</span><span class="sxs-lookup"><span data-stu-id="e8dc1-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="e8dc1-111">[out] Ein Zeiger auf die Anzahl der breiten `szName`Zeichen, die tatsächlich in zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="e8dc1-112">[out] Ein Zeiger auf eine ASSEMBLYMETADATA-Struktur, die die Assemblymetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="e8dc1-113">[out] Ein Zeiger auf den Hashwert.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="e8dc1-114">Dies ist der Hash mithilfe des SHA-1-Algorithmus der `PublicKey` Eigenschaft der Assembly, auf die verwiesen wird, es sei denn, das arfFullOriginator-Flag der [AssemblyRefFlags-Enumeration](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) wird festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="e8dc1-115">[out] Die Anzahl der breiten Zeichen im zurückgegebenen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="e8dc1-116">[out] Ein Zeiger auf Flags, die die Metadaten beschreiben, die auf eine Assembly angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="e8dc1-117">Der Flags-Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags-Werten.](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="e8dc1-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8dc1-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e8dc1-118">Return Value</span></span>  
 <span data-ttu-id="e8dc1-119">Diese Methode gibt S_OK zurück, wenn sie erfolgreich ist. Andernfalls wird einer der in der Winerror.h-Headerdatei definierten Fehlercodes zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e8dc1-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8dc1-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e8dc1-120">Requirements</span></span>  
 <span data-ttu-id="e8dc1-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8dc1-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8dc1-122">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e8dc1-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8dc1-123">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e8dc1-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e8dc1-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8dc1-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8dc1-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e8dc1-125">See also</span></span>

- [<span data-ttu-id="e8dc1-126">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8dc1-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
