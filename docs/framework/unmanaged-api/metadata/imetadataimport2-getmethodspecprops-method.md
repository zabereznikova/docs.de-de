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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c35212e7d261a5b385823fdaa345f6fbd638571c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079343"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="eae60-102">IMetaDataImport2::GetMethodSpecProps-Methode</span><span class="sxs-lookup"><span data-stu-id="eae60-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="eae60-103">Ruft die Metadatensignatur der Methode verwiesen wird, vom angegebenen MethodSpec token ab.</span><span class="sxs-lookup"><span data-stu-id="eae60-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eae60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eae60-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="eae60-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eae60-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="eae60-106">[in] Ein MethodSpec-Token, das die Instanziierung der Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="eae60-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="eae60-107">[out] Ein Zeiger auf das MethodDef oder MethodRef Token, das die Definition der Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="eae60-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="eae60-108">[out] Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="eae60-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="eae60-109">[out] Die Größe in Bytes, des `ppvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="eae60-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eae60-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eae60-110">Requirements</span></span>  
 <span data-ttu-id="eae60-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eae60-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eae60-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eae60-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eae60-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="eae60-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eae60-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eae60-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eae60-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eae60-115">See also</span></span>

- [<span data-ttu-id="eae60-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eae60-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="eae60-117">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eae60-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
