---
title: "Übersicht über WPF-XAML-Browseranwendungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XBAP [WPF], XAML browser application
- WPF XAML browser applications (XBAP)
- XAML browser applications (XBAP)
- browser-hosted applications [WPF]
ms.assetid: 3a7a86a8-75d5-4898-96b9-73da151e5e16
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c894d431aa31e32b4a8cb7ff02d39d5aa5e95381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="wpf-xaml-browser-applications-overview"></a>Übersicht über WPF-XAML-Browseranwendungen
<a name="introduction"></a>
[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]kombiniert die Funktionen von Webanwendungen und Rich-Client-Anwendungen. Wie Webanwendungen können XBAPs auf einem Webserver bereitgestellt werden und aus Internet Explorer oder Firefox gestartet werden. XBAPs können von den Funktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] profitieren, genau wie Rich Client-Anwendungen. Auch die Entwicklung von XBAPs ähnelt der Rich Client-Entwicklung. Dieses Thema bietet eine allgemeine einfache Einführung in die XBAP-Entwicklung und beschreibt die Unterschiede zwischen der Entwicklung von XBAP und standardmäßigen Rich Client-Anwendungen.  
  
 Dieses Thema enthält folgende Abschnitte:  
  
-   [Erstellen einer neuen XAML-Browseranwendung (XBAP)](#creating_a_new_xaml_browser_application_xbap)  
  
-   [Bereitstellen einer XBAP](#deploying_a_xbap)  
  
-   [Kommunizieren mit der Hostwebseite](#communicating_with_the_host_web_page)  
  
-   [XBAP-Sicherheitsüberlegungen](#xbap_security_considerations)  
  
-   [Überlegungen zur XBAP-Startzeitleistung](#xbap_start_time_performance_considerations)  
  
<a name="creating_a_new_xaml_browser_application_xbap"></a>   
## <a name="creating-a-new-xaml-browser-application-xbap"></a>Erstellen einer neuen XAML-Browseranwendung (XBAP)  
 Die einfachste Methode zum Erstellen eines neuen XBAP-Projekts bietet [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]. Wenn Sie ein neues Projekt erstellen, wählen Sie **WPF-Browseranwendung** aus der Liste der Vorlagen aus. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines neuen WPF-Browseranwendungsprojekts](http://msdn.microsoft.com/en-us/72ef4d90-e163-42a1-8df0-ea7ccfd1901f).  
  
 Wenn Sie das XBAP-Projekt ausführen, wird es in einem Browserfenster geöffnet, nicht in einem eigenständigen Fenster. Wenn Sie die XBAP aus [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] debuggen, wird die Anwendung mit Internetzonenberechtigung ausgeführt und löst daher Sicherheitsausnahmen aus, wenn diese Berechtigungen überschritten werden. Weitere Informationen finden Sie unter[ Sicherheit (WPF)](../../../../docs/framework/wpf/security-wpf.md) und [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../../../../docs/framework/wpf/wpf-partial-trust-security.md).  
  
> [!NOTE]
>  Wenn Sie nicht mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] entwickeln oder mehr über die Projektdateien erfahren möchten, finden Sie weitere Informationen unter [Erstellen einer WPF-Anwendung (WPF)](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md).  
  
<a name="deploying_a_xbap"></a>   
## <a name="deploying-an-xbap"></a>Bereitstellen einer XBAP  
 Wenn Sie eine XBAP erstellen, schließt die Ausgabe die folgenden drei Dateien ein:  
  
|Datei|Beschreibung|  
|----------|-----------------|  
|Ausführbare Datei (.exe)|Diese enthält den kompilierten Code und hat die Erweiterung EXE.|  
|Anwendungsmanifest (.manifest)|Dieses enthält die der Anwendung zugeordneten Metadaten und hat die Erweiterung MANIFEST.|  
|Bereitstellungsmanifest (.xbap)|Dieses enthält die Informationen, die [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)] zum Bereitstellen der Anwendung verwendet. Sie hat die Erweiterung XBAP.|  
  
 Sie stellen XBAPs auf einem Webserver, z.B. [!INCLUDE[TLA#tla_iis50](../../../../includes/tlasharptla-iis50-md.md)] oder höheren Versionen, bereit. Sie müssen [!INCLUDE[TLA2#tla_winfx](../../../../includes/tla2sharptla-winfx-md.md)] nicht auf dem Webserver installieren, müssen aber die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA#tla_mime](../../../../includes/tlasharptla-mime-md.md)]-Typen und -Dateierweiterungen registrieren. Weitere Informationen finden Sie unter [Vorgehensweise: Konfigurieren von IIS 5.0 und IIS 6.0, um WPF-Anwendungen bereitzustellen](../../../../docs/framework/wpf/app-development/how-to-configure-iis-5-0-and-iis-6-0-to-deploy-wpf-applications.md).  
  
 Zum Vorbereiten der XBAP für die Bereitstellung kopieren Sie die EXE-Datei und die zugeordneten Manifeste auf den Webserver. Erstellen Sie eine HTML-Seite, die einen Link enthält, um das Bereitstellungsmanifest zu öffnen. Dabei handelt es sich um die Datei mit der Erweiterung XBAP. Wenn ein Benutzer auf den Link zur XBAP-Datei klickt, wird das Herunterladen und Starten der Anwendung automatisch von [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)] erledigt. Im folgenden Beispielcode wird eine HTML-Seite dargestellt, die einen Link enthält, der auf eine XBAP zeigt.  
  
```html
<html>   
    <head></head>  
    <body>   
        <a href="XbapEx.xbap">Click this link to launch the application</a>  
    </body>   
</html>  
```  
  
 Sie können eine XBAP auch im Frame einer Webseite hosten. Erstellen Sie eine Webseite mit einem oder mehreren Frames. Legen Sie die Quelleigenschaft eines Frames auf die Bereitstellungsmanifestdatei fest. Wenn Sie den integrierten Mechanismus verwenden möchten, um zwischen der Hostingwebseite und der XBAP zu kommunizieren, müssen Sie die Anwendung in einem Frame hosten. Im folgenden Beispielcode ist eine HTML-Seite mit zwei Frames dargestellt, wobei die Quelle für den zweiten Frame auf eine XBAP festgelegt ist.  
  
```html
<html>   
    <head>
        <title>A page with frames</title>
    </head>  
    <frameset cols="50%,50%">   
        <frame src="introduction.htm">   
        <frame src="XbapEx.xbap">   
    </frameset>   
</html>  
```  
  
### <a name="clearing-cached-xbaps"></a>Löschen von zwischengespeicherten XBAPs  
 In einigen Situationen stellen Sie nach dem Neuerstellen und Starten der XBAP fest, dass eine frühere Version der XBAP geöffnet wird. Dieses Verhalten kann beispielsweise auftreten, wenn die XBAP-Assemblyversionsnummer statisch ist und Sie die XBAP über die Befehlszeile starten. Da die Versionsnummer zwischen die zwischengespeicherte Version (die Version, die zuvor gestartet wurde) und die neue Version gleich bleibt, wird die neue Version der XBAP in diesem Fall nicht heruntergeladen. Stattdessen wird die zwischengespeicherte Version geladen.  
  
 In diesen Situationen können Sie die zwischengespeicherte Version entfernen, indem Sie den Befehl **Mage** (der mit Visual Studio oder [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)] installiert wird) über die Befehlszeile ausführen. Der folgende Befehl löscht den Anwendungscache.  
  
 ```console
 Mage.exe -cc
 ```
  
 Dieser Befehl gewährleistet, dass die neueste Version der XBAP gestartet wird. Wenn Sie die Anwendung in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] debuggen, sollte die aktuelle Version der XBAP gestartet werden. Es wird empfohlen, die Bereitstellungsversionsnummer mit jedem Build zu aktualisieren. Weitere Informationen über Mage finden Sie unter [Mage.exe (Tool zum Generieren und Bearbeiten von Manifesten)](../../../../docs/framework/tools/mage-exe-manifest-generation-and-editing-tool.md).  
  
<a name="communicating_with_the_host_web_page"></a>   
## <a name="communicating-with-the-host-web-page"></a>Kommunizieren mit der Hostwebseite  
 Wenn die Anwendung in einem HTML-Frame gehostet wird, können Sie mit der Webseite kommunizieren, die die XBAP enthält. Zu diesem Zweck wird das Abrufen der <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> Eigenschaft <xref:System.Windows.Interop.BrowserInteropHelper>. Diese Eigenschaft gibt ein Skriptobjekt zurück, das das HTML-Fenster darstellt. Sie können dann auf die Eigenschaften, Methoden und Ereignisse auf dem [Fensterobjekt](http://go.microsoft.com/fwlink/?LinkId=160274) mit regulärer Punktsyntax zugreifen. Sie können auch auf Skriptmethoden und globale Variablen zugreifen. Im folgenden Beispiel wird veranschaulicht, wie Sie das Skriptobjekt abrufen und den Browser schließen.  
  
 [!code-csharp[XbapBrowserInterop#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/xbapbrowserinterop/cs/page1.xaml.cs#10)]
 [!code-vb[XbapBrowserInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/xbapbrowserinterop/vb/page1.xaml.vb#10)]  
  
### <a name="debugging-xbaps-that-use-hostscript"></a>Debuggen von XBAPs, die HostScript verwenden  
 Wenn XBAP verwendet die <xref:System.Windows.Interop.BrowserInteropHelper.HostScript%2A> Objekt für die Kommunikation mit HTML-Fenster, es gibt zwei Einstellungen, die Sie angeben, müssen zum Ausführen und Debuggen der Anwendung in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]. Die Anwendung muss Zugriff auf ihre Ursprungssite haben, und Sie müssen die Anwendung mit der HTML-Seite starten, die die XBAP enthält. Die folgenden Schritte beschreiben, wie diese beiden Einstellungen überprüft werden:  
  
1.  Öffnen Sie die Projekteigenschaften in Visual Studio.  
  
2.  Klicken Sie auf der Registerkarte **Sicherheit** auf **Erweitert**.  
  
     Das Dialogfeld „Erweiterte Sicherheitseinstellungen“wird angezeigt.  
  
3.  Stellen Sie sicher, dass das Kontrollkästchen **Der Anwendung Zugriff auf die Ursprungssite gewähren** aktiviert ist, und klicken Sie dann auf **OK**.  
  
4.  Wählen Sie auf der Registerkarte **Debuggen** die Option **Browser mit folgender URL starten** aus, und geben Sie die URL für die HTML-Seite an, die die XBAP enthält.  
  
5.  Klicken Sie in Internet Explorer auf die Schaltfläche **Extras**, und wählen Sie dann **Internetoptionen** aus.  
  
     Das Dialogfeld "Internetoptionen" wird angezeigt.  
  
6.  Klicken Sie auf die Registerkarte **Erweitert**.  
  
7.  Aktivieren Sie in der Liste **Einstellungen** unter **Sicherheit** das Kontrollkästchen **Ausführung aktiver Inhalte in Dateien auf dem lokalen Computer zulassen**.  
  
8.  Klicken Sie auf **OK**.  
  
     Die Änderungen werden wirksam, nachdem Sie Internet Explorer neu gestartet haben.  
  
> [!CAUTION]
>  Aktiven Inhalt in Internet Explorer zu aktivieren, gefährdet möglicherweise den Computer. Weitere Informationen finden Sie unter [Security and privacy features in Internet Explorer (Sicherheits- und Datenschutzfunktionen in Internet Explorer)](http://go.microsoft.com/fwlink/?LinkId=179286). Wenn Sie die Internet Explorer-Sicherheitseinstellungen nicht ändern wollen, können Sie die HTML-Seite von einem Server starten und den [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]-Debugger an den Prozess anfügen.  
  
<a name="xbap_security_considerations"></a>   
## <a name="xbap-security-considerations"></a>XBAP-Sicherheitsüberlegungen  
 XBAPs werden in der Regel in einem teilweise vertrauenswürdigen Sicherheitsbereich (Sandbox) ausgeführt, der auf den Berechtigungssatz für die Internetzone beschränkt ist. Daher muss Ihre Implementierung die Teilmenge der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elemente unterstützen, die in der Internetzone unterstützt werden, oder Sie müssen die Berechtigungen der Anwendung erweitern. Weitere Informationen finden Sie unter [Sicherheit (WPF)](../../../../docs/framework/wpf/security-wpf.md).  
  
 Bei Verwendung einer <xref:System.Windows.Controls.WebBrowser> Steuerelement in der WPF-Anwendung instanziiert intern das systemeigene WebBrowser ActiveX-Steuerelement. Wenn die Anwendung eine teilweise vertrauenswürdige XBAP ist, die in Internet Explorer ausgeführt wird, wird das ActiveX-Steuerelement in einem dedizierten Thread des Internet Explorer-Prozesses ausgeführt. Daher gelten die folgenden Einschränkungen:  
  
-   Die <xref:System.Windows.Controls.WebBrowser> Steuerelement sollte ähnlich den Hostbrowser und sicherheitseinschränkungen einschließlich Verhalten bereitstellen. Einige dieser Sicherheitseinschränkungen können durch die Internet Explorer-Sicherheitseinstellungen gesteuert werden. Weitere Informationen finden Sie unter [Sicherheit (WPF)](../../../../docs/framework/wpf/security-wpf.md).  
  
-   Eine Ausnahme wird ausgelöst, wenn eine XBAP domänenübergreifend in eine HTML-Seite geladen wird.  
  
-   Eingabe wird in einem separaten Thread aus der WPF <xref:System.Windows.Controls.WebBrowser>, damit Tastatureingaben nicht abgefangen können werden und der Zustand des Eingabemethoden-Editor nicht gemeinsam genutzt wird.  
  
-   Die zeitliche Steuerung oder die Reihenfolge der Navigation weicht möglicherweise ab, da das ActiveX-Steuerelement in einem anderen Thread ausgeführt wird. Zum Beispiel wird die Navigation zu einer Seite nicht immer abgebrochen, indem eine andere Navigationsanforderung gestartet wird.  
  
-   Ein benutzerdefiniertes ActiveX-Steuerelement hat möglicherweise Probleme mit Kommunikation, da die WPF-Anwendung in einem separaten Thread ausgeführt wird.  
  
-   <xref:System.Windows.Interop.HwndHost.MessageHook>wird nicht ausgelöst, da <xref:System.Windows.Interop.HwndHost> kann nicht als Unterklasse eines Fensters in einem anderen Prozess oder Thread ausgeführt wird.  
  
### <a name="creating-a-full-trust-xbap"></a>Erstellen einer XBAP mit voller Vertrauenswürdigkeit  
 Wenn die XBAP volle Vertrauenswürdigkeit erfordert, können Sie das Projekt ändern, um diese Berechtigung zu aktivieren. Die folgenden Schritte beschreiben, wie volle Vertrauenswürdigkeit aktiviert wird:  
  
1.  Öffnen Sie die Projekteigenschaften in Visual Studio.  
  
2.  Aktivieren Sie die Option **Voll vertrauenswürdige Anwendung** auf der Registerkarte **Sicherheit**.  
  
 Diese Einstellung nimmt die folgenden Änderungen vor:  
  
-   In der Projektdatei wird der `<TargetZone>`-Elementwert in `Custom` geändert.  
  
-   Im Anwendungsmanifest (app.manifest) wird ein `Unrestricted="true"`-Attribut zum `PermissionSet`-Element hinzugefügt.  
  
    ```xml
    <PermissionSet class="System.Security.PermissionSet"   
                   version="1"   
                   ID="Custom"   
                   SameSite="site"   
                   Unrestricted="true" />  
    ```  
  
### <a name="deploying-a-full-trust-xbap"></a>Bereitstellen einer XBAP mit voller Vertrauenswürdigkeit  
 Wenn Sie eine vollständig vertrauenswürdige XBAP bereitstellen, die nicht dem ClickOnce Trusted-Bereitstellungsmodell folgt, hängt das Verhalten bei der Ausführung der Anwendung durch den Benutzer von der Sicherheitszone ab. In einigen Fällen erhält der Benutzer bei der Installation eine Warnung. Der Benutzer kann auswählen, ob die Installation fortgesetzt oder abgebrochen werden soll. In der folgenden Tabelle werden das Verhalten der Anwendung für jede Sicherheitszone und die erforderlichen Schritte für die volle Vertrauenswürdigkeit der Anwendung beschrieben.  
  
|Sicherheitszone|Verhalten|Erhalten der vollen Vertrauenswürdigkeit|  
|-------------------|--------------|------------------------|  
|Lokaler Computer|Automatisch volle Vertrauenswürdigkeit|Es ist keine Aktion erforderlich.|  
|Intranet und vertrauenswürdige Websites|Eingabeaufforderung für volle Vertrauenswürdigkeit|Signieren Sie die XBAP mit einem Zertifikat, damit der Benutzer die Quelle in der Eingabeaufforderung sieht.|  
|Internet|Schlägt fehl mit „Vertrauenswürdigkeit nicht gewährt“|Signieren Sie die XBAP mit einem Zertifikat.|  
  
> [!NOTE]
>  Das in der obigen Tabelle beschriebene Verhalten gilt für vollständig vertrauenswürdige XBAPs, die nicht dem ClickOnce Trusted-Bereitstellungsmodell folgen.  
  
 Es wird empfohlen, dass Sie das ClickOnce Trusted-Bereitstellungsmodell zum Bereitstellen einer vollständig vertrauenswürdigen XBAP verwenden. Mit diesem Modell können Sie der XBAP unabhängig von der Sicherheitszone automatisch die volle Vertrauenswürdigkeit gewähren lassen, sodass der Benutzer nicht aufgefordert wird. Als Teil dieses Modells müssen Sie die Anwendung mit einem Zertifikat für einen vertrauenswürdigen Verleger signieren. Weitere Informationen finden Sie unter [Überblick über die Bereitstellung vertrauenswürdiger Anwendungen](/visualstudio/deployment/trusted-application-deployment-overview) und [Introduction to Code Signing (Einführung in die Codesignatur)](http://go.microsoft.com/fwlink/?LinkId=166327).  
  
<a name="xbap_start_time_performance_considerations"></a>   
## <a name="xbap-start-time-performance-considerations"></a>Überlegungen zur XBAP-Startzeitleistung  
 Ein wichtiger Aspekt der XBAP-Leistung ist ihre Startzeit. Falls eine XPAB die erste zu ladende WPF-Anwendung darstellt, kann die *Kaltstartzeit* zehn Sekunden oder mehr betragen. Dies ist darauf zurückzuführen, dass die Statusseite von WPF gerendert wird und sowohl die CLR als auch WPF für die Anzeige der Anwendung kaltgestartet werden müssen.  
  
 Wenn Sie in [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)] starten, wird die XBAP-Kaltstartzeit reduziert, indem eine nicht verwaltete Statusseite in einer frühen Phase im Bereitstellungszyklus angezeigt wird. Die Statusseite wird fast unmittelbar nach dem Start der Anwendung angezeigt, da sie mit nativen Hostingcode angezeigt und in HTML gerendert wird.  
  
 Außerdem wird durch eine verbesserte Parallelität der [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)]-Downloadsequenz die Startzeit um bis zu zehn Prozent verbessert. Nachdem [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] Manifeste heruntergeladen und überprüft hat, beginnt der Anwendungsdownload und die Statusanzeige wird aktualisiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Konfigurieren von Visual Studio 2005 zum Debuggen einer XAML-Browseranwendung, um einen Webdienst aufzurufen](../../../../docs/framework/wpf/app-development/configure-vs-to-debug-a-xaml-browser-to-call-a-web-service.md)  
 [Bereitstellen von WPF-Anwendungen](../../../../docs/framework/wpf/app-development/deploying-a-wpf-application-wpf.md)
