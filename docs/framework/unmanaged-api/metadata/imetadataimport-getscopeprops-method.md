---
title: IMetaDataImport::GetScopeProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 5a89d1406daa9a2416a708b63d88fd9005234015
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729199"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="d505a-102">IMetaDataImport::GetScopeProps-Methode</span><span class="sxs-lookup"><span data-stu-id="d505a-102">IMetaDataImport::GetScopeProps Method</span></span>

<span data-ttu-id="d505a-103">Ruft den Namen und optional den Versionsbezeichner der Assembly oder des Moduls im aktuellen Metadatenbereich ab.</span><span class="sxs-lookup"><span data-stu-id="d505a-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d505a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d505a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d505a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d505a-105">Parameters</span></span>  

 `szName`  
 <span data-ttu-id="d505a-106">vorgenommen Ein Puffer für den Assemblynamen oder den Modulnamen.</span><span class="sxs-lookup"><span data-stu-id="d505a-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d505a-107">in Die Größe in breit Zeichen von `szName` .</span><span class="sxs-lookup"><span data-stu-id="d505a-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d505a-108">vorgenommen Die Anzahl der breit Zeichen, die in zurückgegeben werden `szName` .</span><span class="sxs-lookup"><span data-stu-id="d505a-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="d505a-109">[out, optional] Ein Zeiger auf eine GUID, die die Version der Assembly oder des Moduls eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d505a-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d505a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d505a-110">Remarks</span></span>  

 <span data-ttu-id="d505a-111">Die [IMetaDataEmit:: setmoduleproperties](imetadataemit-setmoduleprops-method.md) -Methode wird verwendet, um diese Eigenschaften festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d505a-111">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d505a-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d505a-112">Requirements</span></span>  

 <span data-ttu-id="d505a-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d505a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d505a-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d505a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d505a-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d505a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d505a-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d505a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d505a-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d505a-117">See also</span></span>

- [<span data-ttu-id="d505a-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d505a-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d505a-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d505a-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
