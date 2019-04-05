---
title: Hosten von Win32-Inhalt in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: 8773cac1e421ecdca036e88d79797dae16f72b17
ms.sourcegitcommit: 68eb5c4928e2b082f178a42c16f73fedf52c2ab8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59055078"
---
# <a name="hosting-win32-content-in-wpf"></a>Hosten von Win32-Inhalt in WPF

## <a name="prerequisites"></a>Vorraussetzungen

Finden Sie unter [WPF und Win32-Interoperation](wpf-and-win32-interoperation.md).

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Eine exemplarische Vorgehensweise für Win32, Windows Presentation Framework (HwndHost)

Wiederverwenden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Inhalte innerhalb von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen verwenden <xref:System.Windows.Interop.HwndHost>, d.h. ein Steuerelement, mit der HWNDs aussehen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt. Wie <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> ist einfach zu verwenden: leiten Sie von <xref:System.Windows.Interop.HwndHost> und implementieren `BuildWindowCore` und `DestroyWindowCore` Methoden instanziieren, klicken Sie dann Ihre <xref:System.Windows.Interop.HwndHost> abgeleiteten Klasse ein, und platzieren Sie ihn in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Anwendung.

Wenn Ihre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Logik wird bereits als Steuerelement verpackt die `BuildWindowCore` Implementierung ist nicht viel mehr als einen Aufruf von `CreateWindow`. Um beispielsweise erstellen Sie eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX-Steuerelements in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:

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

Aber nehmen wir an der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Code ist nicht ganz so eigenständig? Wenn also, Sie erstellen, können eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld ein, und betten Sie seinen Inhalt in einem größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Das Beispiel zeigt dies [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], obwohl es auch möglich, dies in einer anderen Sprache oder in der Befehlszeile verwenden.

Beginnen Sie mit einem einfachen Dialogfeld, das in kompiliert wird eine [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] Projekt.

Platzieren Sie das Dialogfeld in den größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung:

- Kompilieren Sie die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] als verwaltet (`/clr`)

- Aktivieren Sie das Dialogfeld, in ein Steuerelement

- Definieren Sie die abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> mit `BuildWindowCore` und `DestroyWindowCore` Methoden

- Außer Kraft setzen `TranslateAccelerator` Methode zum Behandeln von Tastatureingaben im Dialogfeld

- Außer Kraft setzen `TabInto` -Methode zur Unterstützung der TAB-Taste

- Außer Kraft setzen `OnMnemonic` Methode, um Zugriffstasten unterstützt werden.

- Instanziieren der <xref:System.Windows.Interop.HwndHost> Unterklasse und platzieren Sie es unter dem richtigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element

### <a name="turn-the-dialog-into-a-control"></a>Aktivieren Sie das Dialogfeld, in ein Steuerelement

Sie können ein Dialogfeld, das in eine untergeordnete HWND mithilfe der WS_CHILD und DS_CONTROL-Stile aktivieren. Wechseln Sie in der Ressourcendatei (.rc), in das Dialogfeld "definiert ist, und suchen Sie den Anfang der Definition des Dialogfelds:

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

Ändern Sie die zweite Zeile hinzu:

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

Diese Aktion Paketen nicht vollständig es in ein Steuerelement eigenständigen; Sie benötigen zum Aufrufen `IsDialogMessage()` damit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] bestimmte Nachrichten verarbeiten kann, aber die Änderung des Steuerelements bietet eine einfache Möglichkeit zum Einfügen von diesen Steuerelementen in einem anderen HWND.

## <a name="subclass-hwndhost"></a>HwndHost-Unterklasse

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

Erstellen Sie dann auf eine abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> und überschreiben die `BuildWindowCore` und `DestroyWindowCore` Methoden:

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

Hier verwenden Sie die `CreateDialog` um das Dialogfeld zu erstellen, die eigentlich ein Steuerelement ist. Da dies eine der ersten Methoden aufgerufen ist die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], gehen Sie genauso einige Standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Initialisierung durch Aufrufen einer Funktion, die Sie später definieren wird aufgerufen, `InitializeGlobals()`:

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>Überschreiben Sie TranslateAccelerator-Methode, um das Dialogfeld-Schlüssel behandelt

Wenn Sie dieses Beispiel ausgeführt wurde, erhalten Sie ein Dialogfeldsteuerelement, das anzeigt, aber es würde Tastatureingaben verarbeiten, wird ein Dialogfeld ein Dialogfeld für die funktionale ignorieren. Sollten Sie jetzt überschreiben die `TranslateAccelerator` Implementierung (Dies ist aus `IKeyboardInputSink`, eine Schnittstelle, die <xref:System.Windows.Interop.HwndHost> implementiert). Diese Methode wird aufgerufen, wenn die Anwendung WM_KEYDOWN und WM_SYSKEYDOWN empfängt.

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

Dies ist viel Code in einem Stück, damit sie einige ausführlicheren Erklärungen verwenden kann. Zunächst wird der Code mit [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] Makros; Sie müssen bedenken, dass es bereits ein Makro, das mit dem Namen ist `TranslateAccelerator`, der in winuser.h definiert ist:

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

Achten Sie also zum Definieren einer `TranslateAccelerator` Methode und keine `TranslateAcceleratorW` Methode.

Auf ähnliche Weise vorhanden ist, die nicht verwaltete winuser.h Meldung und die verwaltete `Microsoft::Win32::MSG` Struktur. Eindeutig zu machen, zwischen den beiden mit dem [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` Operator.

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

Zurück zum `TranslateAccelerator`. Das Grundprinzip ist zum Aufrufen der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Funktion `IsDialogMessage` so viele Verarbeitungen wie möglich zu tun, aber `IsDialogMessage` hat keinen Zugriff auf irgendetwas außerhalb des Dialogfelds. Während eine Benutzer-Registerkarte, um das Dialogfeld, wenn die TAB-Taste direkt hinter das letzte Steuerelement in unser Dialogfeld ausgeführt wird, müssen Sie den Fokus festgelegt werden, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil durch Aufrufen von `IKeyboardInputSite::OnNoMoreStops`.

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

Rufen Sie abschließend `IsDialogMessage` auf. Aber zu den Aufgaben von einem `TranslateAccelerator` Methode teilt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt an, ob die Tastatureingabe oder nicht behandelt. Wenn Sie es nicht verarbeitet hat, kann das Eingabeereignis Tunneln und bubblen in der Rest der Anwendung. Sie werden hier der verfügbar machen, eine Eigenart von Messange Tastaturbehandlung und der Art der Eingabe-Architektur in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Leider `IsDialogMessage` gibt keine in keiner Weise zurück, ob es sich um eine bestimmte Tastatureingabe behandelt. Schlimmer noch, er ruft `DispatchMessage()` Tastatureingaben nicht behandelt werden muss.  Daher Sie die Reverse-Engineering müssen `IsDialogMessage`, und ihn nur aufrufen, für die Schlüssel, die Sie wissen es behandelt:

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

### <a name="override-tabinto-method-to-support-tabbing"></a>Überschreiben Sie TabInto-Methode, um Unterstützung für TAB-Taste

Nun, da Sie implementiert haben `TranslateAccelerator`, Benutzer kann auf tab-Taste im Dialogfeld im Feld und den Wechsel in die größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Aber ein Benutzer kann nicht wieder in das Dialogfeld Registerkarte. Um dieses Problem Sie außer Kraft setzen `TabInto`:

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

Die `TraversalRequest` -Parameter erfahren Sie, ob die Tab-Aktion auf einer Registerkarte oder UMSCHALT ist.

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Überschreiben Sie OnMnemonic-Methode, um Zugriffstasten unterstützt werden.

Tastaturbehandlung ist fast abgeschlossen, aber es gibt ein, was fehlt: mnemonischen Code des funktionieren nicht. Wenn ein Benutzer Alt + F drücken, springt Doe der Fokus nicht auf die "First Name:" "Bearbeiten". Überschreiben Sie daher die `OnMnemonic` Methode:

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

Warum nicht aufrufen `IsDialogMessage` hier?  Wie zuvor – Sie darüber zu informieren können müssen, müssen Sie das gleiche Problem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code, ob Ihr Code die Tastatureingabe oder nicht behandelt und `IsDialogMessage` nicht. Es gibt auch ein zweites Problem, da `IsDialogMessage` verweigert das mnemonische Zeichen verarbeitet, wenn das fokussierte HWND nicht innerhalb des Dialogfelds ist.

### <a name="instantiate-the-hwndhost-derived-class"></a>Instanziieren der HwndHost abgeleitete Klasse

Nun, dass alle Schlüssel und die Registerkarte Unterstützung vorhanden ist, Sie können schließlich Ihre <xref:System.Windows.Interop.HwndHost> in den größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung. Wenn die Hauptassembly der Anwendung, im geschrieben wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ist die einfachste Möglichkeit, die sie in der richtigen Stelle platzieren lassen Sie eine leere <xref:System.Windows.Controls.Border> Element eingefügt werden sollen die <xref:System.Windows.Interop.HwndHost>. Hier erstellen Sie eine <xref:System.Windows.Controls.Border> mit dem Namen `insertHwndHostHere`:

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

Dann bleibt, besteht darin, einen guten Ausgangspunkt in Codesequenz instanziiert finden die <xref:System.Windows.Interop.HwndHost> und eine Verbindung mit der <xref:System.Windows.Controls.Border>. In diesem Beispiel fügen Sie ihn in den Konstruktor für die <xref:System.Windows.Window> abgeleitete Klasse:

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

So erhalten Sie:

![Screenshot der WPF-Anwendung](./media/interoparch09.PNG "InteropArch09")

## <a name="see-also"></a>Siehe auch

- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
