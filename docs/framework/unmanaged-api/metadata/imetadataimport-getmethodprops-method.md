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
ms.openlocfilehash: 4a258ce9121a287929ca5bc39c480f1ca2596e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437461"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="3438d-102">IMetaDataImport::GetMethodProps-Methode</span><span class="sxs-lookup"><span data-stu-id="3438d-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="3438d-103">Ruft die Metadaten ab, die der Methode zugeordnet sind, auf die durch das angegebene MethodDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3438d-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3438d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3438d-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="3438d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3438d-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="3438d-106">in Das MethodDef-Token, das die Methode darstellt, für die Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3438d-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="3438d-107">vorgenommen Ein Zeiger auf ein TypeDef-Token, das den Typ darstellt, der die Methode implementiert.</span><span class="sxs-lookup"><span data-stu-id="3438d-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="3438d-108">vorgenommen Ein Zeiger auf einen Puffer, der den Methodennamen aufweist.</span><span class="sxs-lookup"><span data-stu-id="3438d-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="3438d-109">in Die angeforderte Größe `szMethod`.</span><span class="sxs-lookup"><span data-stu-id="3438d-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="3438d-110">vorgenommen Ein Zeiger auf die Größe in breit Zeichen `szMethod`oder im Fall von abschneiden die tatsächliche Anzahl der breit Zeichen im Methodennamen.</span><span class="sxs-lookup"><span data-stu-id="3438d-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="3438d-111">vorgenommen Ein Zeiger auf alle Flags, die der Methode zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3438d-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="3438d-112">vorgenommen Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="3438d-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="3438d-113">vorgenommen Ein Zeiger auf die Größe `ppvSigBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="3438d-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="3438d-114">vorgenommen Ein Zeiger auf die relative virtuelle Adresse der Methode.</span><span class="sxs-lookup"><span data-stu-id="3438d-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="3438d-115">vorgenommen Ein Zeiger auf alle Implementierungsflags für die Methode.</span><span class="sxs-lookup"><span data-stu-id="3438d-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3438d-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="3438d-116">Requirements</span></span>  
 <span data-ttu-id="3438d-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3438d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3438d-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3438d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3438d-119">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3438d-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3438d-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3438d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3438d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3438d-121">See also</span></span>

- [<span data-ttu-id="3438d-122">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3438d-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="3438d-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3438d-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
