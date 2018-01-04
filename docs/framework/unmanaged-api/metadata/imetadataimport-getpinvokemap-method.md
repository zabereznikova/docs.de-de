---
title: IMetaDataImport::GetPinvokeMap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetPinvokeMap
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a28d628040a35d309515703563239a5f802dc4a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="e37e9-102">IMetaDataImport::GetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="e37e9-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="e37e9-103">Ruft ein ModuleRef-Token zum Darstellen der Zielassembly eines PInvoke-Aufrufs ab.</span><span class="sxs-lookup"><span data-stu-id="e37e9-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e37e9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e37e9-104">Syntax</span></span>  
  
```  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e37e9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e37e9-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e37e9-106">[in] Ein FieldDef oder MethodDef-Token die Zuordnungsmetadaten PInvoke für abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e37e9-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="e37e9-107">[out] Ein Zeiger auf die Flags, die für die Zuordnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e37e9-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="e37e9-108">Dieser Wert ist eine Bitmaske aus der [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="e37e9-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="e37e9-109">[out] Der Name des Ziels nicht verwalteten DLL.</span><span class="sxs-lookup"><span data-stu-id="e37e9-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="e37e9-110">[in] Die Größe in Breitzeichen `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="e37e9-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="e37e9-111">[out] Die Anzahl der Breitzeichen, die im zurückgegebenen `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="e37e9-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="e37e9-112">[out] Ein Zeiger auf ein ModuleRef-Token, die nicht verwaltete Objekt Zielbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="e37e9-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e37e9-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e37e9-113">Requirements</span></span>  
 <span data-ttu-id="e37e9-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e37e9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e37e9-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e37e9-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e37e9-116">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e37e9-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e37e9-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e37e9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e37e9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e37e9-118">See Also</span></span>  
 [<span data-ttu-id="e37e9-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e37e9-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e37e9-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e37e9-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
