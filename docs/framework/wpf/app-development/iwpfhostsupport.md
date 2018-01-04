---
title: IWpfHostSupport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a516d5917c2106bc83842befac9b506312fcce1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="9783d-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="9783d-102">IWpfHostSupport</span></span>
<span data-ttu-id="9783d-103">Anwendungen, die hosten [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalt über PresentationHost.exe implementieren diese Schnittstelle für einen Integration zwischen dem Host und PresentationHost.exe bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9783d-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9783d-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9783d-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="9783d-105">Hosten von Anwendungen wie Webbrowsern können [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Inhalt, einschließlich [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und loose XAML.</span><span class="sxs-lookup"><span data-stu-id="9783d-105"> applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="9783d-106">Auf Host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Inhalt [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Anwendungen erstellen Sie eine Instanz von der [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="9783d-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](http://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="9783d-107">Gehostet werden, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] erstellt eine Instanz von PresentationHost.exe, die der gehostete [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Content an den Host für die Anzeige in der [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=97911).</span><span class="sxs-lookup"><span data-stu-id="9783d-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](http://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="9783d-108">Die Integration von aktiviert `IWpfHostSupport` PresentationHost.exe ermöglicht:</span><span class="sxs-lookup"><span data-stu-id="9783d-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
-   <span data-ttu-id="9783d-109">Ermitteln Sie, und registrieren Sie mit der Eingaben unformatierten Medien (Human Interface Devices), denen die hostanwendung interessiert ist.</span><span class="sxs-lookup"><span data-stu-id="9783d-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
-   <span data-ttu-id="9783d-110">Erhalten Sie eingehende Nachrichten aus der registrierten Geräte für unformatierte Eingabe und die entsprechenden Weiterleiten von Nachrichten an die hostanwendung.</span><span class="sxs-lookup"><span data-stu-id="9783d-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
-   <span data-ttu-id="9783d-111">Fragen Sie die hostanwendung für benutzerdefinierte Benutzeroberflächen Status- und Fehlerinformationen.</span><span class="sxs-lookup"><span data-stu-id="9783d-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9783d-112">Diese API ist nur für die Verwendung auf dem lokalen Clientcomputer vorgesehen und wird nur zu diesem Zweck unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9783d-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="9783d-113">Member</span><span class="sxs-lookup"><span data-stu-id="9783d-113">Members</span></span>  
  
|<span data-ttu-id="9783d-114">Member</span><span class="sxs-lookup"><span data-stu-id="9783d-114">Member</span></span>|<span data-ttu-id="9783d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9783d-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9783d-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="9783d-116">GetRawInputDevices</span></span>](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|<span data-ttu-id="9783d-117">Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.</span><span class="sxs-lookup"><span data-stu-id="9783d-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="9783d-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="9783d-118">FilterInputMessage</span></span>](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|<span data-ttu-id="9783d-119">Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9783d-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="9783d-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="9783d-120">GetCustomUI</span></span>](../../../../docs/framework/wpf/app-development/getcustomui.md)|<span data-ttu-id="9783d-121">Bietet standardmäßig PresentationHost.exe eigene Bereitstellungsstatus und Fehler bei der Bereitstellung von Benutzeroberflächen, die angezeigt werden, wenn WPF-Inhalt bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9783d-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
