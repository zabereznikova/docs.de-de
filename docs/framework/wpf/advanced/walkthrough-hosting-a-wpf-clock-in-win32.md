---
title: 'Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32'
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 1fdc0c9ccf1464d7519a4c5935520de1206ca9bb
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794159"
---
# <a name="walkthrough-host-a-wpf-clock-in-win32"></a>Exemplarische Vorgehensweise: Hosten einer WPF-Uhr in Win32

Wenn Sie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in Win32-Anwendungen einfügen möchten, verwenden Sie <xref:System.Windows.Interop.HwndSource>, der das HWND bereitstellt, das Ihren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt enthält. Erstellen Sie zunächst die <xref:System.Windows.Interop.HwndSource>, und geben Sie Ihr Parameter ähnlich wie bei "kreatewindow" an. Dann informieren Sie den <xref:System.Windows.Interop.HwndSource> über den gewünschten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt. Schließlich erhalten Sie das HWND aus dem <xref:System.Windows.Interop.HwndSource>. In dieser exemplarischen Vorgehensweise wird veranschaulicht, wie ein gemischtes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer Win32-Anwendung erstellt wird, die das Eigenschaften Dialogfeld des Betriebssystems für **Datum und Uhrzeit**

## <a name="prerequisites"></a>Erforderliche Komponenten

Siehe [WPF-und Win32-Interoperation](wpf-and-win32-interoperation.md).

## <a name="how-to-use-this-tutorial"></a>Zur Verwendung dieses Lernprogramms

Dieses Tutorial konzentriert sich auf die wichtigsten Schritte zum Erstellen einer interoperativen Anwendung. Das Lernprogramm wird durch ein Beispiel für ein Beispiel für die [Win32-Takt Interaktion](https://go.microsoft.com/fwlink/?LinkID=160051)unterstützt, aber dieses Beispiel reflektiert das Endprodukt. In diesem Tutorial werden die Schritte so beschrieben, als würden Sie mit einem vorhandenen Win32-Projekt beginnen, das möglicherweise ein bereits vorhandenes Projekt ist, und Sie haben der Anwendung einen gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hinzugefügt. Sie können Ihr Endprodukt mit dem [Beispiel für die Win32-Takt Interaktion](https://go.microsoft.com/fwlink/?LinkID=160051)vergleichen.

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Eine exemplarische Vorgehensweise für Windows Presentation Framework in Win32 (HwndSource)

Die folgende Grafik zeigt das angestrebte Endprodukt dieses Tutorials:

![Screenshot, der das Dialogfeld Datums-und Uhrzeit Eigenschaften anzeigt.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

Sie können dieses Dialogfeld neu erstellen, C++ indem Sie ein Win32-Projekt in Visual Studio erstellen und den Dialog-Editor verwenden, um Folgendes zu erstellen:

![Dialogfeld "Eigenschaften für Datum und Uhrzeit neu erstellt"](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

(Sie müssen Visual Studio nicht verwenden, um <xref:System.Windows.Interop.HwndSource>zu verwenden, und Sie müssen nicht zum Schreiben von C++ Win32-Programmen verwenden. Dies ist jedoch eine ziemlich typische Methode, um dies zu tun, und eignet sich gut für eine schrittweise Lernprogramm Erklärung).

Sie müssen fünf bestimmte unter Schritte ausführen, um eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr in das Dialogfeld zu versetzen:

1. Aktivieren Sie das Win32-Projekt, um verwalteten Code ( **/CLR**) aufzurufen, indem Sie Projekteinstellungen in Visual Studio ändern.

2. Erstellen Sie eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in einer separaten dll.

3. Legen Sie diese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in einem <xref:System.Windows.Interop.HwndSource>ab.

4. Verwenden Sie die <xref:System.Windows.Interop.HwndSource.Handle%2A>-Eigenschaft, um ein HWND für dieses <xref:System.Windows.Controls.Page> zu erhalten.

5. Verwenden Sie Win32, um zu entscheiden, wo das HWND in der größeren Win32-Anwendung platziert werden soll.

## <a name="clr"></a>/clr

Der erste Schritt besteht darin, dieses nicht verwaltete Win32-Projekt in ein solches zu verwandeln, das verwalteten Code abrufen kann. Verwenden Sie die/CLR-Compileroption, die mit den erforderlichen DLLs verknüpft wird, die Sie verwenden möchten, und passen Sie die Main-Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]an.

So aktivieren Sie die Verwendung von verwaltetem Code C++ innerhalb des Projekts: Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Eigenschaften**aus. Ändern Sie auf der Eigenschaften Seite **Allgemein** (Standard) die Common Language Runtime-Unterstützung in `/clr`.

Fügen Sie als nächstes Verweise auf DLLs hinzu, die für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]erforderlich sind: presentationcore. dll, presentationframework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll und UIAutomationTypes. dll. (Bei den nachfolgenden Anweisungen wird davon ausgegangen, dass das Betriebssystem auf Laufwerk C: installiert ist.)

1. Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise...** und innerhalb dieses Dialog Felds:

2. Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise**aus.

3. Klicken Sie auf **neuen Verweis hinzufügen**, klicken Sie auf die Registerkarte Durchsuchen, geben Sie c:\Programme\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll ein, und klicken Sie auf OK.

4. Wiederholen Sie diesen Schritt für PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. Wiederholen Sie diesen Schritt für WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. Wiederholen Sie diesen Schritt für UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. Wiederholen Sie diesen Schritt für UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. Klicken Sie auf **neuen Verweis hinzufügen**, wählen Sie System. dll, und klicken Sie auf **OK**.

9. Klicken Sie auf **OK** , um die Eigenschaften Seiten Mausklick das win32clock zum Hinzufügen von verweisen zu schließen.

 Fügen Sie abschließend die `STAThreadAttribute` der `_tWinMain`-Methode für die Verwendung mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]hinzu:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

Dieses Attribut weist den Common Language Runtime (CLR) an, dass beim Initialisieren Component Object Model (com) ein Single Thread-Apartment Modell (STA) verwendet wird, das für [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (und Windows Forms) erforderlich ist.

## <a name="create-a-windows-presentation-framework-page"></a>Erstellen einer Windows Presentation Framework-Seite

Als Nächstes erstellen Sie eine DLL, die eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>definiert. Häufig ist es am einfachsten, den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> als eigenständige Anwendung zu erstellen und den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil auf diese Weise zu schreiben und zu debuggen. Anschließend kann das Projekt in eine DLL-Datei umgewandelt werden, indem Sie mit der rechten Maustaste auf das Projekt klicken, auf **Eigenschaften**klicken, die Anwendung aufrufen und den Ausgabetyp in Windows-Klassenbibliothek ändern.

Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] DLL-Projekt kann dann mit dem Win32-Projekt (eine Projekt Mappe, die zwei Projekte enthält) kombiniert werden – klicken Sie mit der rechten Maustaste auf die Projekt Mappe, und wählen Sie **add\vorhandenes Projekt**.

Um diese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll aus dem Win32-Projekt zu verwenden, müssen Sie einen Verweis hinzufügen:

1. Klicken Sie mit der rechten Maustaste auf Mausklick das win32clock Project, und wählen Sie **Verweise**aus.

2. Klicken Sie auf **neuen Verweis hinzufügen**.

3. Klicken Sie auf die Registerkarte **Projekte** . Wählen Sie wpfclock und dann OK aus.

4. Klicken Sie auf **OK** , um die Eigenschaften Seiten Mausklick das win32clock zum Hinzufügen von verweisen zu schließen.

## <a name="hwndsource"></a>HwndSource

Als nächstes verwenden Sie <xref:System.Windows.Interop.HwndSource>, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> wie ein HWND aussehen zu lassen. Sie fügen diesen Codeblock zu einer C++-Datei hinzu:

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

 Dann definieren Sie eine Funktion, die den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt erstellt, eine <xref:System.Windows.Interop.HwndSource> um die Datei setzt und das HWND zurückgibt:

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

Stellen Sie dann eine Verbindung zwischen der Seite und der <xref:System.Windows.Interop.HwndSource>her:

```cpp
source->RootVisual = page;
```

 Und in der letzten Zeile wird das HWND für den <xref:System.Windows.Interop.HwndSource>zurückgegeben:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Positionieren des HWND

Nachdem Sie nun über ein HWND verfügen, das die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr enthält, müssen Sie das HWND in das Win32-Dialogfeld einfügen. Wenn Sie genau wissen, wo das HWND abgelegt werden soll, übergeben Sie einfach diese Größe und den Speicherort an die `GetHwnd` Funktion, die Sie zuvor definiert haben. Da Sie für die Definition des Dialogs aber eine Ressourcendatei verwendet haben, können Sie nicht sicher wissen, wo ein HWND jeweils platziert sein wird. Sie können den Visual Studio-Dialog-Editor verwenden, um ein statisches Win32-Steuerelement zu platzieren, wo Sie die Uhr drehen möchten ("Uhr hier einfügen"), und dieses verwenden, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr zu positionieren.

Wenn Sie WM_INITDIALOG behandeln, verwenden Sie `GetDlgItem`, um das HWND für den Platzhalter statisch abzurufen:

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

Und erstellen Sie das HWND der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr an diesem Speicherort:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

Um das Lernprogramm interessant zu machen und eine echte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr zu erzeugen, müssen Sie an dieser Stelle ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Clock-Steuerelement erstellen. Den größten Teil davon können Sie in Markup erledigen, mit nur einigen wenigen Ereignishandlern im CodeBehind. Da es sich bei diesem Tutorial um Interoperabilität und nicht um das Design der Steuerelemente handelt, wird hier der gesamte Code für die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Uhr als Codeblock bereitgestellt, ohne diskrete Anweisungen für die Erstellung oder die Bedeutung der einzelnen Teile. Experimentieren Sie ruhig mit diesem Code, um Aussehen, Verhalten oder Funktionalität des Steuerelements zu ändern.

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
