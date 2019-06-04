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
ms.openlocfilehash: 57163ccfcc6dff343a8bbc7d63564ae6b57b5ff6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490505"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="4bc77-102">CreateICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="4bc77-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="4bc77-103">Erstellt eine [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="4bc77-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="4bc77-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="4bc77-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bc77-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4bc77-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bc77-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4bc77-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="4bc77-107">[out] Ein Zeiger auf die Adresse eines neuen `ICeeFileGen` Objekt.</span><span class="sxs-lookup"><span data-stu-id="4bc77-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4bc77-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4bc77-108">Return Value</span></span>  
 <span data-ttu-id="4bc77-109">Diese Methode gibt die standard-COM-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="4bc77-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4bc77-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4bc77-110">Remarks</span></span>  
 <span data-ttu-id="4bc77-111">Die `ICeeFileGen` Objekt wird verwendet, um die common Language Runtime (CLR)-Datei (portable Executable)-Dateien erstellen.</span><span class="sxs-lookup"><span data-stu-id="4bc77-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="4bc77-112">Rufen Sie die [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) Funktion zerstört das `ICeeFileGen` Objekt nach Abschluss.</span><span class="sxs-lookup"><span data-stu-id="4bc77-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bc77-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4bc77-113">Requirements</span></span>  
 <span data-ttu-id="4bc77-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4bc77-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bc77-115">**Header:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="4bc77-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="4bc77-116">**Bibliothek:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="4bc77-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="4bc77-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bc77-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bc77-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4bc77-118">See also</span></span>

- [<span data-ttu-id="4bc77-119">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="4bc77-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
