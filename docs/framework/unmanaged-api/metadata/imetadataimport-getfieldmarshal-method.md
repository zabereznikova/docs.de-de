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
ms.openlocfilehash: 35f73135dbeea1c79d15e0a9e9367c5d533487ce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676859"
---
# <a name="imetadataimportgetfieldmarshal-method"></a><span data-ttu-id="cbb5e-102">IMetaDataImport::GetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="cbb5e-102">IMetaDataImport::GetFieldMarshal Method</span></span>

<span data-ttu-id="cbb5e-103">Ruft einen Zeiger auf den systemeigenen, nicht verwalteten Typ des Felds ab, das durch das angegebene Feld Metadaten-Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cbb5e-103">Gets a pointer to the native, unmanaged type of the field represented by the specified field metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbb5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbb5e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFieldMarshal (  
   [in]  mdToken             tk,
   [out] PCCOR_SIGNATURE     *ppvNativeType,  
   [out] ULONG               *pcbNativeType
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbb5e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cbb5e-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="cbb5e-106">in Das Metadatentoken, das das Feld darstellt, für das Interop-Marshallinginformationen zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="cbb5e-106">[in] The metadata token that represents the field to get interop marshaling information for.</span></span>  
  
 `ppvNativeType`  
 <span data-ttu-id="cbb5e-107">vorgenommen Ein Zeiger auf die Metadatensignatur des systemeigenen Typs des Felds.</span><span class="sxs-lookup"><span data-stu-id="cbb5e-107">[out] A pointer to the metadata signature of the field's native type.</span></span>  
  
 `pcbNativeType`  
 <span data-ttu-id="cbb5e-108">vorgenommen Die Größe von in Bytes `ppvNativeType` .</span><span class="sxs-lookup"><span data-stu-id="cbb5e-108">[out] The size in bytes of `ppvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbb5e-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cbb5e-109">Requirements</span></span>  

 <span data-ttu-id="cbb5e-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbb5e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbb5e-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="cbb5e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cbb5e-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cbb5e-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cbb5e-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbb5e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb5e-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cbb5e-114">See also</span></span>

- [<span data-ttu-id="cbb5e-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbb5e-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="cbb5e-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbb5e-116">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
