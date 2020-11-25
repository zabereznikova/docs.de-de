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
ms.openlocfilehash: c34215f48190e60bd1a851f31b8b23f09491f4e1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729238"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="64719-102">IMetaDataImport::GetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="64719-102">IMetaDataImport::GetPinvokeMap Method</span></span>

<span data-ttu-id="64719-103">Ruft ein ModuleRef-Token zum Darstellen der Zielassembly eines PInvoke-Aufrufs ab.</span><span class="sxs-lookup"><span data-stu-id="64719-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64719-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64719-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="64719-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="64719-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="64719-106">in Ein FieldDef-oder MethodDef-Token, für das die PInvoke-Mapping-Metadaten zu erhalten sind.</span><span class="sxs-lookup"><span data-stu-id="64719-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="64719-107">vorgenommen Ein Zeiger auf Flags, die für die Zuordnung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="64719-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="64719-108">Dieser Wert ist eine Bitmaske aus der [CorPinvokeMap](corpinvokemap-enumeration.md) -Enumeration.</span><span class="sxs-lookup"><span data-stu-id="64719-108">This value is a bitmask from the [CorPinvokeMap](corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="64719-109">vorgenommen Der Name der nicht verwalteten Ziel-dll.</span><span class="sxs-lookup"><span data-stu-id="64719-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="64719-110">in Die Größe in breit Zeichen von `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="64719-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="64719-111">vorgenommen Die Anzahl der breit Zeichen, die in zurückgegeben werden `szImportName` .</span><span class="sxs-lookup"><span data-stu-id="64719-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="64719-112">vorgenommen Ein Zeiger auf ein ModuleRef-Token, das die nicht verwaltete Zielobjekt Bibliothek darstellt.</span><span class="sxs-lookup"><span data-stu-id="64719-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64719-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="64719-113">Requirements</span></span>  

 <span data-ttu-id="64719-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64719-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64719-115">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="64719-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64719-116">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="64719-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64719-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64719-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64719-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64719-118">See also</span></span>

- [<span data-ttu-id="64719-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64719-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="64719-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="64719-120">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
