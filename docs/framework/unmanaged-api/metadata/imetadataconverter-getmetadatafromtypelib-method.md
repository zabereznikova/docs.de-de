---
title: IMetaDataConverter::GetMetaDataFromTypeLib-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeLib
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib
helpviewer_keywords:
- IMetaDataConverter::GetMetaDataFromTypeLib method [.NET Framework metadata]
- GetMetaDataFromTypeLib method [.NET Framework metadata]
ms.assetid: 97dc3a56-adfa-431f-889e-06a35ac84d51
topic_type:
- apiref
ms.openlocfilehash: 09a1605deda5b51be604c3b8f0c69fa5adcf9dc0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175953"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="0835f-102">IMetaDataConverter::GetMetaDataFromTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="0835f-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="0835f-103">Ruft einen Schnittstellenzeiger auf eine [IMetaDataImport-Instanz](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) ab, die die `ITypeLib` Metadatensignatur der Typbibliothek darstellt, die von der angegebenen Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0835f-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0835f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0835f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0835f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0835f-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="0835f-106">[in] Zeiger auf `ITypeLib` ein Objekt, das die Typbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="0835f-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="0835f-107">[out] Zeiger auf einen Speicherort, der `IMetaDataImport` die Adresse der Instanz empfängt, die die Metadatensignatur darstellt.</span><span class="sxs-lookup"><span data-stu-id="0835f-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0835f-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0835f-108">Requirements</span></span>  
 <span data-ttu-id="0835f-109">**Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0835f-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0835f-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0835f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0835f-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0835f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0835f-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0835f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0835f-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0835f-113">See also</span></span>

- [<span data-ttu-id="0835f-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0835f-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0835f-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0835f-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
