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
ms.openlocfilehash: 6391e819d53c3ed8f0d596b15c4a2bb268f72fd5
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436281"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="0dcd7-102">IMetaDataConverter::GetMetaDataFromTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="0dcd7-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="0dcd7-103">Ruft einen Schnittstellen Zeiger auf eine [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Instanz ab, die die Metadatensignatur der Typbibliothek darstellt, die durch die angegebene `ITypeLib`-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-103">Gets an interface pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0dcd7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0dcd7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,   
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0dcd7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0dcd7-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="0dcd7-106">in Zeiger auf ein `ITypeLib` Objekt, das die Typbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="0dcd7-107">vorgenommen Ein Zeiger auf einen Speicherort, der die Adresse der `IMetaDataImport` Instanz empfängt, die die Metadatensignatur darstellt.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0dcd7-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0dcd7-108">Requirements</span></span>  
 <span data-ttu-id="0dcd7-109">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0dcd7-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0dcd7-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0dcd7-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0dcd7-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="0dcd7-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0dcd7-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0dcd7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0dcd7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0dcd7-113">See also</span></span>

- [<span data-ttu-id="0dcd7-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0dcd7-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0dcd7-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0dcd7-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
