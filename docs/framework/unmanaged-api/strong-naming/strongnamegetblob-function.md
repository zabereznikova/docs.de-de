---
title: StrongNameGetBlob-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12daac766a09c297bfa129f69342ebad20977e7c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780134"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="52c38-102">StrongNameGetBlob-Funktion</span><span class="sxs-lookup"><span data-stu-id="52c38-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="52c38-103">Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf.</span><span class="sxs-lookup"><span data-stu-id="52c38-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="52c38-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="52c38-104">This function has been deprecated.</span></span> <span data-ttu-id="52c38-105">Verwenden der [ICLRStrongName:: StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="52c38-105">Use the [ICLRStrongName::StrongNameGetBLob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52c38-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="52c38-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52c38-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="52c38-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="52c38-108">[in] Ein gültiger Pfad zur ausführbaren Datei geladen werden.</span><span class="sxs-lookup"><span data-stu-id="52c38-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="52c38-109">[in] Der Puffer, in dem die ausführbare Datei geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="52c38-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="52c38-110">[in, out] Die maximale Größe in Bytes, des angeforderten `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="52c38-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="52c38-111">Bei der Rückgabe die tatsächliche Größe in Bytes der `pbBlob`.</span><span class="sxs-lookup"><span data-stu-id="52c38-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52c38-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="52c38-112">Return Value</span></span>  
 <span data-ttu-id="52c38-113">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="52c38-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52c38-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="52c38-114">Remarks</span></span>  
 <span data-ttu-id="52c38-115">Wenn die `StrongNameGetBlob` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="52c38-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52c38-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52c38-116">Requirements</span></span>  
 <span data-ttu-id="52c38-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52c38-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52c38-118">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="52c38-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="52c38-119">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="52c38-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="52c38-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52c38-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52c38-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52c38-121">See also</span></span>

- [<span data-ttu-id="52c38-122">StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="52c38-122">StrongNameGetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="52c38-123">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="52c38-123">StrongNameGetBlobFromImage Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="52c38-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="52c38-124">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
