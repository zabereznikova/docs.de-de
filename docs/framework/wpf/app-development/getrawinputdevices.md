---
title: GetRawInputDevices
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
ms.openlocfilehash: 18564e0de8f88e89f8fb71d28ee3bfeccceea4ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507563"
---
# <a name="getrawinputdevices"></a><span data-ttu-id="40112-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="40112-102">GetRawInputDevices</span></span>
<span data-ttu-id="40112-103">Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.</span><span class="sxs-lookup"><span data-stu-id="40112-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="40112-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="40112-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="40112-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="40112-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="40112-106">[out] Ein Zeiger auf ein [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) zum Aufzählen der Eingabegeräte für Rohdaten.</span><span class="sxs-lookup"><span data-stu-id="40112-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="40112-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="40112-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="40112-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="40112-108">HRESULT:</span></span>  
  
 <span data-ttu-id="40112-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) wird nur von PresentationHost.exe verwendet werden, wenn S_OK zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="40112-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="40112-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="40112-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="40112-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="40112-111">Remarks</span></span>  
 <span data-ttu-id="40112-112">Eingabegeräte für Rohdaten sind Eingabegeräte wie Tastaturen, Mäuse und weniger verbreitete Geräte wie Fernbedienungen.</span><span class="sxs-lookup"><span data-stu-id="40112-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="40112-113">Nachdem die Liste der Eingabegeräte für Rohdaten abgerufen wurde, registriert "PresentationHost.exe" diese Geräte, um WM_INPUT-Benachrichtigungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="40112-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40112-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40112-114">See also</span></span>
- [<span data-ttu-id="40112-115">GetRawInputDeviceList</span><span class="sxs-lookup"><span data-stu-id="40112-115">GetRawInputDeviceList</span></span>](/windows/desktop/api/winuser/nf-winuser-getrawinputdevicelist)
- [<span data-ttu-id="40112-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="40112-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
