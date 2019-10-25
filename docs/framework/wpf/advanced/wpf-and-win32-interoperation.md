---
title: Interaktion zwischen WPF und Win32
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 7248b0e5abcf2c6357dc7ce7c708eaa85358061a
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846797"
---
# <a name="wpf-and-win32-interoperation"></a>Interaktion zwischen WPF und Win32

Dieses Thema enthält eine Übersicht über die Interaktion zwischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Code und [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Code. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie allerdings bereits erheblichen Aufwand für [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Code betrieben haben, kann es effektiver sein, zumindest einen Teil dieses Codes wiederzuverwenden.

<a name="basics"></a>

## <a name="wpf-and-win32-interoperation-basics"></a>Grundlagen der Interaktion zwischen WPF und Win32

Es gibt zwei grundlegende Verfahren der Interaktion zwischen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Code und [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Code.

- Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Fenster. Mit diesem Verfahren können Sie die erweiterten Grafikfunktionen von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] im Rahmen standardmäßiger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Fenster und -Anwendungen nutzen.

- Hosten eines [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Fensters in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt. Mit diesem Verfahren können Sie ein vorhandenes benutzerdefiniertes [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Steuerelement im Zusammenhang mit anderem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt verwenden und Daten über die Grenzen hinweg übergeben.

In diesem Thema wird das Konzept beider Verfahren erläutert. Eine eher Code-orientierte Erläuterung zum Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] finden Sie unter [Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32](walkthrough-hosting-wpf-content-in-win32.md). Eine eher Code-orientierte Erläuterung zum Hosten von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF](walkthrough-hosting-a-win32-control-in-wpf.md).

<a name="projects"></a>

## <a name="wpf-interoperation-projects"></a>WPF-Interaktionsprojekte

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-APIs sind verwalteter Code, aber die meisten vorhandenen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Programme werden in C++nicht verwaltetem geschrieben.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-APIs können nicht von einem echten nicht verwalteten Programm aufgerufen werden. Mithilfe der Option `/clr` mit dem Microsoft Visual C++ Compiler können Sie jedoch ein gemischtes, verwaltetes, nicht verwaltetes Programm erstellen, mit dem Sie verwaltete und nicht verwaltete API-Aufrufe nahtlos mischen können.

Eine Komplikation auf Projektebene besteht darin, dass Sie [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Dateien nicht C++ in ein-Projekt kompilieren können.  Dieses Problem lässt sich durch verschiedene Verfahren zur Projektaufteilung kompensieren.

- Erstellen Sie C# eine DLL, die alle Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]Seiten als kompilierte Assembly enthält, und lassen C++ Sie dann die ausführbare Datei als Verweis in die ausführbare Datei einschließen.

- Erstellen Sie C# eine ausführbare Datei für den[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Inhalt, und verweisen C++ Sie auf eine DLL, die den[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]Inhalt enthält.

- Verwenden Sie <xref:System.Windows.Markup.XamlReader.Load%2A>, um beliebige [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] zur Laufzeit zu laden, anstatt ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]zu kompilieren.

- Verwenden Sie überhaupt kein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], und schreiben Sie die gesamte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in Code, wobei die Elementstruktur über <xref:System.Windows.Application> aufgebaut wird.

Verwenden Sie die für Sie am besten geeignete Vorgehensweise.

> [!NOTE]
> Wenn Sie/CLI noch nicht C++verwendet haben, bemerken Sie möglicherweise einige "neue" Schlüsselwörter wie`gcnew`und`nullptr`in den Codebeispielen für Interoperation. Diese Schlüsselwörter ersetzen die ältere Syntax mit doppeltem Unterstrich (`__gc`) und stellen eine natürlichere Syntax für verwalteten C++Code in bereit.  Weitere Informationen zu den C++von/CLI verwalteten Features finden Sie unter [Komponenten Erweiterungen für laufzeitplattformen](/cpp/windows/component-extensions-for-runtime-platforms).

<a name="hwnds"></a>

## <a name="how-wpf-uses-hwnds"></a>Wie WPF HWNDs verwendet

Um [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] "HWND interop" optimal nutzen zu können, müssen Sie wissen, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWNDs verwendet. Bei jedem HWND können Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Rendering mit dem DirectX-Rendering oder dem GDI/GDI+-Rendering nicht mischen. Dies hat verschiedene Auswirkungen. Um diese Renderingmodelle überhaupt kombinieren zu können, müssen Sie eine Interaktionslösung erstellen und festgelegte Interaktionssegmente für jedes gewählte Renderingmodell verwenden. Durch das Renderingverhalten wird außerdem eine "Airspace"-Beschränkung erzeugt, die die Funktionsfähigkeit der Interaktionslösung einschränkt. Das "Airspace"-Konzept wird im Thema [Technology Regions Overview (Übersicht über die Bereichstechnologie)](technology-regions-overview.md) genauer erklärt.

Alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elemente auf dem Bildschirm werden letztlich von einem HWND unterstützt. Wenn Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>erstellen, erstellt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein HWND auf oberster Ebene und verwendet eine <xref:System.Windows.Interop.HwndSource>, um die <xref:System.Windows.Window> und deren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in das HWND einzufügen.  Dieses einzige HWND wird vom Rest des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts in der Anwendung gemeinsam verwendet. Davon ausgenommen sind Menüs, Dropdown-Kombinationsfelder und andere Popupelemente. Diese Elemente erstellen ihr eigenes Fenster auf der obersten Ebene, weshalb ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Menü über das Fenster-HWND hinausgehen kann, in dem es enthalten ist. Wenn Sie <xref:System.Windows.Interop.HwndHost> verwenden, um ein HWND in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]einzufügen, informiert [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], wie das neue untergeordnete HWND relativ zum [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND positioniert werden kann.

Ein mit dem HWND verwandtes Konzept ist die Transparenz innerhalb und zwischen jedem HWND. Dies wird auch im Thema [Technology Regions Overview (Übersicht über die Bereichstechnologie)](technology-regions-overview.md) erläutert.

<a name="hosting_a_wpf_page"></a>

## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Hosten von WPF-Inhalt in einem Microsoft Win32-Fenster

Entscheidend für das Hosten eines [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ist die <xref:System.Windows.Interop.HwndSource>-Klasse. Diese Klasse umschließt den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt mit einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Fenster, sodass der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt als untergeordnetes Fenster in Ihre [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] eingebunden werden kann. Bei folgender Vorgehensweise werden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer einzigen Anwendung zusammengefasst.

1. Implementieren Sie den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt (das Stammelement des Inhalts) als verwaltete Klasse. In der Regel erbt diese Klasse von einer der Klassen, die mehrere untergeordnete Elemente enthalten und/oder als Stammelement verwendet werden können, wie z. B. <xref:System.Windows.Controls.DockPanel> oder <xref:System.Windows.Controls.Page>. In nachfolgenden Schritten wird diese Klasse als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklasse und Instanzen dieser Klasse als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsobjekte bezeichnet.

2. Implementieren einer Windows-Anwendung C++mit/CLI. Wenn Sie mit einer vorhandenen nicht verwalteten C++ Anwendung beginnen, können Sie diese normalerweise aktivieren, um verwalteten Code aufzurufen, indem Sie die Projekteinstellungen so ändern, dass Sie das`/clr`-Compilerflag enthalten (der vollständige Bereich, der zur Unterstützung der`/clr`Kompilierung erforderlich ist) wird in diesem Thema nicht beschrieben).

3. Legen Sie das Threadingmodell auf Singlethread-Apartment (STA) fest. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet dieses Threadingmodell.

4. Behandeln Sie die WM_CREATE-Benachrichtigung in der Fensterprozedur.

5. Gehen Sie im Handler (oder in einer Funktion, die vom Handler aufgerufen wird) wie folgt vor:

    1. Erstellen Sie ein neues <xref:System.Windows.Interop.HwndSource>-Objekt mit dem HWND des übergeordneten Fensters als dessen `parent`-Parameter.

    2. Erstellen Sie eine Instanz der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklasse.

    3. Weisen Sie der <xref:System.Windows.Interop.HwndSource>-Objekt <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft einen Verweis auf das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Objekt zu.

    4. Die <xref:System.Windows.Interop.HwndSource>-Eigenschaft des <xref:System.Windows.Interop.HwndSource.Handle%2A>-Objekts enthält das Fensterhandle (HWND). Um ein HWND zu erhalten, das Sie im nicht verwalteten Teil der Anwendung verwenden können, wandeln Sie `Handle.ToPointer()` in ein HWND um.

6. Implementieren Sie eine verwaltete Klasse, die ein statisches Feld mit einem Verweis auf das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsobjekt enthält. Diese Klasse ermöglicht es Ihnen, einen Verweis auf das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Objekt aus dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Code zu erhalten, aber noch wichtiger ist, dass die <xref:System.Windows.Interop.HwndSource> nicht versehentlich an die Garbage Collection übergeben wird.

7. Fügen Sie zum Empfangen von Benachrichtigungen vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsobjekt an ein oder mehrere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsobjektereignisse einen Handler an.

8. Kommunizieren Sie mithilfe des im statischen Feld gespeicherten Verweises mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsobjekt, um Eigenschaften festzulegen, Methoden aufzurufen usw.

> [!NOTE]
> Sie können einige oder alle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklassendefinitionen für Schritt 1 in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] mit der standardmäßigen partiellen Klasse der Inhaltsklasse verwenden, wenn Sie eine separate Assembly erstellen und dann darauf verweisen. Obwohl Sie bei der Kompilierung von <xref:System.Windows.Application> zu einer Assembly in der Regel ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Objekt aufnehmen, verwenden Sie dieses <xref:System.Windows.Application> nicht unbedingt bei der Interoperation; Sie verwenden vielleicht nur eine oder mehrere der Stammklassen für [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Dateien, auf die von der Anwendung verwiesen wird, und verweisen auf ihre partiellen Klassen. Der Rest der Prozedur entspricht im Wesentlichen der oben beschriebenen.
>
> Jeder dieser Schritte wird durch Code im Thema [Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32](walkthrough-hosting-wpf-content-in-win32.md) veranschaulicht.

<a name="hosting_an_hwnd"></a>

## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>Hosten eines Microsoft Win32-Fensters in WPF

Der Schlüssel zum Hosting eines [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fensters in anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalten ist die <xref:System.Windows.Interop.HwndHost>-Klasse. Diese Klasse umschließt das Fenster mit einem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Element, das einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elementstruktur hinzugefügt werden kann. <xref:System.Windows.Interop.HwndHost> unterstützt auch APIs, mit denen Sie Aufgaben wie die Verarbeitung von Nachrichten für das gehostete Fenster ausführen können. Die grundlegende Prozedur lautet wie folgt:

1. Erstellen Sie eine Elementstruktur für eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung (durch Code oder Markup möglich). Suchen Sie einen geeigneten und zulässigen Punkt in der Elementstruktur, an dem die <xref:System.Windows.Interop.HwndHost>-Implementierung als untergeordnetes Element hinzugefügt werden kann. In den nachfolgenden Schritten wird dieses Element als reservierendes Element bezeichnet.

2. Erstellen Sie durch Ableiten von <xref:System.Windows.Interop.HwndHost> ein Objekt mit dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Inhalt.

3. Überschreiben Sie in dieser Hostklasse die <xref:System.Windows.Interop.HwndHost>-Methode <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>. Geben Sie das HWND des gehosteten Fensters zurück. Möglicherweise ist es sinnvoll, die eigentlichen Steuerelemente als untergeordnetes Fenster des zurückgegebenen Fensters zu umschließen; durch Umschließen der Steuerelemente mit einem Hostfenster kann der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt Benachrichtigungen von den Steuerelementen erhalten. Diese Vorgehensweise hilft bei der Behebung einiger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Probleme in Bezug auf die Meldungsbehandlung an der Begrenzung des gehosteten Steuerelements.

4. Überschreiben Sie die <xref:System.Windows.Interop.HwndHost>-Methoden <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> und <xref:System.Windows.Interop.HwndHost.WndProc%2A>. Hiermit sollen eine Bereinigung durchgeführt und Verweise auf den gehosteten Inhalt entfernt werden, insbesondere dann, wenn Sie Verweise auf nicht verwaltete Objekte erstellt haben.

5. Erstellen Sie in der CodeBehind-Datei eine Instanz der Steuerelement-Hostingklasse, und machen Sie diese zu einem untergeordneten Element des reservierenden Elements. In der Regel wird ein Ereignishandler wie <xref:System.Windows.FrameworkElement.Loaded> oder der Konstruktor der partiellen Klasse verwendet. Sie können den Interaktionsinhalt aber auch durch ein Laufzeitverhalten hinzufügen.

6. Verarbeiten Sie ausgewählte Fenstermeldungen wie Steuerelementbenachrichtigungen. Es gibt zwei Verfahrensweisen. Beide ermöglichen denselben Zugang zum Meldungsstream, Sie können also das Verfahren auswählen, das Ihnen einfacher erscheint.

    - Implementieren Sie die Meldungsverarbeitung für alle Meldungen (nicht nur Meldungen zum Herunterfahren) in der Überschreibung der <xref:System.Windows.Interop.HwndHost>-Methode <xref:System.Windows.Interop.HwndHost.WndProc%2A>.

    - Lassen Sie das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Hostingelement die Meldungen durch Behandeln des <xref:System.Windows.Interop.HwndHost.MessageHook>-Ereignisses verarbeiten. Dieses Ereignis wird für jede Meldung ausgelöst, die an die Hauptfensterprozedur des gehosteten Fensters gesendet wird.

    - Sie können keine Meldungen von prozessexternen Fenstern mit <xref:System.Windows.Interop.HwndHost.WndProc%2A> verarbeiten.

7. Kommunizieren Sie mit dem gehosteten Fenster mithilfe eines Plattformaufrufs, um die nicht verwaltete `SendMessage`-Funktion aufzurufen.

Durch Befolgen dieser Schritte wird eine Anwendung erstellt, die per Mauseingabe funktioniert. Sie können das gehostete Fenster durch Implementieren der <xref:System.Windows.Interop.IKeyboardInputSink>-Schnittstelle mit Unterstützung der TAB-Verwendung versehen.

Jeder dieser Schritte wird durch Code im Thema [Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF](walkthrough-hosting-a-win32-control-in-wpf.md) veranschaulicht.

### <a name="hwnds-inside-wpf"></a>HWNDs in WPF

Sie können sich <xref:System.Windows.Interop.HwndHost> als ein spezielles Steuerelement vorstellen. (Technisch gesehen handelt es sich bei <xref:System.Windows.Interop.HwndHost> um eine <xref:System.Windows.FrameworkElement> abgeleitete Klasse, nicht um eine <xref:System.Windows.Controls.Control> abgeleitete Klasse, Sie kann jedoch als Steuerelement für die Interoperation betrachtet werden.) <xref:System.Windows.Interop.HwndHost> abstrahiert die zugrunde liegende [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Natur der gehosteten Inhalte so, dass der Rest von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] den gehosteten Inhalt als ein anderes Steuerelement ähnliches Objekt betrachtet, das Eingaben Rendering und verarbeiten soll. <xref:System.Windows.Interop.HwndHost> verhält sich im Allgemeinen wie jede andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>. es gibt jedoch einige wichtige Unterschiede in Bezug auf die Ausgabe (Zeichnung und Grafiken) und die Eingabe (Maus und Tastatur), basierend auf den Einschränkungen, die die zugrunde liegenden HWNDs unterstützen können.

#### <a name="notable-differences-in-output-behavior"></a>Wichtige Unterschiede im Ausgabeverhalten

- <xref:System.Windows.FrameworkElement>, die <xref:System.Windows.Interop.HwndHost>-Basisklasse, verfügt über einige Eigenschaften, die Änderungen an der Benutzeroberfläche beinhalten. Hierzu gehören Eigenschaften wie <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>, wodurch die Anordnung von Elementen innerhalb dieses Element als übergeordnetes Element geändert wird. Den meisten dieser Eigenschaften werden jedoch keine möglichen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Entsprechungen zugeordnet, selbst wenn solche Entsprechungen vorhanden sind. Zu viele dieser Eigenschaften und ihre Bedeutungen sind zu renderingspezifisch, als dass Zuordnungen praktisch wären. Daher hat das Festlegen von Eigenschaften wie <xref:System.Windows.FrameworkElement.FlowDirection%2A> auf <xref:System.Windows.Interop.HwndHost> keine Auswirkungen.

- <xref:System.Windows.Interop.HwndHost> kann nicht gedreht, skaliert, verzerrt oder auf andere Weise durch eine Transformation geändert werden.

- <xref:System.Windows.Interop.HwndHost> bietet keine Unterstützung für die <xref:System.Windows.UIElement.Opacity%2A>-Eigenschaft (Alphablending). Falls der Inhalt im <xref:System.Windows.Interop.HwndHost><xref:System.Drawing>-Vorgänge ausführt, die Alphainformationen enthalten, stellt dies an sich keine Verletzung dar, von <xref:System.Windows.Interop.HwndHost> als Ganzem wird jedoch nur eine Durchlässigkeit von 1,0 (100 %) unterstützt.

- <xref:System.Windows.Interop.HwndHost> wird über anderen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Elementen in demselben Fenster auf oberster Ebene angezeigt. Ein mit <xref:System.Windows.Controls.ToolTip> oder <xref:System.Windows.Controls.ContextMenu> erstelltes Menü stellt jedoch ein separates Fenster auf oberster Ebene dar und verhält sich deshalb korrekt mit <xref:System.Windows.Interop.HwndHost>.

- <xref:System.Windows.Interop.HwndHost> berücksichtigt den Auswahlbereich seines übergeordneten <xref:System.Windows.UIElement> nicht. Dies stellt ein potenzielles Problem dar, wenn Sie versuchen, eine <xref:System.Windows.Interop.HwndHost>-Klasse in einen Bildlaufbereich oder <xref:System.Windows.Controls.Canvas> einzufügen.

#### <a name="notable-differences-in-input-behavior"></a>Wichtige Unterschiede im Eingabeverhalten

- Im Allgemeinen werden Eingabeereignisse bei Eingabegeräten innerhalb des von <xref:System.Windows.Interop.HwndHost> gehosteten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Bereichs direkt an [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] weitergegeben.

- Während sich der Mauszeiger über dem <xref:System.Windows.Interop.HwndHost>befindet, empfängt Ihre Anwendung keine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Mausereignisse, und der Wert der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaft wird <xref:System.Windows.UIElement.IsMouseOver%2A> `false`.

- Während der <xref:System.Windows.Interop.HwndHost> über den Tastaturfokus verfügt, empfängt Ihre Anwendung keine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Tastatur Ereignisse, und der Wert der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Eigenschaft wird <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> `false`.

- Wenn sich der Fokus innerhalb des <xref:System.Windows.Interop.HwndHost> und Änderungen an einem anderen Steuerelement innerhalb des <xref:System.Windows.Interop.HwndHost>befinden, empfängt Ihre Anwendung die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignisse <xref:System.Windows.UIElement.GotFocus> oder <xref:System.Windows.UIElement.LostFocus>nicht.

- Entsprechende Tablettstifteigenschaften und -Ereignisse verhalten sich analog und geben keine Informationen aus, wenn sich der Tablettstift über <xref:System.Windows.Interop.HwndHost> befindet.

<a name="tabbing_mnemonics_accelerators"></a>

## <a name="tabbing-mnemonics-and-accelerators"></a>TAB-TASTE und Zugriffstasten

Die <xref:System.Windows.Interop.IKeyboardInputSink>-Schnittstelle und die <xref:System.Windows.Interop.IKeyboardInputSite>-Schnittstelle ermöglichen eine nahtlose Tastatureinbindung bei gemischten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendungen und [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Anwendungen:

- Wechseln zwischen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Komponenten und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Komponenten mithilfe der TAB-TASTE

- Zugriffstasten funktionieren sowohl beim Fokus auf einer Win32-Komponente als auch auf einer WPF-Komponente.

Sowohl die <xref:System.Windows.Interop.HwndHost>-Klasse als auch die <xref:System.Windows.Interop.HwndSource>-Klasse stellen eine Implementierung von <xref:System.Windows.Interop.IKeyboardInputSink> bereit, sie behandeln jedoch möglicherweise nicht alle Eingabemeldungen, die in komplexeren Szenarien erwünscht sind. Überschreiben Sie die entsprechenden Methoden, um das gewünschte Tastaturverhalten zu erhalten.

Die Schnittstellen unterstützen nur Vorgänge, die den Übergang zwischen dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Bereich und dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Bereich betreffen. Innerhalb des [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Bereichs wird das TAB-Verhalten ggf. vollständig durch die von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] implementierte Tabulatorreihenfolgenlogik gesteuert.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [Exemplarische Vorgehensweise: Hosten eines Win32-Steuerelements in WPF](walkthrough-hosting-a-win32-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32](walkthrough-hosting-wpf-content-in-win32.md)
