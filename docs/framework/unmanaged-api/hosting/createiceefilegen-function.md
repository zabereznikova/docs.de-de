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
ms.openlocfilehash: 566f73335861a8eb769b21a254e0e93b51a78d02
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756389"
---
# <a name="createiceefilegen-function"></a><span data-ttu-id="8eb33-102">CreateICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="8eb33-102">CreateICeeFileGen Function</span></span>
<span data-ttu-id="8eb33-103">Erstellt eine [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="8eb33-103">Creates an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="8eb33-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="8eb33-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8eb33-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8eb33-105">Syntax</span></span>  
  
```  
HRESULT CreateICeeFileGen (  
    [out] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8eb33-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8eb33-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="8eb33-107">[out] Ein Zeiger auf die Adresse eines neuen `ICeeFileGen` Objekt.</span><span class="sxs-lookup"><span data-stu-id="8eb33-107">[out] A pointer to the address of a new `ICeeFileGen` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8eb33-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8eb33-108">Return Value</span></span>  
 <span data-ttu-id="8eb33-109">Diese Methode gibt die standard-COM-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="8eb33-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8eb33-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8eb33-110">Remarks</span></span>  
 <span data-ttu-id="8eb33-111">Die `ICeeFileGen` Objekt wird verwendet, um die common Language Runtime (CLR)-Datei (portable Executable)-Dateien erstellen.</span><span class="sxs-lookup"><span data-stu-id="8eb33-111">The `ICeeFileGen` object is used to create common language runtime (CLR) portable executable (PE) files.</span></span>  
  
 <span data-ttu-id="8eb33-112">Rufen Sie die [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) Funktion zerstört das `ICeeFileGen` Objekt nach Abschluss.</span><span class="sxs-lookup"><span data-stu-id="8eb33-112">Call the [DestroyICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/destroyiceefilegen-function.md) function to destroy the `ICeeFileGen` object when finished.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8eb33-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8eb33-113">Requirements</span></span>  
 <span data-ttu-id="8eb33-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8eb33-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8eb33-115">**Header:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="8eb33-115">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="8eb33-116">**Bibliothek:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="8eb33-116">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="8eb33-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8eb33-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8eb33-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8eb33-118">See also</span></span>

- [<span data-ttu-id="8eb33-119">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="8eb33-119">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
