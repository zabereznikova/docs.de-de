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
ms.openlocfilehash: a35ec4e3c3110616ac20cd31db134371838deda0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461928"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="c357f-102">StrongNameKeyDelete-Funktion</span><span class="sxs-lookup"><span data-stu-id="c357f-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="c357f-103">Löscht den angegebenen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="c357f-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="c357f-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="c357f-104">This function has been deprecated.</span></span> <span data-ttu-id="c357f-105">Verwenden der [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="c357f-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c357f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c357f-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c357f-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c357f-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="c357f-108">[in] Der Name des Schlüsselcontainers zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c357f-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c357f-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c357f-109">Return Value</span></span>  
 <span data-ttu-id="c357f-110">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="c357f-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c357f-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c357f-111">Remarks</span></span>  
 <span data-ttu-id="c357f-112">Verwenden der [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) Funktion, um ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="c357f-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="c357f-113">Wenn die `StrongNameKeyDelete` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c357f-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c357f-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c357f-114">Requirements</span></span>  
 <span data-ttu-id="c357f-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c357f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c357f-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c357f-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="c357f-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c357f-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c357f-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c357f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c357f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c357f-119">See Also</span></span>  
 [<span data-ttu-id="c357f-120">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="c357f-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="c357f-121">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="c357f-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="c357f-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c357f-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
