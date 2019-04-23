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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6c550ff7af2dda8bc06afd771024fe290339904
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089782"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="a0edd-102">IMetaDataAssemblyImport::GetAssemblyRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="a0edd-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="a0edd-103">Ruft den Satz von Eigenschaften für den der Assemblyverweis verweist mit der angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="a0edd-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0edd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0edd-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="a0edd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0edd-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="a0edd-106">[in] Die `mdAssemblyRef` Metadatentoken, das die Assemblyverweis für das Abrufen der Eigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="a0edd-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="a0edd-107">[out] Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="a0edd-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="a0edd-108">[out] Die Anzahl der Bytes im öffentlichen Schlüssel oder ein token zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0edd-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="a0edd-109">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="a0edd-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="a0edd-110">[in] Die Größe in Breitzeichen von `szName`.</span><span class="sxs-lookup"><span data-stu-id="a0edd-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="a0edd-111">[out] Ein Zeiger auf die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="a0edd-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="a0edd-112">[out] Ein Zeiger auf ein ASSEMBLYMETADATA-Struktur, die die Metadaten der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="a0edd-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="a0edd-113">[out] Ein Zeiger auf den Hashwert.</span><span class="sxs-lookup"><span data-stu-id="a0edd-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="a0edd-114">Dies ist der Hash, mit dem SHA-1-Algorithmus, der die `PublicKey` die Assemblyeigenschaft auf die verwiesen wird, es sei denn, das ArfFullOriginator-flag von der [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) Enumeration festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a0edd-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="a0edd-115">[out] Die Anzahl von Breitzeichen in den zurückgegebenen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="a0edd-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="a0edd-116">[out] Ein Zeiger auf Flags, die auf eine Assembly angewendete Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a0edd-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="a0edd-117">Der Wert des Flags ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="a0edd-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0edd-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0edd-118">Return Value</span></span>  
 <span data-ttu-id="a0edd-119">Diese Methode gibt S_OK zurück, wenn er erfolgreich abgeschlossen wurde; Andernfalls wird eine der in der Headerdatei "Winerror.h" definierten Fehlercodes zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0edd-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0edd-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0edd-120">Requirements</span></span>  
 <span data-ttu-id="a0edd-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0edd-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0edd-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a0edd-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0edd-123">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a0edd-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0edd-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0edd-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0edd-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0edd-125">See also</span></span>

- [<span data-ttu-id="a0edd-126">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0edd-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
