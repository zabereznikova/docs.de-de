---
title: IMetaDataImport::GetFieldMarshal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetFieldMarshal
helpviewer_keywords:
- GetFieldMarshal method [.NET Framework metadata]
- IMetaDataImport::GetFieldMarshal method [.NET Framework metadata]
ms.assetid: 4e2d88c6-8a3a-4fbe-900b-b4f4c06bf6bf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3bc90a17a0469cd716c1e3e990b5c0fb2ff8bf5a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647573"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="9fe6e-102">IMetaDataImport::GetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="9fe6e-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="9fe6e-103">Ruft einen Zeiger auf den systemeigenen, nicht verwalteten Typ des Felds durch das angegebene Field-Metadatentoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9fe6e-104">Syntax</span></span>  
  
```  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9fe6e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9fe6e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9fe6e-106">[in] Das Metadatentoken, das Feld zum Abrufen von Interop-Marshalling-Informationen darstellt.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="9fe6e-107">[out] Ein Zeiger auf die Metadatensignatur der systemeigenen Typ des Felds.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="9fe6e-108">[out] Die Größe in Bytes der `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="9fe6e-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fe6e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9fe6e-109">Requirements</span></span>  
 <span data-ttu-id="9fe6e-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fe6e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe6e-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9fe6e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9fe6e-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9fe6e-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9fe6e-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe6e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe6e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9fe6e-114">See also</span></span>
- [<span data-ttu-id="9fe6e-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fe6e-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9fe6e-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9fe6e-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
