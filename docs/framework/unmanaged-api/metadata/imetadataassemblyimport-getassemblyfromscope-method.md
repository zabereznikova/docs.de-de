---
title: IMetaDataAssemblyImport::GetAssemblyFromScope-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyFromScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyFromScope method [.NET Framework metadata]
- GetAssemblyFromScope method [.NET Framework metadata]
ms.assetid: 0b437f70-561d-48c7-abe0-0cb9ace10c08
topic_type:
- apiref
ms.openlocfilehash: 953aa16566c2a15939fbd556f478bbdb3c0c77d0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448237"
---
# <a name="imetadataassemblyimportgetassemblyfromscope-method"></a><span data-ttu-id="1c060-102">IMetaDataAssemblyImport::GetAssemblyFromScope-Methode</span><span class="sxs-lookup"><span data-stu-id="1c060-102">IMetaDataAssemblyImport::GetAssemblyFromScope Method</span></span>
<span data-ttu-id="1c060-103">Ruft einen Zeiger auf die Assembly im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="1c060-103">Gets a pointer to the assembly in the current scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c060-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c060-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyFromScope (  
    [out] mdAssembly  *ptkAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1c060-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c060-105">Parameters</span></span>  
 `ptkAssembly`  
 <span data-ttu-id="1c060-106">vorgenommen Ein Zeiger auf das abgerufene `mdAssembly` Token, das die Assembly identifiziert.</span><span class="sxs-lookup"><span data-stu-id="1c060-106">[out] A pointer to the retrieved `mdAssembly` token that identifies the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c060-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1c060-107">Requirements</span></span>  
 <span data-ttu-id="1c060-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c060-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c060-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1c060-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1c060-110">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c060-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1c060-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c060-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c060-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c060-112">See also</span></span>

- [<span data-ttu-id="1c060-113">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1c060-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
