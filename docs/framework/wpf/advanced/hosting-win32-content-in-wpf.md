---
title: Hosten von Win32-Inhalt in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: beb7d5e6e1f934b89bb7516eb7e9bbbaad696238
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-win32-content-in-wpf"></a>Hosten von Win32-Inhalt in WPF
## <a name="prerequisites"></a>Erforderliche Komponenten  
 Finden Sie unter [WPF und Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Eine exemplarische Vorgehensweise zur Win32 in Windows PresentationFramework (HwndHost)  
 Wiederverwenden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Inhalte innerhalb von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendungen verwenden <xref:System.Windows.Interop.HwndHost>, dies ist ein Steuerelement, das Aussehen HWNDs macht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt.  Wie <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> ist einfach zu verwenden: Ableiten von <xref:System.Windows.Interop.HwndHost> und implementieren `BuildWindowCore` und `DestroyWindowCore` Methoden, instanziieren Sie dann Ihre <xref:System.Windows.Interop.HwndHost> abgeleitete Klasse, und platzieren Sie ihn in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Anwendung.  
  
 Wenn Ihre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Logik wird als ein Steuerelement bereits verpackt die `BuildWindowCore` Implementierung ist etwas mehr als ein Aufruf von `CreateWindow`.  Z. B. zum Erstellen einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX-Steuerelement in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:  
  
```  
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
  
 Aber nehmen Sie an der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Code ist nicht ganz so geschlossene? Wenn also, Sie erstellen, können eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld Feld und dessen Inhalt in einen größeren einbetten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.  Das Beispiel zeigt dies in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], obwohl es auch möglich ist, dies in einer anderen Sprache oder in der Befehlszeile durchführen.  
  
 Beginnen Sie mit einem einfachen Dialogfeld, das kompiliert wird eine [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] Projekt.  
  
 Als Nächstes das Dialogfeld "in den größeren einführen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung:  
  
-   Kompilieren Sie die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] als verwaltet (`/clr`)  
  
-   Aktivieren Sie das Dialogfeld "in ein Steuerelement  
  
-   Definieren die abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> mit `BuildWindowCore` und `DestroyWindowCore` Methoden  
  
-   Überschreiben Sie `TranslateAccelerator` Methode zum Behandeln von Tastatureingaben im Dialogfeld  
  
-   Überschreiben Sie `TabInto` -Methode zur Unterstützung der TAB-Taste  
  
-   Überschreiben Sie `OnMnemonic` Methode, um Zugriffstasten unterstützt werden.  
  
-   Instanziieren der <xref:System.Windows.Interop.HwndHost> Unterklasse und platzieren Sie es unter dem richtigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element  
  
### <a name="turn-the-dialog-into-a-control"></a>Aktivieren Sie das Dialogfeld "in ein Steuerelement  
 Sie können ein untergeordnetes Element unter Verwendung der Formatvorlagen WS_CHILD und DS_CONTROL HWND ein Dialogfeld verwandeln.  Wechseln Sie in der Ressourcendatei (.rc), in das Dialogfeld "definiert ist, und suchen Sie den Anfang der Definition des Dialogs:  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 Ändern Sie die zweite Zeile hinzu:  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 Diese Aktion ist nicht vollständig es in eine geschlossene Steuerelement Paket; müssen Sie dennoch aufrufen `IsDialogMessage()` damit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] bestimmte Nachrichten verarbeiten kann, aber die Änderung Steuerelement bietet eine einfache Möglichkeit, diese Steuerelemente in einem anderen HWND einfügen.  
  
## <a name="subclass-hwndhost"></a>HwndHost-Unterklasse  
 Importieren Sie die folgenden Namespaces:  
  
```  
namespace ManagedCpp  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Input;  
    using namespace System::Windows::Media;  
    using namespace System::Runtime::InteropServices;  
```  
  
 Erstellen Sie eine abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> und überschreiben die `BuildWindowCore` und `DestroyWindowCore` Methoden:  
  
```  
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
  
 Hier verwenden Sie die `CreateDialog` um das Dialogfeld zu erstellen, die eigentlich ein Steuerelement ist.  Da dies eine der ersten Methoden aufgerufen wird die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], ergreifen Sie auch einige Standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Initialisierung durch Aufrufen einer Funktion, die Sie später definieren aufgerufen `InitializeGlobals()`:  
  
```  
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
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>Überschreiben Sie TranslateAccelerator-Methode, um das Dialogfeld Schlüssel behandelt.  
 Wenn Sie dieses Beispiel ausgeführt haben jetzt erhalten Sie ein Dialogfeldsteuerelement, das anzeigt, aber es würde ignorieren all die Tastatur verarbeiten, wird ein Dialogfeld eine funktionale (Dialogfeld).  Sie sollten jetzt Überschreiben der `TranslateAccelerator` Implementierung (die stammen aus `IKeyboardInputSink`, eine Schnittstelle, die <xref:System.Windows.Interop.HwndHost> implementiert).  Diese Methode wird aufgerufen, wenn die Anwendung WM_KEYDOWN und WM_SYSKEYDOWN empfängt.  
  
```  
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
  
 Dies ist viel Code in einem Stück daher einige ausführlichen Erklärungen verwendet werden konnte.  Zunächst wird der Code mit [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] Makros; Sie müssen sich bewusst sein, dass es bereits ein Makro mit dem Namen ist `TranslateAccelerator`, winuser.h definiert:  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 Achten Sie also zum Definieren einer `TranslateAccelerator` Methode und keine `TranslateAcceleratorW` Methode.  
  
 Auf ähnliche Weise vorhanden ist, die nicht verwaltete winuser.h MSG und die verwaltete `Microsoft::Win32::MSG` Struktur.  Sie können die Mehrdeutigkeit zwischen den beiden mit Aufheben der [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` Operator.  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 Sowohl Meld haben die gleichen Daten, aber manchmal ist es einfacher, mit der nicht verwalteten Definition zu arbeiten, damit in diesem Beispiel die offensichtliche Konvertierungsroutine zu definieren:  
  
```  
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
  
 Zurück zur `TranslateAccelerator`.  Das grundlegende Prinzip ist das Aufrufen der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Funktion `IsDialogMessage` so viel Arbeit wie möglich, aber `IsDialogMessage` verfügt nicht über Zugriff auf alle Elemente außerhalb der Dialog. Während eine Registerkarte "Benutzer", um das Dialogfeld, wenn die TAB-Taste hinter das letzte Steuerelement unsere im Dialogfeld "ausgeführt wird, müssen Sie zum Festlegen des Fokus auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil durch Aufrufen von `IKeyboardInputSite::OnNoMoreStops`.  
  
```  
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
  
 Rufen Sie abschließend `IsDialogMessage` auf.  Aber zu den Aufgaben von einer `TranslateAccelerator` mitteilen, Methode [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt an, ob Sie die Tastatureingabe behandelt. Wenn Sie noch nicht verarbeitet hat, das Eingabeereignis kann getunnelt und Blasendiagramme über den Rest der Anwendung. Sie werden hier der verfügbar machen, eine Besonderheit der Messange Tastaturbehandlung sowie die Art der Eingabe-Architektur in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Leider `IsDialogMessage` gibt keinen in keiner Weise zurück, ob es sich um eine bestimmte Tastatureingabe behandelt.  Noch schlimmer, er ruft `DispatchMessage()` auf Tastatureingaben nicht behandeln sollte!  Daher Sie die Rückentwicklung müssen `IsDialogMessage`, und rufen sie nur für die Sie wissen, dass sie Schlüssel behandelt:  
  
```  
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
  
### <a name="override-tabinto-method-to-support-tabbing"></a>Außer Kraft setzen Sie TabInto-Methode, um Unterstützung TAB-Taste  
 Nun, da Sie implementiert haben `TranslateAccelerator`, ein Benutzer kann in das Dialogfeld um Registerkarte und es in den größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.  Aber ein Benutzer kann nicht wieder in das Dialogfeld Registerkarte.  Zum lösen, die Sie außer Kraft setzen `TabInto`:  
  
```  
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
  
 Die `TraversalRequest` Parameter sehen Sie, ob die Registerkarte Aktion eine Registerkarte oder UMSCHALT ist.  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a>Überschreiben Sie OnMnemonic-Methode, um Zugriffstasten unterstützt werden.  
 Tastaturbehandlung ist fast abgeschlossen, aber es ist eine Sache fehlt – Mnemonik funktionieren nicht.  Wenn ein Benutzer die Alt-D drückt, den Fokus Doe nicht wechseln Sie zu der "First Name:" Eingabefeld. Überschreiben Sie daher die `OnMnemonic` Methode:  
  
```  
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
  
 Warum nicht aufrufen `IsDialogMessage` hier?  Wie zuvor – Sie informieren können müssen, müssen Sie das gleiche Problem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code, ob Ihr Code die Tastatureingabe behandelt wurde oder nicht, und `IsDialogMessage` , die nicht möglich.  Es gibt auch ein zweites Problem, da `IsDialogMessage` lehnt das mnemonische Zeichen zu verarbeiten, wenn das fokussierte HWND nicht innerhalb des Dialogfelds "" ist.  
  
### <a name="instantiate-the-hwndhost-derived-class"></a>Instanziieren der HwndHost abgeleitete Klasse  
 Nun, dass sämtliche Unterstützung für die Schlüssel und die Registerkarte vorhanden ist, Sie können schließlich Ihr <xref:System.Windows.Interop.HwndHost> in den größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.  Wenn die Hauptassembly der Anwendung, in geschrieben wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], die einfachste Möglichkeit, am richtigen Ort eingefügt werden soll, lassen Sie eine leere ist <xref:System.Windows.Controls.Border> Element, in dem Sie aufnehmen möchten, die <xref:System.Windows.Interop.HwndHost>.  Hier erstellen Sie eine <xref:System.Windows.Controls.Border> mit dem Namen `insertHwndHostHere`:  
  
```  
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
  
 Dann alle bleibt suchen, ist eine gute im Code Instanziieren der <xref:System.Windows.Interop.HwndHost> und eine Verbindung mit der <xref:System.Windows.Controls.Border>.  In diesem Beispiel fügen Sie es in den Konstruktor für die <xref:System.Windows.Window> abgeleitete Klasse:  
  
```  
public partial class Window1 : Window {  
    public Window1() {  
    }  
  
    void Window1_Loaded(object sender, RoutedEventArgs e) {  
        HwndHost host = new ManagedCpp.MyHwndHost();  
        insertHwndHostHere.Child = host;  
    }  
}  
```  
  
 Dadurch können Sie:  
  
 ![WPF-Anwendung Screenshot](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")  
  
## <a name="see-also"></a>Siehe auch  
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
