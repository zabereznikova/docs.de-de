---
title: Hosting von Win32-Inhalten
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: c0c62f1999feaf591c512314515f01e83fa12591
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052090"
---
# <a name="hosting-win32-content-in-wpf"></a>Hosten von Win32-Inhalt in WPF

## <a name="prerequisites"></a>Voraussetzungen

Siehe [WPF-und Win32-Interoperation](wpf-and-win32-interoperation.md).

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Exemplarische Vorgehensweise von Win32 in Windows Presentation Framework (HwndHost)

Verwenden Sie zum wieder verwenden von Win32-Inhalt in- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen <xref:System.Windows.Interop.HwndHost> . Hierbei handelt es sich um ein Steuerelement, das HWNDs als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt ansieht. Wie <xref:System.Windows.Interop.HwndSource> <xref:System.Windows.Interop.HwndHost> ist einfach zu verwenden: leiten Sie von ab <xref:System.Windows.Interop.HwndHost> `BuildWindowCore` , implementieren `DestroyWindowCore` Sie die-Methode und die-Methode, instanziieren <xref:System.Windows.Interop.HwndHost> Sie Ihre abgeleitete Klasse, und platzieren Sie Sie in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.

Wenn die Win32-Logik bereits als Steuerelement gepackt ist, `BuildWindowCore` ist die Implementierung kaum mehr als ein-Befehl `CreateWindow` . So erstellen Sie z. b. ein Win32-ListBox-Steuerelement in C++:

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

Angenommen, der Win32-Code ist nicht ganz so eigenständig? Wenn dies der Fall ist, können Sie ein Win32-Dialogfeld erstellen und seinen Inhalt in eine größere Anwendung einbetten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Das Beispiel zeigt dies in Visual Studio und C++, obwohl dies auch in einer anderen Sprache oder über die Befehlszeile möglich ist.

Beginnen Sie mit einem einfachen Dialogfeld, das in ein C++-DLL-Projekt kompiliert wird.

Führen Sie als nächstes den Dialog in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ein:

- Kompilieren Sie die dll als verwaltet ( `/clr` ).

- Dialogfeld in ein Steuerelement umwandeln

- Definieren der abgeleiteten Klasse von <xref:System.Windows.Interop.HwndHost> mit `BuildWindowCore` -und- `DestroyWindowCore` Methoden

- Überschreibungs `TranslateAccelerator` Methode zum Behandeln von Dialog Schlüsseln

- Außerkraftsetzungs `TabInto` Methode zur Unterstützung von Tabstopps

- Überschreibungs `OnMnemonic` Methode zur Unterstützung von mnetmonics

- Instanziieren <xref:System.Windows.Interop.HwndHost> Sie die Unterklasse, und legen Sie Sie unter dem rechten Element ab. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]

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

Mit dieser Aktion wird Sie nicht vollständig in ein eigenständiges Steuerelement paketieren. Sie müssen trotzdem aufzurufen `IsDialogMessage()` , damit Win32 bestimmte Nachrichten verarbeiten kann, aber die Steuerelement Änderung bietet eine einfache Möglichkeit, diese Steuerelemente in einem anderen HWND zu platzieren.

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

Erstellen Sie dann eine abgeleitete Klasse von, <xref:System.Windows.Interop.HwndHost> und überschreiben Sie die `BuildWindowCore` `DestroyWindowCore` Methoden und:

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

Hier verwenden Sie `CreateDialog` , um das Dialogfeld zu erstellen, das tatsächlich ein Steuerelement ist. Da dies eine der ersten Methoden ist, die in der dll aufgerufen werden, sollten Sie auch eine standardmäßige Win32-Initialisierung durchführen, indem Sie eine Funktion aufrufen, die Sie später definieren `InitializeGlobals()` :

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

Wenn Sie dieses Beispiel jetzt ausgeführt haben, erhalten Sie ein Dialogfeld Steuerelement, das angezeigt wird, aber es würde die gesamte Tastatur Verarbeitung ignorieren, durch die ein Dialogfeld zu einem funktionalen Dialogfeld wird. Jetzt sollten Sie die- `TranslateAccelerator` Implementierung überschreiben (aus `IKeyboardInputSink` einer Schnittstelle, die <xref:System.Windows.Interop.HwndHost> implementiert). Diese Methode wird aufgerufen, wenn die Anwendung WM_KEYDOWN und WM_SYSKEYDOWN empfängt.

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

Dabei handelt es sich um einen großen Code in einem Teil, der einige Ausführlichere Erläuterungen verwenden könnte. Zuerst der Code, der C++-und C++-Makros verwendet. Sie müssen beachten, dass bereits ein Makro mit dem Namen vorhanden ist `TranslateAccelerator` , das in winuser. h definiert ist:

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

Stellen Sie daher sicher, dass Sie eine `TranslateAccelerator` Methode und keine `TranslateAcceleratorW` Methode definieren.

Ebenso gibt es sowohl die nicht verwaltete Winuser. h-Meldung als auch die verwaltete `Microsoft::Win32::MSG` Struktur. Mit dem C++-Operator können Sie zwischen den beiden unterschieden werden `::` .

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}
```

Beide Msgs verfügen über dieselben Daten. manchmal ist es jedoch einfacher, mit der nicht verwalteten Definition zu arbeiten. in diesem Beispiel können Sie also die offensichtliche Konvertierungsroutine definieren:

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

Zurück zu `TranslateAccelerator` . Das Grundprinzip besteht darin, die Win32-Funktion aufzurufen `IsDialogMessage` , um so viel Arbeit wie möglich zu erledigen, aber keinen `IsDialogMessage` Zugriff auf etwas außerhalb des Dialog Felds. Wenn im Dialogfeld die Registerkarte Benutzer im Dialogfeld angezeigt wird, müssen Sie den Fokus auf den Teil festlegen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] indem Sie aufrufen `IKeyboardInputSite::OnNoMoreStops` .

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

Rufen Sie abschließend `IsDialogMessage` auf. Aber eine der Verantwortlichkeiten einer `TranslateAccelerator` Methode gibt Aufschluss darüber, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ob Sie den Tastatureingaben behandelt haben. Wenn Sie es nicht behandelt haben, kann das Eingabe Ereignis einen Tunnel durchlaufen und durch den Rest der Anwendung Blasen. Hier machen Sie eine Voreinstellung von Tastatur Messange-Behandlung und die Art der Eingabe Architektur in Win32 verfügbar. Leider wird `IsDialogMessage` nicht in irgendeiner Weise zurückgegeben, unabhängig davon, ob ein bestimmter Tastatur Strich verarbeitet wird. Noch schlimmer ist, dass Sie bei Tastatureingaben aufgerufen wird, die `DispatchMessage()` nicht behandelt werden sollten!  Sie müssen sich also rückgängig machen `IsDialogMessage` und müssen nur für die Schlüssel aufgerufen werden, die er behandelt:

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

Nachdem Sie nun implementiert haben `TranslateAccelerator` , kann ein Benutzer im Dialogfeld mit der Tab-Taste navigieren und in der größeren Anwendung darauf klicken [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] . Ein Benutzer kann jedoch nicht zurück in das Dialogfeld zurückkehren. Um dieses Problem zu beheben, überschreiben Sie Folgendes `TabInto` :

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

Der- `TraversalRequest` Parameter gibt an, ob die Registerkarten Aktion eine Registerkarte oder eine UMSCHALT Registerkarte ist.

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Überschreiben der onmnetmonic-Methode zur Unterstützung von mnetmonics

Die Tastatur Behandlung ist fast vollständig, aber es fehlt eine Sache, – mnetmonics funktioniert nicht. Wenn ein Benutzer ALT + F drückt, springt der Fokus "Doe" nicht in das Bearbeitungsfeld "First Name:". Daher überschreiben Sie die- `OnMnemonic` Methode:

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

Warum wird hier nicht aufgerufen `IsDialogMessage` ?  Sie haben dasselbe Problem wie zuvor. Sie müssen in der Lage sein, Code darüber zu informieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , ob der Code die Tastatureingaben behandelt hat, und dies nicht `IsDialogMessage` . Es gibt auch ein zweites Problem, da `IsDialogMessage` die Verarbeitung des mnetmonischen, wenn sich das fokussierte HWND nicht innerhalb des Dialog Felds befindet.

### <a name="instantiate-the-hwndhost-derived-class"></a>Instanziieren der abgeleiteten HwndHost-Klasse

Nachdem nun alle Schlüssel-und Registerkarten Unterstützung vorhanden sind, können Sie Ihren <xref:System.Windows.Interop.HwndHost> in die größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung einfügen. Wenn die Hauptanwendung in geschrieben ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , besteht die einfachste Möglichkeit, Sie an der richtigen Stelle zu platzieren, darin, ein leeres Element zu verlassen, <xref:System.Windows.Controls.Border> in das Sie die platzieren möchten <xref:System.Windows.Interop.HwndHost> . Hier erstellen Sie einen mit dem <xref:System.Windows.Controls.Border> Namen `insertHwndHostHere` :

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

Dann müssen Sie nur noch einen guten Speicherort in der Code Sequenz finden, um die zu instanziieren <xref:System.Windows.Interop.HwndHost> und eine Verbindung mit dem herzustellen <xref:System.Windows.Controls.Border> . In diesem Beispiel fügen Sie Sie in den Konstruktor für die <xref:System.Windows.Window> abgeleitete Klasse ein:

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

## <a name="see-also"></a>Siehe auch

- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
