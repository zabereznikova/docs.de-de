---
title: StrongNameGetBlobFromImage-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b076c39ccf40ca5b613cab94ecc75716158d97a9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780124"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="9d3d2-102">StrongNameGetBlobFromImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="9d3d2-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="9d3d2-103">Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="9d3d2-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-104">This function has been deprecated.</span></span> <span data-ttu-id="9d3d2-105">Verwenden der [ICLRStrongName:: StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d3d2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d3d2-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d3d2-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="9d3d2-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="9d3d2-108">[in] Die Speicheradresse des Assemblymanifests zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="9d3d2-109">[in] Die Größe in Bytes, der das Bild am `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="9d3d2-110">[in] Ein Puffer, die binäre Darstellung des Bilds enthält.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="9d3d2-111">[in, out] Die maximale Größe in Bytes, des angeforderten `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="9d3d2-112">Bei der Rückgabe die tatsächliche Größe in Bytes der `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d3d2-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9d3d2-113">Return Value</span></span>  
 <span data-ttu-id="9d3d2-114">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d3d2-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9d3d2-115">Remarks</span></span>  
 <span data-ttu-id="9d3d2-116">Wenn die `StrongNameGetBlobFromImage` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9d3d2-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d3d2-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9d3d2-117">Requirements</span></span>  
 <span data-ttu-id="9d3d2-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d3d2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d3d2-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="9d3d2-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="9d3d2-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9d3d2-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9d3d2-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d3d2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d3d2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d3d2-122">See also</span></span>

- [<span data-ttu-id="9d3d2-123">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="9d3d2-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="9d3d2-124">StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="9d3d2-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="9d3d2-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9d3d2-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
