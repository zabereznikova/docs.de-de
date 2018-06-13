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
ms.openlocfilehash: 8954c2f6ecaf2767dd01b0601096d9e3f6df9b98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425453"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="be51e-102">IBindingDisplay::InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="be51e-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="be51e-103">Initialisiert die [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="be51e-103">Initializes the [IBindingDisplay](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be51e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be51e-104">Syntax</span></span>  
  
```  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="be51e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="be51e-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="be51e-106">[in] Der Prozessbezeichner.</span><span class="sxs-lookup"><span data-stu-id="be51e-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be51e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="be51e-107">Remarks</span></span>  
 <span data-ttu-id="be51e-108">Der Debugger Ruft die `InitializeForProcess` Methode zum Zeitpunkt der Erstellung die Bindungsanzeige zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="be51e-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="be51e-109">`InitializeForProcess` zum Zeitpunkt der Erstellung vor jeder anderen Methode aufgerufen werden muss, um auf `IBindingDisplay` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="be51e-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be51e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be51e-110">Requirements</span></span>  
 <span data-ttu-id="be51e-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be51e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be51e-112">**Header:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="be51e-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="be51e-113">**Bibliothek:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="be51e-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="be51e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be51e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be51e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be51e-115">See Also</span></span>  
 [<span data-ttu-id="be51e-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="be51e-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
