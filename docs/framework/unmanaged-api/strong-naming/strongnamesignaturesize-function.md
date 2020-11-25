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
ms.openlocfilehash: 6a2b3afe66f1eaa358c5f80de50f14ceb730048b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708477"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="0b245-102">StrongNameSignatureSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="0b245-102">StrongNameSignatureSize Function</span></span>

<span data-ttu-id="0b245-103">Gibt die Größe der Signatur mit starkem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="0b245-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="0b245-104">`StrongNameSignatureSize` wird in der Regel von Compilern verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert werden soll, wenn eine verzögert signierte Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0b245-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="0b245-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="0b245-105">This function has been deprecated.</span></span> <span data-ttu-id="0b245-106">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="0b245-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b245-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b245-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="0b245-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b245-108">Parameters</span></span>  

 `pbPublicKeyBlob`  
 <span data-ttu-id="0b245-109">in Eine Struktur vom Typ [PublicKeyBlob](publickeyblob-structure.md) , die den öffentlichen Teil des Schlüssel Paars enthält, das zum Generieren der starken Namens Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0b245-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="0b245-110">in Die Größe von in Bytes `pbPublicKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="0b245-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="0b245-111">in Die Anzahl der Bytes, die zum Speichern der starken Namens Signatur erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="0b245-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0b245-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0b245-112">Return Value</span></span>  

 <span data-ttu-id="0b245-113">`true` nach erfolgreichem Abschluss: andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="0b245-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b245-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0b245-114">Remarks</span></span>  

 <span data-ttu-id="0b245-115">Wenn die `StrongNameSignatureSize` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0b245-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b245-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0b245-116">Requirements</span></span>  

 <span data-ttu-id="0b245-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b245-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b245-118">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="0b245-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="0b245-119">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0b245-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b245-120">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b245-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b245-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b245-121">See also</span></span>

- [<span data-ttu-id="0b245-122">StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="0b245-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="0b245-123">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b245-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
