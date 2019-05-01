---
title: 'Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 4001c34f6673e036bdbf731baed782c6dc0a16b0
ms.sourcegitcommit: 89fcad7e816c12eb1299128481183f01c73f2c07
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "63808049"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32

Einzufügenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendungen verwenden <xref:System.Windows.Interop.HwndSource>, das bietet des HWND, das enthält Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt. Erstellen Sie zunächst die <xref:System.Windows.Interop.HwndSource>, legen sie Parameter, die denen von CreateWindow ähneln. Sie weisen die <xref:System.Windows.Interop.HwndSource> über die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt darin enthalten sein soll. Schließlich erhalten Sie das HWND aus der <xref:System.Windows.Interop.HwndSource>. Diese exemplarische Vorgehensweise veranschaulicht, wie Sie ein gemischtes erstellen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] -Anwendung, die das Betriebssystemdialogfeld **Datums- und Uhrzeiteigenschaften** Dialogfeld.

## <a name="prerequisites"></a>Vorraussetzungen

Finden Sie unter [WPF und Win32-Interoperation](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Verwendung dieses Tutorials

Dieses Tutorial konzentriert sich auf die wichtigsten Schritte zum Erstellen einer interoperativen Anwendung. Ein Beispiel, das Tutorial stützt [Beispiel für die Interaktion von Win32-Uhr](https://go.microsoft.com/fwlink/?LinkID=160051), aber dieses Beispiel ist das Endprodukt repräsentiert. In diesem Tutorial werden die Schritte aus, als ob Sie mit einem vorhandenen starten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] eigenes Projekt, z. B. einem vorhandenen Projekt und ein gehostetes hinzufügen wurden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] für Ihre Anwendung. Sie können Ihr Endprodukt mit vergleichen [Beispiel für die Interaktion von Win32-Uhr](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Eine exemplarische Vorgehensweise für Windows Presentation Framework in Win32 (HwndSource)

Die folgende Grafik zeigt das angestrebte Endprodukt dieses Tutorials:

![Screenshot, das Dialogfeld Eigenschaften von Datum und Uhrzeit zeigt.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Sie können dieses Dialogfeld reproduzieren, indem Sie erstellen eine C++ Win32-Projekt in Visual Studio und Verwenden des Dialog-Editors Folgendes erstellen:

![Neu erstellte Dialogfeld Datums- und Uhrzeiteigenschaften](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

(Sie müssen nicht mit [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] verwenden <xref:System.Windows.Interop.HwndSource>, und Sie müssen nicht C++ verwenden, um das Schreiben von [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Programme, aber dies ist eine durchaus übliche Vorgehensweise und eignet sich gut für eine schrittweise Erklärung des Tutorials).

Sie müssen fünf bestimmte Teilschritte zu erreichen, um die put ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr in das Dialogfeld:

1. Aktivieren Sie Ihre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt, um verwalteten Code aufrufen (**"/ CLR"**) durch Ändern von projekteinstellungen in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].

2. Erstellen Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> in einer separaten DLL.

3. Einfügen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> innerhalb einer <xref:System.Windows.Interop.HwndSource>.

4. Rufen Sie ein HWND für diesen <xref:System.Windows.Controls.Page> mithilfe der <xref:System.Windows.Interop.HwndSource.Handle%2A> Eigenschaft.

5. Verwendung [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] entscheiden, wo das HWND innerhalb der größeren [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendung

## <a name="clr"></a>/clr

Der erste Schritt ist, dieses nicht verwaltete [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt in eine, die aufgerufen wird, können von verwaltetem Code. Sie verwenden die Compileroption "/ CLR", die die erforderlichen DLLs verknüpft werden, Sie verwenden möchten, und passen Sie die Main-Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].

So aktivieren Sie die Verwendung von verwaltetem Code im C++-Projekt: Mit der rechten Maustaste auf das win32clock-Projekt, und wählen Sie **Eigenschaften**. Auf der **allgemeine** Eigenschaftenseite (Standardeinstellung), ändern Sie Common Language Runtime-Unterstützung in `/clr`.

Fügen Sie Verweise auf DLLs für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll. (Bei den nachfolgenden Anweisungen wird davon ausgegangen, dass das Betriebssystem auf Laufwerk C: installiert ist.)

1. Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** , und klicken Sie in diesem Dialogfeld:

2. Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** .

3. Klicken Sie auf **neuen Verweis hinzufügen**, klicken Sie auf die Registerkarte "Durchsuchen", geben Sie c:\Programme\Microsoft c:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll aus, und klicken Sie auf OK.

4. Wiederholen Sie für "PresentationFramework.dll": C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Wiederholen Sie für "WindowsBase.dll": C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Wiederholen Sie für UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Wiederholen Sie für "UIAutomationProvider.dll": C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. Klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie "System.dll" aus, und klicken Sie auf **OK**.

9. Klicken Sie auf **OK** um die win32clock-Eigenschaftenseiten zum Hinzufügen von Verweisen zu beenden.

 Fügen Sie abschließend die `STAThreadAttribute` auf die `_tWinMain` Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Dieses Attribut teilt die [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] , die bei der Initialisierung [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], muss bei Verwendung ein Modells für Singlethread-Apartment (STA), der erforderlich ist [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).

## <a name="create-a-windows-presentation-framework-page"></a>Erstellen einer Windows Presentation Framework-Seite

Als Nächstes erstellen Sie eine DLL, definiert ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>. Es ist häufig am einfachsten, erstellen die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> als eigenständige Anwendung, und Schreiben und Debuggen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Codeabschnitte darin. Danach kann das Projekt in eine DLL aktiviert werden, mit der rechten Maustaste auf das Projekt **Eigenschaften**, zur Anwendung wechseln und das Ändern der Ausgabetyp für Windows-Klassenbibliothek.

Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Dll-Projekt kann dann mit kombiniert werden die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt (eine Projektmappe, die zwei Projekte enthält) – mit der rechten Maustaste auf die Projektmappe, wählen **hinzufügen\vorhandenes Projekt**.

Verwendet werden soll, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Dll aus dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] -Projekt müssen Sie einen Verweis hinzufügen:

1. Mit der rechten Maustaste win32clock-Projekt, und wählen Sie **Verweise...** .

2. Klicken Sie auf **neuen Verweis hinzufügen**.

3. Klicken Sie auf die Registerkarte **Projekte**. Wählen Sie „WPFClock” aus und klicken Sie auf OK.

4. Klicken Sie auf **OK** um die win32clock-Eigenschaftenseiten zum Hinzufügen von Verweisen zu beenden.

## <a name="hwndsource"></a>HwndSource

Verwenden Sie als Nächstes <xref:System.Windows.Interop.HwndSource> vornehmen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> ein HWND aussehen. Sie fügen diesen Codeblock zu einer C++-Datei hinzu:

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;

    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
        HwndSource^ source = gcnew HwndSource(
            0, // class style
            WS_VISIBLE | WS_CHILD, // style
            0, // exstyle
            x, y, width, height,
            "hi", // NAME
            IntPtr(parent)        // parent window
            );

        UIElement^ page = gcnew WPFClock::Clock();
        source->RootVisual = page;
        return (HWND) source->Handle.ToPointer();
    }
}
}
```

 Dies ist ein langer Codeabschnitt, der einiger Erklärungen bedarf. Der erste Teil besteht aus verschiedenen Klauseln, die dafür sorgen, dass nicht alle Aufrufe vollständig qualifiziert werden müssen:

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 Anschließend definieren Sie eine Funktion, die erstellt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, fügt ein <xref:System.Windows.Interop.HwndSource> Rand, und gibt den HWND zurück:

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

Erstellen Sie zunächst eine <xref:System.Windows.Interop.HwndSource>, denen von CreateWindow ähneln, deren Parameter:

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

Anschließend Sie erstellen die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhaltsklasse, indem Sie ihren Konstruktor aufrufen:

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

Verbinden Sie Sie dann die Seite, um die <xref:System.Windows.Interop.HwndSource>:

```cpp
source->RootVisual = page;
```

 Und geben Sie in der letzten Zeile zurück HWND für den <xref:System.Windows.Interop.HwndSource>:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Positionieren des HWND

Nun, Sie verfügen über ein HWND mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr, müssen Sie das HWND platziert die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld. Wenn Sie wissen, dass nur, wo das HWND, nur übergeben Sie dessen Größe und Position, an die `GetHwnd` Funktion, die Sie zuvor definiert haben. Da Sie für die Definition des Dialogs aber eine Ressourcendatei verwendet haben, können Sie nicht sicher wissen, wo ein HWND jeweils platziert sein wird. Können Sie die [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] Dialog-Editor Platzieren einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] statische steuern, in dem Sie die Uhr haben möchten ("Uhr hier einfügen"), und positionieren Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr.

Bei der Sie WM_INITDIALOG handeln, verwenden Sie `GetDlgItem` das HWND für den Platzhalter statische abrufen:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

Klicken Sie dann berechnet die Größe und Position des Platzhalters "STATIC", und Sie nehmen können die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Uhr an dieser Stelle:

RECT rectangle;

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

Blenden Sie anschließen den Platzhalter „STATIC” aus:

```cpp
ShowWindow(placeholder, SW_HIDE);
```

Und erstellen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND an diesem Speicherort:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Um das Tutorial etwas interessanter zu machen, und um eine echte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr, Sie benötigen zum Erstellen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr-Steuerelement an diesem Punkt. Den größten Teil davon können Sie in Markup erledigen, mit nur einigen wenigen Ereignishandlern im CodeBehind. Da in diesem Tutorial zu Interoperabilität und Design von Steuerelementen beschäftigt ist, wird der vollständige Code für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr dient hier als Codeblock, ohne Einzelschritte Aufbau oder die Bedeutung der einzelnen Teile. Experimentieren Sie ruhig mit diesem Code, um Aussehen, Verhalten oder Funktionalität des Steuerelements zu ändern.

Dies ist das Markup:

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

Und hier das zugehörige CodeBehind:

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

Das Endergebnis sieht folgendermaßen aus:

![Das Dialogfeld Datums- und Uhrzeiteigenschaften Endergebnis](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

Um Ihr Ergebnis mit den Code zu vergleichen, die diese Abbildung produzierte, finden Sie unter [Beispiel für die Interaktion von Win32-Uhr](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Beispiel für Interaktion mit der Win32-Uhr](https://go.microsoft.com/fwlink/?LinkID=160051)
