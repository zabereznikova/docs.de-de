---
title: StrongNameKeyDelete-Funktion
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799021"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="19b86-102">StrongNameKeyDelete-Funktion</span><span class="sxs-lookup"><span data-stu-id="19b86-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="19b86-103">Löscht den angegebenen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="19b86-103">Deletes the specified key container.</span></span>

<span data-ttu-id="19b86-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="19b86-104">This function has been deprecated.</span></span> <span data-ttu-id="19b86-105">Verwenden Sie stattdessen die [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="19b86-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="19b86-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="19b86-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="19b86-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="19b86-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="19b86-108">in Der Name des zu löschenden Schlüssel Containers.</span><span class="sxs-lookup"><span data-stu-id="19b86-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="19b86-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="19b86-109">Return Value</span></span>

<span data-ttu-id="19b86-110">`true`nach erfolgreichem Abschluss: `false`andernfalls.</span><span class="sxs-lookup"><span data-stu-id="19b86-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="19b86-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="19b86-111">Remarks</span></span>

<span data-ttu-id="19b86-112">Verwenden Sie die [StrongNameKeyInstall](strongnamekeyinstall-function.md) -Funktion, um ein öffentliches/privates Schlüsselpaar in einen Container zu importieren.</span><span class="sxs-lookup"><span data-stu-id="19b86-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="19b86-113">Wenn die `StrongNameKeyDelete` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) -Funktion auf, um den zuletzt generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="19b86-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="19b86-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19b86-114">Requirements</span></span>

<span data-ttu-id="19b86-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19b86-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="19b86-116">**Header:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="19b86-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="19b86-117">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="19b86-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="19b86-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19b86-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="19b86-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19b86-119">See also</span></span>

- [<span data-ttu-id="19b86-120">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="19b86-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="19b86-121">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="19b86-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="19b86-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19b86-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
