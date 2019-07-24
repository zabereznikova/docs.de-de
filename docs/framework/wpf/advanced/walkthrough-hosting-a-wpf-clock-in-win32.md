---
title: 'Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 98e48060bbb82764e1e541797c666ca33f247c39
ms.sourcegitcommit: 24a4a8eb6d8cfe7b8549fb6d823076d7c697e0c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "68400477"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32

Verwenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Sie zum Einfügen in Anwendungen, das das HWND bereitstellt, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ihren Inhalt enthält. <xref:System.Windows.Interop.HwndSource> Erstellen Sie zunächst das <xref:System.Windows.Interop.HwndSource>, und geben Sie ihm Parameter ähnlich "kreatewindow". Dann geben Sie die <xref:System.Windows.Interop.HwndSource> Informationen über [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] den gewünschten Inhalt an. Schließlich erhalten Sie das HWND aus dem <xref:System.Windows.Interop.HwndSource>. In dieser exemplarischen Vorgehensweise wird veranschaulicht, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wie [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ein gemischtes innerhalb der Anwendung erstellt wird, die das **Datum und die Uhrzeit-Eigenschaften** Dialogfeld des Betriebssystems

## <a name="prerequisites"></a>Vorraussetzungen

Siehe [WPF-und Win32-Interoperation](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Verwendung dieses Tutorials

Dieses Tutorial konzentriert sich auf die wichtigsten Schritte zum Erstellen einer interoperativen Anwendung. Das Lernprogramm wird durch ein Beispiel für ein Beispiel für die [Win32-Takt Interaktion](https://go.microsoft.com/fwlink/?LinkID=160051)unterstützt, aber dieses Beispiel reflektiert das Endprodukt. In diesem Tutorial werden die Schritte so dokumentiert, als würden Sie mit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] einem vorhandenen Projekt, möglicherweise mit einem bereits vorhandenen Projekt, beginnen, und Sie haben eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gehostete zu Ihrer Anwendung hinzugefügt. Sie können Ihr Endprodukt mit dem [Beispiel für die Win32-Takt Interaktion](https://go.microsoft.com/fwlink/?LinkID=160051)vergleichen.

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Eine exemplarische Vorgehensweise für Windows Presentation Framework in Win32 (HwndSource)

Die folgende Grafik zeigt das angestrebte Endprodukt dieses Tutorials:

![Screenshot, der das Dialogfeld Datums-und Uhrzeit Eigenschaften anzeigt.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Sie können dieses Dialogfeld neu erstellen, C++ indem Sie ein Win32-Projekt in Visual Studio erstellen und den Dialog-Editor verwenden, um Folgendes zu erstellen:

![Dialogfeld "Eigenschaften für Datum und Uhrzeit neu erstellt"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

(Sie müssen [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] nicht verwenden <xref:System.Windows.Interop.HwndSource>, um zu verwenden, und Sie müssen nicht C++ zum Schreiben [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] von Programmen verwenden. Dies ist jedoch eine ziemlich typische Methode, um dies zu tun, und eignet sich gut für eine schrittweise Lernprogramm Erklärung).

Sie müssen fünf bestimmte unter Schritte ausführen, um eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr in den Dialog zu versetzen:

1. Aktivieren Sie [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] das Projekt, um verwalteten Code ( **/CLR**) aufzurufen, indem [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]Sie die Projekteinstellungen in ändern.

2. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ErstellenSie<xref:System.Windows.Controls.Page> in einer separaten dll.

3. Fügen Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das <xref:System.Windows.Controls.Page> in <xref:System.Windows.Interop.HwndSource>eine ein.

4. Verwenden Sie die <xref:System.Windows.Controls.Page> <xref:System.Windows.Interop.HwndSource.Handle%2A> -Eigenschaft, um ein HWND zu erhalten.

5. Verwenden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Sie, um zu entscheiden, wo das HWND in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] der größeren Anwendung platziert werden soll.

## <a name="clr"></a>/clr

Der erste Schritt besteht darin, dieses nicht verwaltete [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt in eines zu verwandeln, das verwalteten Code abrufen kann. Verwenden Sie die/CLR-Compileroption, die mit den erforderlichen DLLs verknüpft wird, die Sie verwenden möchten, und passen Sie die Main [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Methode für die Verwendung mit an.

So aktivieren Sie die Verwendung von verwaltetem Code C++ innerhalb des Projekts: Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Eigenschaften**. Ändern Sie auf der Eigenschaften Seite **Allgemein** (Standard) die Common Language Runtime-unter `/clr`Stützung in.

Fügen Sie als nächstes Verweise auf DLLs hinzu [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], die für erforderlich sind: "PresentationCore. dll", "presentationframework. dll", "System. dll", "WindowsBase. dll", "UIAutomationProvider. dll" und "UIAutomationTypes. dll". (Bei den nachfolgenden Anweisungen wird davon ausgegangen, dass das Betriebssystem auf Laufwerk C: installiert ist.)

1. Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise...** und innerhalb dieses Dialog Felds:

2. Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise**aus.

3. Klicken Sie auf **neuen Verweis hinzufügen**, klicken Sie auf die Registerkarte Durchsuchen, geben Sie c:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll ein, und klicken Sie auf OK.

4. Wiederholen Sie diesen Schritt für presentationframework. dll: C:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Wiederholen Sie diesen Schritt für "WindowsBase. dll: C:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Wiederholen Sie diesen Schritt für UIAutomationTypes. dll: C:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Wiederholen Sie diesen Schritt für UIAutomationProvider. dll: C:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\uiautomationprovider.dll.

8. Klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie System. dll, und klicken Sie auf **OK**.

9. Klicken Sie auf **OK** , um die Eigenschaften Seiten Mausklick das win32clock zum Hinzufügen von verweisen zu schließen.

 Fügen Sie abschließend der `STAThreadAttribute` `_tWinMain` -Methode zur Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hinzu:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Dieses Attribut teilt dem Common Language Runtime (CLR) mit, dass es beim [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]initialisieren ein Single Thread-Apartment-Modell (STA) verwenden sollte, das für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (und [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]) erforderlich ist.

## <a name="create-a-windows-presentation-framework-page"></a>Erstellen einer Windows Presentation Framework-Seite

Als Nächstes erstellen Sie eine DLL, die eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>definiert. Häufig ist es am [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> einfachsten, als eigenständige Anwendung zu erstellen und den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil auf diese Weise zu schreiben und zu debuggen. Anschließend kann das Projekt in eine DLL-Datei umgewandelt werden, indem Sie mit der rechten Maustaste auf das Projekt klicken, auf **Eigenschaften**klicken, die Anwendung aufrufen und den Ausgabetyp in Windows-Klassenbibliothek ändern.

Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DLL-Projekt kann dann mit dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt kombiniert werden (eine Projekt Mappe, die zwei Projekte enthält) – klicken Sie mit der rechten Maustaste auf die Projekt Mappe, und wählen Sie **add\vorhandenes Projekt**aus.

Um diese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll aus dem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Projekt zu verwenden, müssen Sie einen Verweis hinzufügen:

1. Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise**aus.

2. Klicken Sie auf **neuen Verweis hinzufügen**.

3. Klicken Sie auf die Registerkarte **Projekte**. Wählen Sie „WPFClock” aus und klicken Sie auf OK.

4. Klicken Sie auf **OK** , um die Eigenschaften Seiten Mausklick das win32clock zum Hinzufügen von verweisen zu schließen.

## <a name="hwndsource"></a>HwndSource

Als nächstes verwenden <xref:System.Windows.Interop.HwndSource> Sie, um das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> aussehen wie ein HWND zu gestalten. Sie fügen diesen Codeblock zu einer C++-Datei hinzu:

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

 Dann definieren Sie eine Funktion, die den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt erstellt, eine <xref:System.Windows.Interop.HwndSource> umschließt und den HWND zurückgibt:

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

Erstellen Sie zunächst eine <xref:System.Windows.Interop.HwndSource>, deren Parameter mit "kreatewindow" vergleichbar sind:

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

Anschließend erstellen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalts Klasse, indem Sie Ihren Konstruktor aufrufen:

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

Anschließend verbinden Sie die Seite mit dem <xref:System.Windows.Interop.HwndSource>:

```cpp
source->RootVisual = page;
```

 Und in der letzten Zeile das HWND für den <xref:System.Windows.Interop.HwndSource>zurückgeben:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Positionieren des HWND

Nachdem Sie nun über ein HWND verfügen, das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Uhr enthält, müssen Sie dieses HWND in das [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld einfügen. Wenn Sie genau wissen, wo das HWND abgelegt werden soll, übergeben Sie einfach diese Größe und den Speicherort an die Funktion, die `GetHwnd` Sie zuvor definiert haben. Da Sie für die Definition des Dialogs aber eine Ressourcendatei verwendet haben, können Sie nicht sicher wissen, wo ein HWND jeweils platziert sein wird. Sie können den [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] Dialog-Editor verwenden, um [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] ein statisches Steuerelement zu platzieren, wo Sie die Uhr verschieben möchten ("Uhr hier einfügen"), und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dieses verwenden, um die Uhr zu positionieren.

Mit WM_INITDIALOG können Sie `GetDlgItem` das HWND für den Platzhalter STATIC abrufen:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

Anschließend berechnen Sie die Größe und Position des Platzhalters statisch, sodass Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr an dieser Stelle platzieren können:

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

Und erstellen Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] das HWND der Uhr an diesem Speicherort:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Damit das Lernprogramm interessant wird und eine echte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr erzeugt werden kann, müssen Sie an dieser Stelle ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock-Steuerelement erstellen. Den größten Teil davon können Sie in Markup erledigen, mit nur einigen wenigen Ereignishandlern im CodeBehind. Da es sich bei diesem Tutorial um die Interoperabilität handelt und nicht um das Design der Steuer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente, wird der gesamte Code für die Uhr hier als Codeblock bereitgestellt, ohne diskrete Anweisungen für die Erstellung oder die Bedeutung der einzelnen Teile. Experimentieren Sie ruhig mit diesem Code, um Aussehen, Verhalten oder Funktionalität des Steuerelements zu ändern.

Dies ist das Markup:

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

Und hier das zugehörige CodeBehind:

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

Das Endergebnis sieht folgendermaßen aus:

![Dialogfeld "endgültige Datums-und Uhrzeit Eigenschaften"](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

Informationen zum Vergleichen des Ergebnisses mit dem Code, der diesen Screenshot erzeugt hat, finden Sie unter Beispiel für die [Win32-Takt Interaktion](https://go.microsoft.com/fwlink/?LinkID=160051).

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
- [Beispiel für Interaktion mit der Win32-Uhr](https://go.microsoft.com/fwlink/?LinkID=160051)
