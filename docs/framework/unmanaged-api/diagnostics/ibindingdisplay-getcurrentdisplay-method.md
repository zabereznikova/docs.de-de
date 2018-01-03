---
title: IBindingDisplay::GetCurrentDisplay-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IBindingDisplay.GetCurrentDisplay
api_location: diasymreader.dll
api_type: COM
f1_keywords: IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7013b07d0ebf2709d6c2b6f791960a8e7d35d678
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="8554c-102">IBindingDisplay::GetCurrentDisplay-Methode</span><span class="sxs-lookup"><span data-stu-id="8554c-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="8554c-103">Gibt die aktuelle Bindungsanzeigeinformationen zurück.</span><span class="sxs-lookup"><span data-stu-id="8554c-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8554c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8554c-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8554c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8554c-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="8554c-106">[out, Retval] Ein Zeiger auf ein SafeArray-Elements, das die Bindungsinformationen für die Anzeige enthält.</span><span class="sxs-lookup"><span data-stu-id="8554c-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8554c-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8554c-107">Remarks</span></span>  
 <span data-ttu-id="8554c-108">Die [IBindingDisplay:: InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) Methode muss zuvor war erfolgreich, und das Programm muss von einem Debugger beendet werden.</span><span class="sxs-lookup"><span data-stu-id="8554c-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="8554c-109">Der Aufrufer muss das zurückgegebene deallocate `SAFEARRAY` Arbeitsspeicher mit [SafeArrayDestroy](http://msdn.microsoft.com/en-us/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span><span class="sxs-lookup"><span data-stu-id="8554c-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](http://msdn.microsoft.com/en-us/fc94f7e7-b903-4c78-905c-54df1f8d13fa).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8554c-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8554c-110">Requirements</span></span>  
 <span data-ttu-id="8554c-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8554c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8554c-112">**Header:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="8554c-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="8554c-113">**Bibliothek:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="8554c-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="8554c-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8554c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8554c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8554c-115">See Also</span></span>  
 [<span data-ttu-id="8554c-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8554c-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 [<span data-ttu-id="8554c-117">InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="8554c-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
