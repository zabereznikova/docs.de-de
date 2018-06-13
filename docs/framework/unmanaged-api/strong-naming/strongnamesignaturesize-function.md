---
title: StrongNameSignatureSize-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c11de99359701bb6c3198a0b1dc18ba4318c8bc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461200"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="e49fc-102">StrongNameSignatureSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="e49fc-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="e49fc-103">Gibt die Größe der Signatur des starken Namens.</span><span class="sxs-lookup"><span data-stu-id="e49fc-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="e49fc-104">`StrongNameSignatureSize` wird in der Regel vom Compiler verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert, beim Erstellen einer Assembly verzögert signiert.</span><span class="sxs-lookup"><span data-stu-id="e49fc-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="e49fc-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="e49fc-105">This function has been deprecated.</span></span> <span data-ttu-id="e49fc-106">Verwenden der [ICLRStrongName:: StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="e49fc-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e49fc-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e49fc-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="e49fc-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="e49fc-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="e49fc-109">[in] Eine Struktur des Typs [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , enthält den öffentlichen Teil des Schlüsselpaars verwendet, um die Signatur mit starkem Namen generieren.</span><span class="sxs-lookup"><span data-stu-id="e49fc-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="e49fc-110">[in] Die Größe in Bytes, der `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="e49fc-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e49fc-111">[in] Die Anzahl der Bytes, die zum Speichern der Signatur mit starkem Namen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e49fc-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e49fc-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e49fc-112">Return Value</span></span>  
 <span data-ttu-id="e49fc-113">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="e49fc-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e49fc-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e49fc-114">Remarks</span></span>  
 <span data-ttu-id="e49fc-115">Wenn die `StrongNameSignatureSize` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e49fc-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e49fc-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e49fc-116">Requirements</span></span>  
 <span data-ttu-id="e49fc-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e49fc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e49fc-118">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="e49fc-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="e49fc-119">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e49fc-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e49fc-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e49fc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49fc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e49fc-121">See Also</span></span>  
 [<span data-ttu-id="e49fc-122">StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="e49fc-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)  
 [<span data-ttu-id="e49fc-123">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e49fc-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
