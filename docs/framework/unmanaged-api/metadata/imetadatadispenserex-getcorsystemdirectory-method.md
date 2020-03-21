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
ms.openlocfilehash: fb673666543bea3df44005ee3b20d311524f51d0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175914"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="7238b-102">IMetaDataDispenserEx::GetCORSystemDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="7238b-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>
<span data-ttu-id="7238b-103">Ruft das Verzeichnis ab, das die aktuelle Common Language Runtime (CLR) enthält.</span><span class="sxs-lookup"><span data-stu-id="7238b-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="7238b-104">Diese Methode wird nur für die Verwendung durch Out-of-Process-Debugger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7238b-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="7238b-105">Wenn sie von einer anderen Komponente aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7238b-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7238b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7238b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7238b-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7238b-107">Parameters</span></span>  
 `szBuffer`  
 <span data-ttu-id="7238b-108">[out] Der Puffer, der den Verzeichnisnamen empfängt.</span><span class="sxs-lookup"><span data-stu-id="7238b-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7238b-109">[in] Die Größe von in `szBuffer`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="7238b-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="7238b-110">[out] Die Anzahl der Bytes, die tatsächlich in `szBuffer`zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="7238b-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7238b-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7238b-111">Requirements</span></span>  
 <span data-ttu-id="7238b-112">**Plattform:** Siehe [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7238b-112">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7238b-113">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7238b-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7238b-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7238b-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7238b-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7238b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7238b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7238b-116">See also</span></span>

- [<span data-ttu-id="7238b-117">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7238b-117">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="7238b-118">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7238b-118">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
