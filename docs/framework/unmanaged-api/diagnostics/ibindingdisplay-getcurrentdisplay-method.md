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
ms.openlocfilehash: d52f089923d16f93345444c07ff8e0619644f2eb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725152"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="9c263-102">IBindingDisplay::GetCurrentDisplay-Methode</span><span class="sxs-lookup"><span data-stu-id="9c263-102">IBindingDisplay::GetCurrentDisplay Method</span></span>

<span data-ttu-id="9c263-103">Gibt die aktuellen Bindungs Anzeigeinformationen zurück.</span><span class="sxs-lookup"><span data-stu-id="9c263-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c263-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c263-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c263-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c263-105">Parameters</span></span>  

 `display`  
 <span data-ttu-id="9c263-106">[out, retval] Ein Zeiger auf ein SafeArray, das die Informationen zur Bindungs Anzeige enthält.</span><span class="sxs-lookup"><span data-stu-id="9c263-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9c263-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9c263-107">Remarks</span></span>  

 <span data-ttu-id="9c263-108">Die [IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) -Methode muss bereits erfolgreich sein, und das Programm muss von einem Debugger beendet werden.</span><span class="sxs-lookup"><span data-stu-id="9c263-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="9c263-109">Der Aufrufer muss den zurückgegebenen `SAFEARRAY` Speicher mithilfe von [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="9c263-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c263-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9c263-110">Requirements</span></span>  

 <span data-ttu-id="9c263-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c263-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c263-112">**Header:** Bindingdisplay. h</span><span class="sxs-lookup"><span data-stu-id="9c263-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="9c263-113">**Bibliothek:** Bindingdisplay. idl</span><span class="sxs-lookup"><span data-stu-id="9c263-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="9c263-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c263-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c263-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9c263-115">See also</span></span>

- [<span data-ttu-id="9c263-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c263-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="9c263-117">InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="9c263-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
