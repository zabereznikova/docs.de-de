---
title: StrongNameKeyInstall-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyInstall
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyInstall
helpviewer_keywords: StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60044e12a884a28cb7485118a95d2bf7650723fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="66264-102">StrongNameKeyInstall-Funktion</span><span class="sxs-lookup"><span data-stu-id="66264-102">StrongNameKeyInstall Function</span></span>
<span data-ttu-id="66264-103">Importiert ein öffentliches/privates Schlüsselpaar in einen Container.</span><span class="sxs-lookup"><span data-stu-id="66264-103">Imports a public/private key pair into a container.</span></span>  
  
 <span data-ttu-id="66264-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="66264-104">This function has been deprecated.</span></span> <span data-ttu-id="66264-105">Verwenden der [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="66264-105">Use the [ICLRStrongName::StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66264-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="66264-106">Syntax</span></span>  
  
```  
BOOLEAN StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="66264-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="66264-107">Parameters</span></span>  
 `wszKeyContainer`  
 <span data-ttu-id="66264-108">[in] Der Name des Schlüsselcontainers.</span><span class="sxs-lookup"><span data-stu-id="66264-108">[in] The name of the key container.</span></span> <span data-ttu-id="66264-109">`wszKeyContainer`eine nicht leere Zeichenfolge muss sein.</span><span class="sxs-lookup"><span data-stu-id="66264-109">`wszKeyContainer` must be a non-empty string.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="66264-110">[in] Das binäre Schlüsselpaar.</span><span class="sxs-lookup"><span data-stu-id="66264-110">[in] The binary key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="66264-111">[in] Die Größe in Bytes, der `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="66264-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66264-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="66264-112">Return Value</span></span>  
 <span data-ttu-id="66264-113">`true`Bei erfolgreichem Abschluss; andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="66264-113">`true` on successful completion; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66264-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="66264-114">Remarks</span></span>  
 <span data-ttu-id="66264-115">Verwenden der [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) Funktion, um den Schlüsselcontainer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="66264-115">Use the [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) function to delete the key container.</span></span>  
  
 <span data-ttu-id="66264-116">Wenn die `StrongNameKeyInstall` Funktion nicht erfolgreich abgeschlossen wird, rufen Sie die [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) Funktion, um den letzten generierten Fehler abzurufen.</span><span class="sxs-lookup"><span data-stu-id="66264-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66264-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="66264-117">Requirements</span></span>  
 <span data-ttu-id="66264-118">**Plattformen:** WindSee [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66264-118">**Platforms:** WindSee [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66264-119">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="66264-119">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="66264-120">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="66264-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="66264-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66264-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66264-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66264-122">See Also</span></span>  
 [<span data-ttu-id="66264-123">StrongNameKeyInstall-Methode</span><span class="sxs-lookup"><span data-stu-id="66264-123">StrongNameKeyInstall Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [<span data-ttu-id="66264-124">StrongNameKeyDelete-Methode</span><span class="sxs-lookup"><span data-stu-id="66264-124">StrongNameKeyDelete Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [<span data-ttu-id="66264-125">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="66264-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
