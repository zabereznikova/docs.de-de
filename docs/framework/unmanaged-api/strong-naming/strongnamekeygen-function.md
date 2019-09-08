---
title: StrongNameKeyGen-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen function [.NET Framework strong naming]
ms.assetid: 883e413a-ad2f-4f7f-b1b9-aeb8fe5b65f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f062f47790136e8cd39c6751b7c75eef660c2b9a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799138"
---
# <a name="strongnamekeygen-function"></a><span data-ttu-id="c734a-102">StrongNameKeyGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="c734a-102">StrongNameKeyGen Function</span></span>
<span data-ttu-id="c734a-103">Erstellt ein neues öffentliches/privates Schlüsselpaar für die Verwendung starker Namen.</span><span class="sxs-lookup"><span data-stu-id="c734a-103">Creates a new public/private key pair for strong name use.</span></span>  
  
 <span data-ttu-id="c734a-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="c734a-104">This function has been deprecated.</span></span> <span data-ttu-id="c734a-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="c734a-105">Use the [ICLRStrongName::StrongNameKeyGen](../hosting/iclrstrongname-strongnamekeygen-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c734a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c734a-106">Syntax</span></span>  
  
```cpp  
BOOLEAN StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c734a-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c734a-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c734a-108">in Der angeforderte Schlüssel Container Name.</span><span class="sxs-lookup"><span data-stu-id="c734a-108">[in] The requested key container name.</span></span> <span data-ttu-id="c734a-109">`wszKeyContainer`muss eine nicht leere Zeichenfolge oder NULL sein, um einen temporären Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c734a-109">`wszKeyContainer` must be a non-empty string, or null to generate a temporary name.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c734a-110">in Gibt an, ob der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="c734a-110">[in] Specifies whether to leave the key registered.</span></span> <span data-ttu-id="c734a-111">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c734a-111">The following values are supported:</span></span>  
  
- <span data-ttu-id="c734a-112">0x00000000-wird verwendet `wszKeyContainer` , wenn den Wert NULL hat, um einen temporären Schlüssel Container Namen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="c734a-112">0x00000000 - Used when `wszKeyContainer` is null to generate a temporary key container name.</span></span>  
  
- <span data-ttu-id="c734a-113">0x00000001 (`SN_LEAVE_KEY`): gibt an, dass der Schlüssel registriert bleiben soll.</span><span class="sxs-lookup"><span data-stu-id="c734a-113">0x00000001 (`SN_LEAVE_KEY`) - Specifies that the key should be left registered.</span></span>  
  
 `ppbKeyBlob`  
 <span data-ttu-id="c734a-114">vorgenommen Das zurückgegebene Paar aus öffentlichem und privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c734a-114">[out] The returned public/private key pair.</span></span>  
  
 `pcbKeyBlob`  
 <span data-ttu-id="c734a-115">vorgenommen Die Größe von `ppbKeyBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="c734a-115">[out] The size, in bytes, of `ppbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c734a-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c734a-116">Return Value</span></span>  
 <span data-ttu-id="c734a-117">`true`nach erfolgreichem Abschluss: `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="c734a-117">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c734a-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c734a-118">Remarks</span></span>  
 <span data-ttu-id="c734a-119">Die `StrongNameKeyGen` -Funktion erstellt einen 1024-Bit-Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c734a-119">The `StrongNameKeyGen` function creates a 1024-bit key.</span></span> <span data-ttu-id="c734a-120">Nachdem der Schlüssel abgerufen wurde, sollten Sie die [strongnamefrebuffer](strongnamefreebuffer-function.md) -Funktion zum Freigeben des zugewiesenen Speichers abrufen.</span><span class="sxs-lookup"><span data-stu-id="c734a-120">After the key is retrieved, you should call the [StrongNameFreeBuffer](strongnamefreebuffer-function.md) function to release the allocated memory.</span></span>  
  
 <span data-ttu-id="c734a-121">Wenn die `StrongNameKeyGen` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c734a-121">If the `StrongNameKeyGen` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c734a-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c734a-122">Requirements</span></span>  
 <span data-ttu-id="c734a-123">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c734a-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c734a-124">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="c734a-124">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c734a-125">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c734a-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c734a-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c734a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c734a-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c734a-127">See also</span></span>

- [<span data-ttu-id="c734a-128">StrongNameKeyGen-Methode</span><span class="sxs-lookup"><span data-stu-id="c734a-128">StrongNameKeyGen Method</span></span>](../hosting/iclrstrongname-strongnamekeygen-method.md)
- [<span data-ttu-id="c734a-129">StrongNameKeyGenEx-Methode</span><span class="sxs-lookup"><span data-stu-id="c734a-129">StrongNameKeyGenEx Method</span></span>](../hosting/iclrstrongname-strongnamekeygenex-method.md)
- [<span data-ttu-id="c734a-130">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c734a-130">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
