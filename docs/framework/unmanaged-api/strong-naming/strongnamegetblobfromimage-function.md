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
ms.openlocfilehash: b136e1fa480e53bcacfd9ea832d1dc4d1bd69f74
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162776"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="d77bb-102">StrongNameGetBlobFromImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="d77bb-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="d77bb-103">Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.</span><span class="sxs-lookup"><span data-stu-id="d77bb-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="d77bb-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="d77bb-104">This function has been deprecated.</span></span> <span data-ttu-id="d77bb-105">Verwenden der [ICLRStrongName:: StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="d77bb-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d77bb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d77bb-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d77bb-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d77bb-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="d77bb-108">[in] Die Speicheradresse des Assemblymanifests zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d77bb-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="d77bb-109">[in] Die Größe in Bytes, der das Bild am `pbBase`.</span><span class="sxs-lookup"><span data-stu-id="d77bb-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="d77bb-110">[in] Ein Puffer, die binäre Darstellung des Bilds enthält.</span><span class="sxs-lookup"><span data-stu-id="d77bb-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="d77bb-111">[in, out] Die maximale Größe in Bytes, des angeforderten `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="d77bb-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="d77bb-112">Bei der Rückgabe die tatsächliche Größe in Bytes der `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="d77bb-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d77bb-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d77bb-113">Return Value</span></span>  
 `true` <span data-ttu-id="d77bb-114">Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d77bb-114">on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d77bb-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d77bb-115">Remarks</span></span>  
 <span data-ttu-id="d77bb-116">Wenn die `StrongNameGetBlobFromImage` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d77bb-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d77bb-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d77bb-117">Requirements</span></span>  
 <span data-ttu-id="d77bb-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d77bb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d77bb-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d77bb-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d77bb-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d77bb-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="d77bb-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d77bb-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d77bb-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d77bb-122">See also</span></span>

- [<span data-ttu-id="d77bb-123">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="d77bb-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="d77bb-124">StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="d77bb-124">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="d77bb-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d77bb-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
