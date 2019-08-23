---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964783"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="67123-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="67123-102">IWpfHostSupport</span></span>
<span data-ttu-id="67123-103">Anwendungen, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalte über "PresentationHost. exe" hosten, implementieren diese Schnittstelle, um einen Punkt der Integration zwischen dem Host und "PresentationHost. exe" bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="67123-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67123-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67123-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="67123-105">Anwendungen (z. b. Webbrowser [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] ) können Inhalt [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] hosten, einschließlich und freiem XAML.</span><span class="sxs-lookup"><span data-stu-id="67123-105">applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="67123-106">Anwendungen erstellen [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] eine Instanz [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] des [Webbrowser-Steuer](https://go.microsoft.com/fwlink/?LinkId=97911)Elements, um Inhalte zu hosten.</span><span class="sxs-lookup"><span data-stu-id="67123-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="67123-107">Zum Hosten [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]erstellteine Instanz von "PresentationHost. exe", die den gehosteten Inhalt für den Host zur Anzeige im [Webbrowser-Steuer](https://go.microsoft.com/fwlink/?LinkId=97911)Element bereitstellt. [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67123-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="67123-108">Die von `IWpfHostSupport` aktivierte Integration ermöglicht PresentationHost. exe Folgendes:</span><span class="sxs-lookup"><span data-stu-id="67123-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="67123-109">Ermitteln und registrieren Sie sich bei den roheingabe Geräten (Human Interface Devices), an denen die Host Anwendung interessiert ist.</span><span class="sxs-lookup"><span data-stu-id="67123-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="67123-110">Empfangen von Eingabe Nachrichten von den registrierten roheingabe-Geräten und weiterleiten entsprechender Nachrichten an die Host Anwendung.</span><span class="sxs-lookup"><span data-stu-id="67123-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="67123-111">Fragen Sie die Host Anwendung nach Benutzeroberflächen für benutzerdefinierte Fortschritte und Fehler ab.</span><span class="sxs-lookup"><span data-stu-id="67123-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67123-112">Diese API ist nur für die Verwendung auf dem lokalen Clientcomputer vorgesehen und wird nur zu diesem Zweck unterstützt.</span><span class="sxs-lookup"><span data-stu-id="67123-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="67123-113">Member</span><span class="sxs-lookup"><span data-stu-id="67123-113">Members</span></span>  
  
|<span data-ttu-id="67123-114">Member</span><span class="sxs-lookup"><span data-stu-id="67123-114">Member</span></span>|<span data-ttu-id="67123-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="67123-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="67123-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="67123-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="67123-117">Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.</span><span class="sxs-lookup"><span data-stu-id="67123-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="67123-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="67123-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="67123-119">Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="67123-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="67123-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="67123-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="67123-121">PresentationHost. exe bietet standardmäßig einen eigenen Bereitstellungs Fortschritt und Bereitstellungs Fehler-Benutzeroberflächen, die beim Bereitstellen von WPF-Inhalt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="67123-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
