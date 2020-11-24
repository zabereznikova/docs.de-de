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
ms.openlocfilehash: ea0e6f96028afc201f498119976eb87aa762a6eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681690"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a><span data-ttu-id="f1934-102">IMetaDataDispenserEx::GetCORSystemDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="f1934-102">IMetaDataDispenserEx::GetCORSystemDirectory Method</span></span>

<span data-ttu-id="f1934-103">Ruft das Verzeichnis ab, das die aktuelle Common Language Runtime (CLR) enthält.</span><span class="sxs-lookup"><span data-stu-id="f1934-103">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="f1934-104">Diese Methode wird nur für die Verwendung durch out-of-Process-debuggger unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1934-104">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="f1934-105">Wenn Sie von einer anderen Komponente aufgerufen wird, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1934-105">If called from another component, it will return E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1934-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1934-106">Syntax</span></span>  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1934-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1934-107">Parameters</span></span>  

 `szBuffer`  
 <span data-ttu-id="f1934-108">vorgenommen Der Puffer, der den Verzeichnisnamen empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="f1934-108">[out] The buffer to receive the directory name.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f1934-109">in Die Größe von in Bytes `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="f1934-109">[in] The size, in bytes, of `szBuffer`.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="f1934-110">vorgenommen Die Anzahl von Bytes, die tatsächlich in zurückgegeben werden `szBuffer` .</span><span class="sxs-lookup"><span data-stu-id="f1934-110">[out] The number of bytes actually returned in `szBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1934-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f1934-111">Requirements</span></span>  

 <span data-ttu-id="f1934-112">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1934-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1934-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f1934-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1934-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1934-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1934-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1934-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1934-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1934-116">See also</span></span>

- [<span data-ttu-id="f1934-117">IMetaDataDispenserEx-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1934-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="f1934-118">IMetaDataDispenser-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1934-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
