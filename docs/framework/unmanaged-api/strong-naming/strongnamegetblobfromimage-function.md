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
ms.openlocfilehash: 86b99b29a85f498a6bfa0363a446bf589876bff9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799082"
---
# <a name="strongnamegetblobfromimage-function"></a><span data-ttu-id="8c4d1-102">StrongNameGetBlobFromImage-Funktion</span><span class="sxs-lookup"><span data-stu-id="8c4d1-102">StrongNameGetBlobFromImage Function</span></span>
<span data-ttu-id="8c4d1-103">Ruft eine binäre Darstellung des Assemblyimages an der angegebenen Speicheradresse ab.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-103">Gets a binary representation of the assembly image at the specified memory address.</span></span>  
  
 <span data-ttu-id="8c4d1-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-104">This function has been deprecated.</span></span> <span data-ttu-id="8c4d1-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-105">Use the [ICLRStrongName::StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c4d1-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c4d1-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c4d1-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c4d1-107">Parameters</span></span>  
 `pbBase`  
 <span data-ttu-id="8c4d1-108">in Die Speicheradresse des zugeordneten Assemblymanifests.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-108">[in] The memory address of the mapped assembly manifest.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="8c4d1-109">in Die Größe des Bilds `pbBase`in Bytes in.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-109">[in] The size, in bytes, of the image at `pbBase`.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="8c4d1-110">in Ein Puffer, der die binäre Darstellung des Bilds enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-110">[in] A buffer to contain the binary representation of the image.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="8c4d1-111">[in, out] Die angeforderte maximale Größe von `pbBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-111">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="8c4d1-112">Bei der Rückgabe die tatsächliche Größe von `pbBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-112">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c4d1-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8c4d1-113">Return Value</span></span>  
 <span data-ttu-id="8c4d1-114">`true`nach erfolgreichem Abschluss: `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-114">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c4d1-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8c4d1-115">Remarks</span></span>  
 <span data-ttu-id="8c4d1-116">Wenn die `StrongNameGetBlobFromImage` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8c4d1-116">If the `StrongNameGetBlobFromImage` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c4d1-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c4d1-117">Requirements</span></span>  
 <span data-ttu-id="8c4d1-118">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c4d1-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c4d1-119">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="8c4d1-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="8c4d1-120">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8c4d1-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8c4d1-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c4d1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c4d1-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c4d1-122">See also</span></span>

- [<span data-ttu-id="8c4d1-123">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="8c4d1-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="8c4d1-124">StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="8c4d1-124">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="8c4d1-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c4d1-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
