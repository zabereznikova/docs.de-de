---
title: IBindingDisplay::GetCurrentDisplay-Methode
ms.date: 03/30/2017
api_name:
- IBindingDisplay.GetCurrentDisplay
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- IBindingDisplay::GetCurrentDisplay
helpviewer_keywords:
- IBindingDisplay::GetCurrentDisplay method [.NET Framework debugging]
- GetCurrentDisplay method [.NET Framework debugging]
ms.assetid: d28eeea4-c4e0-40d4-91de-198d98cfa13c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 472e06c3a00762a7bb012fbcb525d8e0b3a9271a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61599519"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="29741-102">IBindingDisplay::GetCurrentDisplay-Methode</span><span class="sxs-lookup"><span data-stu-id="29741-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="29741-103">Gibt die aktuelle Bindungsanzeigeinformationen zurück.</span><span class="sxs-lookup"><span data-stu-id="29741-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29741-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="29741-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29741-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="29741-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="29741-106">[Out, Retval] Ein Zeiger auf ein Safearray, das die Bindungsinformationen für die Anzeige enthält.</span><span class="sxs-lookup"><span data-stu-id="29741-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="29741-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="29741-107">Remarks</span></span>  
 <span data-ttu-id="29741-108">Die [IBindingDisplay:: InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) Methode muss zuvor erfolgreich ausgeführt, und das Programm von einem Debugger beendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="29741-108">The [IBindingDisplay::InitializeForProcess](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="29741-109">Der Aufrufer muss das zurückgegebene freigeben `SAFEARRAY` Arbeitsspeicher mit ["SafeArrayDestroy"](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span><span class="sxs-lookup"><span data-stu-id="29741-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="29741-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="29741-110">Requirements</span></span>  
 <span data-ttu-id="29741-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="29741-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="29741-112">**Header:** BindingDisplay.h</span><span class="sxs-lookup"><span data-stu-id="29741-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="29741-113">**Bibliothek:** BindingDisplay.idl</span><span class="sxs-lookup"><span data-stu-id="29741-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="29741-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="29741-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29741-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29741-115">See also</span></span>

- [<span data-ttu-id="29741-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="29741-116">IBindingDisplay Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)
- [<span data-ttu-id="29741-117">InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="29741-117">InitializeForProcess Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-initializeforprocess-method.md)
