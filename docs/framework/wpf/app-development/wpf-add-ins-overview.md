---
title: "Übersicht über WPF-Add-Ins"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add-ins and XAML browser applications [WPF]
- add-ins overview [WPF]
- add-ins [WPF], performance
- add-ins [WPF], benefits
- .NET Framework add-in model [WPF]
- add-ins [WPF], user interface
- add-ins and the user interface [WPF]
- add-ins [WPF], architecture
- add-ins [WPF], limitations
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 290682542a0accaf38408127f7358625abca14af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="wpf-add-ins-overview"></a>Übersicht über WPF-Add-Ins
<a name="Introduction"></a> [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] beinhaltet ein Add-In-Modell, mit dem Entwickler Anwendungen erstellen können, die Add-In-Erweiterbarkeit unterstützen. Dieses Add-In-Modell ermöglicht die Erstellung von Add-Ins, die in die Anwendungsfunktionalität integriert werden und diese erweitern. In einigen Szenarien müssen Anwendungen auch [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s anzeigen, die von Add-Ins bereitgestellt werden. In diesem Thema wird gezeigt, wie durch [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] erweitert wird, um diese Szenarien sowie die zugrunde liegende Architektur, die Vorteile und die Einschränkungen zu ermöglichen.  
  

  
<a name="Requirements"></a>   
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Kenntnisse des Add-In-Modells von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] sind erforderlich. Weitere Informationen finden Sie unter [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md).  
  
<a name="AddInsOverview"></a>   
## <a name="add-ins-overview"></a>Übersicht über Add-Ins  
 Um das mit dem Integrieren neuer Funktionen verbundene erneute Kompilieren und Bereitstellen von Anwendungen zu vermeiden, da diese Vorgänge sehr komplex sind, sind Anwendungen mit Erweiterbarkeitsmechanismen ausgestattet. Diese ermöglichen Entwicklern (sowohl Erst- als auch Drittanbieter) das Erstellen anderer Anwendungen, die integriert werden können. Diese Art von Erweiterbarkeit wird in der Regel durch die Verwendung von Add-Ins (auch als „Add-Ons“ oder „Plug-Ins“ bezeichnet) unterstützt. Es folgen Beispiele für reale Anwendungen, die eine Erweiterbarkeit mit Add-Ins verfügbar machen:  
  
-   Internet Explorer-Add-Ons  
  
-   Windows Media Player-Plug-Ins  
  
-   Visual Studio-Add-Ins  
  
 Beispielsweise können Drittanbieterentwickler mithilfe des Add-In-Modells von Windows Media Player „Plug-Ins“ implementieren, durch die der Windows Media Player auf vielfältige Weise erweitert wird. Dazu zählen das Erstellen von Decodern und Encodern für Medienformate, für die keine systemeigene Unterstützung durch Windows Media Player besteht (z. B. DVD, MP3), Audioeffekte und Skins. Jedes Add-In-Modell ist so aufgebaut, dass es die zu einer Anwendung gehörenden Funktionen verfügbar macht, obwohl verschiedene Entitäten und Verhaltensweisen für alle Add-In-Modelle gelten.  
  
 Die drei Hauptentitäten typischer Add-In-Erweiterbarkeitslösungen sind *Verträge*, *Add-Ins* und *Hostanwendungen*. Mit Verträgen wird auf zwei Arten definiert, wie Add-Ins mit Hostanwendungen integriert sind:  
  
-   Add-Ins sind in Funktionen integriert, die von Hostanwendungen implementiert werden.  
  
-   Hostanwendungen machen Funktionen verfügbar, in die Add-Ins integriert werden.  
  
 Damit Add-Ins verwendet werden können, müssen sie von Hostanwendungen gefunden und zur Laufzeit geladen werden. Daher sind Anwendungen, die Add-Ins unterstützen, zusätzlich für folgende Aufgaben verantwortlich:  
  
-   **Ermittlung**: Suchen nach Add-Ins, die von Hostanwendungen unterstützte Verträge einhalten.  
  
-   **Aktivierung**: Laden, Ausführen und Herstellen der Kommunikation mit Add-Ins.  
  
-   **Isolation**: Verwenden von Anwendungsdomänen oder Prozessen zum Einrichten von Isolationsgrenzen, die Anwendungen vor möglichen Sicherheitsproblemen und Problemen bei der Ausführung von Add-Ins schützen.  
  
-   **Kommunikation**: Durch das Aufrufen von Methoden und Übergeben von Daten können Add-Ins und Hostanwendungen über Isolationsgrenzen hinweg miteinander kommunizieren.  
  
-   **Verwaltung der Lebensdauer**: Laden und Entladen von Anwendungsdomänen und -prozessen auf eine klare, vorhersehbare Weise (siehe [Anwendungsdomänen](../../../../docs/framework/app-domains/application-domains.md)).  
  
-   **Versionsverwaltung**: Sicherstellen, dass Hostanwendungen und Add-Ins auch dann noch kommunizieren können, wenn neue Versionen erstellt wurden.  
  
 Letztlich ist es eine wichtige Aufgabe, ein stabiles Add-In-Modell zu entwickeln. Aus diesem Grund stellt [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] eine Infrastruktur zum Erstellen von Add-In-Modellen bereit.  
  
> [!NOTE]
>  Weitere Informationen zu Add-Ins finden Sie unter [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>Übersicht über das Add-In-Modell von .NET Framework  
 Die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Add-In-Modell, das der <xref:System.AddIn> -Namespace enthält einen Satz von Typen, die entwickelt wurden, um die Entwicklung von Add-in-Erweiterbarkeit vereinfachen. Das Fundament des Add-In-Modells von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] stellt der *Vertrag* dar. Dort ist festgelegt, wie eine Hostanwendung und ein Add-In miteinander kommunizieren. Ein Vertrag wird mit einer für Hostanwendungen spezifischen *Ansicht* des Vertrags für eine Hostanwendung verfügbar gemacht. Auf ähnliche Weise wird eine für Add-Ins spezifische *Ansicht* des Vertrags für das Add-In verfügbar gemacht. Ein *Adapter* ermöglicht es einer Hostanwendung und einem Add-In, zwischen ihren jeweiligen Ansichten des Vertrags miteinander zu kommunizieren. Verträge, Ansichten und Adapter werden als Segmente bezeichnet, und mehrere miteinander verbundene Segmente stellen eine *Pipeline* dar. Pipelines sind die Grundlage, wenn es für das Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] darum geht, Aufgaben wie Ermittlung, Aktivierung, Sicherheitsisolation, Ausführungsisolation (unter Verwendung von Anwendungsdomänen und -prozessen), Kommunikation, Verwaltung der Lebensdauer und Versionsverwaltung zu unterstützen.  
  
 Mit dieser Unterstützung können Entwickler Add-Ins erstellen, die mit den Funktionen einer Hostanwendung integriert werden. In einigen Szenarien müssen Hostanwendungen die von Add-Ins bereitgestellten [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s anzeigen. Da jede Präsentationstechnologie in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] über ein eigenes Modell zum Implementieren von [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s verfügt, unterstützt das Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] keine bestimmte Präsentationstechnologie. Stattdessen erweitert [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Unterstützung für Add-Ins.  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>WPF-Add-Ins  
 Wenn Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in Verbindung mit dem Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] verwenden, können Sie den unterschiedlichsten Szenarien gerecht werden, in denen Hostanwendungen [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s aus Add-Ins anzeigen müssen. Für diese Szenarien eignet sich insbesondere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mit den folgenden zwei Programmiermodellen:  
  
1.  **Das Add-In gibt eine Benutzeroberfläche zurück**. Wie im Vertrag definiert, gibt ein Add-In über einen Methodenaufruf eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an die Hostanwendung zurück. Das Szenario wird in den folgenden Fällen verwendet:  
  
    -   Die Darstellung einer vom Add-In zurückgegebenen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] hängt von den zur Laufzeit vorhandenen Daten oder Bedingungen ab, z. B. von dynamisch generierten Berichten.  
  
    -   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für durch ein Add-In bereitgestellte Dienste unterscheidet sich von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Hostanwendungen, die das Add-In verwenden können.  
  
    -   Das Add-In führt in erster Linie einen Dienst für die Hostanwendung aus und meldet den Status an die Hostanwendung mit einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
2.  **Das Add-In ist eine Benutzeroberfläche**. Ein Add-In ist eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], wie im Vertrag definiert. Das Szenario wird in den folgenden Fällen verwendet:  
  
    -   Ein Add-In stellt ausschließlich die angezeigten Dienste bereit, z. B. eine Werbung.  
  
    -   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für von einem Add-In bereitgestellte Dienste wird von allen Hostanwendungen genutzt, die das Add-In verwenden können, z. B. Rechner oder Farbauswahl.  
  
 In diesen Szenarien ist es erforderlich, dass [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Objekte zwischen den Domänen der Hostanwendung und der Add-In-Anwendung übergeben werden können. Da beim Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] für die Kommunikation zwischen Anwendungsdomänen Remoting erforderlich ist, müssen die übergebenen Objekte remotefähig sein.  
  
 Ein remotefähiges Objekt stellt die Instanz einer Klasse dar, für die eine oder mehrere der folgenden Aussagen gelten:  
  
-   Leitet sich von der <xref:System.MarshalByRefObject> Klasse.  
  
-   Implementiert die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle.  
  
-   Hat die <xref:System.SerializableAttribute> Attribut angewendet.  
  
> [!NOTE]
>  Weitere Informationen über das Erstellen von remotefähigen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Objekten finden Sie unter [Erstellen remotefähiger Objekte](http://msdn.microsoft.com/en-us/01197253-3f13-43b7-894d-9683e431192a).  
  
 Die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Typen von [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] sind nicht remotefähig. Um das Problem zu beheben, erweitert [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], damit die durch Add-Ins erstellte [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von Hostanwendungen angezeigt werden kann. Diese Unterstützung wird durch bereitgestellt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] durch zwei Arten: die <xref:System.AddIn.Contract.INativeHandleContract> Schnittstelle und zwei statische Methoden implementiert, indem Sie die <xref:System.AddIn.Pipeline.FrameworkElementAdapters> Klasse: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. Im Allgemeinen werden diese Typen und Methoden wie folgt verwendet:  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]erfordert, dass [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] gebotenen-add-ins sind Klassen, die direkt oder indirekt abgeleitet <xref:System.Windows.FrameworkElement>, z. B. Formen, Steuerelemente, Benutzersteuerelemente, Layoutbereiche und Seiten.  
  
2.  Wo der Vertrag deklariert, dass eine Benutzeroberfläche zwischen Add-Ins und der hostanwendung übergeben wird, muss es als deklariert eine <xref:System.AddIn.Contract.INativeHandleContract> (keine <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> ist eine remotefähige Darstellung des Add-Ins [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Isolation hinweg übergeben werden können.  
  
3.  Bevor das Add-in der Anwendungsdomäne übergeben wird eine <xref:System.Windows.FrameworkElement> als verpackt ist ein <xref:System.AddIn.Contract.INativeHandleContract> durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  Nach der die Anwendungsdomäne der hostanwendung übergeben werden die <xref:System.AddIn.Contract.INativeHandleContract> müssen neu gepackt werden, als ein <xref:System.Windows.FrameworkElement> durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Wie <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> werden verwendet, richtet sich nach dem jeweiligen Szenario. Die folgenden Abschnitte bieten ausführliche Informationen zu den Programmiermodellen.  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>Add-In gibt eine Benutzeroberfläche zurück  
 Damit ein Add-In eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an eine Hostanwendung zurückgeben kann, müssen folgende Voraussetzungen erfüllt sein:  
  
1.  Hostanwendung, Add-In und Pipeline müssen erstellt worden sein, wie in der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Dokumentation unter [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md) beschrieben.  
  
2.  Der Vertrag implementieren muss <xref:System.AddIn.Contract.IContract> und zum Zurückgeben einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], der Vertrag muss eine Methode mit einem Rückgabewert vom Typ deklarieren <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] übergebenen zwischen Add-Ins und dem Host Anwendung muss direkt oder indirekt von abgeleitet <xref:System.Windows.FrameworkElement>.  
  
4.  Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von zurückgegebenen das Add-in muss konvertiert werden, aus einer <xref:System.Windows.FrameworkElement> auf ein <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze.  
  
5.  Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zurückgegeben wird, muss eine Konvertierung von einem <xref:System.AddIn.Contract.INativeHandleContract> auf eine <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze.  
  
6.  Die hostanwendung zeigt das zurückgegebene <xref:System.Windows.FrameworkElement>.  
  
 Ein Beispiel dafür, wie ein Add-In, das eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zurückgibt, implementiert wird, finden Sie unter [Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche zurückgibt](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>Add-In ist eine Benutzeroberfläche  
 Wenn ein Add-In eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ist, gelten die folgenden Voraussetzungen:  
  
1.  Hostanwendung, Add-In und Pipeline müssen erstellt worden sein, wie in der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Dokumentation unter [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md) beschrieben.  
  
2.  Die Vertragsschnittstelle für das Add-in implementieren muss <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3.  Das Add-in, das die hostanwendung übergeben wird muss direkt oder indirekt von abgeleitet <xref:System.Windows.FrameworkElement>.  
  
4.  Das Add-in muss konvertiert werden, aus einer <xref:System.Windows.FrameworkElement> auf eine <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze.  
  
5.  Das Add-in muss konvertiert werden, aus einer <xref:System.AddIn.Contract.INativeHandleContract> auf eine <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze.  
  
6.  Die hostanwendung zeigt das zurückgegebene <xref:System.Windows.FrameworkElement>.  
  
 Ein Beispiel, in dem das Implementieren eines Add-Ins veranschaulicht wird, bei dem es sich um eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] handelt, finden Sie unter [Gewusst wie: Erstellen eines Add-Ins, das eine Benutzeroberfläche ist](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>Zurückgeben mehrerer Benutzeroberflächen durch ein Add-In  
 Add-Ins stellen oft mehrere [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s zur Verfügung, die Hostanwendungen anzeigen können. Betrachten Sie beispielsweise ein Add-In, das eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ist, die auch Statusinformationen für die Hostanwendung bereitstellt, gleichzeitig als eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]. Sie können ein Add-In dieser Art implementieren, indem Sie eine Kombination der Verfahren aus den Modellen [Add-In gibt eine Benutzeroberfläche zurück](#ReturnUIFromAddInContract) und [Add-In ist eine Benutzeroberfläche](#AddInIsAUI) verwenden.  
  
<a name="AddInsAndXBAPs"></a>   
## <a name="add-ins-and-xaml-browser-applications"></a>Add-Ins und XAML-Browseranwendungen  
 In den bisherigen Beispielen wurde die Hostanwendung als eigenständige Anwendung installiert. [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]-Browseranwendungen können jedoch auch Add-Ins hosten, wobei allerdings die folgenden zusätzlichen Erstellungs- und Implementierungsanforderungen gelten:  
  
-   Das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Anwendungsmanifest muss so konfiguriert sein, dass Pipeline- (Ordner und Assemblys) und Add-In-Assembly in den [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]-Anwendungscache auf dem Clientcomputer heruntergeladen werden, und zwar in denselben Ordner wie [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   Der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Code zum Ermitteln und Laden von Add-Ins muss den [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Anwendungscache für [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] als Speicherort für Pipeline und Add-In verwenden.  
  
-   [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] muss das Add-In in einen speziellen Sicherheitskontext laden, wenn das Add-In auf lose Dateien verweist, die sich auf der Ursprungssite befinden. Wenn sie von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s gehostet werden, können Add-Ins nur auf lose Dateien verweisen, die auf der Ursprungssite der Hostanwendung gespeichert sind.  
  
 In den folgenden Unterabschnitten werden diese Aufgaben ausführlich beschrieben.  
  
### <a name="configuring-the-pipeline-and-add-in-for-clickonce-deployment"></a>Konfigurieren der Pipeline und des Add-Ins für die ClickOnce-Bereitstellung  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s werden in einen sicheren Ordner heruntergeladen und von dort aus im [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Bereitstellungscache ausgeführt. Damit eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ein Add-In hosten kann, müssen auch Pipeline- und Add-In-Assembly in den sicheren Ordner heruntergeladen werden. Um dies zu erreichen, müssen Sie das Anwendungsmanifest so konfigurieren, dass sowohl die Pipeline- als auch die Add-In-Assembly heruntergeladen wird. Diese Aufgabe lässt sich am einfachsten in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] ausführen, obwohl Pipeline- und Add-In-Assembly im Stammordner des [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Hostprojekts gespeichert sein müssen, damit [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] die Pipelineassemblys ermitteln kann.  
  
 Folglich muss der erste Schritt darin bestehen, die Pipeline- und Add-In-Assembly im Stammverzeichnis des [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Projekts zu erstellen. Dazu wird die Buildausgabe der einzelnen Pipelineassembly- und Add-In-Assemblyprojekte festgelegt. Die folgende Tabelle zeigt die Buildausgabepfade für die Pipelineassemblyprojekte und das Add-In-Assemblyprojekt, die sich in demselben Projektmappen- und Stammordner befinden wie das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Hostprojekt.  
  
 Tabelle 1: Buildausgabepfade für die Pipelineassemblys, die von einer XBAP gehostet werden  
  
|Pipelineassemblyprojekt|Ausgabepfad erstellen|  
|-------------------------------|-----------------------|  
|Vertrag|`..\HostXBAP\Contracts\`|  
|Add-In-Ansicht|`..\HostXBAP\AddInViews\`|  
|Add-In-seitiger Adapter|`..\HostXBAP\AddInSideAdapters\`|  
|Hostseitiger Adapter|`..\HostXBAP\HostSideAdapters\`|  
|Add-In|`..\HostXBAP\AddIns\WPFAddIn1`|  
  
 Der nächste Schritt besteht darin, die Pipelineassemblys und die Add-In-Assembly als die Inhaltsdateien der [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] anzugeben. Dazu werden folgende Schritte ausgeführt:  
  
1.  Hinzufügen der Pipeline- und Add-In-Assembly zum Projekt, indem Sie im Projektmappen-Explorer mit der rechten Maustaste auf die einzelnen Pipelineordner klicken und die Option **Zu Projekt hinzufügen** auswählen.  
  
2.  Festlegen des **Buildvorgangs** jeder Pipelineassembly und jeder Add-In-Assembly im **Eigenschaftenfenster** auf **Inhalt**.  
  
 Im letzten Schritt muss das Anwendungsmanifest so konfiguriert werden, dass sowohl die Pipelineassemblydateien als auch die Add-In-Assemblydatei heruntergeladen werden. Die Dateien sollten in Ordnern im Stammverzeichnis des Ordners in dem [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Cache gespeichert sein, den die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Anwendung belegt. Die Konfiguration richten Sie in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] durch folgende Schritte ein:  
  
1.  Klicken Sie mit der rechten Maustaste auf das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Projekt, klicken Sie auf **Eigenschaften**, auf **Veröffentlichen** und dann auf die Schaltfläche **Anwendungsdateien**.  
  
2.  Legen Sie im Dialogfeld **Anwendungsdateien** den **Veröffentlichungsstatus** der einzelnen Pipeline- und Add-In-DLLs auf **Einschließen (Auto)** und die **Downloadgruppe** für die Pipeline- und Add-In-DLLs auf **(Erforderlich)** fest.  
  
### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>Verwenden der Pipeline und des Add-Ins von der Anwendungsbasis  
 Sind Pipeline und Add-In für die [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Bereitstellung konfiguriert, werden sie in denselben [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Cacheordner heruntergeladen wie die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Damit Pipeline und Add-In aus der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] verwendet werden können, müssen sie vom [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Code aus der Anwendungsbasis abgerufen werden. Die unterschiedlichen Typen und Member des Add-In-Modells von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], die zum Verwenden von Pipelines und Add-Ins verfügbar sind, bieten spezielle Unterstützung für dieses Szenario. Erstens wird durch der Pfad identifiziert die <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> -Enumerationswert. Diesen Wert verwenden Sie mit Überladungen der relevanten Add-In-Member, wenn Pipelines verwendet werden sollen, die Folgendes enthalten:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>Zugreifen auf die Ursprungssite des Hosts  
 Damit ein Add-In auf Dateien von der Ursprungssite verweisen kann, muss das Add-In mit einer Sicherheitsisolation geladen werden, die der Hostanwendung entspricht. Bei dieser Sicherheitsstufe identifizierte der <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> Enumerationswert, und übergeben der <xref:System.AddIn.Hosting.AddInToken.Activate%2A> Methode, wenn ein Add-In aktiviert wird.  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>Architektur des WPF-Add-Ins  
 Auf der höchsten Ebene wie wir gesehen haben, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ermöglicht [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -add-ins implementieren [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] (ableiten, die direkt oder indirekt aus <xref:System.Windows.FrameworkElement>) mit <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Das Ergebnis ist, dass die hostanwendung zurückgegeben wird ein <xref:System.Windows.FrameworkElement> angezeigte aus [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in der hostanwendung.  
  
 Für einfache [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Add-In-Szenarien reichen diese Informationen für Entwickler aus. Für komplexere Szenarien, insbesondere solche, bei denen weitere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Dienste wie Layout, Ressourcen und Datenbindung zum Einsatz kommen, sind umfassendere Kenntnisse darüber erforderlich, wie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Unterstützung erweitert. Andernfalls können Sie die Vorteile und Einschränkungen nicht verstehen.  
  
 Im Wesentlichen ist es so, dass [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] keine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von einem Add-In an eine Hostanwendung übergibt, sondern dass [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Win32-Fensterhandle für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] übergibt, und zwar unter Verwendung der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Interoperabilität. Daher geschieht Folgendes, wenn eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von einem Add-In an eine Hostanwendung übergeben wird:  
  
-   Auf der Seite des Add-Ins ruft [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ein Fensterhandle für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ab, die von der Hostanwendung angezeigt wird. Das Fensterhandle wird von einer internen gekapselt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] von abgeleitete Klasse <xref:System.Windows.Interop.HwndSource> und implementiert <xref:System.AddIn.Contract.INativeHandleContract>. Eine Instanz dieser Klasse zurückgegebene <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> und das Add-in Anwendungsdomäne zu Anwendungsdomäne der hostanwendung gemarshallt wird.  
  
-   Auf der Hostseite Anwendung [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] packt neu der <xref:System.Windows.Interop.HwndSource> als eine interne [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] von abgeleitete Klasse <xref:System.Windows.Interop.HwndHost> und nutzt <xref:System.AddIn.Contract.INativeHandleContract>. Eine Instanz dieser Klasse zurückgegebene <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> zur hostanwendung.  
  
 <xref:System.Windows.Interop.HwndHost>zum Anzeigen vorhanden [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], erkennbar Fensterhandles, aus [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]. Weitere Informationen finden Sie unter [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
 Zusammengefasst <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> vorhanden sein, um das Fensterhandle für ermöglichen eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eine hostanwendung von einem Add-in übergeben werden, in denen gekapselt durch eine <xref:System.Windows.Interop.HwndHost> und den Host angezeigt Anwendung [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
> [!NOTE]
>  Da die hostanwendung erhält eine <xref:System.Windows.Interop.HwndHost>, die hostanwendung das Objekt, das von zurückgegebene kann nicht konvertiert werden <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> in den Typ, die sie als durch das Add-in implementiert wird (z. B. eine <xref:System.Windows.Controls.UserControl>).  
  
 Naturgemäß <xref:System.Windows.Interop.HwndHost> gelten bestimmte Einschränkungen, die beeinflussen, wie Sie hostanwendungen verwendet werden können. Allerdings [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erweitert <xref:System.Windows.Interop.HwndHost> mehrere Funktionen für Add-in-Szenarien. Diese Vorteile und die Einschränkungen werden nachstehend beschrieben.  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>Vorteile des WPF-Add-Ins  
 Da [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -add-in [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] angezeigten stammen aus hostanwendungen, die über eine interne Klasse, die abgeleitet <xref:System.Windows.Interop.HwndHost>, diese [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] sind eingeschränkt durch die Funktionen der <xref:System.Windows.Interop.HwndHost> in Bezug auf [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Services wie z. B. Layout, Rendering, Datenbindung, Stile, Vorlagen und Ressourcen. Allerdings [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ergänzt die internen <xref:System.Windows.Interop.HwndHost> Unterklasse mit zusätzlichen Funktionen, die Folgendes enthalten:  
  
-   Wechseln mit der TAB-TASTE zwischen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] einer Hostanwendung und der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add-Ins. Beachten Sie, dass die "Add-in wird eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" Programmiermodell muss der Add-In-seitiger Adapter überschreiben <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> so TAB-Taste, aktivieren Sie, ob das Add-in ist vollständig vertrauenswürdig oder teilweise vertrauenswürdig.  
  
-   Berücksichtigen der Anforderungen an Barrierefreiheit für Add-In-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s, die von [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s für Hostanwendungen angezeigt werden.  
  
-   Ermöglichen, dass [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendungen in Szenarien mit mehreren Anwendungsdomänen sicher ausgeführt werden.  
  
-   Verhindern von unberechtigten Zugriffen auf Add-In-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]n-Fensterhandles, wenn Add-Ins mit Sicherheitsisolation ausgeführt werden (d. h. in einem teilweise vertrauenswürdigen Sicherheitsbereich (Sandbox)). Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> wird sichergestellt, dass diese Sicherheit:  
  
    -   Für die "Add-Ins gibt eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" Programmiermodell, die einzige Möglichkeit, übergeben Sie das Fensterhandle für ein Add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] über die Isolation Grenze ist das Aufrufen <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    -   Für die "Add-in ist eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" Programmierung überschreiben <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> auf der Add-In-seitiger Adapter und der Aufruf <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (wie in den vorherigen Beispielen gezeigt) ist es erforderlich, den Aufruf des Add-In-seitiger Adapters `QueryContract` Implementierung vom hostseitige Adapter.  
  
-   Bereitstellen von Ausführungsschutz für mehrere Anwendungsdomänen. Aufgrund von Einschränkungen bei Anwendungsdomänen führen unbehandelte Ausnahmen, die in Add-In-Anwendungsdomänen ausgelöst werden, zum Absturz der gesamten Anwendung, auch wenn eine Isolationsgrenze eingerichtet ist. [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] und das Add-In-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bieten jedoch eine einfache Möglichkeit, das Problem zu umgehen und die Anwendungsstabilität zu verbessern. Ein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] add-in, das zeigt eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellt eine <xref:System.Windows.Threading.Dispatcher> für den Thread, der die Anwendungsdomäne, ausgeführt wird, wenn die hostanwendung ist eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung. Sie können erkennen, dass nicht behandelte Ausnahmen, die auftreten, in der Anwendungsdomäne durch Behandeln der <xref:System.Windows.Threading.Dispatcher.UnhandledException> -Ereignis für die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] -add-in des <xref:System.Windows.Threading.Dispatcher>. Sie erhalten die <xref:System.Windows.Threading.Dispatcher> aus der <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> Eigenschaft.  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>Einschränkungen des WPF-Add-Ins  
 Über die Vorteile, [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] hinzugefügt, um das Standardverhalten von bereitgestellten <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>, und Fensterhandles, zudem bestehen Einschränkungen für Add-in- [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] von hostanwendungen angezeigt werden:  
  
-   Das Ausschneideverhalten der Hostanwendung wird von den von einer Hostanwendung angezeigten Add-In-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s nicht berücksichtigt.  
  
-   Der Begriff *Airspace* in Interoperabilitätsszenarien gilt auch für Add-Ins (siehe [Übersicht über die Technologieregionen](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)).  
  
-   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Dienste einer Hostanwendung, z. B. Ressourcenvererbung, Datenbindung und Befehle sind für Add-In-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]s nicht automatisch verfügbar. Um diese Dienste für das Add-In bereitzustellen, müssen Sie die Pipeline aktualisieren.  
  
-   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add-Ins kann nicht gedreht, skaliert, verzerrt oder auf andere Weise durch eine Transformation geändert werden (siehe [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)).  
  
-   Inhalte innerhalb von Add-in- [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] , gerendert wird Zeichenvorgänge aus der <xref:System.Drawing> Namespace kann Alphablending enthalten. Allerdings müssen sowohl die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add-Ins als auch die sie enthaltende [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Hostanwendung zu 100 % deckend sein, d. h., die `Opacity`-Eigenschaft muss für beide auf 1 festgelegt sein.  
  
-   Wenn die <xref:System.Windows.Window.AllowsTransparency%2A> Eigenschaft eines Fensters in der hostanwendung, die ein Add-In enthält [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] festgelegt ist, um `true`, das Add-in nicht sichtbar ist. Dies gilt auch, wenn die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] des Add-Ins zu 100 % deckend ist (die `Opacity`-Eigenschaft also den Wert 1 hat).  
  
-   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add-Ins muss über anderen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Elementen in demselben Fenster auf oberster Ebene angezeigt werden.  
  
-   Kein Teil über ein Add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] mit gerendert werden eine <xref:System.Windows.Media.VisualBrush>. Stattdessen kann das Add-In eine Momentaufnahme der generierten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellen, um eine Bitmap zu erstellen, die mit vertraglich definierten Methoden an die Hostanwendung übergeben werden kann.  
  
-   Mediendateien können nicht wiedergegeben werden, aus einer <xref:System.Windows.Controls.MediaElement> in einem Add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
-   Für die Add-In-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] generierte Mausereignisse werden von der Hostanwendung weder empfangen noch ausgelöst. Die `IsMouseOver`-Eigenschaft für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Hostanwendung hat den Wert `false`.  
  
-   Wenn der Fokus zwischen Steuerelementen in einer Add-In-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wechselt, wird das `GotFocus`-Ereignis und das `LostFocus`-Ereignis von der Hostanwendung weder empfangen noch ausgelöst.  
  
-   Der Teil einer Hostanwendung, der eine Add-In-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] enthält, wird beim Drucken weiß angezeigt.  
  
-   Alle Verteiler (finden Sie unter <xref:System.Windows.Threading.Dispatcher>) durch das Add-in erstellt [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] muss manuell beendet werden, bevor das Owner-Add-in entladen wird, wenn die hostanwendung die Ausführung wird fortgeführt. Der Vertrag kann Methoden implementieren, die es der Hostanwendung ermöglichen, dem Add-In vor dem Entladen ein Signal zu übermitteln. Dadurch kann die Add-In-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] die Dispatcher beenden.  
  
-   Wenn ein Add-in [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ist ein <xref:System.Windows.Controls.InkCanvas> oder enthält ein <xref:System.Windows.Controls.InkCanvas>, Sie können nicht entladen des Add-Ins.  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>Leistungsoptimierung  
 Werden mehrere Anwendungsdomänen verwendet, werden die von den einzelnen Anwendungen benötigten verschiedenen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Assemblys standardmäßig alle in die Domäne dieser Anwendung geladen. Aufgrund der Zeit, die zum Erstellen neuer Anwendungsdomänen und für das Starten der darin enthaltenen Anwendungen erforderlich ist, kann die Leistung beeinträchtigt werden. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet allerdings die Möglichkeit, Startzeiten zu verkürzen. Dazu werden Anwendungen angewiesen, Assemblys in Anwendungsdomänen gemeinsam zu nutzen, wenn sie bereits geladen sind. Verwenden Sie hierzu die <xref:System.LoaderOptimizationAttribute> -Attribut, das auf die Einstiegspunktmethode angewendet werden muss (`Main`). In diesem Fall müssen Sie lediglich zum Implementieren Ihrer Anwendungsdefinition Code verwenden (siehe [Übersicht über die Anwendungsverwaltung](../../../../docs/framework/wpf/app-development/application-management-overview.md)).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.LoaderOptimizationAttribute>  
 [Add-Ins und Erweiterbarkeit](../../../../docs/framework/add-ins/index.md)  
 [Anwendungsdomänen](../../../../docs/framework/app-domains/application-domains.md)  
 [Übersicht über .NET Framework-Remoting](http://msdn.microsoft.com/en-us/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)  
 [Machen Objekte remotefähig](http://msdn.microsoft.com/en-us/01197253-3f13-43b7-894d-9683e431192a)  
 [Themen zur Vorgehensweise](../../../../docs/framework/wpf/app-development/how-to-topics.md)
