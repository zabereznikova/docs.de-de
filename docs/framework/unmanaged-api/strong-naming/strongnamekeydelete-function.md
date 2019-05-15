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
ms.openlocfilehash: 717d2104db8addf40e5187cee4cc8c46e5dc355e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636743"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="86814-102">StrongNameKeyDelete-Funktion</span><span class="sxs-lookup"><span data-stu-id="86814-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="86814-103">Löscht den angegebenen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="86814-103">Deletes the specified key container.</span></span>

<span data-ttu-id="86814-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="86814-104">This function has been deprecated.</span></span> <span data-ttu-id="86814-105">Verwenden der [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="86814-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="86814-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="86814-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="86814-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="86814-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="86814-108">[in] Der Name des Containers mit dem Schlüssel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="86814-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="86814-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="86814-109">Return Value</span></span>

<span data-ttu-id="86814-110">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="86814-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="86814-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86814-111">Remarks</span></span>

<span data-ttu-id="86814-112">Verwenden der [StrongNameKeyInstall](strongnamekeyinstall-function.md) Funktion, um ein öffentliches/privates Schlüsselpaar in einem Container zu importieren.</span><span class="sxs-lookup"><span data-stu-id="86814-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="86814-113">Wenn die `StrongNameKeyDelete` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="86814-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="86814-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86814-114">Requirements</span></span>

<span data-ttu-id="86814-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86814-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="86814-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="86814-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="86814-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="86814-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="86814-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86814-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="86814-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86814-119">See also</span></span>

- [<span data-ttu-id="86814-120">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="86814-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="86814-121">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="86814-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="86814-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86814-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
