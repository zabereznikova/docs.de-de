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
ms.openlocfilehash: 1f45310bc65bc8614033182a81db451b79bcf97f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714717"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="9b577-102">IMetaDataConverter::GetMetaDataFromTypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="9b577-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>

<span data-ttu-id="9b577-103">Ruft einen Zeiger auf eine [IMetaDataImport](imetadataimport-interface.md) -Instanz ab, die die Metadatensignatur der Typbibliothek darstellt, auf die von der angegebenen-Instanz verwiesen wird `ITypeInfo` .</span><span class="sxs-lookup"><span data-stu-id="9b577-103">Gets a pointer to an [IMetaDataImport](imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b577-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b577-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b577-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9b577-105">Parameters</span></span>  

 `pITI`  
 <span data-ttu-id="9b577-106">in Ein Zeiger auf ein `ITypeInfo` Objekt, das auf die Typbibliothek verweist.</span><span class="sxs-lookup"><span data-stu-id="9b577-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="9b577-107">vorgenommen Ein Zeiger auf einen Speicherort, der die Adresse der- `IMetaDataImport` Instanz empfängt, die die Metadatensignatur darstellt.</span><span class="sxs-lookup"><span data-stu-id="9b577-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9b577-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9b577-108">Requirements</span></span>  

 <span data-ttu-id="9b577-109">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9b577-109">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b577-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9b577-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9b577-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="9b577-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9b577-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9b577-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b577-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9b577-113">See also</span></span>

- [<span data-ttu-id="9b577-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b577-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="9b577-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9b577-115">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
