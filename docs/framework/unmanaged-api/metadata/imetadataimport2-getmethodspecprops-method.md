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
ms.openlocfilehash: 6b5b3b3b5a3613668f4470f48083ae010cc9d336
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445256"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="4e539-102">IMetaDataImport2::GetMethodSpecProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4e539-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="4e539-103">Ruft die Metadatensignatur der Methode ab, auf die durch das angegebene MethodSpec-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4e539-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e539-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e539-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="4e539-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e539-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="4e539-106">in Ein MethodSpec-Token, das die Instanziierung der Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="4e539-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="4e539-107">vorgenommen Ein Zeiger auf das MethodDef-oder MethodRef-Token, das die Methoden Definition darstellt.</span><span class="sxs-lookup"><span data-stu-id="4e539-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="4e539-108">vorgenommen Ein Zeiger auf die binäre Metadatensignatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="4e539-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="4e539-109">vorgenommen Die Größe `ppvSigBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="4e539-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e539-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4e539-110">Requirements</span></span>  
 <span data-ttu-id="4e539-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e539-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e539-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4e539-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e539-113">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e539-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e539-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e539-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e539-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e539-115">See also</span></span>

- [<span data-ttu-id="4e539-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e539-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="4e539-117">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e539-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
