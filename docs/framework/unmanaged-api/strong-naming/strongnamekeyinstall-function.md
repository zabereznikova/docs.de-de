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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798996"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="f08db-102">StrongNameKeyInstall-Funktion</span><span class="sxs-lookup"><span data-stu-id="f08db-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="f08db-103">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="f08db-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="f08db-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="f08db-104">This function has been deprecated.</span></span> <span data-ttu-id="f08db-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="f08db-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="f08db-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f08db-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="f08db-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f08db-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="f08db-108">in Der Name des Schlüssel Containers.</span><span class="sxs-lookup"><span data-stu-id="f08db-108">[in] The name of the key container.</span></span> <span data-ttu-id="f08db-109">`wszKeyContainer`muss eine nicht leere Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="f08db-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="f08db-110">in Das binäre Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="f08db-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="f08db-111">in Die Größe von `pbKeyBlob`in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f08db-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f08db-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f08db-112">Return Value</span></span>

<span data-ttu-id="f08db-113">`true`nach erfolgreichem Abschluss: `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="f08db-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f08db-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f08db-114">Remarks</span></span>

<span data-ttu-id="f08db-115">Verwenden Sie die [StrongNameKeyDelete](strongnamekeydelete-function.md) -Funktion, um den Schlüssel Container zu löschen.</span><span class="sxs-lookup"><span data-stu-id="f08db-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="f08db-116">Wenn die `StrongNameKeyInstall` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f08db-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="f08db-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f08db-117">Requirements</span></span>

<span data-ttu-id="f08db-118">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f08db-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f08db-119">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="f08db-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="f08db-120">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f08db-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="f08db-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f08db-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f08db-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f08db-122">See also</span></span>

- [<span data-ttu-id="f08db-123">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="f08db-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="f08db-124">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="f08db-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="f08db-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f08db-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
