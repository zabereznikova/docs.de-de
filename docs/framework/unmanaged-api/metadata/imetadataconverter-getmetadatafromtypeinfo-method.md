---
title: IMetaDataConverter::GetMetaDataFromTypeInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataConverter.GetMetaDataFromTypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter::GetMetaDataFromTypeInfo
helpviewer_keywords:
- GetMetaDataFromTypeInfo method [.NET Framework metadata]
- IMetaDataConverter::GetMetaDataFromTypeInfo method [.NET Framework metadata]
ms.assetid: d44484bb-23a3-49c3-9e46-69d0d9ab4f0f
topic_type:
- apiref
ms.openlocfilehash: f9f3e3f196f74a7dea3c722925f1d03968688882
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009001"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="ddb9d-102">IMetaDataConverter::GetMetaDataFromTypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ddb9d-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="ddb9d-103">Ruft einen Zeiger auf eine [IMetaDataImport](imetadataimport-interface.md) -Instanz ab, die die Metadatensignatur der Typbibliothek darstellt, auf die von der angegebenen-Instanz verwiesen wird `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="ddb9d-103">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddb9d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ddb9d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddb9d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ddb9d-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="ddb9d-106">in Ein Zeiger auf ein `ITypeInfo` Objekt, das auf die Typbibliothek verweist.</span><span class="sxs-lookup"><span data-stu-id="ddb9d-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="ddb9d-107">vorgenommen Ein Zeiger auf einen Speicherort, der die Adresse der- `IMetaDataImport` Instanz empfängt, die die Metadatensignatur darstellt.</span><span class="sxs-lookup"><span data-stu-id="ddb9d-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddb9d-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ddb9d-108">Requirements</span></span>  
 <span data-ttu-id="ddb9d-109">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ddb9d-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddb9d-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ddb9d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ddb9d-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddb9d-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ddb9d-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddb9d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddb9d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddb9d-113">See also</span></span>

- [<span data-ttu-id="ddb9d-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ddb9d-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ddb9d-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ddb9d-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
