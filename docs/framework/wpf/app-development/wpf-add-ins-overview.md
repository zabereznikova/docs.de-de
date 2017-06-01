---
title: "&#220;bersicht &#252;ber WPF-Add-Ins | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework-Add-In-Modell [WPF]"
  - "Add-Ins [WPF], Architektur"
  - "Add-Ins [WPF], Vorteile"
  - "Add-Ins [WPF], Einschränkungen"
  - "Add-Ins [WPF], Leistung"
  - "Add-Ins [WPF], Benutzeroberfläche"
  - "Add-Ins und die Benutzeroberfläche [WPF]"
  - "Add-Ins und XAML-Browseranwendungen [WPF]"
  - "Add-Ins-Übersicht [WPF]"
ms.assetid: 00b4c776-29a8-4dba-b603-280a0cdc2ade
caps.latest.revision: 36
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 35
---
# &#220;bersicht &#252;ber WPF-Add-Ins
<a name="Introduction"></a> [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] beinhaltet ein Add\-In\-Modell, mit dem Entwickler Anwendungen erstellen können, die Add\-In\-Erweiterbarkeit unterstützen.  Dieses Add\-In\-Modell ermöglicht die Erstellung von Add\-Ins, die in die Anwendungsfunktionalität integriert werden und diese erweitern.  In einigen Szenarien müssen Anwendungen auch [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] anzeigen, die von Add\-Ins bereitgestellt werden.  In diesem Thema wird gezeigt, wie durch [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] erweitert wird, um diese Szenarien sowie die zugrunde liegende Architektur, die Vorteile und die Einschränkungen zu ermöglichen.  
  
   
  
<a name="Requirements"></a>   
## Vorbereitungsmaßnahmen  
 Kenntnisse des Add\-In\-Modells von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] sind erforderlich.  Weitere Informationen finden Sie unter [Add\-Ins und Erweiterbarkeit](../../../../ml/index.xml).  
  
<a name="AddInsOverview"></a>   
## Übersicht über Add\-Ins  
 Um das mit dem Integrieren neuer Funktionen verbundene erneute Kompilieren und Bereitstellen von Anwendungen zu vermeiden, da diese Vorgänge sehr komplex sind, sind Anwendungen mit Erweiterbarkeitsmechanismen ausgestattet. Diese ermöglichen Entwicklern \(sowohl Erst\- als auch Drittanbieter\) das Erstellen anderer Anwendungen, die integriert werden können.  Diese Art von Erweiterbarkeit wird in der Regel durch die Verwendung von Add\-Ins \(auch als "Add\-Ons" oder "Plug\-Ins" bezeichnet\) unterstützt.  Es folgen Beispiele für reale Anwendungen, die eine Erweiterbarkeit mit Add\-Ins verfügbar machen:  
  
-   Internet Explorer\-Add\-Ons  
  
-   Windows Media Player\-Plug\-Ins  
  
-   Visual Studio\-Add\-Ins  
  
 Beispielsweise können Drittanbieterentwickler mithilfe des Add\-In\-Modells von Windows Media Player "Plug\-Ins" implementieren, durch die der Windows Media Player auf vielfältige Weise erweitert wird. Dazu zählen das Erstellen von Decodern und Encodern für Medienformate, für die keine systemeigene Unterstützung durch Windows Media Player besteht \(z. B. DVD, MP3\), Audioeffekte und Skins.  Jedes Add\-In\-Modell ist so aufgebaut, dass es die zu einer Anwendung gehörenden Funktionen verfügbar macht, obwohl verschiedene Entitäten und Verhaltensweisen für alle Add\-In\-Modelle gelten.  
  
 Die drei Hauptentitäten typischer Add\-In\-Erweiterbarkeitslösungen sind *Verträge*, *Add\-Ins* und *Hostanwendungen*.  Mit Verträgen wird auf zwei Arten definiert, wie Add\-Ins mit Hostanwendungen integriert sind:  
  
-   Add\-Ins sind in Funktionen integriert, die von Hostanwendungen implementiert werden.  
  
-   Hostanwendungen machen Funktionen verfügbar, in die Add\-Ins integriert werden.  
  
 Damit Add\-Ins verwendet werden können, müssen sie von Hostanwendungen gefunden und zur Laufzeit geladen werden.  Daher sind Anwendungen, die Add\-Ins unterstützen, zusätzlich für folgende Aufgaben verantwortlich:  
  
-   **Ermittlung**: Suchen nach Add\-Ins, die von Hostanwendungen unterstützte Verträge einhalten.  
  
-   **Aktivierung**: Laden, Ausführen und Herstellen der Kommunikation mit Add\-Ins.  
  
-   **Isolation**: Verwenden von Anwendungsdomänen oder Prozessen zum Einrichten von Isolationsgrenzen, die Anwendungen vor möglichen Sicherheitsproblemen und Problemen bei der Ausführung von Add\-Ins schützen.  
  
-   **Kommunikation**: Durch das Aufrufen von Methoden und Übergeben von Daten können Add\-Ins und Hostanwendungen über Isolationsgrenzen hinweg miteinander kommunizieren.  
  
-   **Verwaltung der Lebensdauer**: Laden und Entladen von Anwendungsdomänen und \-prozessen auf eine klare, vorhersehbare Weise \(siehe [Anwendungsdomänen](../../../../docs/framework/app-domains/application-domains.md)\).  
  
-   **Versionsverwaltung**: Sicherstellen, dass Hostanwendungen und Add\-Ins auch dann noch kommunizieren können, wenn neue Versionen erstellt wurden.  
  
 Letztlich ist es eine wichtige Aufgabe, ein stabiles Add\-In\-Modell zu entwickeln.  Aus diesem Grund stellt [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] eine Infrastruktur zum Erstellen von Add\-In\-Modellen bereit.  
  
> [!NOTE]
>  Weitere Informationen zu Add\-Ins finden Sie unter [Add\-Ins und Erweiterbarkeit](../../../../ml/index.xml).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## Übersicht über das Add\-In\-Modell von .NET Framework  
 Das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], das im <xref:System.AddIn>\-Namespace vorkommt, enthält eine Reihe von Typen, mit denen die Entwicklung der Add\-In\-Erweiterbarkeit vereinfacht werden soll.  Das Fundament des Add\-In\-Modells von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] stellt der *Vertrag* dar. Dort ist festgelegt, wie eine Hostanwendung und ein Add\-In miteinander kommunizieren.  Ein Vertrag wird mit einer für Hostanwendungen spezifischen *Ansicht* des Vertrags für eine Hostanwendung verfügbar gemacht.  Auf ähnliche Weise wird eine für Add\-Ins spezifische *Ansicht* des Vertrags für das Add\-In verfügbar gemacht.  Ein *Adapter* ermöglicht es einer Hostanwendung und einem Add\-In, zwischen ihren jeweiligen Ansichten des Vertrags miteinander zu kommunizieren.  Verträge, Ansichten und Adapter werden als Segmente bezeichnet, und mehrere miteinander verbundene Segmente stellen eine *Pipeline* dar.  Pipelines sind die Grundlage, wenn es für das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] darum geht, Aufgaben wie Ermittlung, Aktivierung, Sicherheitsisolation, Ausführungsisolation \(unter Verwendung von Anwendungsdomänen und \-prozessen\), Kommunikation, Verwaltung der Lebensdauer und Versionsverwaltung zu unterstützen.  
  
 Mit dieser Unterstützung können Entwickler Add\-Ins erstellen, die mit den Funktionen einer Hostanwendung integriert werden.  In einigen Szenarien müssen Hostanwendungen die von Add\-Ins bereitgestellten [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] anzeigen.  Da jede Präsentationstechnologie in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] über ein eigenes Modell zum Implementieren von [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] verfügt, unterstützt das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] keine bestimmte Präsentationstechnologie.  Stattdessen erweitert [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]nunterstützung für Add\-Ins.  
  
<a name="WPFAddInModel"></a>   
## WPF\-Add\-Ins  
 Wenn Sie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] in Verbindung mit dem Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] verwenden, können Sie den unterschiedlichsten Szenarien gerecht werden, in denen Hostanwendungen [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] aus Add\-Ins anzeigen müssen.  Für diese Szenarien eignet sich insbesondere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mit den folgenden zwei Programmiermodellen:  
  
1.  **Das Add\-In gibt eine Benutzeroberfläche zurück**.  Wie im Vertrag definiert, gibt ein Add\-In über einen Methodenaufruf eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an die Hostanwendung zurück.  Das Szenario wird in den folgenden Fällen verwendet:  
  
    -   Die Darstellung einer vom Add\-In zurückgegebenen [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] hängt von den zur Laufzeit vorhandenen Daten oder Bedingungen ab, z. B. von dynamisch generierten Berichten.  
  
    -   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für durch ein Add\-In bereitgestellte Dienste unterscheidet sich von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Hostanwendungen, die das Add\-In verwenden können.  
  
    -   Das Add\-In führt in erster Linie einen Dienst für die Hostanwendung aus und meldet den Status an die Hostanwendung mit einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
2.  **Das Add\-In ist eine Benutzeroberfläche**.  Ein Add\-In ist eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], wie im Vertrag definiert.  Das Szenario wird in den folgenden Fällen verwendet:  
  
    -   Ein Add\-In stellt ausschließlich die angezeigten Dienste bereit, z. B. eine Werbung.  
  
    -   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] für von einem Add\-In bereitgestellte Dienste wird von allen Hostanwendungen genutzt, die das Add\-In verwenden können, z. B. Rechner oder Farbauswahl.  
  
 In diesen Szenarien ist es erforderlich, dass [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]nobjekte zwischen den Domänen der Hostanwendung und der Add\-In\-Anwendung übergeben werden können.  Da beim Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] für die Kommunikation zwischen Anwendungsdomänen Remoting erforderlich ist, müssen die übergebenen Objekte remotefähig sein.  
  
 Ein remotefähiges Objekt stellt die Instanz einer Klasse dar, für die eine oder mehrere der folgenden Aussagen gelten:  
  
-   Wird von der <xref:System.MarshalByRefObject>\-Klasse abgeleitet.  
  
-   Implementiert die <xref:System.Runtime.Serialization.ISerializable>\-Schnittstelle.  
  
-   Verfügt über das <xref:System.SerializableAttribute>\-Attribut.  
  
> [!NOTE]
>  Weitere Informationen über das Erstellen von remotefähigen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Objekten finden Sie unter [Making Objects Remotable](http://msdn.microsoft.com/de-de/01197253-3f13-43b7-894d-9683e431192a).  
  
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]ntypen von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] sind nicht remotefähig.  Um das Problem zu beheben, erweitert [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], damit die durch Add\-Ins erstellte [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von Hostanwendungen angezeigt werden kann.  Diese Unterstützung stellt [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] durch zwei Typen bereit: die <xref:System.AddIn.Contract.INativeHandleContract>\-Schnittstelle und zwei statische Methoden, die von der <xref:System.AddIn.Pipeline.FrameworkElementAdapters>\-Klasse implementiert werden: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  Im Allgemeinen werden diese Typen und Methoden wie folgt verwendet:  
  
1.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erfordert, dass von Add\-Ins bereitgestellte [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] direkt oder indirekt von <xref:System.Windows.FrameworkElement> abgeleitete Klassen sind, z. B. Formen, Steuerelemente, Benutzersteuerelemente, Layoutbereiche und Seiten.  
  
2.  Wenn in dem Vertrag angegeben ist, dass eine Benutzeroberfläche zwischen dem Add\-In und der Hostanwendung übergeben wird, muss er als <xref:System.AddIn.Contract.INativeHandleContract> deklariert sein \(nicht als <xref:System.Windows.FrameworkElement>\). <xref:System.AddIn.Contract.INativeHandleContract> ist eine remotefähige Darstellung der Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die über Isolationsgrenzen hinweg übergeben werden kann.  
  
3.  Vor dem Übergeben von der Anwendungsdomäne des Add\-Ins wird ein <xref:System.Windows.FrameworkElement> als <xref:System.AddIn.Contract.INativeHandleContract> gepackt. Dies geschieht durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4.  Nach dem Übergeben an die Anwendungsdomäne der Hostanwendung muss der <xref:System.AddIn.Contract.INativeHandleContract> erneut als <xref:System.Windows.FrameworkElement> gepackt werden. Die geschieht durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Die Verwendung von <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> hängt von dem jeweiligen Szenario ab.  Die folgenden Abschnitte bieten ausführliche Informationen zu den Programmiermodellen.  
  
<a name="ReturnUIFromAddInContract"></a>   
## Add\-In gibt eine Benutzeroberfläche zurück  
 Damit ein Add\-In eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] an eine Hostanwendung zurückgeben kann, müssen folgende Voraussetzungen erfüllt sein:  
  
1.  Hostanwendung, Add\-In und Pipeline müssen erstellt worden sein, wie in der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Dokumentation unter [Add\-Ins und Erweiterbarkeit](../../../../ml/index.xml) beschrieben.  
  
2.  Der Vertrag muss <xref:System.AddIn.Contract.IContract> implementieren. Zum Zurückgeben einer [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] muss der Vertrag eine Methode mit einem Rückgabewert vom Typ <xref:System.AddIn.Contract.INativeHandleContract> deklarieren.  
  
3.  Die zwischen Add\-In und Hostanwendung übergebene [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] muss direkt oder indirekt von <xref:System.Windows.FrameworkElement> abgeleitet werden.  
  
4.  Die vom Add\-In zurückgegebene [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] muss vor dem Überschreiten der Isolationsgrenze von <xref:System.Windows.FrameworkElement> in <xref:System.AddIn.Contract.INativeHandleContract> umgewandelt werden.  
  
5.  Die zurückgegebene [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] muss nach dem Überschreiten der Isolationsgrenze von <xref:System.AddIn.Contract.INativeHandleContract> in <xref:System.Windows.FrameworkElement> umgewandelt werden.  
  
6.  Die Hostanwendung zeigt das zurückgegebene <xref:System.Windows.FrameworkElement> an.  
  
 Ein Beispiel dafür, wie ein Add\-In, das eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zurückgibt, implementiert wird, finden Sie unter [Gewusst wie: Erstellen eines Add\-Ins, das eine Benutzeroberfläche zurückgibt](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## Add\-In ist eine Benutzeroberfläche  
 Wenn ein Add\-In eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ist, gelten die folgenden Voraussetzungen:  
  
1.  Hostanwendung, Add\-In und Pipeline müssen erstellt worden sein, wie in der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Dokumentation unter [Add\-Ins und Erweiterbarkeit](../../../../ml/index.xml) beschrieben.  
  
2.  Die Vertragsschnittstelle für das Add\-In muss <xref:System.AddIn.Contract.INativeHandleContract> implementieren.  
  
3.  Das an die Hostanwendung übergebene Add\-In muss direkt oder indirekt von <xref:System.Windows.FrameworkElement> abgeleitet werden.  
  
4.  Das Add\-In muss vor dem Überschreiten der Isolationsgrenze von <xref:System.Windows.FrameworkElement> in <xref:System.AddIn.Contract.INativeHandleContract> umgewandelt werden.  
  
5.  Das Add\-In muss nach dem Überschreiten der Isolationsgrenze von <xref:System.AddIn.Contract.INativeHandleContract> in <xref:System.Windows.FrameworkElement> umgewandelt werden.  
  
6.  Die Hostanwendung zeigt das zurückgegebene <xref:System.Windows.FrameworkElement> an.  
  
 Ein Beispiel, in dem das Implementieren eines Add\-Ins veranschaulicht wird, bei dem es sich um eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] handelt, finden Sie unter [Gewusst wie: Erstellen eines Add\-Ins, das eine Benutzeroberfläche ist](../../../../docs/framework/wpf/app-development/how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## Zurückgeben mehrerer Benutzeroberflächen durch ein Add\-In  
 Add\-Ins stellen oft mehrere [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] zur Verfügung, die Hostanwendungen anzeigen können.  Betrachten Sie beispielsweise ein Add\-In, das eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ist, die auch Statusinformationen für die Hostanwendung bereitstellt, gleichzeitig als eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  Sie können ein Add\-In dieser Art implementieren, indem Sie eine Kombination der Verfahren aus den Modellen [Add\-In gibt eine Benutzeroberfläche zurück](#ReturnUIFromAddInContract) und [Add\-In ist eine Benutzeroberfläche](#AddInIsAUI) verwenden.  
  
<a name="AddInsAndXBAPs"></a>   
## Add\-Ins und XAML\-Browseranwendungen  
 In den bisherigen Beispielen wurde die Hostanwendung als eigenständige Anwendung installiert.  [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] können jedoch auch Add\-Ins hosten, wobei allerdings die folgenden zusätzlichen Erstellungs\- und Implementierungsanforderungen gelten:  
  
-   Das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Anwendungsmanifest muss so konfiguriert sein, dass Pipeline\- \(Ordner und Assemblys\) und Add\-In\-Assembly in den [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]\-Anwendungscache auf dem Clientcomputer heruntergeladen werden, und zwar in denselben Ordner wie [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
-   Der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Code zum Ermitteln und Laden von Add\-Ins muss den [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]\-Anwendungscache für [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] als Speicherort für Pipeline und Add\-In verwenden.  
  
-   [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] muss das Add\-In in einen speziellen Sicherheitskontext laden, wenn das Add\-In auf lose Dateien verweist, die sich auf der Ursprungssite befinden. Wenn sie von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] gehostet werden, können Add\-Ins nur auf lose Dateien verweisen, die auf der Ursprungssite der Hostanwendung gespeichert sind.  
  
 In den folgenden Unterabschnitten werden diese Aufgaben ausführlich beschrieben.  
  
### Konfigurieren der Pipeline und des Add\-Ins für die ClickOnce\-Bereitstellung  
 [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] werden in einen sicheren Ordner heruntergeladen und von dort aus im [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]\-Bereitstellungscache ausgeführt.  Damit eine [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] ein Add\-In hosten kann, müssen auch Pipeline\- und Add\-In\-Assembly in den sicheren Ordner heruntergeladen werden.  Um dies zu erreichen, müssen Sie das Anwendungsmanifest so konfigurieren, dass sowohl die Pipeline\- als auch die Add\-In\-Assembly heruntergeladen wird.  Diese Aufgabe lässt sich am einfachsten in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] ausführen, obwohl Pipeline\- und Add\-In\-Assembly im Stammordner des [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Hostprojekts gespeichert sein müssen, damit [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] die Pipelineassemblys ermitteln kann.  
  
 Folglich muss der erste Schritt darin bestehen, die Pipeline\- und Add\-In\-Assembly im Stammverzeichnis des [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Projekts zu erstellen. Dazu wird die Buildausgabe der einzelnen Pipelineassembly\- und Add\-In\-Assemblyprojekte festgelegt.  Die folgende Tabelle zeigt die Buildausgabepfade für die Pipelineassemblyprojekte und das Add\-In\-Assemblyprojekt, die sich in demselben Projektmappen\- und Stammordner befinden wie das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Hostprojekt.  
  
 Tabelle 1: Buildausgabepfade für die Pipelineassemblys, die von einer XBAP gehostet werden  
  
|Pipelineassemblyprojekt|Ausgabepfad erstellen|  
|-----------------------------|---------------------------|  
|Vertrag|`..  \HostXBAP\Contracts\`|  
|Add\-In\-Ansicht|`..  \HostXBAP\AddInViews\`|  
|Add\-In\-seitiger Adapter|`..  \HostXBAP\AddInSideAdapters\`|  
|Hostseitiger Adapter|`..  \HostXBAP\HostSideAdapters\`|  
|Add\-In|`..  \HostXBAP\AddIns\WPFAddIn1`|  
  
 Der nächste Schritt besteht darin, die Pipelineassemblys und die Add\-In\-Assembly als die Inhaltsdateien der [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)] in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] anzugeben. Dazu werden folgende Schritte ausgeführt:  
  
1.  Hinzufügen der Pipeline\- und Add\-In\-Assembly zum Projekt, indem Sie im Projektmappen\-Explorer mit der rechten Maustaste auf die einzelnen Pipelineordner klicken und die Option **Zu Projekt hinzufügen** auswählen.  
  
2.  Festlegen des **Buildvorgangs** jeder Pipelineassembly und jeder Add\-In\-Assembly im **Eigenschaftenfenster** auf **Inhalt**.  
  
 Im letzten Schritt muss das Anwendungsmanifest so konfiguriert werden, dass sowohl die Pipelineassemblydateien als auch die Add\-In\-Assemblydatei heruntergeladen werden.  Die Dateien sollten in Ordnern im Stammverzeichnis des Ordners in dem [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]\-Cache gespeichert sein, den die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Anwendung belegt.  Die Konfiguration richten Sie in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] durch folgende Schritte ein:  
  
1.  Klicken Sie mit der rechten Maustaste auf das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Projekt, klicken Sie auf **Eigenschaften**, auf **Veröffentlichen** und dann auf die Schaltfläche **Anwendungsdateien**.  
  
2.  Legen Sie im Dialogfeld **Anwendungsdateien** den **Veröffentlichungsstatus** der einzelnen Pipeline\- und Add\-In\-DLLs auf **Einschließen \(Auto\)** und die **Downloadgruppe** für die Pipeline\- und Add\-In\-DLLs auf **\(Erforderlich\)** fest.  
  
### Verwenden der Pipeline und des Add\-Ins von der Anwendungsbasis  
 Sind Pipeline und Add\-In für die [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]\-Bereitstellung konfiguriert, werden sie in denselben [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]\-Cacheordner heruntergeladen wie die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  Damit Pipeline und Add\-In aus der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] verwendet werden können, müssen sie vom [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]\-Code aus der Anwendungsbasis abgerufen werden.  Die unterschiedlichen Typen und Member des Add\-In\-Modells von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], die zum Verwenden von Pipelines und Add\-Ins verfügbar sind, bieten spezielle Unterstützung für dieses Szenario.  Zuerst wird der Pfad durch den <xref:System.AddIn.Hosting.PipelineStoreLocation>\-Enumerationswert identifiziert.  Diesen Wert verwenden Sie mit Überladungen der relevanten Add\-In\-Member, wenn Pipelines verwendet werden sollen, die Folgendes enthalten:  
  
-   <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
-   [AddInStore.FindAddIns\(Type, PipelineStoreLocation, String\<xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=fullName>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
-   <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=fullName>  
  
### Zugreifen auf die Ursprungssite des Hosts  
 Damit ein Add\-In auf Dateien von der Ursprungssite verweisen kann, muss das Add\-In mit einer Sicherheitsisolation geladen werden, die der Hostanwendung entspricht.  Diese Sicherheitsebene wird durch den <xref:System.AddIn.Hosting.AddInSecurityLevel?displayProperty=fullName>\-Enumerationswert identifiziert und beim Aktivieren eines Add\-Ins an die <xref:System.AddIn.Hosting.AddInToken.Activate%2A>\-Methode übergeben.  
  
<a name="WPFAddInModelArchitecture"></a>   
## Architektur des WPF\-Add\-Ins  
 Wie bereits erwähnt, ermöglicht [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] auf oberster Ebene, dass [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Add\-Ins [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] implementieren \(die direkt oder indirekt von <xref:System.Windows.FrameworkElement> abgeleitet werden\), und zwar mithilfe von <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  Als Ergebnis wird an die Hostanwendung <xref:System.Windows.FrameworkElement> zurückgegeben, das von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] in der Hostanwendung angezeigt wird.  
  
 Für einfache [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]n\-Add\-In\-Szenarien reichen diese Informationen für Entwickler aus.  Für komplexere Szenarien, insbesondere solche, bei denen weitere [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Dienste wie Layout, Ressourcen und Datenbindung zum Einsatz kommen, sind umfassendere Kenntnisse darüber erforderlich, wie [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] um [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]nunterstützung erweitert. Andernfalls können Sie die Vorteile und Einschränkungen nicht verstehen.  
  
 Im Wesentlichen ist es so, dass [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] keine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von einem Add\-In an eine Hostanwendung übergibt, sondern dass [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] das Win32\-Fensterhandle für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] übergibt, und zwar unter Verwendung der [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Interoperabilität.  Daher geschieht Folgendes, wenn eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von einem Add\-In an eine Hostanwendung übergeben wird:  
  
-   Auf der Seite des Add\-Ins ruft [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] ein Fensterhandle für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] ab, die von der Hostanwendung angezeigt wird.  Das Fensterhandle wird von einer internen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Klasse gekapselt, die von <xref:System.Windows.Interop.HwndSource> abgeleitet wird und <xref:System.AddIn.Contract.INativeHandleContract> implementiert.  Eine Instanz dieser Klasse wird von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> zurückgegeben und von der Anwendungsdomäne des Add\-Ins an die Anwendungsdomäne der Hostanwendung gemarshallt.  
  
-   Auf der Seite der Hostanwendung wird <xref:System.Windows.Interop.HwndSource> von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] als interne [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Klasse neu gepackt, die von <xref:System.Windows.Interop.HwndHost> abgeleitet wird und <xref:System.AddIn.Contract.INativeHandleContract> nutzt.  Eine Instanz dieser Klasse wird von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> an die Hostanwendung zurückgegeben.  
  
 <xref:System.Windows.Interop.HwndHost> ist enthalten, damit die durch Fensterhandles identifizierten [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] aus [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] angezeigt werden.  Weitere Informationen finden Sie unter [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
 Zusammenfassend lässt sich sagen, dass <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> vorhanden sind, damit das Fensterhandle für eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von einem Add\-In an eine Hostanwendung übergeben werden kann, wo es durch <xref:System.Windows.Interop.HwndHost> gekapselt und von der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Hostanwendung angezeigt wird.  
  
> [!NOTE]
>  Da die Hostanwendung <xref:System.Windows.Interop.HwndHost> abruft, kann die Hostanwendung das von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> zurückgegebene Objekt nicht in den Typ konvertieren, mit dem vom Add\-In implementiert wurde \(z. B. <xref:System.Windows.Controls.UserControl>\).  
  
 <xref:System.Windows.Interop.HwndHost> unterliegt bestimmten Einschränkungen, die sich auf die Verwendung durch Hostanwendungen auswirken.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] erweitert <xref:System.Windows.Interop.HwndHost> allerdings um mehrere Funktionen für Add\-In\-Szenarien.  Diese Vorteile und die Einschränkungen werden nachstehend beschrieben.  
  
<a name="WPFAddInModelBenefits"></a>   
## Vorteile des WPF\-Add\-Ins  
 Da Add\-In\-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] mithilfe einer internen Klasse, die von <xref:System.Windows.Interop.HwndHost> abgeleitet wird, über Hostanwendungen angezeigt werden, sind diese [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] durch die Funktionen von <xref:System.Windows.Interop.HwndHost> eingeschränkt, was Dienste der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] von [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] wie Layout, Rendering, Datenbindung, Formate, Vorlagen und Ressourcen betrifft.  Allerdings erweitert [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] die interne <xref:System.Windows.Interop.HwndHost>\-Unterklasse um zusätzliche Funktionen, beispielsweise:  
  
-   Wechseln mit der TAB\-TASTE zwischen der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] einer Hostanwendung und der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add\-Ins.  Beachten Sie, dass es für das Programmiermodell "Add\-In ist eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" erforderlich ist, dass der Add\-In\-seitige Adapter <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> überschreibt, um das Wechseln mit der TAB\-TASTE zu aktivieren. Dies gilt sowohl für voll vertrauenswürdige als auch für teilweise vertrauenswürdige Add\-Ins.  
  
-   Berücksichtigen der Anforderungen an Barrierefreiheit für Add\-In\-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], die von [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] für Hostanwendungen angezeigt werden.  
  
-   Ermöglichen, dass [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendungen in Szenarien mit mehreren Anwendungsdomänen sicher ausgeführt werden.  
  
-   Verhindern von unberechtigten Zugriffen auf Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]n\-Fensterhandles, wenn Add\-Ins mit Sicherheitsisolation ausgeführt werden \(d. h. in einem teilweise vertrauenswürdigen Sicherheitsbereich \(Sandbox\)\).  Das Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> gewährleistet diese Sicherheit:  
  
    -   Beim Programmiermodell "Add\-In gibt eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] zurück", kann nur dadurch das Fensterhandle für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add\-Ins über die Isolationsgrenze hinweg übergeben werden, dass <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> aufgerufen wird.  
  
    -   Beim Programmiermodell "Add\-In ist eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]" ist es erforderlich, <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> auf dem Add\-In\-seitigen Adapter zu überschreiben und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> aufzurufen \(wie in den vorhergehenden Beispielen gezeigt\). Außerdem muss die `QueryContract`\-Implementierung des Add\-In\-seitigen Adapters vom hostseitigen Adapter aufgerufen werden.  
  
-   Bereitstellen von Ausführungsschutz für mehrere Anwendungsdomänen.  Aufgrund von Einschränkungen bei Anwendungsdomänen führen unbehandelte Ausnahmen, die in Add\-In\-Anwendungsdomänen ausgelöst werden, zum Absturz der gesamten Anwendung, auch wenn eine Isolationsgrenze eingerichtet ist.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] und das Add\-In\-Modell von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bieten jedoch eine einfache Möglichkeit, das Problem zu umgehen und die Anwendungsstabilität zu verbessern.  Ein [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Add\-In, das eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] anzeigt, erstellt <xref:System.Windows.Threading.Dispatcher> für den Thread, auf dem die Anwendungsdomäne ausgeführt wird, wenn es sich bei der Hostanwendung um eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Anwendung handelt.  Sie können alle unbehandelten Ausnahmen ermitteln, die in der Anwendungsdomäne auftreten, indem Sie das <xref:System.Windows.Threading.Dispatcher.UnhandledException>\-Ereignis von <xref:System.Windows.Threading.Dispatcher> des [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Add\-Ins behandeln.  Sie können <xref:System.Windows.Threading.Dispatcher> aus der <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>\-Eigenschaft abrufen.  
  
<a name="WPFAddInModelLimitations"></a>   
## Einschränkungen des WPF\-Add\-Ins  
 Neben den Vorteilen, die [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] für die von <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> und Fensterhandles bereitgestellten Standardverhalten bietet, gibt es auch Einschränkungen für Add\-In\-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], die von Hostanwendungen angezeigt werden:  
  
-   Das Ausschneideverhalten der Hostanwendung wird von den von einer Hostanwendung angezeigten Add\-In\-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] nicht berücksichtigt.  
  
-   Der Begriff *Airspace* in Interoperabilitätsszenarien gilt auch für Add\-Ins \(siehe [Übersicht über die Technologieregionen](../../../../docs/framework/wpf/advanced/technology-regions-overview.md)\).  
  
-   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]ndienste einer Hostanwendung, z. B. Ressourcenvererbung, Datenbindung und Befehle sind für Add\-In\-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)] nicht automatisch verfügbar.  Um diese Dienste für das Add\-In bereitzustellen, müssen Sie die Pipeline aktualisieren.  
  
-   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add\-Ins kann nicht gedreht, skaliert, verzerrt oder auf andere Weise durch eine Transformation geändert werden \(siehe [Übersicht über Transformationen](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)\).  
  
-   Inhalte innerhalb von Add\-In\-[!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)], die durch Zeichenvorgänge aus dem <xref:System.Drawing>\-Namespace gerendert werden, können Alphablending umfassen.  Allerdings müssen sowohl die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add\-Ins als auch die sie enthaltende [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Hostanwendung zu 100 % deckend sein, d. h., die `Opacity`\-Eigenschaft muss für beide auf 1 festgelegt sein.  
  
-   Wenn die <xref:System.Windows.Window.AllowsTransparency%2A>\-Eigenschaft eines Fensters in der Hostanwendung, die die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add\-Ins enthält, auf `true` festgelegt ist, ist das Add\-In nicht sichtbar.  Dies gilt auch, wenn die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] des Add\-Ins zu 100 % deckend ist \(die `Opacity`\-Eigenschaft also den Wert 1 hat\).  
  
-   Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add\-Ins muss über anderen [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]\-Elementen in demselben Fenster auf oberster Ebene angezeigt werden.  
  
-   Kein Teil einer Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] kann mit <xref:System.Windows.Media.VisualBrush> gerendert werden.  Stattdessen kann das Add\-In eine Momentaufnahme der generierten [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellen, um eine Bitmap zu erstellen, die mit vertraglich definierten Methoden an die Hostanwendung übergeben werden kann.  
  
-   Mediendateien können nicht von einem <xref:System.Windows.Controls.MediaElement> in der [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] eines Add\-Ins wiedergegeben werden.  
  
-   Für die Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] generierte Mausereignisse werden von der Hostanwendung weder empfangen noch ausgelöst. Die `IsMouseOver`\-Eigenschaft für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Hostanwendung hat den Wert `false`.  
  
-   Wenn der Fokus zwischen Steuerelementen in einer Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] wechselt, wird das `GotFocus`\-Ereignis und das `LostFocus`\-Ereignis von der Hostanwendung weder empfangen noch ausgelöst.  
  
-   Der Teil einer Hostanwendung, der eine Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] enthält, wird beim Drucken weiß angezeigt.  
  
-   Alle Dispatcher \(siehe <xref:System.Windows.Threading.Dispatcher>\), die von der Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] erstellt wurden, müssen manuell beendet werden, bevor das Add\-In des Besitzers entladen wird, wenn die Ausführung der Hostanwendung fortgesetzt wird.  Der Vertrag kann Methoden implementieren, die es der Hostanwendung ermöglichen, dem Add\-In vor dem Entladen ein Signal zu übermitteln. Dadurch kann die Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] die Dispatcher beenden.  
  
-   Handelt es sich bei der Add\-In\-[!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] um <xref:System.Windows.Controls.InkCanvas>, oder enthält sie <xref:System.Windows.Controls.InkCanvas>, können Sie das Add\-In nicht entladen.  
  
<a name="PerformanceOptimization"></a>   
## Leistungsoptimierung  
 Werden mehrere Anwendungsdomänen verwendet, werden die von den einzelnen Anwendungen benötigten verschiedenen [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]\-Assemblys standardmäßig alle in die Domäne dieser Anwendung geladen.  Aufgrund der Zeit, die zum Erstellen neuer Anwendungsdomänen und für das Starten der darin enthaltenen Anwendungen erforderlich ist, kann die Leistung beeinträchtigt werden.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] bietet allerdings die Möglichkeit, Startzeiten zu verkürzen. Dazu werden Anwendungen angewiesen, Assemblys in Anwendungsdomänen gemeinsam zu nutzen, wenn sie bereits geladen sind.  Um dies zu erreichen, verwenden Sie das <xref:System.LoaderOptimizationAttribute>\-Attribut, das auf die Einstiegspunktmethode \(`Main`\) angewendet werden muss.  In diesem Fall müssen Sie lediglich zum Implementieren Ihrer Anwendungsdefinition Code verwenden \(siehe [Übersicht über die Anwendungsverwaltung](../../../../docs/framework/wpf/app-development/application-management-overview.md)\).  
  
## Siehe auch  
 <xref:System.LoaderOptimizationAttribute>   
 [Add\-Ins und Erweiterbarkeit](../../../../ml/index.xml)   
 [Anwendungsdomänen](../../../../docs/framework/app-domains/application-domains.md)   
 [.NET Framework Remoting Overview](http://msdn.microsoft.com/de-de/eccb1d31-0a22-417a-97fd-f4f1f3aa4462)   
 [Making Objects Remotable](http://msdn.microsoft.com/de-de/01197253-3f13-43b7-894d-9683e431192a)   
 [Gewusst wie\-Themen](../../../../docs/framework/wpf/app-development/how-to-topics.md)