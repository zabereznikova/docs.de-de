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
ms.openlocfilehash: 8f8c0c2cb8dea8ad2b9c0040654122ef5942aca0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008390"
---
# <a name="imetadataconvertergetmetadatafromtypelib-method"></a><span data-ttu-id="609bd-102">IMetaDataConverter::GetMetaDataFromTypeLib-Methode</span><span class="sxs-lookup"><span data-stu-id="609bd-102">IMetaDataConverter::GetMetaDataFromTypeLib Method</span></span>
<span data-ttu-id="609bd-103">Ruft einen Schnittstellen Zeiger auf eine [IMetaDataImport](imetadataimport-interface.md) -Instanz ab, die die Metadatensignatur der Typbibliothek darstellt, die von der angegebenen-Instanz dargestellt wird `ITypeLib` .</span><span class="sxs-lookup"><span data-stu-id="609bd-103">Gets an interface pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library represented by the specified `ITypeLib` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="609bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="609bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeLib (  
    [in]  ITypeLib        *pITL,
    [out] IMetaDataImport **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="609bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="609bd-105">Parameters</span></span>  
 `pITL`  
 <span data-ttu-id="609bd-106">in Zeiger auf ein `ITypeLib` Objekt, das die Typbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="609bd-106">[in] Pointer to an `ITypeLib` object that represents the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="609bd-107">vorgenommen Ein Zeiger auf einen Speicherort, der die Adresse der- `IMetaDataImport` Instanz empfängt, die die Metadatensignatur darstellt.</span><span class="sxs-lookup"><span data-stu-id="609bd-107">[out] Pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="609bd-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="609bd-108">Requirements</span></span>  
 <span data-ttu-id="609bd-109">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="609bd-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="609bd-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="609bd-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="609bd-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="609bd-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="609bd-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="609bd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="609bd-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="609bd-113">See also</span></span>

- [<span data-ttu-id="609bd-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="609bd-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="609bd-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="609bd-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
