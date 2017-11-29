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
ms.openlocfilehash: 85d4ed09d6c5ca17e148d531e6aac483ff737d51
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Anwendungen, die hosten [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalt über PresentationHost.exe implementieren diese Schnittstelle für einen Integration zwischen dem Host und PresentationHost.exe bereitstellen.  
  
## <a name="remarks"></a>Hinweise  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]Hosten von Anwendungen wie Webbrowsern können [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Inhalt, einschließlich [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] und loose XAML. Auf Host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Inhalt [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Anwendungen erstellen Sie eine Instanz von der [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=97911). Gehostet werden, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] erstellt eine Instanz von PresentationHost.exe, die der gehostete [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Content an den Host für die Anzeige in der [WebBrowser-Steuerelement](http://go.microsoft.com/fwlink/?LinkId=97911).  
  
 Die Integration von aktiviert `IWpfHostSupport` PresentationHost.exe ermöglicht:  
  
-   Ermitteln Sie, und registrieren Sie mit der Eingaben unformatierten Medien (Human Interface Devices), denen die hostanwendung interessiert ist.  
  
-   Erhalten Sie eingehende Nachrichten aus der registrierten Geräte für unformatierte Eingabe und die entsprechenden Weiterleiten von Nachrichten an die hostanwendung.  
  
-   Fragen Sie die hostanwendung für benutzerdefinierte Benutzeroberflächen Status- und Fehlerinformationen.  
  
> [!NOTE]
>  Diese API ist nur für die Verwendung auf dem lokalen Clientcomputer vorgesehen und wird nur zu diesem Zweck unterstützt.  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)|Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.|  
|[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)|Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.|  
|[GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md)|Bietet standardmäßig PresentationHost.exe eigene Bereitstellungsstatus und Fehler bei der Bereitstellung von Benutzeroberflächen, die angezeigt werden, wenn WPF-Inhalt bereitgestellt wird.|
