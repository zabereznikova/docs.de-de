---
title: ICorRuntimeHost::Start-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: ccad76e1c8a49222d4f527f8b7b18d4e40ff8cae
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83760406"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="42d43-102">ICorRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="42d43-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="42d43-103">Startet die Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="42d43-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42d43-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="42d43-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="42d43-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="42d43-105">Return Value</span></span>  
  
|<span data-ttu-id="42d43-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="42d43-106">HRESULT</span></span>|<span data-ttu-id="42d43-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="42d43-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="42d43-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="42d43-108">S_OK</span></span>|<span data-ttu-id="42d43-109">Der Vorgang wurde durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="42d43-109">The operation was successful.</span></span>|  
|<span data-ttu-id="42d43-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="42d43-110">S_FALSE</span></span>|<span data-ttu-id="42d43-111">Der Vorgang konnte nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="42d43-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="42d43-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="42d43-112">E_FAIL</span></span>|<span data-ttu-id="42d43-113">Ein unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="42d43-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="42d43-114">Wenn eine Methode E_FAIL zurückgibt, kann die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42d43-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="42d43-115">Nachfolgende Aufrufe von Hosting-APIs geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="42d43-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="42d43-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="42d43-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="42d43-117">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="42d43-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42d43-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="42d43-118">Remarks</span></span>  
 <span data-ttu-id="42d43-119">Es ist in der Regel nicht notwendig, die-Methode aufzurufen `Start` , da die CLR bei der ersten Anforderung zum Ausführen von verwaltetem Code automatisch startet.</span><span class="sxs-lookup"><span data-stu-id="42d43-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42d43-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="42d43-120">Requirements</span></span>  
 <span data-ttu-id="42d43-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42d43-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42d43-122">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="42d43-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="42d43-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="42d43-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42d43-124">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="42d43-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d43-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42d43-125">See also</span></span>

- [<span data-ttu-id="42d43-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42d43-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
