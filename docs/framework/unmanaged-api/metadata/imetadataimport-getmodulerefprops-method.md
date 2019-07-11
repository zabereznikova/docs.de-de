---
title: IMetaDataImport::GetModuleRefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetModuleRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetModuleRefProps
helpviewer_keywords:
- GetModuleRefProps method [.NET Framework metadata]
- IMetaDataImport::GetModuleRefProps method [.NET Framework metadata]
ms.assetid: b558e766-4c11-4628-ae47-b4e0a1800168
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: be4408758db1cbf7839c12cb66ff395625925f69
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779018"
---
# <a name="imetadataimportgetmodulerefprops-method"></a><span data-ttu-id="5b497-102">IMetaDataImport::GetModuleRefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5b497-102">IMetaDataImport::GetModuleRefProps Method</span></span>
<span data-ttu-id="5b497-103">Ruft den Namen des Moduls ab, auf das vom angegebenen Metadatentoken verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5b497-103">Gets the name of the module referenced by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b497-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b497-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModuleRefProps (  
   [in]  mdModuleRef         mur,  
   [out] LPWSTR              szName,   
   [in]  ULONG               cchName,   
   [out] ULONG               *pchName   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b497-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b497-105">Parameters</span></span>  
 `mur`  
 <span data-ttu-id="5b497-106">[in] Das ModuleRef-Metadatentoken, das das Modul zum Abrufen von Metadateninformationen für verweist.</span><span class="sxs-lookup"><span data-stu-id="5b497-106">[in] The ModuleRef metadata token that references the module to get metadata information for.</span></span>  
  
 `szName`  
 <span data-ttu-id="5b497-107">[out] Ein Puffer, die den Namen des Moduls enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="5b497-107">[out] A buffer to hold the module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="5b497-108">[in] Die angeforderte Größe des `szName` in Breitzeichen.</span><span class="sxs-lookup"><span data-stu-id="5b497-108">[in] The requested size of `szName` in wide characters.</span></span>  
  
 `pchName`  
 <span data-ttu-id="5b497-109">[out] Die zurückgegebene Größe von `szName` in Breitzeichen.</span><span class="sxs-lookup"><span data-stu-id="5b497-109">[out] The returned size of `szName` in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b497-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b497-110">Requirements</span></span>  
 <span data-ttu-id="5b497-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b497-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b497-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5b497-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5b497-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5b497-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5b497-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b497-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b497-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b497-115">See also</span></span>

- [<span data-ttu-id="5b497-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b497-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5b497-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b497-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
