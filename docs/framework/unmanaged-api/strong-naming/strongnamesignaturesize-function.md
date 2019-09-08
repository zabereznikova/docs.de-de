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
ms.openlocfilehash: 38f98b971e430a2c35a4c484f4f9c4bf387c640c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798958"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="60f75-102">StrongNameSignatureSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="60f75-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="60f75-103">Gibt die Größe der Signatur mit starkem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="60f75-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="60f75-104">`StrongNameSignatureSize`wird in der Regel von Compilern verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert werden soll, wenn eine verzögert signierte Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="60f75-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="60f75-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="60f75-105">This function has been deprecated.</span></span> <span data-ttu-id="60f75-106">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="60f75-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60f75-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="60f75-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="60f75-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="60f75-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="60f75-109">in Eine Struktur vom Typ [PublicKeyBlob](publickeyblob-structure.md) , die den öffentlichen Teil des Schlüssel Paars enthält, das zum Generieren der starken Namens Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="60f75-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="60f75-110">in Die Größe von `pbPublicKeyBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="60f75-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="60f75-111">in Die Anzahl der Bytes, die zum Speichern der starken Namens Signatur erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="60f75-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="60f75-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="60f75-112">Return Value</span></span>  
 <span data-ttu-id="60f75-113">`true`nach erfolgreichem Abschluss: `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="60f75-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="60f75-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="60f75-114">Remarks</span></span>  
 <span data-ttu-id="60f75-115">Wenn die `StrongNameSignatureSize` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="60f75-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60f75-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="60f75-116">Requirements</span></span>  
 <span data-ttu-id="60f75-117">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60f75-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60f75-118">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="60f75-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="60f75-119">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="60f75-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="60f75-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60f75-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f75-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60f75-121">See also</span></span>

- [<span data-ttu-id="60f75-122">StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="60f75-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="60f75-123">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60f75-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
