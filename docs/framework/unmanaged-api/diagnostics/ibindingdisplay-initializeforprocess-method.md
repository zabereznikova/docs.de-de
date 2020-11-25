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
ms.openlocfilehash: f9e65b49c9a3b506cba3493d81a40f2759dca781
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725145"
---
# <a name="ibindingdisplayinitializeforprocess-method"></a><span data-ttu-id="ff6bd-102">IBindingDisplay::InitializeForProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="ff6bd-102">IBindingDisplay::InitializeForProcess Method</span></span>

<span data-ttu-id="ff6bd-103">Initialisiert das [IBindingDisplay](ibindingdisplay-interface.md) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="ff6bd-103">Initializes the [IBindingDisplay](ibindingdisplay-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff6bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff6bd-104">Syntax</span></span>  
  
```cpp  
HRESULT InitializeForProcess (  
    [in] ULONG32   pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff6bd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ff6bd-105">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="ff6bd-106">in Der Prozess Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="ff6bd-106">[in] The process identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff6bd-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ff6bd-107">Remarks</span></span>  

 <span data-ttu-id="ff6bd-108">Der Debugger ruft die- `InitializeForProcess` Methode zum Erstellungs Zeitpunkt auf, um die Bindungs Anzeige zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="ff6bd-108">The debugger calls the `InitializeForProcess` method at creation time to initialize the binding display.</span></span> <span data-ttu-id="ff6bd-109">`InitializeForProcess` muss zur Erstellungszeit aufgerufen werden, bevor eine andere Methode für `IBindingDisplay` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ff6bd-109">`InitializeForProcess` must be called at creation time before any other method on `IBindingDisplay` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff6bd-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ff6bd-110">Requirements</span></span>  

 <span data-ttu-id="ff6bd-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff6bd-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff6bd-112">**Header:** Bindingdisplay. h</span><span class="sxs-lookup"><span data-stu-id="ff6bd-112">**Header:** BindingDisplay.h</span></span>  
  
 <span data-ttu-id="ff6bd-113">**Bibliothek:** Bindingdisplay. idl</span><span class="sxs-lookup"><span data-stu-id="ff6bd-113">**Library:** BindingDisplay.idl</span></span>  
  
 <span data-ttu-id="ff6bd-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff6bd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff6bd-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ff6bd-115">See also</span></span>

- [<span data-ttu-id="ff6bd-116">IBindingDisplay-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ff6bd-116">IBindingDisplay Interface</span></span>](ibindingdisplay-interface.md)
