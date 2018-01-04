---
title: StrongNameKeyDelete-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyDelete
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyDelete
helpviewer_keywords: StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d3acd8ae5f330e23642a679962a04ccb4f7e8ec6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="38c46-102">StrongNameKeyDelete-Funktion</span><span class="sxs-lookup"><span data-stu-id="38c46-102">StrongNameKeyDelete Function</span></span>
<span data-ttu-id="38c46-103">Löscht den angegebenen Schlüsselcontainer.</span><span class="sxs-lookup"><span data-stu-id="38c46-103">Deletes the specified key container.</span></span>  
  
 <span data-ttu-id="38c46-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="38c46-104">This function has been deprecated.</span></span> <span data-ttu-id="38c46-105">Verwenden der [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="38c46-105">Use the [ICLRStrongName::StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38c46-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="38c46-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyDelete (  
    [in]  LPCWSTR   wszKeyContainer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38c46-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="38c46-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="38c46-108">[in] Der Name des Schlüsselcontainers zu löschen.</span><span class="sxs-lookup"><span data-stu-id="38c46-108">[in] The name of the key container to delete.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38c46-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38c46-109">Return Value</span></span>  
 <span data-ttu-id="38c46-110">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="38c46-110">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38c46-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="38c46-111">Remarks</span></span>  
 <span data-ttu-id="38c46-112">Verwenden der [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) Funktion, um ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="38c46-112">Use the [StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeyinstall-function.md) function to importa a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="38c46-113">Wenn die `StrongNameKeyDelete` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="38c46-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38c46-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38c46-114">Requirements</span></span>  
 <span data-ttu-id="38c46-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38c46-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38c46-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="38c46-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="38c46-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="38c46-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38c46-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38c46-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38c46-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38c46-119">See Also</span></span>  
 [<span data-ttu-id="38c46-120">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="38c46-120">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="38c46-121">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="38c46-121">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="38c46-122">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="38c46-122">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
