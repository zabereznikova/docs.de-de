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
ms.openlocfilehash: b5e4e2a817abff7b0cf24223b7f245fc6f86c1d9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544990"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="fd6e9-102">StrongNameSignatureSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="fd6e9-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="fd6e9-103">Gibt die Größe der Signatur mit starkem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="fd6e9-104">`StrongNameSignatureSize` wird normalerweise vom Compiler verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert, beim Erstellen einer mit Verzögerung signierten Assembly.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="fd6e9-105">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-105">This function has been deprecated.</span></span> <span data-ttu-id="fd6e9-106">Verwenden der [ICLRStrongName:: StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-106">Use the [ICLRStrongName::StrongNameSignatureSize](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd6e9-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd6e9-107">Syntax</span></span>  
  
```  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd6e9-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd6e9-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="fd6e9-109">[in] Eine Struktur des Typs [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) , enthält den öffentlichen Teil des Schlüsselpaars verwendet, um die Signatur mit starkem Namen generieren.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-109">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="fd6e9-110">[in] Die Größe in Bytes, des `pbPublicKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="fd6e9-111">[in] Die Anzahl der Bytes, die zum Speichern der Signatur mit starkem Namen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fd6e9-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fd6e9-112">Return Value</span></span>  
 <span data-ttu-id="fd6e9-113">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd6e9-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd6e9-114">Remarks</span></span>  
 <span data-ttu-id="fd6e9-115">Wenn die `StrongNameSignatureSize` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="fd6e9-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd6e9-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd6e9-116">Requirements</span></span>  
 <span data-ttu-id="fd6e9-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd6e9-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd6e9-118">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="fd6e9-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="fd6e9-119">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fd6e9-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fd6e9-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd6e9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd6e9-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd6e9-121">See also</span></span>
- [<span data-ttu-id="fd6e9-122">StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="fd6e9-122">StrongNameSignatureSize Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="fd6e9-123">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd6e9-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
