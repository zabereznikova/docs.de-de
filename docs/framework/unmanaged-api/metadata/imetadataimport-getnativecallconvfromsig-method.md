---
title: IMetaDataImport::GetNativeCallConvFromSig-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetNativeCallConvFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 44b5dfb31cfe0364a745b729018be536f6be9aac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778968"
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="84792-102">IMetaDataImport::GetNativeCallConvFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="84792-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="84792-103">Ruft die systemeigene Aufrufkonvention für die Methode ab, die durch den angegebenen Signaturzeiger dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="84792-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84792-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84792-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84792-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84792-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="84792-106">[in] Ein Zeiger auf die Metadatensignatur der Methode, die Aufrufkonvention für zurück.</span><span class="sxs-lookup"><span data-stu-id="84792-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="84792-107">[in] Die Größe in Bytes der `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="84792-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="84792-108">[out] Ein Zeiger auf die systemeigene Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="84792-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84792-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84792-109">Requirements</span></span>  
 <span data-ttu-id="84792-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84792-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84792-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="84792-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84792-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="84792-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84792-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84792-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84792-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84792-114">See also</span></span>

- <xref:System.Runtime.InteropServices.CallingConvention>
- [<span data-ttu-id="84792-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84792-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="84792-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84792-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
