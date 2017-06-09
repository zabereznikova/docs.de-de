---
title: "Hosten von Win32-Inhalt in WPF | Microsoft Docs"
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
  - "Interoperabilität [WPF], Lernprogramme"
  - "Interoperabilität [WPF], Win32"
  - "Win32-Code, WPF-Interoperation"
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Hosten von Win32-Inhalt in WPF
## Vorbereitungsmaßnahmen  
 Weitere Informationen finden Sie unter [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).  
  
## Beispiel für Win32\-Inhalte im Windows Presentation Framework \(HwndHost\)  
 Wenn Sie [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Inhalte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendungen wiederverwenden möchten, verwenden Sie <xref:System.Windows.Interop.HwndHost>. Durch dieses Steuerelement werden HWNDs wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Inhalte dargestellt.  Wie <xref:System.Windows.Interop.HwndSource> ist auch <xref:System.Windows.Interop.HwndHost> unkompliziert zu verwenden: Leiten Sie von <xref:System.Windows.Interop.HwndHost> ab, implementieren Sie die `BuildWindowCore`\-Methode und die `DestroyWindowCore`\-Methode, instanziieren Sie dann die von <xref:System.Windows.Interop.HwndHost> abgeleitete Klasse, und platzieren Sie sie in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung.  
  
 Falls Ihre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Logik bereits als Steuerelement verpackt wurde, besteht die `BuildWindowCore`\-Implementierung im Grunde nur aus einem Aufruf an `CreateWindow`.  So erstellen Sie zum Beispiel ein [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-LISTBOX\-Steuerelement in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:  
  
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
  
 Was geschieht jedoch, wenn der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Code nicht ganz in sich abgeschlossen ist?  In diesem Fall können Sie ein [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Dialogfeld erstellen und seinen Inhalt in eine größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung einbetten.  Im Beispiel wird Code aus [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] gezeigt, Sie können jedoch auch eine andere Sprache oder die Befehlszeile verwenden.  
  
 Beginnen Sie mit einem einfachen Dialogfeld, das in ein [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]\-[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]\-Projekt kompiliert wird.  
  
 Platzieren Sie das Dialogfeld dann in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung:  
  
-   Kompilieren Sie die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] als verwaltet \(`/clr`\).  
  
-   Konvertieren Sie das Dialogfeld in ein Steuerelement.  
  
-   Definieren Sie die abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> mit der `BuildWindowCore`\-Methode und mit der `DestroyWindowCore`\-Methode.  
  
-   Überschreiben Sie die `TranslateAccelerator`\-Methode, damit Tastatureingaben im Dialogfeld verarbeitet werden können.  
  
-   Überschreiben Sie die `TabInto`\-Methode, damit das Wechseln mit der TAB\-TASTE unterstützt wird.  
  
-   Überschreiben Sie die `OnMnemonic`\-Methode, damit Zugriffstasten unterstützt werden.  
  
-   Instanziieren Sie die <xref:System.Windows.Interop.HwndHost>\-Unterklasse, und platzieren Sie sie unter dem richtigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Element.  
  
### Konvertieren des Dialogfelds in ein Steuerelement  
 Sie können ein Dialogfeld mit dem WS\_CHILD\-Stil und dem DS\_CONTROL\-Stil in ein untergeordnetes HWND konvertieren.  Öffnen Sie die Ressourcendatei \(.rc\), in der das Dialogfeld definiert ist, und suchen Sie den Anfang der Dialogfelddefinition:  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 Ändern Sie die zweite Zeile folgendermaßen:  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 Hierdurch wird das Dialogfeld jedoch noch nicht ganz als abgeschlossenes Steuerelement verpackt. Sie müssen noch `IsDialogMessage()` aufrufen, damit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] bestimmte Nachrichten verarbeiten kann. Die Umwandlung in ein Steuerelement ist jedoch eine gute Möglichkeit, diese Steuerelemente in einem anderen HWND zu platzieren.  
  
## HwndHost\-Unterklasse  
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
  
 Erstellen Sie dann eine abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost>, und überschreiben Sie die `BuildWindowCore`\-Methode und die `DestroyWindowCore`\-Methode:  
  
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
  
 An dieser Stelle verwenden Sie `CreateDialog`, um das Dialogfeld zu erstellen, das eigentlich ein Steuerelement ist.  Da dies eine der ersten in der [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] aufgerufenen Methoden ist, sollte auch eine gewisse Standard\-[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Initialisierung erfolgen. Hierfür wird die `InitializeGlobals()`\-Funktion aufgerufen, die Sie erst später definieren:  
  
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
  
### Überschreiben der TranslateAccelerator\-Methode zum Verarbeiten von Tastatureingaben im Dialogfeld  
 Wenn Sie das Beispiel jetzt ausführen, erhalten Sie ein Dialogfeldsteuerelement, das zwar angezeigt wird, aber auf keine Tastatureingaben reagiert, durch die ein Dialogfeld zu einem funktionierenden Dialogfeld wird.  Daher sollten Sie jetzt die `TranslateAccelerator`\-Implementierung überschreiben \(die von `IKeyboardInputSink`, einer von <xref:System.Windows.Interop.HwndHost> implementierten Schnittstelle, stammt\).  Diese Methode wird aufgerufen, wenn die Anwendung WM\_KEYDOWN und WM\_SYSKEYDOWN empfängt.  
  
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
  
 Dieser große Codeabschnitt bedarf wohl noch einiger Erklärungen.  Zunächst zum Code, in dem ein [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]\-Makro und ein [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]\-Makro verwendet werden. Sie müssen sich dabei bewusst sein, dass es bereits ein in winuser.h definiertes `TranslateAccelerator`\-Makro gibt:  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 Definieren Sie daher auf alle Fälle eine `TranslateAccelerator`\-Methode und keine `TranslateAcceleratorW`\-Methode.  
  
 Ebenso gibt es die nicht verwaltete winuser.h\-MSG\-Struktur und die verwaltete `Microsoft::Win32::MSG`\-Struktur.  Sie können die beiden mithilfe des [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]\-Operators `::` eindeutig machen.  
  
```  
  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 Beide MSGs weisen die gleichen Daten auf, gelegentlich fällt die Arbeit mit der nicht verwalteten Definition jedoch leichter, daher können Sie in diesem Beispiel die offensichtliche Konvertierungsroutine definieren:  
  
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
  
 Und nun zurück zu `TranslateAccelerator`.  Das Grundprinzip besteht darin, die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]\-Funktion `IsDialogMessage` aufzurufen und so viel Arbeit wie möglich erledigen zu lassen. `IsDialogMessage` kann jedoch nicht auf Elemente außerhalb des Dialogfelds zugreifen. Wenn Benutzer beim Navigieren im Dialogfeld mit der TAB\-TASTE über das letzte Steuerelement im Dialogfeld hinausspringen, muss der Fokus durch Aufrufen von `IKeyboardInputSite::OnNoMoreStops` auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-seitigen Teil gerichtet werden.  
  
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
  
 Rufen Sie abschließend `IsDialogMessage` auf.  Eine der Aufgaben der `TranslateAccelerator`\-Methode besteht darin, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] darüber zu informieren, ob die Tastatureingabe behandelt wurde oder nicht.  Wurde sie nicht behandelt, kann das Eingabeereignis die übrige Anwendung abwärts oder aufwärts durchlaufen.  An dieser Stelle werden eine Eigenart der Behandlung von Tastaturmeldungen sowie die Beschaffenheit der Eingabearchitektur in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] deutlich.  `IsDialogMessage` gibt keinerlei Informationen darüber zurück, ob eine bestimmte Tastatureingabe behandelt wird.  Und noch schlimmer: Die Funktion ruft `DispatchMessage()` sogar bei Tastatureingaben auf, die sie gar nicht behandeln sollte\!  Daher müssen Sie `IsDialogMessage` zurückentwickeln, sodass die Funktion nur bei Eingaben aufgerufen wird, die sie behandeln soll:  
  
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
  
### Überschreiben der TabInto\-Methode zur Unterstützung des Wechsels mit der TAB\-TASTE  
 Nachdem `TranslateAccelerator` implementiert wurde, können sich Benutzer mit der TAB\-TASTE durch das Dialogfeld bewegen und in die größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung wechseln.  Eine Rückkehr in das Dialogfeld mit der TAB\-TASTE ist jedoch nicht möglich.  Um dieses Problem zu lösen, überschreiben Sie `TabInto`:  
  
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
  
 Über den `TraversalRequest`\-Parameter erfahren Sie, ob es sich bei der TAB\-Aktion um einen Wechsel mit TAB oder mit UMSCHALT\+TAB handelt.  
  
### Überschreiben der OnMnemonic\-Methode zur Unterstützung von Zugriffstasten  
 Die Behandlung von Tastatureingaben ist fast vollständig, allerdings funktionieren noch keine Zugriffstasten.  Wenn Benutzer die Tastenkombination ALT\+F drücken, springt der Fokus nicht zum Eingabefeld für den Vornamen.  Überschreiben Sie daher die `OnMnemonic`\-Methode:  
  
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
  
 Und warum wird an dieser Stelle nicht `IsDialogMessage` aufgerufen?  Weil immer noch das gleiche Problem besteht: Dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Code muss mitgeteilt werden, ob Ihr Code die Tastatureingabe behandelt hat. `IsDialogMessage` ist dazu nicht in der Lage.  Und es gibt noch ein weiteres Problem: `IsDialogMessage` verarbeitet das Tastenkürzel nur, wenn das fokussierte HWND im Dialogfeld liegt.  
  
### Instanziieren der von HwndHost abgeleiteten Klasse  
 Nachdem jetzt Tastatureingaben und TAB\-Wechsel unterstützt werden, können Sie <xref:System.Windows.Interop.HwndHost> in die größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Anwendung einfügen.  Falls die Hauptanwendung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] geschrieben ist, lässt sich die Platzierung an der richtigen Stelle am einfachsten dadurch vornehmen, dass Sie ein leeres <xref:System.Windows.Controls.Border>\-Element an der Stelle erstellen, an der <xref:System.Windows.Interop.HwndHost> eingefügt werden soll.  In diesem Fall erstellen Sie den <xref:System.Windows.Controls.Border> `insertHwndHostHere`:  
  
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
  
 Nun müssen Sie nur noch eine geeignete Stelle im Code finden, an der <xref:System.Windows.Interop.HwndHost> instanziiert und mit <xref:System.Windows.Controls.Border> verknüpft werden kann.  In diesem Beispiel erfolgt die Platzierung im Konstruktor für die abgeleitete <xref:System.Windows.Window>\-Klasse:  
  
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
  
 Und so erhalten Sie:  
  
 ![Bildschirmabbildung der WPF&#45;Anwendung](../../../../docs/framework/wpf/advanced/media/interoparch09.png "InteropArch09")  
  
## Siehe auch  
 [Interaktion zwischen WPF und Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)