---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 97a120c57624ada32e6661bd8a613c4ea1d01b2f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591391"
---
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Anwendungen, in denen [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalte über PresentationHost.exe implementieren diese Schnittstelle zum Bereitstellen eine Integration zwischen dem Host und PresentationHost.exe.  
  
## <a name="remarks"></a>Hinweise  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Anwendungen wie Webbrowsern können hosten [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Inhalt, einschließlich [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] Loose XAML. Auf Host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Inhalt [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Anwendungen erstellen Sie eine Instanz von der [WebBrowser-Steuerelement](https://go.microsoft.com/fwlink/?LinkId=97911). Gehostet werden, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] erstellt eine Instanz des PresentationHost.exe, die der gehostete [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] Inhalt an den Host für die Anzeige in der [WebBrowser-Steuerelement](https://go.microsoft.com/fwlink/?LinkId=97911).  
  
 Die Integration von aktiviert `IWpfHostSupport` PresentationHost.exe ermöglicht:  
  
- Ermitteln Sie und registrieren Sie mit der Eingabegeräte für Rohdaten (Eingabegeräte), denen die hostanwendung interessant ist.  
  
- Erhalten Sie eingehende Nachrichten aus der registrierten Geräten für unformatierte Eingabe und die entsprechenden Weiterleiten von Nachrichten an die hostanwendung.  
  
- Fragen Sie die hostanwendung für benutzerdefinierte Status- und Benutzeroberflächen.  
  
> [!NOTE]
>  Diese API ist nur für die Verwendung auf dem lokalen Clientcomputer vorgesehen und wird nur zu diesem Zweck unterstützt.  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.|  
|[FilterInputMessage](filterinputmessage.md)|Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.|  
|[GetCustomUI](getcustomui.md)|Bietet standardmäßig PresentationHost.exe eigene Bereitstellungsstatus und die Fehler bei der Bereitstellung von Benutzeroberflächen, die angezeigt werden, wenn WPF-Inhalt bereitgestellt wird.|
