---
title: CreateICeeFileGen-Funktion
ms.date: 03/30/2017
api_name:
- CreateICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- CreateICeeFileGen
helpviewer_keywords:
- CreateICeeFileGen function [.NET Framework hosting]
ms.assetid: e36e1fd8-8456-4359-bdc3-3ec1765f041f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e367ab3c966cea2d875b1de5b4244db5c4b813e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702222"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="c49a3-102">CreateICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="c49a3-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="c49a3-103">Erstellt eine [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="c49a3-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="c49a3-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="c49a3-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c49a3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c49a3-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c49a3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="c49a3-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="c49a3-107">[out] Ein Zeiger auf die Adresse eines neuen `ICeeFileGen` Objekt.</span><span class="sxs-lookup"><span data-stu-id="c49a3-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c49a3-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c49a3-108">Return Value</span></span>  
 <span data-ttu-id="c49a3-109">Diese Methode gibt die standard-COM-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="c49a3-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c49a3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c49a3-110">Remarks</span></span>  
 <span data-ttu-id="c49a3-111">Die `ICeeFileGen` Objekt wird verwendet, um die common Language Runtime (CLR)-Datei (portable Executable)-Dateien erstellen.</span><span class="sxs-lookup"><span data-stu-id="c49a3-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="c49a3-112">Rufen Sie die [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) Funktion zerstört das `ICeeFileGen` Objekt nach Abschluss.</span><span class="sxs-lookup"><span data-stu-id="c49a3-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c49a3-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c49a3-113">Requirements</span></span>  
 <span data-ttu-id="c49a3-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c49a3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c49a3-115">**Header:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="c49a3-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="c49a3-116">**Bibliothek:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="c49a3-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="c49a3-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c49a3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c49a3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c49a3-118">See also</span></span>
- [<span data-ttu-id="c49a3-119">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="c49a3-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
