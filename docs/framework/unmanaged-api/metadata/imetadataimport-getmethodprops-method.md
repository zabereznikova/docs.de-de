---
title: IMetaDataImport::GetMethodProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 57604d80d40130ca147c026852b7bcd23f8f90bc
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496455"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="48dc9-102">IMetaDataImport::GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="48dc9-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="48dc9-103">Ruft die Metadaten ab, die der Methode zugeordnet sind, auf die durch das angegebene MethodDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="48dc9-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48dc9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48dc9-104">Syntax</span></span>  
  
```  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48dc9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="48dc9-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="48dc9-106">[in] Das MethodDef-Token, das die Methode zum Zurückgeben von Metadaten für darstellt.</span><span class="sxs-lookup"><span data-stu-id="48dc9-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="48dc9-107">[out] Ein Zeiger auf ein TypeDef-Token, das den Typ darstellt, der die Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="48dc9-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="48dc9-108">[out] Ein Zeiger auf einen Puffer, der den Namen der Methode hat.</span><span class="sxs-lookup"><span data-stu-id="48dc9-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="48dc9-109">[in] Die angeforderte Größe des `szMethod`.</span><span class="sxs-lookup"><span data-stu-id="48dc9-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="48dc9-110">[out] Ein Zeiger auf die Größe in Breitzeichen `szMethod`, oder im Fall von abschneiden, die tatsächliche Anzahl von Breitzeichen in den Methodennamen.</span><span class="sxs-lookup"><span data-stu-id="48dc9-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="48dc9-111">[out] Ein Zeiger auf Flags der Methode zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="48dc9-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="48dc9-112">[out] Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="48dc9-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="48dc9-113">[out] Ein Zeiger auf die Größe in Bytes der `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="48dc9-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="48dc9-114">[out] Ein Zeiger auf die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="48dc9-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="48dc9-115">[out] Ein Zeiger auf die Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="48dc9-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48dc9-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48dc9-116">Requirements</span></span>  
 <span data-ttu-id="48dc9-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48dc9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48dc9-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="48dc9-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48dc9-119">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48dc9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="48dc9-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48dc9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48dc9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48dc9-121">See also</span></span>
- [<span data-ttu-id="48dc9-122">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48dc9-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="48dc9-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48dc9-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
