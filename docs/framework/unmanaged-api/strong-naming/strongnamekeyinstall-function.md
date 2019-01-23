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
ms.openlocfilehash: ecd52fce8033876f0599fa0ba25fae0850c0e01f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54508485"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="7dc18-102">StrongNameKeyInstall-Funktion</span><span class="sxs-lookup"><span data-stu-id="7dc18-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="7dc18-103">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="7dc18-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="7dc18-104">Diese Funktion wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="7dc18-104">This function has been deprecated.</span></span> <span data-ttu-id="7dc18-105">Verwenden der [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="7dc18-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dc18-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dc18-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7dc18-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7dc18-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="7dc18-108">[in] Der Name des Containers mit dem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="7dc18-108">[in] The name of the key container.</span></span> <span data-ttu-id="7dc18-109">`wszKeyContainer` eine nicht leere Zeichenfolge muss sein.</span><span class="sxs-lookup"><span data-stu-id="7dc18-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="7dc18-110">[in] Das binäre Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="7dc18-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="7dc18-111">[in] Die Größe in Bytes, des `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="7dc18-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7dc18-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7dc18-112">Return Value</span></span>  
 <span data-ttu-id="7dc18-113">`true` Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="7dc18-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7dc18-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7dc18-114">Remarks</span></span>  
 <span data-ttu-id="7dc18-115">Verwenden der [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) Funktion, um den Schlüsselcontainer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="7dc18-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="7dc18-116">Wenn die `StrongNameKeyInstall` Funktion nicht erfolgreich abgeschlossen wurde, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7dc18-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dc18-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7dc18-117">Requirements</span></span>  
 <span data-ttu-id="7dc18-118">**Plattformen:** WindSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dc18-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dc18-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="7dc18-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="7dc18-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7dc18-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7dc18-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dc18-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dc18-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dc18-122">See also</span></span>
- [<span data-ttu-id="7dc18-123">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="7dc18-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="7dc18-124">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="7dc18-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="7dc18-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7dc18-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
