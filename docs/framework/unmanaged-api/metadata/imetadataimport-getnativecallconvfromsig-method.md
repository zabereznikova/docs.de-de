---
title: IMetaDataImport::GetNativeCallConvFromSig-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetNativeCallConvFromSig
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetNativeCallConvFromSig
helpviewer_keywords:
- GetNativeCallConvFromSig method [.NET Framework metadata]
- IMetaDataImport::GetNativeCallConvFromSig method [.NET Framework metadata]
ms.assetid: 50e04026-4d4a-47d9-96c1-f4677d6d938b
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56c67ad76fb3a4ce5ab2d107ff59da7a932835b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetnativecallconvfromsig-method"></a><span data-ttu-id="10097-102">IMetaDataImport::GetNativeCallConvFromSig-Methode</span><span class="sxs-lookup"><span data-stu-id="10097-102">IMetaDataImport::GetNativeCallConvFromSig Method</span></span>
<span data-ttu-id="10097-103">Ruft die native Aufrufkonvention für die Methode ab, die durch den angegebenen Signaturzeiger dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="10097-103">Gets the native calling convention for the method that is represented by the specified signature pointer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10097-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10097-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCallConvFromSig (  
   [in]  void const  *pvSig,  
   [in]  ULONG       cbSig,  
   [out] ULONG       *pCallConv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10097-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="10097-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="10097-106">[in] Ein Zeiger auf die Metadatensignatur der Methode, die Aufrufkonvention für zurück.</span><span class="sxs-lookup"><span data-stu-id="10097-106">[in] A pointer to the metadata signature of the method to return the calling convention for.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="10097-107">[in] Die Größe in Bytes des `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="10097-107">[in] The size in bytes of `pvSig`.</span></span>  
  
 `pCallConv`  
 <span data-ttu-id="10097-108">[out] Ein Zeiger auf die systemeigene Aufrufkonvention.</span><span class="sxs-lookup"><span data-stu-id="10097-108">[out] A pointer to the native calling convention.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10097-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10097-109">Requirements</span></span>  
 <span data-ttu-id="10097-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10097-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10097-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="10097-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10097-112">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="10097-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10097-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10097-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10097-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10097-114">See Also</span></span>  
 <xref:System.Runtime.InteropServices.CallingConvention>  
 [<span data-ttu-id="10097-115">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10097-115">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="10097-116">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10097-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
