---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 1a22071696ca012968e042e15cd8a9f4b876fd9f
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45668339"
---
# <a name="filterinputmessage"></a><span data-ttu-id="3d736-102">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="3d736-102">FilterInputMessage</span></span>
<span data-ttu-id="3d736-103">Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3d736-103">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d736-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d736-104">Syntax</span></span>  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3d736-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d736-105">Parameters</span></span>  
 `pMsg`  
  
 <span data-ttu-id="3d736-106">[in] Die WM_INPUT-Meldung, die an das Fenster gesendet wurde, das die unformatierte Eingabe erhält.</span><span class="sxs-lookup"><span data-stu-id="3d736-106">[in] The WM_INPUT message sent to the window that is getting raw input.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3d736-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3d736-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="3d736-108">HRESULT:</span><span class="sxs-lookup"><span data-stu-id="3d736-108">HRESULT:</span></span>  
  
 <span data-ttu-id="3d736-109">S_OK – Der Filter hat die Meldung nicht verarbeitet, und weitere Verarbeitungsschritte können folgen.</span><span class="sxs-lookup"><span data-stu-id="3d736-109">S_OK - The filter did not process the message and further processing may occur.</span></span>  
  
 <span data-ttu-id="3d736-110">S_FALSE – Der Filter hat diese Meldung verarbeitet, und es sollten keine weiteren Verarbeitungsschritte folgen.</span><span class="sxs-lookup"><span data-stu-id="3d736-110">S_FALSE - The filter processed this message and no further processing should occur.</span></span>  
  
 <span data-ttu-id="3d736-111">E_NOTIMPL – bei diesem Wert zurückgegeben wird, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) nicht erneut aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3d736-111">E_NOTIMPL – If this value is returned, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) is not called again.</span></span> <span data-ttu-id="3d736-112">Dieser Wert wird möglicherweise von einer Hostanwendung zurückgegeben, die nur daran interessiert ist, benutzerdefinierte Status- und Fehlerbenutzeroberflächen für "PresentationHost.exe" bereitzustellen, und nicht dafür vorgesehen ist, unformatierte Eingabemeldungen von "PresentationHost.exe" weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="3d736-112">This might be returned from a host application that is only interested in providing custom progress and error user interfaces to PresentationHost.exe is not interested in being forwarded raw input messages from PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d736-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d736-113">Remarks</span></span>  
 <span data-ttu-id="3d736-114">"PresentationHost.exe" ist das Ziel von verschiedenen Geräten für unformatierte Eingabe, einschließlich Tastatur, Mäusen und Fernsteuerungen.</span><span class="sxs-lookup"><span data-stu-id="3d736-114">PresentationHost.exe is the target of various raw input devices, including keyboard, mice, and remote controls.</span></span> <span data-ttu-id="3d736-115">Manchmal hängt das Verhalten in der Hostanwendung von einer Eingabe ab, die andernfalls von "PresentationHost.exe" verarbeitet werden würde.</span><span class="sxs-lookup"><span data-stu-id="3d736-115">Sometimes, behavior in the host application is dependent on input that would otherwise be consumed by PresentationHost.exe.</span></span> <span data-ttu-id="3d736-116">Beispielsweise kann für eine Hostanwendung das Empfangen bestimmter Eingabemeldungen erforderlich sein, um bestimmen zu können, ob bestimmte Elemente der Benutzeroberfläche angezeigt werden sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="3d736-116">For example, a host application may depend on receiving certain input messages to determine whether or not to display specific user interface elements.</span></span>  
  
 <span data-ttu-id="3d736-117">Damit die hostanwendung diese Verhaltensweisen zu den erforderlichen eingabemeldungen empfangen kann, leitet PresentationHost.exe an die gehostete Anwendung entsprechende unformatierte eingabemeldungen durch Aufrufen von [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span><span class="sxs-lookup"><span data-stu-id="3d736-117">To allow the host application to receive the necessary input messages to provide these behaviors, PresentationHost.exe forwards appropriate raw input messages to the hosted application by calling [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span></span>  
  
 <span data-ttu-id="3d736-118">Die gehostete Anwendung empfängt unformatierte eingabemeldungen durch die Registrierung mit dem Satz von Geräten für unformatierte Eingabe (Human Interface Devices) vom [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span><span class="sxs-lookup"><span data-stu-id="3d736-118">The hosted application receives raw input messages by registering with the set of raw input devices (Human Interface Devices) returned by [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d736-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d736-119">See Also</span></span>  
 [<span data-ttu-id="3d736-120">WM_INPUT-Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="3d736-120">WM_INPUT Notification</span></span>](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
