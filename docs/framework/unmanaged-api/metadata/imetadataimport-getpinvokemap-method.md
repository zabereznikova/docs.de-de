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
ms.openlocfilehash: e1be6079ed382b8ab27d0aec16bd725f5c5b9cb5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778907"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="7678c-102">IMetaDataImport::GetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="7678c-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="7678c-103">Ruft ein ModuleRef-Token zum Darstellen der Zielassembly eines PInvoke-Aufrufs ab.</span><span class="sxs-lookup"><span data-stu-id="7678c-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7678c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7678c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7678c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7678c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7678c-106">[in] Ein FieldDef oder MethodDef-Token zum Abrufen von Metadaten die PInvoke-Zuordnung für.</span><span class="sxs-lookup"><span data-stu-id="7678c-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="7678c-107">[out] Ein Zeiger auf Bitflags, die für die Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="7678c-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="7678c-108">Dieser Wert ist eine Bitmaske aus der [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="7678c-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="7678c-109">[out] Der Name des nicht verwalteten Ziel-DLL.</span><span class="sxs-lookup"><span data-stu-id="7678c-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="7678c-110">[in] Die Größe in Breitzeichen `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="7678c-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="7678c-111">[out] Die Anzahl der Breitzeichen, die in zurückgegebenen `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="7678c-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="7678c-112">[out] Ein Zeiger auf ein ModuleRef-Token, die nicht verwaltete Objekt Zielbibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="7678c-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7678c-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7678c-113">Requirements</span></span>  
 <span data-ttu-id="7678c-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7678c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7678c-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7678c-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7678c-116">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7678c-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7678c-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7678c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7678c-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7678c-118">See also</span></span>

- [<span data-ttu-id="7678c-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7678c-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7678c-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7678c-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
