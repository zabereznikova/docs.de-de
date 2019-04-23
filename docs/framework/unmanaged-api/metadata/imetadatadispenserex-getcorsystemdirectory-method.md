---
title: IMetaDataDispenserEx::GetCORSystemDirectory-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3dbfca942d61cd5667293d11f358f06bd000fa2e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59118000"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="5bfde-102">IMetaDataDispenserEx::GetCORSystemDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="5bfde-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="5bfde-103">Ruft das Verzeichnis, das die aktuelle common Language Runtime (CLR enthält) ab.</span><span class="sxs-lookup"><span data-stu-id="5bfde-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="5bfde-104">Diese Methode wird nur für die Verwendung von Out-of-Process-Debugger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5bfde-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="5bfde-105">Wenn aus einer anderen Komponente aufgerufen wird, wird er E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5bfde-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bfde-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bfde-106">Syntax</span></span>  
  
```  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,   
    [in]  DWORD       cchBuffer,   
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bfde-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="5bfde-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="5bfde-108">[out] Der Puffer, der den Namen des Verzeichnisses erhalten.</span><span class="sxs-lookup"><span data-stu-id="5bfde-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="5bfde-109">[in] Die Größe in Bytes, des `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="5bfde-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="5bfde-110">[out] Die Anzahl der Bytes, die tatsächlich im zurückgegebenen `szBuffer`.</span><span class="sxs-lookup"><span data-stu-id="5bfde-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bfde-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5bfde-111">Requirements</span></span>  
 <span data-ttu-id="5bfde-112">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bfde-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bfde-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5bfde-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5bfde-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5bfde-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bfde-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bfde-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bfde-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bfde-116">See also</span></span>

- [<span data-ttu-id="5bfde-117">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bfde-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="5bfde-118">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bfde-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
