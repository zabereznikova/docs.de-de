---
title: IMetaDataImport2::GetMethodSpecProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
ms.openlocfilehash: 0bfbfec930c193ea05a01bd5bd9f46d2ec6714b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175290"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="225a7-102">IMetaDataImport2::GetMethodSpecProps-Methode</span><span class="sxs-lookup"><span data-stu-id="225a7-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="225a7-103">Ruft die Metadatensignatur der Methode ab, auf die durch das angegebene MethodSpec-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="225a7-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="225a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="225a7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="225a7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="225a7-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="225a7-106">[in] Ein MethodSpec-Token, das die Instanziierung der Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="225a7-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="225a7-107">[out] Ein Zeiger auf das MethodDef- oder MethodRef-Token, das die Methodendefinition darstellt.</span><span class="sxs-lookup"><span data-stu-id="225a7-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="225a7-108">[out] Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="225a7-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="225a7-109">[out] Die Größe von in `ppvSigBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="225a7-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="225a7-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="225a7-110">Requirements</span></span>  
 <span data-ttu-id="225a7-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="225a7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="225a7-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="225a7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="225a7-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="225a7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="225a7-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="225a7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="225a7-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="225a7-115">See also</span></span>

- [<span data-ttu-id="225a7-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="225a7-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="225a7-117">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="225a7-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
