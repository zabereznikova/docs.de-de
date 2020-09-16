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
ms.openlocfilehash: db2474741012c4fd1734adafed112821c42c099c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541707"
---
# <a name="ibindingdisplaygetcurrentdisplay-method"></a><span data-ttu-id="e57b9-102">IBindingDisplay::GetCurrentDisplay-Methode</span><span class="sxs-lookup"><span data-stu-id="e57b9-102">IBindingDisplay::GetCurrentDisplay Method</span></span>
<span data-ttu-id="e57b9-103">Gibt die aktuellen Bindungs Anzeigeinformationen zurück.</span><span class="sxs-lookup"><span data-stu-id="e57b9-103">Returns the current binding display information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e57b9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e57b9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentDisplay (  
    [out, retval] SAFEARRAY(struct BindingDisplayTabControl) *display  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e57b9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e57b9-105">Parameters</span></span>  
 `display`  
 <span data-ttu-id="e57b9-106">[out, retval] Ein Zeiger auf ein SafeArray, das die Informationen zur Bindungs Anzeige enthält.</span><span class="sxs-lookup"><span data-stu-id="e57b9-106">[out, retval] A pointer to a safearray containing the binding display information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e57b9-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e57b9-107">Remarks</span></span>  
 <span data-ttu-id="e57b9-108">Die [IBindingDisplay:: InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) -Methode muss bereits erfolgreich sein, und das Programm muss von einem Debugger beendet werden.</span><span class="sxs-lookup"><span data-stu-id="e57b9-108">The [IBindingDisplay::InitializeForProcess](ibindingdisplay-initializeforprocess-method.md) method must have previously succeeded, and the program must be stopped by a debugger.</span></span>  
  
 <span data-ttu-id="e57b9-109">Der Aufrufer muss den zurückgegebenen `SAFEARRAY` Speicher mithilfe von [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy)zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="e57b9-109">The caller must deallocate the returned `SAFEARRAY` memory by using [SafeArrayDestroy](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-safearraydestroy).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e57b9-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e57b9-110">Requirements</span></span>  
 <span data-ttu-id="e57b9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e57b9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e57b9-112">**Header:** Bindingdisplay. h</span><span class="sxs-lookup"><span data-stu-id="e57b9-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="e57b9-113">**Bibliothek:** Bindingdisplay. idl</span><span class="sxs-lookup"><span data-stu-id="e57b9-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="e57b9-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e57b9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57b9-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e57b9-115">See also</span></span>

- [<span data-ttu-id="e57b9-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e57b9-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
- [<span data-ttu-id="e57b9-117">InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e57b9-117">InitializeForProcess Method</span></span>](ibindingdisplay-initializeforprocess-method.md)
