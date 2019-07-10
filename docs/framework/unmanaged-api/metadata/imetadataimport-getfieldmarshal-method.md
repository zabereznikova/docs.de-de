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
ms.openlocfilehash: 40d1817b9eb7f341899efddb469c7fa17a8f8c0e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782392"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="df2b1-102">IMetaDataImport::GetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="df2b1-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="df2b1-103">Ruft einen Zeiger auf den systemeigenen, nicht verwalteten Typ des Felds durch das angegebene Field-Metadatentoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="df2b1-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df2b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df2b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,   
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df2b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df2b1-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="df2b1-106">[in] Das Metadatentoken, das Feld zum Abrufen von Interop-Marshalling-Informationen darstellt.</span><span class="sxs-lookup"><span data-stu-id="df2b1-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="df2b1-107">[out] Ein Zeiger auf die Metadatensignatur der systemeigenen Typ des Felds.</span><span class="sxs-lookup"><span data-stu-id="df2b1-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="df2b1-108">[out] Die Größe in Bytes der `ppvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="df2b1-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df2b1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df2b1-109">Requirements</span></span>  
 <span data-ttu-id="df2b1-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df2b1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df2b1-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="df2b1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df2b1-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="df2b1-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df2b1-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df2b1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df2b1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="df2b1-114">See also</span></span>

- [<span data-ttu-id="df2b1-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df2b1-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="df2b1-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="df2b1-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
