---
title: ICLRMetadataLocator::GetMetadata-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
ms.openlocfilehash: f0ba2342e9704ba06dd1d3612f699298c734a5eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723518"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="33672-102">ICLRMetadataLocator::GetMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="33672-102">ICLRMetadataLocator::GetMetadata Method</span></span>

<span data-ttu-id="33672-103">Wird von den Common Language Runtime (CLR)-Datenzugriffs Diensten aufgerufen, um die Metadaten eines Bilds abzurufen.</span><span class="sxs-lookup"><span data-stu-id="33672-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33672-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33672-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33672-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="33672-105">Parameters</span></span>  

 `imagePath`  
 <span data-ttu-id="33672-106">in Eine Zeichenfolge, die den Pfad der Bilddatei angibt.</span><span class="sxs-lookup"><span data-stu-id="33672-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="33672-107">in Der Zeitstempel der Bilddatei.</span><span class="sxs-lookup"><span data-stu-id="33672-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="33672-108">in Die Größe der Bilddatei.</span><span class="sxs-lookup"><span data-stu-id="33672-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="33672-109">in Die Globally Unique Identifier des Bilds.</span><span class="sxs-lookup"><span data-stu-id="33672-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="33672-110">in Die relative virtuelle Adresse (RVA) der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="33672-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="33672-111">Die Adresse ist relativ zur Basisadresse des Images.</span><span class="sxs-lookup"><span data-stu-id="33672-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="33672-112">[in] Reserviert für zukünftige Verwendung.</span><span class="sxs-lookup"><span data-stu-id="33672-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="33672-113">in Die Größe des Puffers, in dem die Metadaten platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="33672-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="33672-114">vorgenommen Der Puffer, in den die Metadaten platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="33672-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="33672-115">vorgenommen Die Größe der Metadaten, die zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="33672-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33672-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="33672-116">Remarks</span></span>  

 <span data-ttu-id="33672-117">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="33672-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33672-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="33672-118">Requirements</span></span>  

 <span data-ttu-id="33672-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33672-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33672-120">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="33672-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="33672-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33672-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33672-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33672-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33672-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="33672-123">See also</span></span>

- [<span data-ttu-id="33672-124">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="33672-124">ICLRMetadataLocator Interface</span></span>](iclrmetadatalocator-interface.md)
