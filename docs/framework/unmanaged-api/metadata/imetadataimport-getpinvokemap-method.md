---
title: IMetaDataImport::GetPinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2174537e9605ad35e4f6f878954e318c7032b080
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448347"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="520ec-102">IMetaDataImport::GetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="520ec-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="520ec-103">Ruft ein ModuleRef-Token zum Darstellen der Zielassembly eines PInvoke-Aufrufs ab.</span><span class="sxs-lookup"><span data-stu-id="520ec-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="520ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="520ec-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="520ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="520ec-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="520ec-106">[in] Ein FieldDef oder MethodDef-Token die Zuordnungsmetadaten PInvoke für abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="520ec-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="520ec-107">[out] Ein Zeiger auf die Flags, die für die Zuordnung verwendet.</span><span class="sxs-lookup"><span data-stu-id="520ec-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="520ec-108">Dieser Wert ist eine Bitmaske aus der [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="520ec-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="520ec-109">[out] Der Name des Ziels nicht verwalteten DLL.</span><span class="sxs-lookup"><span data-stu-id="520ec-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="520ec-110">[in] Die Größe in Breitzeichen `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="520ec-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="520ec-111">[out] Die Anzahl der Breitzeichen, die im zurückgegebenen `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="520ec-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="520ec-112">[out] Ein Zeiger auf ein ModuleRef-Token, die nicht verwaltete Objekt Zielbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="520ec-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="520ec-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="520ec-113">Requirements</span></span>  
 <span data-ttu-id="520ec-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="520ec-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="520ec-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="520ec-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="520ec-116">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="520ec-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="520ec-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="520ec-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="520ec-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="520ec-118">See Also</span></span>  
 [<span data-ttu-id="520ec-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="520ec-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="520ec-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="520ec-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
