---
title: GetRawInputDevices
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: raw input [WPF]
ms.assetid: c4d37ecd-065a-4d1c-9e6c-26804ae968ca
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5229eb7e72b63f3e44f67dc750d49acbf44410da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getrawinputdevices"></a><span data-ttu-id="e36dd-102">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="e36dd-102">GetRawInputDevices</span></span>
<span data-ttu-id="e36dd-103">Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.</span><span class="sxs-lookup"><span data-stu-id="e36dd-103">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e36dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e36dd-104">Syntax</span></span>  
  
```  
HRESULT GetRawInputDevices( [out] IEnumRAWINPUTDEVICE **ppEnum );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e36dd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e36dd-105">Parameters</span></span>  
 `ppEnum`  
  
 <span data-ttu-id="e36dd-106">[out] Ein Zeiger auf ein [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) zum Aufzählen der unformatierten Eingaben Medien.</span><span class="sxs-lookup"><span data-stu-id="e36dd-106">[out] A pointer to an [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) for enumerating the raw input devices.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e36dd-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e36dd-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="e36dd-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="e36dd-108">HRESULT:</span></span>  
  
 <span data-ttu-id="e36dd-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) wird nur von PresentationHost.exe verwendet werden, wenn S_OK zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e36dd-109">S_OK - [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) will only be used by PresentationHost.exe if S_OK is returned.</span></span>  
  
 <span data-ttu-id="e36dd-110">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e36dd-110">E_NOTIMPL</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e36dd-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e36dd-111">Remarks</span></span>  
 <span data-ttu-id="e36dd-112">Eingabegeräte für Rohdaten sind Eingabegeräte wie Tastaturen, Mäuse und weniger verbreitete Geräte wie Fernbedienungen.</span><span class="sxs-lookup"><span data-stu-id="e36dd-112">Raw input devices are the set of input devices that includes keyboards, mice, and less traditional devices like remote controls.</span></span>  
  
 <span data-ttu-id="e36dd-113">Nachdem die Liste der Eingabegeräte für Rohdaten abgerufen wurde, registriert "PresentationHost.exe" diese Geräte, um WM_INPUT-Benachrichtigungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e36dd-113">Once the list of raw input devices has been retrieved, PresentationHost.exe registers with the devices to receive WM_INPUT notification messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e36dd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e36dd-114">See Also</span></span>  
 [<span data-ttu-id="e36dd-115">http://msdn.Microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.ASP</span><span class="sxs-lookup"><span data-stu-id="e36dd-115">http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp</span></span>](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputfunctions/getrawinputdevicelist.asp)  
 [<span data-ttu-id="e36dd-116">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="e36dd-116">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)
