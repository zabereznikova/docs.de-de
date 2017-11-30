---
title: StrongNameGetBlobFromImage-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameGetBlobFromImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameGetBlobFromImage
helpviewer_keywords: StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 423f874796320d1fbcda2ab642c71b7072642569
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="15029-102">StrongNameGetBlobFromImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="15029-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="15029-103">Ruft eine binäre Darstellung des Assemblyabbilds an der angegebenen Speicheradresse.</span><span class="sxs-lookup"><span data-stu-id="15029-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="15029-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="15029-104">This function has been deprecated.</span></span> <span data-ttu-id="15029-105">Verwenden der [ICLRStrongName:: StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="15029-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15029-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="15029-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15029-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="15029-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="15029-108">[in] Die Speicheradresse des zugeordneten Assemblymanifests.</span><span class="sxs-lookup"><span data-stu-id="15029-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="15029-109">[in] Die Größe in Bytes, der das Abbild `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="15029-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="15029-110">[in] Ein Puffer, die binäre Darstellung des Bilds enthält.</span><span class="sxs-lookup"><span data-stu-id="15029-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="15029-111">[in, out] Die maximale Größe in Bytes, des angeforderten `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="15029-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="15029-112">Nach der Rückgabe der tatsächlichen Größe in Bytes, der `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="15029-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15029-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="15029-113">Return Value</span></span>  
 <span data-ttu-id="15029-114">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="15029-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15029-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15029-115">Remarks</span></span>  
 <span data-ttu-id="15029-116">Wenn die `StrongNameGetBlobFromImage` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="15029-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15029-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="15029-117">Requirements</span></span>  
 <span data-ttu-id="15029-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15029-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15029-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="15029-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="15029-120">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="15029-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="15029-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15029-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15029-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15029-122">See Also</span></span>  
 [<span data-ttu-id="15029-123">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="15029-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [<span data-ttu-id="15029-124">StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="15029-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [<span data-ttu-id="15029-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="15029-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
