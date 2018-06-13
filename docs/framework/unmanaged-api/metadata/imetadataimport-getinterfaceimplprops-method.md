---
title: IMetaDataImport::GetInterfaceImplProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fca044b5dce260a1eed55b01531e7ae21a16ebd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446161"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a><span data-ttu-id="31cf2-102">IMetaDataImport::GetInterfaceImplProps-Methode</span><span class="sxs-lookup"><span data-stu-id="31cf2-102">IMetaDataImport::GetInterfaceImplProps Method</span></span>
<span data-ttu-id="31cf2-103">Ruft einen Zeiger auf das Metadatentoken für die <xref:System.Type> , der die angegebene Methode implementiert und für die Schnittstelle, die diese Methode deklariert.</span><span class="sxs-lookup"><span data-stu-id="31cf2-103">Gets a pointer to the metadata tokens for the <xref:System.Type> that implements the specified method, and for the interface that declares that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31cf2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31cf2-104">Syntax</span></span>  
  
```  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31cf2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31cf2-105">Parameters</span></span>  
 `iiImpl`  
 <span data-ttu-id="31cf2-106">[in] Das Metadatentoken, das die Methode, die für die Klassen- und -Token zurückgeben, darstellt.</span><span class="sxs-lookup"><span data-stu-id="31cf2-106">[in] The metadata token representing the method to return the class and interface tokens for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="31cf2-107">[out] Das Metadatentoken, das die Klasse, die die Methode darstellt.</span><span class="sxs-lookup"><span data-stu-id="31cf2-107">[out] The metadata token representing the class that implements the method.</span></span>  
  
 `ptkIface`  
 <span data-ttu-id="31cf2-108">[out] Das Metadatentoken, das die Schnittstelle, die die implementierte Methode definiert darstellt.</span><span class="sxs-lookup"><span data-stu-id="31cf2-108">[out] The metadata token representing the interface that defines the implemented method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31cf2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31cf2-109">Requirements</span></span>  
 <span data-ttu-id="31cf2-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31cf2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31cf2-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="31cf2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31cf2-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="31cf2-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31cf2-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31cf2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31cf2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31cf2-114">See Also</span></span>  
 [<span data-ttu-id="31cf2-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31cf2-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="31cf2-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="31cf2-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
