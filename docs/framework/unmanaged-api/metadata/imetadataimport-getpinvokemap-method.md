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
ms.openlocfilehash: adb6a9a5f53dcfd8ada5b3aa9d75daac18d50283
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="42b7f-102">IMetaDataImport::GetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="42b7f-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="42b7f-103">Ruft ein ModuleRef-Token zum Darstellen der Zielassembly eines PInvoke-Aufrufs ab.</span><span class="sxs-lookup"><span data-stu-id="42b7f-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42b7f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42b7f-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="42b7f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="42b7f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="42b7f-106">[in] Ein FieldDef oder MethodDef-Token die Zuordnungsmetadaten PInvoke für abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="42b7f-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="42b7f-107">[out] Ein Zeiger auf die Flags, die für die Zuordnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="42b7f-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="42b7f-108">Dieser Wert ist eine Bitmaske aus der [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="42b7f-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="42b7f-109">[out] Der Name des Ziels nicht verwalteten DLL.</span><span class="sxs-lookup"><span data-stu-id="42b7f-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="42b7f-110">[in] Die Größe in Breitzeichen `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="42b7f-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="42b7f-111">[out] Die Anzahl der Breitzeichen, die im zurückgegebenen `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="42b7f-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="42b7f-112">[out] Ein Zeiger auf ein ModuleRef-Token, die nicht verwaltete Objekt Zielbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="42b7f-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42b7f-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42b7f-113">Requirements</span></span>  
 <span data-ttu-id="42b7f-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42b7f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42b7f-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="42b7f-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="42b7f-116">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="42b7f-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="42b7f-117">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42b7f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42b7f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42b7f-118">See Also</span></span>  
 [<span data-ttu-id="42b7f-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42b7f-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="42b7f-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42b7f-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
