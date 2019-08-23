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
# <a name="iwpfhostsupport"></a>IWpfHostSupport
Anwendungen, die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalte über "PresentationHost. exe" hosten, implementieren diese Schnittstelle, um einen Punkt der Integration zwischen dem Host und "PresentationHost. exe" bereitzustellen.  
  
## <a name="remarks"></a>Hinweise  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]Anwendungen (z. b. Webbrowser [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] ) können Inhalt [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] hosten, einschließlich und freiem XAML. Anwendungen erstellen [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] eine Instanz [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] des [Webbrowser-Steuer](https://go.microsoft.com/fwlink/?LinkId=97911)Elements, um Inhalte zu hosten. Zum Hosten [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]erstellteine Instanz von "PresentationHost. exe", die den gehosteten Inhalt für den Host zur Anzeige im [Webbrowser-Steuer](https://go.microsoft.com/fwlink/?LinkId=97911)Element bereitstellt. [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]  
  
 Die von `IWpfHostSupport` aktivierte Integration ermöglicht PresentationHost. exe Folgendes:  
  
- Ermitteln und registrieren Sie sich bei den roheingabe Geräten (Human Interface Devices), an denen die Host Anwendung interessiert ist.  
  
- Empfangen von Eingabe Nachrichten von den registrierten roheingabe-Geräten und weiterleiten entsprechender Nachrichten an die Host Anwendung.  
  
- Fragen Sie die Host Anwendung nach Benutzeroberflächen für benutzerdefinierte Fortschritte und Fehler ab.  
  
> [!NOTE]
> Diese API ist nur für die Verwendung auf dem lokalen Clientcomputer vorgesehen und wird nur zu diesem Zweck unterstützt.  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[GetRawInputDevices](getrawinputdevices.md)|Ermöglicht es der Datei "PresentationHost.exe", Geräte für die Eingabe von Rohdaten (Eingabegeräte, Human Interface Devices) zu erkennen, die für die Hostanwendung interessant sind.|  
|[FilterInputMessage](filterinputmessage.md)|Wird immer dann von "PresentationHost.exe" aufgerufen, wenn eine Meldung empfangen wurde, es sei denn, E_NOTIMPL wurde zurückgegeben.|  
|[GetCustomUI](getcustomui.md)|PresentationHost. exe bietet standardmäßig einen eigenen Bereitstellungs Fortschritt und Bereitstellungs Fehler-Benutzeroberflächen, die beim Bereitstellen von WPF-Inhalt angezeigt werden.|
