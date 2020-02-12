---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: e3edd7f7080562d03453898dba7a9326561803b5
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124194"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="814fa-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="814fa-102">IWpfHostSupport</span></span>
<span data-ttu-id="814fa-103">Anwendungen, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalt über "PresentationHost. exe" hosten, implementieren diese Schnittstelle, um einen Punkt der Integration zwischen dem Host und "PresentationHost. exe" bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="814fa-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="814fa-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="814fa-104">Remarks</span></span>  
 <span data-ttu-id="814fa-105">Win32-Anwendungen (z. b. Webbrowser) können WPF-Inhalte hosten, einschließlich XAML-Browser Anwendungen (XBAPs) und losem XAML-Code.</span><span class="sxs-lookup"><span data-stu-id="814fa-105">Win32 applications such as Web browsers can host WPF content, including XAML browser applications (XBAPs) and loose XAML.</span></span> <span data-ttu-id="814fa-106">Zum Hosten von WPF-Inhalt erstellen Win32-Anwendungen eine Instanz des [Webbrowser-Steuer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))Elements.</span><span class="sxs-lookup"><span data-stu-id="814fa-106">To host WPF content, Win32 applications create an instance of the [WebBrowser control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span> <span data-ttu-id="814fa-107">Um gehostet zu werden, erstellt WPF eine Instanz von "PresentationHost. exe", die den gehosteten WPF-Inhalt für den Host zur Anzeige im [Webbrowser-Steuer](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85))Element bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="814fa-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://docs.microsoft.com/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752040(v=vs.85)).</span></span>  
  
 <span data-ttu-id="814fa-108">Die durch `IWpfHostSupport` aktivierte Integration ermöglicht PresentationHost. exe Folgendes:</span><span class="sxs-lookup"><span data-stu-id="814fa-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="814fa-109">Ermitteln und registrieren Sie sich bei den roheingabe Geräten (Human Interface Devices), an denen die Host Anwendung interessiert ist.</span><span class="sxs-lookup"><span data-stu-id="814fa-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="814fa-110">Empfangen von Eingabe Nachrichten von den registrierten roheingabe-Geräten und weiterleiten entsprechender Nachrichten an die Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="814fa-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="814fa-111">Fragen Sie die Host Anwendung nach Benutzeroberflächen für benutzerdefinierte Fortschritte und Fehler ab.</span><span class="sxs-lookup"><span data-stu-id="814fa-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="814fa-112">Diese API ist nur für die Verwendung auf dem lokalen Clientcomputer vorgesehen und wird nur zu diesem Zweck unterstützt.</span><span class="sxs-lookup"><span data-stu-id="814fa-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="814fa-113">Members</span><span class="sxs-lookup"><span data-stu-id="814fa-113">Members</span></span>  
  
|<span data-ttu-id="814fa-114">Member</span><span class="sxs-lookup"><span data-stu-id="814fa-114">Member</span></span>|<span data-ttu-id="814fa-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="814fa-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="814fa-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="814fa-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="814fa-117">Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.</span><span class="sxs-lookup"><span data-stu-id="814fa-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="814fa-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="814fa-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="814fa-119">Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="814fa-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="814fa-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="814fa-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="814fa-121">PresentationHost. exe bietet standardmäßig einen eigenen Bereitstellungs Fortschritt und Bereitstellungs Fehler-Benutzeroberflächen, die beim Bereitstellen von WPF-Inhalt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="814fa-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
