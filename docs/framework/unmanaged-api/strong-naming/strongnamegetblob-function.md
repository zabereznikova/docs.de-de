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
ms.openlocfilehash: 2d5b3d1d39b5d4c5b7d4db073b3ffaf1c6b88373
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799103"
---
# <a name="strongnamegetblob-function"></a><span data-ttu-id="0eccd-102">StrongNameGetBlob-Funktion</span><span class="sxs-lookup"><span data-stu-id="0eccd-102">StrongNameGetBlob Function</span></span>
<span data-ttu-id="0eccd-103">Füllt den angegebenen Puffer mit der binären Darstellung der ausführbaren Datei an der angegebenen Adresse auf.</span><span class="sxs-lookup"><span data-stu-id="0eccd-103">Fills the specified buffer with the binary representation of the executable file at the specified address.</span></span>  
  
 <span data-ttu-id="0eccd-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="0eccd-104">This function has been deprecated.</span></span> <span data-ttu-id="0eccd-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameGetBlob](../hosting/iclrstrongname-strongnamegetblob-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="0eccd-105">Use the [ICLRStrongName::StrongNameGetBLob](../hosting/iclrstrongname-strongnamegetblob-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0eccd-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0eccd-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0eccd-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0eccd-107">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="0eccd-108">in Ein gültiger Pfad zur ausführbaren Datei, die geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0eccd-108">[in] A valid path to the executable file to be loaded.</span></span>  
  
 `pbBlob`  
 <span data-ttu-id="0eccd-109">in Der Puffer, in den die ausführbare Datei geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0eccd-109">[in] The buffer into which to load the executable file.</span></span>  
  
 `pcbBlob`  
 <span data-ttu-id="0eccd-110">[in, out] Die angeforderte maximale Größe von `pbBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="0eccd-110">[in, out] The requested maximum size, in bytes, of `pbBlob`.</span></span> <span data-ttu-id="0eccd-111">Bei der Rückgabe die tatsächliche Größe von `pbBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="0eccd-111">Upon return, the actual size, in bytes, of `pbBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0eccd-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0eccd-112">Return Value</span></span>  
 <span data-ttu-id="0eccd-113">`true`nach erfolgreichem Abschluss: `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="0eccd-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0eccd-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0eccd-114">Remarks</span></span>  
 <span data-ttu-id="0eccd-115">Wenn die `StrongNameGetBlob` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0eccd-115">If the `StrongNameGetBlob` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eccd-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0eccd-116">Requirements</span></span>  
 <span data-ttu-id="0eccd-117">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eccd-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eccd-118">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="0eccd-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0eccd-119">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0eccd-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0eccd-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eccd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eccd-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0eccd-121">See also</span></span>

- [<span data-ttu-id="0eccd-122">StrongNameGetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="0eccd-122">StrongNameGetBlob Method</span></span>](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [<span data-ttu-id="0eccd-123">StrongNameGetBlobFromImage-Methode</span><span class="sxs-lookup"><span data-stu-id="0eccd-123">StrongNameGetBlobFromImage Method</span></span>](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [<span data-ttu-id="0eccd-124">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0eccd-124">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
