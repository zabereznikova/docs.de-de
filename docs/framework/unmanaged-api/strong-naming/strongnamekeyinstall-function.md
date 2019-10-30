---
title: StrongNameKeyInstall-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125200"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="d446e-102">StrongNameKeyInstall-Funktion</span><span class="sxs-lookup"><span data-stu-id="d446e-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="d446e-103">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="d446e-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="d446e-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="d446e-104">This function has been deprecated.</span></span> <span data-ttu-id="d446e-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="d446e-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="d446e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="d446e-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="d446e-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="d446e-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="d446e-108">in Der Name des Schlüssel Containers.</span><span class="sxs-lookup"><span data-stu-id="d446e-108">[in] The name of the key container.</span></span> <span data-ttu-id="d446e-109">`wszKeyContainer` muss eine nicht leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="d446e-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="d446e-110">in Das binäre Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="d446e-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="d446e-111">in Die Größe `pbKeyBlob`in Byte.</span><span class="sxs-lookup"><span data-stu-id="d446e-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="d446e-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d446e-112">Return Value</span></span>

<span data-ttu-id="d446e-113">`true` nach erfolgreichem Abschluss. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d446e-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d446e-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d446e-114">Remarks</span></span>

<span data-ttu-id="d446e-115">Verwenden Sie die [StrongNameKeyDelete](strongnamekeydelete-function.md) -Funktion, um den Schlüssel Container zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d446e-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="d446e-116">Wenn die `StrongNameKeyInstall`-Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d446e-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="d446e-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d446e-117">Requirements</span></span>

<span data-ttu-id="d446e-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d446e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d446e-119">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d446e-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="d446e-120">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d446e-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="d446e-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d446e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d446e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d446e-122">See also</span></span>

- [<span data-ttu-id="d446e-123">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="d446e-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="d446e-124">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="d446e-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="d446e-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d446e-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
