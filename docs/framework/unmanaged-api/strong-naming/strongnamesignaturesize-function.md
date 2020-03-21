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
ms.openlocfilehash: a19d875b8fb81f2af3821e69452f0f0ed591cd22
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176889"
---
# <a name="strongnamesignaturesize-function"></a><span data-ttu-id="46d66-102">StrongNameSignatureSize-Funktion</span><span class="sxs-lookup"><span data-stu-id="46d66-102">StrongNameSignatureSize Function</span></span>
<span data-ttu-id="46d66-103">Gibt die Größe der Signatur mit starkem Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="46d66-103">Returns the size of the strong name signature.</span></span> <span data-ttu-id="46d66-104">`StrongNameSignatureSize`wird in der Regel von Compilern verwendet, um zu bestimmen, wie viel Speicherplatz in der Datei reserviert werden soll, wenn eine mit Verzögerung signierte Assembly erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="46d66-104">`StrongNameSignatureSize` is typically used by compilers to determine how much space to reserve in the file when creating a delay-signed assembly.</span></span>  
  
 <span data-ttu-id="46d66-105">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="46d66-105">This function has been deprecated.</span></span> <span data-ttu-id="46d66-106">Verwenden Sie stattdessen die [ICLRStrongName::StrongNameSignatureSize-Methode.](../hosting/iclrstrongname-strongnamesignaturesize-method.md)</span><span class="sxs-lookup"><span data-stu-id="46d66-106">Use the [ICLRStrongName::StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46d66-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="46d66-107">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="46d66-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="46d66-108">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="46d66-109">[in] Eine Struktur vom Typ [PublicKeyBlob,](publickeyblob-structure.md) die den öffentlichen Teil des Schlüsselpaars enthält, der zum Generieren der Signatur mit starkem Namen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="46d66-109">[in] A structure of type [PublicKeyBlob](publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="46d66-110">[in] Die Größe von in `pbPublicKeyBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="46d66-110">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="46d66-111">[in] Die Anzahl der Bytes, die zum Speichern der Signatur mit starkem Namen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="46d66-111">[in] The number of bytes required to store the strong name signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="46d66-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="46d66-112">Return Value</span></span>  
 <span data-ttu-id="46d66-113">`true`bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="46d66-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46d66-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="46d66-114">Remarks</span></span>  
 <span data-ttu-id="46d66-115">Wenn `StrongNameSignatureSize` die Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo-Funktion](strongnameerrorinfo-function.md) auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="46d66-115">If the `StrongNameSignatureSize` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46d66-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="46d66-116">Requirements</span></span>  
 <span data-ttu-id="46d66-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46d66-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46d66-118">**Kopfzeile:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="46d66-118">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="46d66-119">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="46d66-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46d66-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46d66-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d66-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46d66-121">See also</span></span>

- [<span data-ttu-id="46d66-122">StrongNameSignatureSize-Methode</span><span class="sxs-lookup"><span data-stu-id="46d66-122">StrongNameSignatureSize Method</span></span>](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [<span data-ttu-id="46d66-123">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46d66-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
