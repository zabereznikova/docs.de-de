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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b87bc814179b35f594ec8fab812055ff0182c5c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59145846"
---
# <a name="imetadataconvertergetmetadatafromtypeinfo-method"></a><span data-ttu-id="7f1b4-102">IMetaDataConverter::GetMetaDataFromTypeInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="7f1b4-102">IMetaDataConverter::GetMetaDataFromTypeInfo Method</span></span>
<span data-ttu-id="7f1b4-103">Ruft einen Zeiger auf ein [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) -Instanz, die die Metadatensignatur der Typbibliothek, auf die verwiesen wird durch das angegebene darstellt `ITypeInfo` Instanz.</span><span class="sxs-lookup"><span data-stu-id="7f1b4-103">Gets a pointer to an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) instance that represents the metadata signature of the type library referenced by the specified `ITypeInfo` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f1b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f1b4-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataFromTypeInfo (  
    [in]  ITypeInfo         *pITI,  
    [out] IMetaDataImport   **ppMDI  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f1b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f1b4-105">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="7f1b4-106">[in] Ein Zeiger auf ein `ITypeInfo` Objekt, das auf die Typbibliothek verweist.</span><span class="sxs-lookup"><span data-stu-id="7f1b4-106">[in] A pointer to an `ITypeInfo` object that refers to the type library.</span></span>  
  
 `ppMDI`  
 <span data-ttu-id="7f1b4-107">[out] Ein Zeiger auf einen Speicherort, die Adresse des empfängt, die `IMetaDataImport` Instanz, die die Signatur für die Metadaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="7f1b4-107">[out] A pointer to a location that receives the address of the `IMetaDataImport` instance that represents the metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f1b4-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7f1b4-108">Requirements</span></span>  
 <span data-ttu-id="7f1b4-109">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f1b4-109">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f1b4-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7f1b4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f1b4-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7f1b4-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7f1b4-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7f1b4-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7f1b4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f1b4-113">See also</span></span>

- [<span data-ttu-id="7f1b4-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f1b4-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7f1b4-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f1b4-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
