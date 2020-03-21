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
ms.openlocfilehash: 91a19e5e15dddd446208dfa3b2c32826282067eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175394"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="bb524-102">IMetaDataImport::GetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="bb524-102">IMetaDataImport::GetFieldMarshal Method</span></span>
<span data-ttu-id="bb524-103">Ruft einen Zeiger auf den systemeigenen, nicht verwalteten Typ des Felds ab, das durch das angegebene Feldmetadatentoken dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bb524-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb524-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb524-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb524-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb524-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="bb524-106">[in] Das Metadatentoken, das das Feld darstellt, für das Interop-Marshallinginformationen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bb524-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="bb524-107">[out] Ein Zeiger auf die Metadatensignatur des systemeigenen Typs des Felds.</span><span class="sxs-lookup"><span data-stu-id="bb524-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="bb524-108">[out] Die Größe in `ppvNativeType`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="bb524-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb524-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bb524-109">Requirements</span></span>  
 <span data-ttu-id="bb524-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb524-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb524-111">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bb524-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bb524-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bb524-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bb524-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb524-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb524-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb524-114">See also</span></span>

- [<span data-ttu-id="bb524-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb524-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="bb524-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb524-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
