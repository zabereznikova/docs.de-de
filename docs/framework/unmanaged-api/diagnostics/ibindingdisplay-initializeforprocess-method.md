---
title: IBindingDisplay::InitializeForProcess-Methode
ms.date: 03/30/2017
api_name:
- IBindingDisplay.InitializeForProcess
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::InitializeForProcess
helpviewer_keywords:
- IBindingDisplay::InitializeForProcess method [.NET Framework debugging]
- InitializeForProcess method [.NET Framework debugging]
ms.assetid: 59417acb-4e59-46ad-acfe-d827e6ab6078
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa1e85751f90c34d40e88207af5c7eed2dd1bb82
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599363"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="fb99c-102">IBindingDisplay::InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="fb99c-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="fb99c-103">Initialisiert die [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="fb99c-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb99c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb99c-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb99c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fb99c-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="fb99c-106">[in] Die Prozess-ID.</span><span class="sxs-lookup"><span data-stu-id="fb99c-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb99c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb99c-107">Remarks</span></span>  
 <span data-ttu-id="fb99c-108">Der Debugger Ruft die `InitializeForProcess` Methode zum Zeitpunkt der Erstellung die Bindungsanzeige zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="fb99c-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="fb99c-109">`InitializeForProcess` muss zum Zeitpunkt der Erstellung vor jeder anderen Methode aufgerufen werden, für `IBindingDisplay` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fb99c-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb99c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb99c-110">Requirements</span></span>  
 <span data-ttu-id="fb99c-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb99c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb99c-112">**Header:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="fb99c-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="fb99c-113">**Bibliothek:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="fb99c-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="fb99c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb99c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb99c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb99c-115">See also</span></span>

- [<span data-ttu-id="fb99c-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fb99c-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
