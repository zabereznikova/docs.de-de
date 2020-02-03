---
title: Hosting von Win32-Inhalten
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: b3113d9f3146e1590363dc9db6f751a429dda74b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747016"
---
# <a name="hosting-win32-content-in-wpf"></a>Hosten von Win32-Inhalt in WPF

## <a name="prerequisites"></a>Voraussetzungen

Siehe [WPF-und Win32-Interoperation](wpf-and-win32-interoperation.md).

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Exemplarische Vorgehensweise von Win32 in Windows Presentation Framework (HwndHost)

Um Win32-Inhalte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen wiederzuverwenden, verwenden Sie <xref:System.Windows.Interop.HwndHost>, bei dem es sich um ein Steuerelement handelt, mit dem HWNDs [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt aussehen. <xref:System.Windows.Interop.HwndHost> ist wie <xref:System.Windows.Interop.HwndSource>einfach zu verwenden: leiten Sie von <xref:System.Windows.Interop.HwndHost> ab, implementieren Sie `BuildWindowCore` und `DestroyWindowCore` Methoden, instanziieren Sie Ihre <xref:System.Windows.Interop.HwndHost> abgeleitete Klasse, und platzieren Sie Sie in ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.

Wenn die Win32-Logik bereits als Steuerelement gepackt ist, ist die `BuildWindowCore` Implementierung kaum mehr als ein `CreateWindow`. So erstellen Sie z. b. ein Win32-ListBox-Steuerelement in C++:

```cpp
virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {
    HWND handle = CreateWindowEx(0, L"LISTBOX",
    L"this is a Win32 listbox",
    WS_CHILD | WS_VISIBLE | LBS_NOTIFY
    | WS_VSCROLL | WS_BORDER,
    0, 0, // x, y
    30, 70, // height, width
    (HWND) hwndParent.Handle.ToPointer(), // parent hwnd
    0, // hmenu
    0, // hinstance
    0); // lparam

    return HandleRef(this, IntPtr(handle));
}

virtual void DestroyWindowCore(HandleRef hwnd) override {
    // HwndHost will dispose the hwnd for us
}
```

Angenommen, der Win32-Code ist nicht ganz so eigenständig? Wenn dies der Fall ist, können Sie ein Win32-Dialogfeld erstellen und seinen Inhalt in eine größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung einbetten. Das Beispiel zeigt dies in Visual Studio und C++, auch wenn es möglich ist, dies in einer anderen Sprache oder in der Befehlszeile zu tun.

Beginnen Sie mit einem einfachen Dialogfeld, das in ein C++ DLL-Projekt kompiliert wird.

Führen Sie als nächstes den Dialog in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ein:

- Kompilieren der dll als verwaltet (`/clr`)

- Dialogfeld in ein Steuerelement umwandeln

- Hiermit wird die abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> mit `BuildWindowCore` und `DestroyWindowCore` Methoden definiert.

- Überschreiben `TranslateAccelerator` Methode zum Behandeln von Dialog Schlüsseln

- Überschreiben `TabInto` Methode zur Unterstützung von Tabstopps

- Überschreiben der `OnMnemonic` Methode zur Unterstützung von mnetmonics

- Instanziieren Sie die <xref:System.Windows.Interop.HwndHost> Unterklasse, und legen Sie Sie unter dem rechten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element ab.

### <a name="turn-the-dialog-into-a-control"></a>Dialog Feld in ein Steuerelement umwandeln

Mithilfe der Stile WS_CHILD und DS_CONTROL können Sie ein Dialogfeld in ein untergeordnetes HWND umwandeln. Wechseln Sie in die Ressourcen Datei (RC-Datei), in der das Dialogfeld definiert ist, und suchen Sie den Anfang der Definition des Dialog Felds:

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

Ändern Sie die zweite Zeile in:

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

Mit dieser Aktion wird Sie nicht vollständig in ein eigenständiges Steuerelement paketieren. Sie müssen weiterhin `IsDialogMessage()` aufzurufen, damit Win32 bestimmte Nachrichten verarbeiten kann, aber die Steuerelement Änderung bietet eine einfache Möglichkeit, diese Steuerelemente in einem anderen HWND zu platzieren.

## <a name="subclass-hwndhost"></a>Unterklasse HwndHost

Importieren Sie die folgenden Namespaces:

```cpp
namespace ManagedCpp
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Input;
    using namespace System::Windows::Media;
    using namespace System::Runtime::InteropServices;
```

Erstellen Sie dann eine abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost>, und überschreiben Sie die Methoden `BuildWindowCore` und `DestroyWindowCore`:

```cpp
public ref class MyHwndHost : public HwndHost, IKeyboardInputSink {
    private:
        HWND dialog;

    protected:
        virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {
            InitializeGlobals();
            dialog = CreateDialog(hInstance,
                MAKEINTRESOURCE(IDD_DIALOG1),
                (HWND) hwndParent.Handle.ToPointer(),
                (DLGPROC) About);
            return HandleRef(this, IntPtr(dialog));
        }

        virtual void DestroyWindowCore(HandleRef hwnd) override {
            // hwnd will be disposed for us
        }
```

Hier verwenden Sie die `CreateDialog`, um das Dialogfeld zu erstellen, das tatsächlich ein Steuerelement ist. Da dies eine der ersten Methoden ist, die in der dll aufgerufen werden, sollten Sie auch eine standardmäßige Win32-Initialisierung durchführen, indem Sie eine Funktion aufrufen, die Sie später definieren, so genannte `InitializeGlobals()`:

```cpp
bool initialized = false;
    void InitializeGlobals() {
        if (initialized) return;
        initialized = true;

        // TODO: Place code here.
        MSG msg;
        HACCEL hAccelTable;

        // Initialize global strings
        LoadString(hInstance, IDS_APP_TITLE, szTitle, MAX_LOADSTRING);
        LoadString(hInstance, IDC_TYPICALWIN32DIALOG, szWindowClass, MAX_LOADSTRING);
        MyRegisterClass(hInstance);
```

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>Überschreiben der TranslateAccelerator-Methode zum Behandeln von Dialog Schlüsseln

Wenn Sie dieses Beispiel jetzt ausgeführt haben, erhalten Sie ein Dialogfeld Steuerelement, das angezeigt wird, aber es würde die gesamte Tastatur Verarbeitung ignorieren, durch die ein Dialogfeld zu einem funktionalen Dialogfeld wird. Nun sollten Sie die `TranslateAccelerator`-Implementierung überschreiben (die aus `IKeyboardInputSink`stammt, eine Schnittstelle, die implementiert <xref:System.Windows.Interop.HwndHost>). Diese Methode wird aufgerufen, wenn die Anwendung WM_KEYDOWN und WM_SYSKEYDOWN empfängt.

```cpp
#undef TranslateAccelerator
        virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
            ModifierKeys modifiers) override
        {
            ::MSG m = ConvertMessage(msg);

            // Win32's IsDialogMessage() will handle most of our tabbing, but doesn't know
            // what to do when it reaches the last tab stop
            if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {
                HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
                HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
                TraversalRequest^ request = nullptr;

                if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {
                    // this code should work, but there’s a bug with interop shift-tab in current builds
                    request = gcnew TraversalRequest(FocusNavigationDirection::Last);
                }
                else if (!GetKeyState(VK_SHIFT) && GetFocus() == lastTabStop) {
                    request = gcnew TraversalRequest(FocusNavigationDirection::Next);
                }

                if (request != nullptr)
                    return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);

            }

            // Only call IsDialogMessage for keys it will do something with.
            if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {
                switch (m.wParam) {
                    case VK_TAB:
                    case VK_LEFT:
                    case VK_UP:
                    case VK_RIGHT:
                    case VK_DOWN:
                    case VK_EXECUTE:
                    case VK_RETURN:
                    case VK_ESCAPE:
                    case VK_CANCEL:
                        IsDialogMessage(dialog, &m);
                        // IsDialogMessage should be called ProcessDialogMessage --
                        // it processes messages without ever really telling you
                        // if it handled a specific message or not
                        return true;
                }
            }

            return false; // not a key we handled
        }
```

Dabei handelt es sich um einen großen Code in einem Teil, der einige Ausführlichere Erläuterungen verwenden könnte. Erstens: der Code mit C++ den C++ Makros und. Sie müssen beachten, dass bereits ein Makro mit dem Namen `TranslateAccelerator`vorhanden ist, das in winuser. h definiert ist:

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

Stellen Sie daher sicher, dass Sie eine `TranslateAccelerator` Methode und keine `TranslateAcceleratorW` Methode definieren.

Ebenso gibt es sowohl die nicht verwaltete Winuser. h-Meldung als auch die verwaltete `Microsoft::Win32::MSG`-Struktur. Mit dem C++ `::`-Operator können Sie zwischen den beiden unterschieden werden.

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}

Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:

```cpp
::MSG ConvertMessage(System::Windows::Interop::MSG% msg) {
    ::MSG m;
    m.hwnd = (HWND) msg.hwnd.ToPointer();
    m.lParam = (LPARAM) msg.lParam.ToPointer();
    m.message = msg.message;
    m.wParam = (WPARAM) msg.wParam.ToPointer();

    m.time = msg.time;

    POINT pt;
    pt.x = msg.pt_x;
    pt.y = msg.pt_y;
    m.pt = pt;

    return m;
}
```

Zurück zum `TranslateAccelerator`. Das Grundprinzip besteht darin, die Win32-Funktion `IsDialogMessage` aufzurufen, um so viel Arbeit wie möglich zu tun, `IsDialogMessage` aber keinen Zugriff auf etwas außerhalb des Dialog Felds hat. Wenn im Dialogfeld die Registerkarte Benutzer im Dialogfeld angezeigt wird, müssen Sie den Fokus auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil durch Aufrufen von `IKeyboardInputSite::OnNoMoreStops`festlegen.

```cpp
// Win32's IsDialogMessage() will handle most of the tabbing, but doesn't know
// what to do when it reaches the last tab stop
if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {
    HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
    HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
    TraversalRequest^ request = nullptr;

    if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {
        request = gcnew TraversalRequest(FocusNavigationDirection::Last);
    }
    else if (!GetKeyState(VK_SHIFT) && GetFocus() ==  lastTabStop) { {
        request = gcnew TraversalRequest(FocusNavigationDirection::Next);
    }

    if (request != nullptr)
        return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);
}
```

Rufen Sie abschließend `IsDialogMessage` auf. Aber eine der Zuständigkeiten einer `TranslateAccelerator` Methode ist [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ob Sie den Tastatureingaben behandelt haben. Wenn Sie es nicht behandelt haben, kann das Eingabe Ereignis einen Tunnel durchlaufen und durch den Rest der Anwendung Blasen. Hier machen Sie eine Voreinstellung von Tastatur Messange-Behandlung und die Art der Eingabe Architektur in Win32 verfügbar. Leider wird `IsDialogMessage` nicht in irgendeiner Weise zurückgegeben, unabhängig davon, ob eine bestimmte Tastatureingabe verarbeitet wird. Noch schlimmer ist, dass `DispatchMessage()` bei Tastatureingaben aufgerufen wird, die nicht behandelt werden sollten!  Daher müssen Sie `IsDialogMessage`rückgängig machen und nur für die Schlüssel anrufen, die Sie behandeln werden:

```cpp
// Only call IsDialogMessage for keys it will do something with.
if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {
    switch (m.wParam) {
        case VK_TAB:
        case VK_LEFT:
        case VK_UP:
        case VK_RIGHT:
        case VK_DOWN:
        case VK_EXECUTE:
        case VK_RETURN:
        case VK_ESCAPE:
        case VK_CANCEL:
            IsDialogMessage(dialog, &m);
            // IsDialogMessage should be called ProcessDialogMessage --
            // it processes messages without ever really telling you
            // if it handled a specific message or not
            return true;
    }
```

### <a name="override-tabinto-method-to-support-tabbing"></a>TabInto-Methode zur Unterstützung von Tabstopps überschreiben

Nachdem Sie `TranslateAccelerator`implementiert haben, kann ein Benutzer im Dialogfeld mit der Tab-Taste navigieren und in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung darauf klicken. Ein Benutzer kann jedoch nicht zurück in das Dialogfeld zurückkehren. Um dieses Problem zu beheben, überschreiben Sie `TabInto`:

```cpp
public:
    virtual bool TabInto(TraversalRequest^ request) override {
        if (request->FocusNavigationDirection == FocusNavigationDirection::Last) {
            HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);
            SetFocus(lastTabStop);
        }
        else {
            HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);
            SetFocus(firstTabStop);
        }
        return true;
    }
```

Der `TraversalRequest`-Parameter gibt an, ob die Registerkarten Aktion eine Registerkarte oder eine UMSCHALT Registerkarte ist.

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Überschreiben der onmnetmonic-Methode zur Unterstützung von mnetmonics

Die Tastatur Behandlung ist fast vollständig, aber es fehlt eine Sache, – mnetmonics funktioniert nicht. Wenn ein Benutzer ALT + F drückt, springt der Fokus "Doe" nicht in das Bearbeitungsfeld "First Name:". Daher überschreiben Sie die `OnMnemonic`-Methode:

```cpp
virtual bool OnMnemonic(System::Windows::Interop::MSG% msg, ModifierKeys modifiers) override {
    ::MSG m = ConvertMessage(msg);

    // If it's one of our mnemonics, set focus to the appropriate hwnd
    if (msg.message == WM_SYSCHAR && GetKeyState(VK_MENU /*alt*/)) {
        int dialogitem = 9999;
        switch (m.wParam) {
            case 's': dialogitem = IDOK; break;
            case 'c': dialogitem = IDCANCEL; break;
            case 'f': dialogitem = IDC_EDIT1; break;
            case 'l': dialogitem = IDC_EDIT2; break;
            case 'p': dialogitem = IDC_EDIT3; break;
            case 'a': dialogitem = IDC_EDIT4; break;
            case 'i': dialogitem = IDC_EDIT5; break;
            case 't': dialogitem = IDC_EDIT6; break;
            case 'z': dialogitem = IDC_EDIT7; break;
        }
        if (dialogitem != 9999) {
            HWND hwnd = GetDlgItem(dialog, dialogitem);
            SetFocus(hwnd);
            return true;
        }
    }
    return false; // key unhandled
};
```

Warum werden hier keine `IsDialogMessage` aufgerufen?  Sie haben dasselbe Problem wie zuvor. Sie müssen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Code informieren können, ob der Code die Tastatureingaben behandelt hat, und `IsDialogMessage` dies nicht tun können. Es gibt auch ein zweites Problem, weil `IsDialogMessage` die Verarbeitung des mnetmonischen verweigert, wenn sich das fokussierte HWND nicht innerhalb des Dialog Felds befindet.

### <a name="instantiate-the-hwndhost-derived-class"></a>Instanziieren der abgeleiteten HwndHost-Klasse

Nachdem Sie nun alle Schlüssel-und Registerkarten Unterstützung eingerichtet haben, können Sie Ihre <xref:System.Windows.Interop.HwndHost> in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung platzieren. Wenn die Hauptanwendung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]geschrieben ist, besteht die einfachste Möglichkeit, Sie an der richtigen Stelle zu platzieren, darin, ein leeres <xref:System.Windows.Controls.Border> Element zu belassen, wo Sie die <xref:System.Windows.Interop.HwndHost>platzieren möchten. Hier erstellen Sie eine <xref:System.Windows.Controls.Border> mit dem Namen `insertHwndHostHere`:

```xaml
<Window x:Class="WPFApplication1.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Windows Presentation Framework Application"
    Loaded="Window1_Loaded"
    >
    <StackPanel>
        <Button Content="WPF button"/>
        <Border Name="insertHwndHostHere" Height="200" Width="500"/>
        <Button Content="WPF button"/>
    </StackPanel>
</Window>
```

Dann müssen Sie nur noch einen guten Speicherort in der Code Sequenz finden, um den <xref:System.Windows.Interop.HwndHost> zu instanziieren und ihn mit dem <xref:System.Windows.Controls.Border>zu verbinden. In diesem Beispiel fügen Sie Sie in den Konstruktor für die <xref:System.Windows.Window> abgeleitete Klasse ein:

```csharp
public partial class Window1 : Window {
    public Window1() {
    }

    void Window1_Loaded(object sender, RoutedEventArgs e) {
        HwndHost host = new ManagedCpp.MyHwndHost();
        insertHwndHostHere.Child = host;
    }
}
```

So erhalten Sie Folgendes:

![Screenshot der WPF-App, die ausgeführt wird.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a>Weitere Informationen

- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
