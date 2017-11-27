---
title: IMetaDataImport::GetParamForMethodIndex-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamForMethodIndex
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cda4ffde7d38d74ddf7a81b6f0af4a556693094d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="e05aa-102">IMetaDataImport::GetParamForMethodIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="e05aa-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="e05aa-103">Ruft das Token, das einen angegebenen Parameter der Methode, die vom angegebenen MethodDef-Token dargestellt darstellt.</span><span class="sxs-lookup"><span data-stu-id="e05aa-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e05aa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e05aa-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e05aa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e05aa-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="e05aa-106">[in] Ein Token, das die Methode den ParameterToken für die zurückzugebenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="e05aa-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="e05aa-107">[in] Die Ordnungsposition in der Parameterliste, in dem der angeforderte Parameter auftritt.</span><span class="sxs-lookup"><span data-stu-id="e05aa-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="e05aa-108">Parameter werden beginnend mit einer mit der Methodenrückgabewert an Position 0 (null) nummeriert.</span><span class="sxs-lookup"><span data-stu-id="e05aa-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="e05aa-109">[out] Ein Zeiger auf ein ParamDef-Token, das den angeforderten Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="e05aa-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e05aa-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e05aa-110">Requirements</span></span>  
 <span data-ttu-id="e05aa-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e05aa-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e05aa-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e05aa-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e05aa-113">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e05aa-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e05aa-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e05aa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05aa-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e05aa-115">See Also</span></span>  
 [<span data-ttu-id="e05aa-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e05aa-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e05aa-117">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e05aa-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
