---
title: IMetaDataTables2::GetMetaDataStreamInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
ms.openlocfilehash: 21fc79f62dba4b16a7a067dff8fb9dcc795c9d35
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708724"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="2854d-102">IMetaDataTables2::GetMetaDataStreamInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="2854d-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>

<span data-ttu-id="2854d-103">Ruft den Namen, die Größe und den Inhalt des Metadatenstreams am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="2854d-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2854d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2854d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2854d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2854d-105">Parameters</span></span>  

 `ix`  
 <span data-ttu-id="2854d-106">in Der Index des angeforderten Metadatenstreams.</span><span class="sxs-lookup"><span data-stu-id="2854d-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="2854d-107">vorgenommen Ein Zeiger auf den Namen des Streams.</span><span class="sxs-lookup"><span data-stu-id="2854d-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2854d-108">vorgenommen Ein Zeiger auf den Metadatenstream.</span><span class="sxs-lookup"><span data-stu-id="2854d-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="2854d-109">vorgenommen Die Größe von in Bytes `ppv` .</span><span class="sxs-lookup"><span data-stu-id="2854d-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2854d-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2854d-110">Requirements</span></span>  

 <span data-ttu-id="2854d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2854d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2854d-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2854d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2854d-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="2854d-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2854d-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2854d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2854d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2854d-115">See also</span></span>

- [<span data-ttu-id="2854d-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2854d-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
- [<span data-ttu-id="2854d-117">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2854d-117">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
