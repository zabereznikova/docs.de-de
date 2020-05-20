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
ms.openlocfilehash: 8645878132359b6218cd62b1ff707208de53704b
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/16/2020
ms.locfileid: "83442149"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="e3d5a-102">IBindingDisplay::InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e3d5a-102">IBindingDisplay::InitializeForProcess Method</span></span>
<span data-ttu-id="e3d5a-103">Initialisiert das [IBindingDisplay](ibindingdisplay-interface.md) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="e3d5a-103">Initializes the [IBindingDisplay](ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3d5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e3d5a-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3d5a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e3d5a-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="e3d5a-106">in Der Prozess Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="e3d5a-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3d5a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e3d5a-107">Remarks</span></span>  
 <span data-ttu-id="e3d5a-108">Der Debugger ruft die- `InitializeForProcess` Methode zum Erstellungs Zeitpunkt auf, um die Bindungs Anzeige zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="e3d5a-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="e3d5a-109">`InitializeForProcess`muss zur Erstellungszeit aufgerufen werden, bevor eine andere Methode für `IBindingDisplay` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e3d5a-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3d5a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e3d5a-110">Requirements</span></span>  
 <span data-ttu-id="e3d5a-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3d5a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3d5a-112">**Header:** Bindingdisplay. h</span><span class="sxs-lookup"><span data-stu-id="e3d5a-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="e3d5a-113">**Bibliothek:** Bindingdisplay. idl</span><span class="sxs-lookup"><span data-stu-id="e3d5a-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="e3d5a-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3d5a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d5a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3d5a-115">See also</span></span>

- [<span data-ttu-id="e3d5a-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e3d5a-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
