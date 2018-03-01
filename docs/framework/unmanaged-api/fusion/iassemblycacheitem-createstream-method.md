---
title: IAssemblyCacheItem::CreateStream-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a24d9732a8e413b3cde0ac1c622743153ff6fd01
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iassemblycacheitemcreatestream-method"></a><span data-ttu-id="d548e-102">IAssemblyCacheItem::CreateStream-Methode</span><span class="sxs-lookup"><span data-stu-id="d548e-102">IAssemblyCacheItem::CreateStream Method</span></span>
<span data-ttu-id="d548e-103">Erstellt einen Stream mit dem angegebenen Namen und das Format an.</span><span class="sxs-lookup"><span data-stu-id="d548e-103">Creates a stream with the specified name and format.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d548e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d548e-104">Syntax</span></span>  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d548e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d548e-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="d548e-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d548e-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszStreamName`  
 <span data-ttu-id="d548e-107">[in] Der Name des zu erstellenden Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="d548e-107">[in] The name of the stream to be created.</span></span>  
  
 `dwFormat`  
 <span data-ttu-id="d548e-108">[in] Das Format der Datei, die gestreamt werden.</span><span class="sxs-lookup"><span data-stu-id="d548e-108">[in] The format of the file to be streamed.</span></span>  
  
 `dwFormatFlags`  
 <span data-ttu-id="d548e-109">[in] Format-spezifische Flags in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="d548e-109">[in] Format-specific flags defined in Fusion.idl.</span></span>  
  
 `ppIStream`  
 <span data-ttu-id="d548e-110">[out] Ein Zeiger auf die Adresse des zurückgegebenen <xref:IStream> Instanz.</span><span class="sxs-lookup"><span data-stu-id="d548e-110">[out] A pointer to the address of the returned <xref:IStream> instance.</span></span>  
  
 `puliMaxSize`  
 <span data-ttu-id="d548e-111">[in, optional] Die maximale Größe des Streams verweist `ppIStream`.</span><span class="sxs-lookup"><span data-stu-id="d548e-111">[in, optional] The maximum size of the stream referenced by `ppIStream`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d548e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d548e-112">Requirements</span></span>  
 <span data-ttu-id="d548e-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d548e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d548e-114">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d548e-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d548e-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d548e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d548e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d548e-116">See Also</span></span>  
 [<span data-ttu-id="d548e-117">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d548e-117">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
