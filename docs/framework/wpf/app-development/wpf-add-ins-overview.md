---
title: Übersicht über WPF-Add-Ins
ms.date: 03/30/2017
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
ms.openlocfilehash: 93fa26927a6afc9d9f7a96198abeef6f45fc35b4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651918"
---
# <a name="wpf-add-ins-overview"></a>Übersicht über WPF-Add-Ins
<a name="Introduction"></a> .NET Framework enthält eine Add-In-Modell, mit denen Entwickler Anwendungen erstellen, die Add-in-Erweiterbarkeit zu unterstützen. Dieses Add-In-Modell ermöglicht die Erstellung von Add-Ins, die in die Anwendungsfunktionalität integriert werden und diese erweitern. In einigen Szenarien müssen Anwendungen auch von Benutzeroberflächen anzeigen, die von Add-Ins bereitgestellt werden. In diesem Thema wird gezeigt, wie das .NET Framework-add-in-Modell zum Aktivieren dieser Szenarien, in der Architektur hinter, dessen Vorteile und Einschränkungen von WPF erweitert.  

<a name="Requirements"></a>   
## <a name="prerequisites"></a>Vorraussetzungen  
 Vertrautheit mit dem Add-In-Modell von .NET Framework ist erforderlich. Weitere Informationen finden Sie unter [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).  
  
<a name="AddInsOverview"></a>   
## <a name="add-ins-overview"></a>Übersicht über Add-Ins  
 Um das mit dem Integrieren neuer Funktionen verbundene erneute Kompilieren und Bereitstellen von Anwendungen zu vermeiden, da diese Vorgänge sehr komplex sind, sind Anwendungen mit Erweiterbarkeitsmechanismen ausgestattet. Diese ermöglichen Entwicklern (sowohl Erst- als auch Drittanbieter) das Erstellen anderer Anwendungen, die integriert werden können. Diese Art von Erweiterbarkeit wird in der Regel durch die Verwendung von Add-Ins (auch als „Add-Ons“ oder „Plug-Ins“ bezeichnet) unterstützt. Es folgen Beispiele für reale Anwendungen, die eine Erweiterbarkeit mit Add-Ins verfügbar machen:  
  
- Internet Explorer-Add-Ons  
  
- Windows Media Player-Plug-Ins  
  
- Visual Studio-Add-Ins  
  
 Beispielsweise können Drittanbieterentwickler mithilfe des Add-In-Modells von Windows Media Player „Plug-Ins“ implementieren, durch die der Windows Media Player auf vielfältige Weise erweitert wird. Dazu zählen das Erstellen von Decodern und Encodern für Medienformate, für die keine systemeigene Unterstützung durch Windows Media Player besteht (z. B. DVD, MP3), Audioeffekte und Skins. Jedes Add-In-Modell ist so aufgebaut, dass es die zu einer Anwendung gehörenden Funktionen verfügbar macht, obwohl verschiedene Entitäten und Verhaltensweisen für alle Add-In-Modelle gelten.  
  
 Die drei Hauptentitäten typischer Add-In-Erweiterbarkeitslösungen sind *Verträge*, *Add-Ins* und *Hostanwendungen*. Mit Verträgen wird auf zwei Arten definiert, wie Add-Ins mit Hostanwendungen integriert sind:  
  
- Add-Ins sind in Funktionen integriert, die von Hostanwendungen implementiert werden.  
  
- Hostanwendungen machen Funktionen verfügbar, in die Add-Ins integriert werden.  
  
 Damit Add-Ins verwendet werden können, müssen sie von Hostanwendungen gefunden und zur Laufzeit geladen werden. Daher sind Anwendungen, die Add-Ins unterstützen, zusätzlich für folgende Aufgaben verantwortlich:  
  
- **Discovery**: Suchen von Add-Ins, die von hostanwendungen unterstützte Verträge einhalten.  
  
- **Aktivierung**: Laden, ausführen und beim Herstellen der Kommunikation mit add-ins.  
  
- **Isolation**: Verwenden von Anwendungsdomänen oder Prozessen zum Einrichten von Isolationsgrenzen, die Anwendungen vor potenziellen Sicherheits- und berichtsausführungsproblemen mit add-ins zu schützen.  
  
- **Kommunikation**: Können Add-Ins und hostanwendungen über Isolationsgrenzen hinweg miteinander kommunizieren, durch Aufrufen von Methoden und übergeben von Daten.  
  
- **Verwaltung der Lebensdauer**: Laden und Entladen von Anwendungsdomänen und Prozesse in eine klare, vorhersehbare Weise (finden Sie unter [Anwendungsdomänen](../../app-domains/application-domains.md)).  
  
- **Versioning**: Sicherstellen, dass hostanwendungen und Add-Ins trotzdem kommunizieren können, wenn neue Versionen erstellt werden.  
  
 Letztlich ist es eine wichtige Aufgabe, ein stabiles Add-In-Modell zu entwickeln. Aus diesem Grund stellt .NET Framework eine Infrastruktur zum Erstellen von Add-in-Modellen.  
  
> [!NOTE]
>  Weitere Informationen zu Add-Ins finden Sie unter [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)).  
  
<a name="NETFrameworkAddInModelOverview"></a>   
## <a name="net-framework-add-in-model-overview"></a>Übersicht über das Add-In-Modell von .NET Framework  
 Die Add-In-Modell von .NET Framework, finden Sie in der <xref:System.AddIn> -Namespace enthält eine Reihe von Typen, die zur Vereinfachung der Entwicklung der Add-in-Erweiterbarkeit entworfen wurden. Die grundlegende Einheit für die Add-In-Modell von .NET Framework ist die *Vertrag*, das definiert, wie eine hostanwendung und ein Add-in miteinander kommunizieren. Ein Vertrag wird mit einer für Hostanwendungen spezifischen *Ansicht* des Vertrags für eine Hostanwendung verfügbar gemacht. Auf ähnliche Weise wird eine für Add-Ins spezifische *Ansicht* des Vertrags für das Add-In verfügbar gemacht. Ein *Adapter* ermöglicht es einer Hostanwendung und einem Add-In, zwischen ihren jeweiligen Ansichten des Vertrags miteinander zu kommunizieren. Verträge, Ansichten und Adapter werden als Segmente bezeichnet, und mehrere miteinander verbundene Segmente stellen eine *Pipeline* dar. Pipelines sind die Grundlage, auf der das Add-In-Modell von .NET Framework-Ermittlung, Aktivierung, Sicherheitsisolation, Ausführungsisolation (unter Verwendung von Anwendungsdomänen und Prozessen), Kommunikation, Verwaltung der Lebensdauer und versionsverwaltung unterstützt.  
  
 Mit dieser Unterstützung können Entwickler Add-Ins erstellen, die mit den Funktionen einer Hostanwendung integriert werden. Einige Szenarien erfordern jedoch hostanwendungen Benutzeroberflächen-add-ins gebotenen anzeigen. Da jede präsentationstechnologie in .NET Framework ein eigenes Modell für die Implementierung von Benutzeroberflächen verfügt, unterstützt das .NET Framework-add-in-Modell keine bestimmte präsentationstechnologie nicht. WPF-Formulare wird stattdessen das .NET Framework-add-in-Modell mit Benutzeroberflächenautomatisierungs-Unterstützung für add-ins erweitert.  
  
<a name="WPFAddInModel"></a>   
## <a name="wpf-add-ins"></a>WPF-Add-Ins  
 WPF ermöglicht in Verbindung mit dem .NET Framework-add-in-Modell, eine Vielzahl von Szenarien abzudecken, auf die hostanwendungen Benutzeroberflächen aus Add-Ins anzeigen müssen. Diese Szenarien werden vor allem von WPF mit den folgenden zwei Programmiermodellen behandelt:  
  
1. **Das Add-In gibt eine Benutzeroberfläche zurück**. Ein Add-in gibt eine Benutzeroberfläche zurück an die hostanwendung über einen Methodenaufruf wie im Vertrag definiert. Das Szenario wird in den folgenden Fällen verwendet:  
  
    - Die Darstellung einer Benutzeroberfläche, die von einem Add-In zurückgegeben wird, ist abhängig von entweder Daten oder Bedingungen, die nur zur Laufzeit, wie z.B. dynamisch generierte Berichte.  
  
    - Die Benutzeroberfläche für die von einem Add-in bereitgestellte Dienste unterscheidet sich von der Benutzeroberfläche der hostanwendungen, die das Add-in verwenden können.  
  
    - Das Add-in in erster Linie einen Dienst für die hostanwendung ausführt, und meldet den Status an die hostanwendung mit einer Benutzeroberfläche.  
  
2. **Das Add-In ist eine Benutzeroberfläche**. Ein Add-in ist eine Benutzeroberfläche, wie im Vertrag definiert. Das Szenario wird in den folgenden Fällen verwendet:  
  
    - Ein Add-In stellt ausschließlich die angezeigten Dienste bereit, z. B. eine Werbung.  
  
    - Die Benutzeroberfläche für ein Add-in bereitgestellte Dienste ist häufig von allen hostanwendungen genutzt, die diese-Add-in, z. B. Rechner oder Farbauswahl verwenden können.  
  
 Diese Szenarien erfordern, dass die UI-Objekte zwischen der hostanwendung und Add-in-Anwendungsdomänen übergeben werden können. Seit .NET Framework, die Kommunikation zwischen Anwendungsdomänen Remoting-add-in-Modell basiert, müssen die Objekte, die dazwischen, übergeben werden remotefähig sein.  
  
 Ein remotefähiges Objekt stellt die Instanz einer Klasse dar, für die eine oder mehrere der folgenden Aussagen gelten:  
  
- Leitet sich von der <xref:System.MarshalByRefObject> Klasse.  
  
- Implementiert die <xref:System.Runtime.Serialization.ISerializable>-Schnittstelle.  
  
- Hat die <xref:System.SerializableAttribute> -Attribut.  
  
> [!NOTE]
>  Weitere Informationen über das Erstellen von remotefähigen .NET Framework-Objekten finden Sie unter [erstellen Remotefähiger Objekte](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100)).  
  
 Die WPF-UI-Typen sind nicht remotefähig. Um das Problem zu beheben, erweitert WPF das .NET Framework-add-in-Modell zum Aktivieren von WPF-UI-add-ins erstellt, die von hostanwendungen angezeigt werden. Diese Unterstützung wird durch WPF durch zwei Arten bereitgestellt: die <xref:System.AddIn.Contract.INativeHandleContract> Schnittstelle und zwei statische Methoden implementiert, indem die <xref:System.AddIn.Pipeline.FrameworkElementAdapters> Klasse: <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>. Im Allgemeinen werden diese Typen und Methoden wie folgt verwendet:  
  
1. WPF ist erforderlich, dass die Benutzeroberflächen-add-ins gebotenen Klassen, die direkt oder indirekt sind von abgeleitet <xref:System.Windows.FrameworkElement>, z. B. Formen, Steuerelemente, Benutzersteuerelemente, Layoutbereiche und Seiten.  
  
2. Wenn der Vertrag deklariert, dass eine Benutzeroberfläche zwischen den Add-in und der hostanwendung übergeben wird, muss es als deklariert werden ein <xref:System.AddIn.Contract.INativeHandleContract> (keinen <xref:System.Windows.FrameworkElement>); <xref:System.AddIn.Contract.INativeHandleContract> ist eine remotefähige Darstellung der Benutzeroberfläche-Add-Ins, die über Isolationsgrenzen hinweg übergeben werden kann.  
  
3. Vor der Weitergabe von das Add-in die Anwendungsdomäne, einem <xref:System.Windows.FrameworkElement> als gepackt ein <xref:System.AddIn.Contract.INativeHandleContract> durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
4. Nach dem übergeben an die Anwendungsdomäne der hostanwendung, die <xref:System.AddIn.Contract.INativeHandleContract> neu verpackt werden müssen, als eine <xref:System.Windows.FrameworkElement> durch Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>.  
  
 Wie <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>, und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> werden verwendet, nach dem jeweiligen Szenario abhängt. Die folgenden Abschnitte bieten ausführliche Informationen zu den Programmiermodellen.  
  
<a name="ReturnUIFromAddInContract"></a>   
## <a name="add-in-returns-a-user-interface"></a>Add-In gibt eine Benutzeroberfläche zurück  
 Für ein Add-in eine Benutzeroberfläche an eine hostanwendung zurückgeben ist Folgendes erforderlich:  
  
1. Die hostanwendung, Add-in- und Pipeline müssen erstellt werden, wie .NET Framework beschrieben [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) Dokumentation.  
  
2. Der Vertrag implementieren muss <xref:System.AddIn.Contract.IContract> und, um eine Benutzeroberfläche zurückzugeben, muss der Vertrag eine Methode mit einem Rückgabewert vom Typ deklarieren <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3. Die Benutzeroberfläche, die zwischen des Add-Ins und der hostanwendung übergeben muss direkt oder indirekt von abgeleitet werden <xref:System.Windows.FrameworkElement>.  
  
4. Die Benutzeroberfläche, die durch das Add-In zurückgegeben wird, muss aus konvertiert werden eine <xref:System.Windows.FrameworkElement> auf eine <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze.  
  
5. Die Benutzeroberfläche, die zurückgegeben wird, muss aus konvertiert werden ein <xref:System.AddIn.Contract.INativeHandleContract> zu einem <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze.  
  
6. Die hostanwendung zeigt das zurückgegebene <xref:System.Windows.FrameworkElement>.  
  
 Ein Beispiel, das veranschaulicht, wie ein Add-in zu implementieren, die eine Benutzeroberfläche zurückgibt, finden Sie unter [Erstellen einer Add-In, das eine Benutzeroberfläche zurückgibt](how-to-create-an-add-in-that-returns-a-ui.md).  
  
<a name="AddInIsAUI"></a>   
## <a name="add-in-is-a-user-interface"></a>Add-In ist eine Benutzeroberfläche  
 Wenn ein Add-in eine Benutzeroberfläche ist, ist Folgendes erforderlich:  
  
1. Die hostanwendung, Add-in- und Pipeline müssen erstellt werden, wie .NET Framework beschrieben [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100)) Dokumentation.  
  
2. Die Vertragsschnittstelle für das Add-in muss implementieren <xref:System.AddIn.Contract.INativeHandleContract>.  
  
3. Das Add-in, das an die hostanwendung übergeben wird muss direkt oder indirekt von abgeleitet werden <xref:System.Windows.FrameworkElement>.  
  
4. Das Add-in muss konvertiert werden, aus einer <xref:System.Windows.FrameworkElement> zu ein <xref:System.AddIn.Contract.INativeHandleContract> vor dem Überschreiten der Isolationsgrenze.  
  
5. Das Add-in muss von konvertiert werden ein <xref:System.AddIn.Contract.INativeHandleContract> auf eine <xref:System.Windows.FrameworkElement> nach dem Überschreiten der Isolationsgrenze.  
  
6. Die hostanwendung zeigt das zurückgegebene <xref:System.Windows.FrameworkElement>.  
  
 Ein Beispiel, das veranschaulicht, wie ein Add-in zu implementieren, die eine Benutzeroberfläche ist, finden Sie unter [erstellen Sie ein Add-in-d. h. eine Benutzeroberfläche](how-to-create-an-add-in-that-is-a-ui.md).  
  
<a name="ReturningMultipleUIsFromAnAddIn"></a>   
## <a name="returning-multiple-uis-from-an-add-in"></a>Zurückgeben mehrerer Benutzeroberflächen durch ein Add-In  
 -Add-ins bieten häufig mehrere Benutzeroberflächen für hostanwendungen angezeigt werden. Betrachten Sie beispielsweise ein Add-in, das eine Benutzeroberfläche ist, die auch Statusinformationen an die hostanwendung, auch als eine Benutzeroberfläche bereitstellt. Sie können ein Add-In dieser Art implementieren, indem Sie eine Kombination der Verfahren aus den Modellen [Add-In gibt eine Benutzeroberfläche zurück](#ReturnUIFromAddInContract) und [Add-In ist eine Benutzeroberfläche](#AddInIsAUI) verwenden.  
  
<a name="AddInsAndXBAPs"></a>   
## <a name="add-ins-and-xaml-browser-applications"></a>Add-Ins und XAML-Browseranwendungen  
 In den bisherigen Beispielen wurde die Hostanwendung als eigenständige Anwendung installiert. [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]-Browseranwendungen können jedoch auch Add-Ins hosten, wobei allerdings die folgenden zusätzlichen Erstellungs- und Implementierungsanforderungen gelten:  
  
- Das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Anwendungsmanifest muss so konfiguriert sein, dass Pipeline- (Ordner und Assemblys) und Add-In-Assembly in den [!INCLUDE[TLA#tla_clickonce](../../../../includes/tlasharptla-clickonce-md.md)]-Anwendungscache auf dem Clientcomputer heruntergeladen werden, und zwar in denselben Ordner wie [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)].  
  
- Der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Code zum Ermitteln und Laden von Add-Ins muss den [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Anwendungscache für [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] als Speicherort für Pipeline und Add-In verwenden.  
  
- [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] muss das Add-In in einen speziellen Sicherheitskontext laden, wenn das Add-In auf lose Dateien verweist, die sich auf der Ursprungssite befinden. Wenn sie von [!INCLUDE[TLA2#tla_xbap#plural](../../../../includes/tla2sharptla-xbapsharpplural-md.md)]s gehostet werden, können Add-Ins nur auf lose Dateien verweisen, die auf der Ursprungssite der Hostanwendung gespeichert sind.  
  
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
  
1. Hinzufügen der Pipeline- und Add-In-Assembly zum Projekt, indem Sie im Projektmappen-Explorer mit der rechten Maustaste auf die einzelnen Pipelineordner klicken und die Option **Zu Projekt hinzufügen** auswählen.  
  
2. Festlegen des **Buildvorgangs** jeder Pipelineassembly und jeder Add-In-Assembly im **Eigenschaftenfenster** auf **Inhalt**.  
  
 Im letzten Schritt muss das Anwendungsmanifest so konfiguriert werden, dass sowohl die Pipelineassemblydateien als auch die Add-In-Assemblydatei heruntergeladen werden. Die Dateien sollten in Ordnern im Stammverzeichnis des Ordners in dem [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Cache gespeichert sein, den die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Anwendung belegt. Die Konfiguration richten Sie in [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] durch folgende Schritte ein:  
  
1. Klicken Sie mit der rechten Maustaste auf das [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Projekt, klicken Sie auf **Eigenschaften**, auf **Veröffentlichen** und dann auf die Schaltfläche **Anwendungsdateien**.  
  
2. Legen Sie im Dialogfeld **Anwendungsdateien** den **Veröffentlichungsstatus** der einzelnen Pipeline- und Add-In-DLLs auf **Einschließen (Auto)** und die **Downloadgruppe** für die Pipeline- und Add-In-DLLs auf **(Erforderlich)** fest.  
  
### <a name="using-the-pipeline-and-add-in-from-the-application-base"></a>Verwenden der Pipeline und des Add-Ins von der Anwendungsbasis  
 Sind Pipeline und Add-In für die [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Bereitstellung konfiguriert, werden sie in denselben [!INCLUDE[TLA2#tla_clickonce](../../../../includes/tla2sharptla-clickonce-md.md)]-Cacheordner heruntergeladen wie die [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]. Damit Pipeline und Add-In aus der [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)] verwendet werden können, müssen sie vom [!INCLUDE[TLA2#tla_xbap](../../../../includes/tla2sharptla-xbap-md.md)]-Code aus der Anwendungsbasis abgerufen werden. Die unterschiedlichen Typen und Member, der das .NET Framework-add-in-Modell für die Verwendung von Pipelines und Add-Ins, bieten besondere Unterstützung für dieses Szenario. Zuerst wird durch der Pfad identifiziert die <xref:System.AddIn.Hosting.PipelineStoreLocation.ApplicationBase> Enumerationswert. Diesen Wert verwenden Sie mit Überladungen der relevanten Add-In-Member, wenn Pipelines verwendet werden sollen, die Folgendes enthalten:  
  
- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
- <xref:System.AddIn.Hosting.AddInStore.FindAddIns%28System.Type%2CSystem.AddIn.Hosting.PipelineStoreLocation%2CSystem.String%5B%5D%29?displayProperty=nameWithType>  
  
- <xref:System.AddIn.Hosting.AddInStore.Rebuild%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
- <xref:System.AddIn.Hosting.AddInStore.Update%28System.AddIn.Hosting.PipelineStoreLocation%29?displayProperty=nameWithType>  
  
### <a name="accessing-the-hosts-site-of-origin"></a>Zugreifen auf die Ursprungssite des Hosts  
 Damit ein Add-In auf Dateien von der Ursprungssite verweisen kann, muss das Add-In mit einer Sicherheitsisolation geladen werden, die der Hostanwendung entspricht. Diese Sicherheitsebene wird durch identifiziert die <xref:System.AddIn.Hosting.AddInSecurityLevel.Host?displayProperty=nameWithType> -Enumerationswert, und übergeben die <xref:System.AddIn.Hosting.AddInToken.Activate%2A> Methode, wenn ein Add-in aktiviert ist.  
  
<a name="WPFAddInModelArchitecture"></a>   
## <a name="wpf-add-in-architecture"></a>Architektur des WPF-Add-Ins  
 Auf der höchsten Ebene, wie wir gesehen haben, mit WPF können .NET Framework-add-ins zum Implementieren von Benutzeroberflächen (ableiten, die direkt oder indirekt von <xref:System.Windows.FrameworkElement>) mit <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A>. Das Ergebnis ist, dass die hostanwendung zurückgegeben wird ein <xref:System.Windows.FrameworkElement> , über die Benutzeroberfläche in der hostanwendung angezeigt wird.  
  
 Für einfache Benutzeroberflächen-add-in Szenarien ist dies so viele Details wie ein Entwickler benötigt. Für komplexere Szenarien, insbesondere solche, die versuchen, die zusätzliche WPF-Diensten wie z. B. Layout, Ressourcen und Datenbindung nutzen ist ausführlichere Kenntnisse wie WPF das .NET Framework-add-in-Modell mit UI-Unterstützung erweitert erforderlich, um dessen Vorteile zu verstehen. und Einschränkungen.  
  
 Im Grunde nicht WPF eine Benutzeroberfläche von einem Add-in an eine hostanwendung übergeben werden. Stattdessen übergibt WPF die Win32-Fensterhandle für die Benutzeroberfläche mithilfe von WPF-Interoperabilität. Tritt auf, wenn eine Benutzeroberfläche in einem Add-in an eine hostanwendung übergeben wird, Folgendes:  
  
- Auf der Add-in-Seite ruft WPF ein Fensterhandle, für die Benutzeroberfläche, die von der hostanwendung angezeigt wird. Das Fensterhandle wird durch eine interne abgeleitete Klasse WPF gekapselt <xref:System.Windows.Interop.HwndSource> und implementiert <xref:System.AddIn.Contract.INativeHandleContract>. Eine Instanz dieser Klasse wird zurückgegeben, durch <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> und, die das Add-in die Anwendungsdomäne zu Anwendungsdomäne der hostanwendung gemarshallt wird.  
  
- Klicken Sie auf der Seite der hostanwendung, WPF neu gepackt der <xref:System.Windows.Interop.HwndSource> als eine interne abgeleitete Klasse WPF <xref:System.Windows.Interop.HwndHost> und nutzt <xref:System.AddIn.Contract.INativeHandleContract>. Eine Instanz dieser Klasse wird zurückgegeben, durch <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> an die hostanwendung.  
  
 <xref:System.Windows.Interop.HwndHost> ist vorhanden, um Benutzeroberflächen, identifiziert durch Fensterhandles von WPF-Benutzeroberflächen anzuzeigen. Weitere Informationen finden Sie unter [Interaktion zwischen WPF und Win32](../advanced/wpf-and-win32-interoperation.md).  
  
 Zusammenfassend <xref:System.AddIn.Contract.INativeHandleContract>, <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>, und <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> vorhanden sein, damit können das Fensterhandle für ein WPF-UI vom ein Add-in an eine hostanwendung übergeben werden, in dem sie durch gekapselt ist eine <xref:System.Windows.Interop.HwndHost> und der hostanwendung-Benutzeroberfläche angezeigt.  
  
> [!NOTE]
>  Da die hostanwendung Ruft eine <xref:System.Windows.Interop.HwndHost>, die hostanwendung das Objekt, das von zurückgegebene kann nicht konvertiert werden <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ContractToViewAdapter%2A> in den Typ auf, die sie als durch das Add-in implementiert wird (z. B. eine <xref:System.Windows.Controls.UserControl>).  
  
 Naturgemäß <xref:System.Windows.Interop.HwndHost> unterliegt bestimmten Einschränkungen, die beeinflussen, wie Sie Hosten von Anwendungen verwendet werden können. Allerdings WPF erweitert <xref:System.Windows.Interop.HwndHost> mehrere Funktionen für Add-in-Szenarien. Diese Vorteile und die Einschränkungen werden nachstehend beschrieben.  
  
<a name="WPFAddInModelBenefits"></a>   
## <a name="wpf-add-in-benefits"></a>Vorteile des WPF-Add-Ins  
 Da WPF-add-in-Benutzeroberflächen angezeigt werden, von hostanwendungen, die mithilfe einer internen Klasse, die von abgeleitet <xref:System.Windows.Interop.HwndHost>, diese Benutzeroberflächen sind eingeschränkt, durch die Funktionen der <xref:System.Windows.Interop.HwndHost> in Bezug auf WPF-UI-Dienste wie Layout, Rendering, Datenbindung, Stile, Vorlagen und Ressourcen. Allerdings WPF erweitert die internen <xref:System.Windows.Interop.HwndHost> -Unterklasse um zusätzliche Funktionen, die Folgendes umfassen:  
  
- TAB-Taste zwischen einer hostanwendung-Benutzeroberfläche und ein Add-in-Benutzeroberfläche. Beachten Sie, dass das Programmiermodell "Add-in-ist eine Benutzeroberfläche" erforderlich, dass der Add-In-seitige Adapter überschreiben <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> , ob das Add-in ist voll vertrauenswürdige als auch teilweise vertrauenswürdigen aktivieren TAB-Taste.  
  
- Anforderungen zur Barrierefreiheit für Add-in-Benutzeroberflächen, die über Benutzeroberflächen für Host-Anwendung angezeigt werden, werden berücksichtigt.  
  
- Aktivieren WPF-Anwendungen problemlos in Szenarien mit mehreren Anwendungsdomänen ausgeführt.  
  
- Verhindern von unberechtigten Zugriffen zum Hinzufügen-UI-Fensterhandles, wenn Add-Ins mit Sicherheitsisolation (d. h. in einem teilweise vertrauenswürdigen Sicherheitsbereich (Sandbox) ausgeführt. Aufrufen von <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> gewährleistet diese Sicherheit:  
  
    - Beim Programmiermodell "Add-in gibt eine Benutzeroberfläche zurück", ist die einzige Möglichkeit, die das Fensterhandle für ein Add-in-Benutzeroberfläche über die Isolationsgrenze hinweg übergeben aufzurufende <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A>.  
  
    - Für das Programmiermodell "Add-in ist eine Benutzeroberfläche" überschreiben <xref:System.AddIn.Pipeline.ContractBase.QueryContract%2A> auf dem Add-In-seitige Adapter und der Aufruf <xref:System.AddIn.Pipeline.FrameworkElementAdapters.ViewToContractAdapter%2A> (wie in den vorherigen Beispielen gezeigt) ist es erforderlich, die Add-In-seitige Adapter aufgerufen `QueryContract` Implementierung von der hostseitiger Adapter.  
  
- Bereitstellen von Ausführungsschutz für mehrere Anwendungsdomänen. Aufgrund von Einschränkungen bei Anwendungsdomänen führen unbehandelte Ausnahmen, die in Add-In-Anwendungsdomänen ausgelöst werden, zum Absturz der gesamten Anwendung, auch wenn eine Isolationsgrenze eingerichtet ist. Allerdings bieten WPF und die Add-In-Modell von .NET Framework eine einfache Möglichkeit, dieses Problem zu umgehen und die Anwendungsstabilität zu verbessern. Erstellt ein WPF-add-in, das eine Benutzeroberfläche anzeigt eine <xref:System.Windows.Threading.Dispatcher> für den Thread, der die Anwendungsdomäne ausgeführt wird, wenn die hostanwendung eine WPF-Anwendung ist. Sie können erkennen, dass alle nicht behandelte Ausnahmen, die in der Anwendungsdomäne, durch Behandeln auftreten der <xref:System.Windows.Threading.Dispatcher.UnhandledException> Ereignis von der WPF-add-in des <xref:System.Windows.Threading.Dispatcher>. Sie erhalten die <xref:System.Windows.Threading.Dispatcher> aus der <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A> Eigenschaft.  
  
<a name="WPFAddInModelLimitations"></a>   
## <a name="wpf-add-in-limitations"></a>Einschränkungen des WPF-Add-Ins  
 Über die Vorteile, die das Standardverhalten, die vom WPF hinzufügt <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost>, und Fensterhandles, es gibt auch Einschränkungen für Add-in-Benutzeroberflächen, die von hostanwendungen angezeigt werden:  
  
- -Add-in Benutzeroberflächen angezeigt, die von einer hostanwendung berücksichtigt Ausschneideverhalten der hostanwendung nicht.  
  
- Der Begriff *Airspace* in Interoperabilitätsszenarien gilt auch für Add-Ins (siehe [Übersicht über die Technologieregionen](../advanced/technology-regions-overview.md)).  
  
- Eine hostanwendung UI-Dienste, wie Vererbung, Datenbindung und Befehle, nicht automatisch für die add-Ins verfügbar sind Benutzeroberflächen. Um diese Dienste für das Add-In bereitzustellen, müssen Sie die Pipeline aktualisieren.  
  
- Ein Benutzeroberflächen-Add-in kann nicht werden gedreht, skaliert, verzerrt oder andernfalls durch eine Transformation geändert (finden Sie unter [Übersicht über Transformationen](../graphics-multimedia/transforms-overview.md)).  
  
- Inhalte innerhalb von Add-in-Benutzeroberflächen, die gerendert wird, durch Zeichenvorgänge aus dem <xref:System.Drawing> Namespace kann Alphablending umfassen. Allerdings müssen sowohl eine Add-in-Benutzeroberfläche und der hostanwendung Benutzeroberfläche, die es enthält 100 % deckend sein; Das heißt, die `Opacity` sowohl Eigenschaft muss auf 1 festgelegt werden.  
  
- Wenn die <xref:System.Windows.Window.AllowsTransparency%2A> eines Fensters in der hostanwendung, die ein Benutzeroberflächen-Add-in enthält-Eigenschaftensatz auf `true`, das Add-in nicht sichtbar ist. Dies gilt auch, wenn der Benutzeroberflächen-Add-in über 100 % deckend ist (d. h. die `Opacity` Eigenschaft hat den Wert 1).  
  
- Ein Benutzeroberflächen-Add-in muss zusätzlich zu anderen WPF-Elemente im selben Fenster der obersten Ebene angezeigt werden.  
  
- Kein Teil ein Add-in-Benutzeroberfläche kann gerendert werden, mithilfe einer <xref:System.Windows.Media.VisualBrush>. Stattdessen kann das Add-in eine Momentaufnahme der generierten Benutzeroberfläche um eine Bitmap zu erstellen, die an die hostanwendung, die mit vertraglich definierten Methoden übergeben werden kann.  
  
- Mediendateien können nicht wiedergegeben werden, von einem <xref:System.Windows.Controls.MediaElement> in einer Benutzeroberfläche-Add-in.  
  
- Mausereignisse, die für die Add-in-Benutzeroberfläche generiert weder empfangen noch ausgelöst von der hostanwendung und dem `IsMouseOver` hostanwendung UI-Eigenschaft weist einen Wert von `false`.  
  
- Wenn den Fokus zwischen Steuerelementen in einer Benutzeroberfläche-Add-in verlagert die `GotFocus` und `LostFocus` Ereignisse weder empfangen noch ausgelöst von der hostanwendung.  
  
- Der Teil einer hostanwendung, die ein Benutzeroberflächen-Add-in enthält, wird beim Drucken Weiß angezeigt.  
  
- Alle Dispatcher (finden Sie unter <xref:System.Windows.Threading.Dispatcher>) durch das Add-in erstellt Benutzeroberfläche muss manuell beendet werden, bevor das Owner-Add-in entladen wird, wenn die hostanwendung die Ausführung wird fortgesetzt. Der Vertrag kann Methoden implementieren, mit denen die hostanwendung das Add-in zu signalisieren, bevor das Add-In entladen wurde, wodurch die Add-in-Benutzeroberfläche die Dispatcher beenden wird.  
  
- Ist ein Benutzeroberflächen-Add-in ein <xref:System.Windows.Controls.InkCanvas> oder enthält ein <xref:System.Windows.Controls.InkCanvas>, Sie können nicht das Add-In entladen.  
  
<a name="PerformanceOptimization"></a>   
## <a name="performance-optimization"></a>Leistungsoptimierung  
 Standardmäßig Wenn mehrere Anwendungsdomänen verwendet werden, werden verschiedenen .NET Framework-Assemblys, die von jeder Anwendung benötigt werden alle in die Domäne dieser Anwendung geladen. Aufgrund der Zeit, die zum Erstellen neuer Anwendungsdomänen und für das Starten der darin enthaltenen Anwendungen erforderlich ist, kann die Leistung beeinträchtigt werden. .NET Framework bietet jedoch eine Möglichkeit, Startzeiten zu verkürzen von Anwendungen angewiesen, Assemblys in Anwendungsdomänen gemeinsam nutzen, wenn sie bereits geladen sind. Verwenden Sie hierzu die <xref:System.LoaderOptimizationAttribute> -Attribut, das auf die Einstiegspunktmethode angewendet werden muss (`Main`). In diesem Fall müssen Sie lediglich zum Implementieren Ihrer Anwendungsdefinition Code verwenden (siehe [Übersicht über die Anwendungsverwaltung](application-management-overview.md)).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.LoaderOptimizationAttribute>
- [Add-Ins und Erweiterbarkeit](/previous-versions/dotnet/netframework-4.0/bb384200(v%3dvs.100))
- [Anwendungsdomänen](../../app-domains/application-domains.md)
- [Übersicht über .NET Framework-Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/kwdt6w2k(v=vs.100))
- [Erstellen Remotefähiger Objekte](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/wcf3swha(v=vs.100))
- [Themen zu Vorgehensweisen](how-to-topics.md)
