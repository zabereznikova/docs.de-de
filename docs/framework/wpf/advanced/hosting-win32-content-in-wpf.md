---
title: Hosten von Win32-Inhalt in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: 9764b995cea0ba5c93625495509b7ee2dd8393ff
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370032"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="a7687-102">Hosten von Win32-Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="a7687-102">Hosting Win32 Content in WPF</span></span>
## <a name="prerequisites"></a><span data-ttu-id="a7687-103">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="a7687-103">Prerequisites</span></span>  
 <span data-ttu-id="a7687-104">Finden Sie unter [WPF und Win32-Interoperation](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="a7687-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="a7687-105">Eine exemplarische Vorgehensweise für Win32, Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="a7687-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>  
 <span data-ttu-id="a7687-106">Wiederverwenden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Inhalte innerhalb von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen verwenden <xref:System.Windows.Interop.HwndHost>, d.h. ein Steuerelement, mit der HWNDs aussehen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt.</span><span class="sxs-lookup"><span data-stu-id="a7687-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>  <span data-ttu-id="a7687-107">Wie <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> ist einfach zu verwenden: leiten Sie von <xref:System.Windows.Interop.HwndHost> und implementieren `BuildWindowCore` und `DestroyWindowCore` Methoden instanziieren, klicken Sie dann Ihre <xref:System.Windows.Interop.HwndHost> abgeleiteten Klasse ein, und platzieren Sie ihn in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a7687-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  
  
 <span data-ttu-id="a7687-108">Wenn Ihre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Logik wird bereits als Steuerelement verpackt die `BuildWindowCore` Implementierung ist nicht viel mehr als einen Aufruf von `CreateWindow`.</span><span class="sxs-lookup"><span data-stu-id="a7687-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span>  <span data-ttu-id="a7687-109">Um beispielsweise erstellen Sie eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX-Steuerelements in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="a7687-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span></span>  
  
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
  
 <span data-ttu-id="a7687-110">Aber nehmen wir an der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Code ist nicht ganz so eigenständig?</span><span class="sxs-lookup"><span data-stu-id="a7687-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="a7687-111">Wenn also, Sie erstellen, können eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld ein, und betten Sie seinen Inhalt in einem größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a7687-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="a7687-112">Das Beispiel zeigt dies [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], obwohl es auch möglich, dies in einer anderen Sprache oder in der Befehlszeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7687-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], although it is also possible to do this in a different language or at the command line.</span></span>  
  
 <span data-ttu-id="a7687-113">Beginnen Sie mit einem einfachen Dialogfeld, das in kompiliert wird eine [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="a7687-113">Start with a simple dialog, which is compiled into a [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>  
  
 <span data-ttu-id="a7687-114">Platzieren Sie das Dialogfeld in den größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung:</span><span class="sxs-lookup"><span data-stu-id="a7687-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>  
  
-   <span data-ttu-id="a7687-115">Kompilieren Sie die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] als verwaltet (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="a7687-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>  
  
-   <span data-ttu-id="a7687-116">Aktivieren Sie das Dialogfeld, in ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a7687-116">Turn the dialog into a control</span></span>  
  
-   <span data-ttu-id="a7687-117">Definieren Sie die abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> mit `BuildWindowCore` und `DestroyWindowCore` Methoden</span><span class="sxs-lookup"><span data-stu-id="a7687-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>  
  
-   <span data-ttu-id="a7687-118">Außer Kraft setzen `TranslateAccelerator` Methode zum Behandeln von Tastatureingaben im Dialogfeld</span><span class="sxs-lookup"><span data-stu-id="a7687-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>  
  
-   <span data-ttu-id="a7687-119">Außer Kraft setzen `TabInto` -Methode zur Unterstützung der TAB-Taste</span><span class="sxs-lookup"><span data-stu-id="a7687-119">Override `TabInto` method to support tabbing</span></span>  
  
-   <span data-ttu-id="a7687-120">Außer Kraft setzen `OnMnemonic` Methode, um Zugriffstasten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a7687-120">Override `OnMnemonic` method to support mnemonics</span></span>  
  
-   <span data-ttu-id="a7687-121">Instanziieren der <xref:System.Windows.Interop.HwndHost> Unterklasse und platzieren Sie es unter dem richtigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element</span><span class="sxs-lookup"><span data-stu-id="a7687-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>  
  
### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="a7687-122">Aktivieren Sie das Dialogfeld, in ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="a7687-122">Turn the Dialog into a Control</span></span>  
 <span data-ttu-id="a7687-123">Sie können ein Dialogfeld, das in eine untergeordnete HWND mithilfe der WS_CHILD und DS_CONTROL-Stile aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a7687-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span>  <span data-ttu-id="a7687-124">Wechseln Sie in der Ressourcendatei (.rc), in das Dialogfeld "definiert ist, und suchen Sie den Anfang der Definition des Dialogfelds:</span><span class="sxs-lookup"><span data-stu-id="a7687-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 <span data-ttu-id="a7687-125">Ändern Sie die zweite Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="a7687-125">Change the second line to:</span></span>  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 <span data-ttu-id="a7687-126">Diese Aktion Paketen nicht vollständig es in ein Steuerelement eigenständigen; Sie benötigen zum Aufrufen `IsDialogMessage()` damit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] bestimmte Nachrichten verarbeiten kann, aber die Änderung des Steuerelements bietet eine einfache Möglichkeit zum Einfügen von diesen Steuerelementen in einem anderen HWND.</span><span class="sxs-lookup"><span data-stu-id="a7687-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>  
  
## <a name="subclass-hwndhost"></a><span data-ttu-id="a7687-127">HwndHost-Unterklasse</span><span class="sxs-lookup"><span data-stu-id="a7687-127">Subclass HwndHost</span></span>  
 <span data-ttu-id="a7687-128">Importieren Sie die folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="a7687-128">Import the following namespaces:</span></span>  
  
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
  
 <span data-ttu-id="a7687-129">Erstellen Sie dann auf eine abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> und überschreiben die `BuildWindowCore` und `DestroyWindowCore` Methoden:</span><span class="sxs-lookup"><span data-stu-id="a7687-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>  
  
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
  
 <span data-ttu-id="a7687-130">Hier verwenden Sie die `CreateDialog` um das Dialogfeld zu erstellen, die eigentlich ein Steuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="a7687-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span>  <span data-ttu-id="a7687-131">Da dies eine der ersten Methoden aufgerufen ist die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], gehen Sie genauso einige Standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Initialisierung durch Aufrufen einer Funktion, die Sie später definieren wird aufgerufen, `InitializeGlobals()`:</span><span class="sxs-lookup"><span data-stu-id="a7687-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>  
  
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
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="a7687-132">Überschreiben Sie TranslateAccelerator-Methode, um das Dialogfeld-Schlüssel behandelt</span><span class="sxs-lookup"><span data-stu-id="a7687-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>  
 <span data-ttu-id="a7687-133">Wenn Sie dieses Beispiel ausgeführt wurde, erhalten Sie ein Dialogfeldsteuerelement, das anzeigt, aber es würde Tastatureingaben verarbeiten, wird ein Dialogfeld ein Dialogfeld für die funktionale ignorieren.</span><span class="sxs-lookup"><span data-stu-id="a7687-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span>  <span data-ttu-id="a7687-134">Sollten Sie jetzt überschreiben die `TranslateAccelerator` Implementierung (Dies ist aus `IKeyboardInputSink`, eine Schnittstelle, die <xref:System.Windows.Interop.HwndHost> implementiert).</span><span class="sxs-lookup"><span data-stu-id="a7687-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span>  <span data-ttu-id="a7687-135">Diese Methode wird aufgerufen, wenn die Anwendung WM_KEYDOWN und WM_SYSKEYDOWN empfängt.</span><span class="sxs-lookup"><span data-stu-id="a7687-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>  
  
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
  
 <span data-ttu-id="a7687-136">Dies ist viel Code in einem Stück, damit sie einige ausführlicheren Erklärungen verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="a7687-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span>  <span data-ttu-id="a7687-137">Zunächst wird der Code mit [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] Makros; Sie müssen bedenken, dass es bereits ein Makro, das mit dem Namen ist `TranslateAccelerator`, der in winuser.h definiert ist:</span><span class="sxs-lookup"><span data-stu-id="a7687-137">First, the code using [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 <span data-ttu-id="a7687-138">Achten Sie also zum Definieren einer `TranslateAccelerator` Methode und keine `TranslateAcceleratorW` Methode.</span><span class="sxs-lookup"><span data-stu-id="a7687-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>  
  
 <span data-ttu-id="a7687-139">Auf ähnliche Weise vorhanden ist, die nicht verwaltete winuser.h Meldung und die verwaltete `Microsoft::Win32::MSG` Struktur.</span><span class="sxs-lookup"><span data-stu-id="a7687-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span>  <span data-ttu-id="a7687-140">Eindeutig zu machen, zwischen den beiden mit dem [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` Operator.</span><span class="sxs-lookup"><span data-stu-id="a7687-140">You can disambiguate between the two using the [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operator.</span></span>  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 <span data-ttu-id="a7687-141">Sowohl Nachrichten haben die gleichen Daten, aber manchmal ist es einfacher, mit der Definition des nicht verwalteten zu arbeiten, sodass in diesem Beispiel Sie die offensichtliche Konvertierungsroutine definieren können:</span><span class="sxs-lookup"><span data-stu-id="a7687-141">Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:</span></span>  
  
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
  
 <span data-ttu-id="a7687-142">Zurück zum `TranslateAccelerator`.</span><span class="sxs-lookup"><span data-stu-id="a7687-142">Back to `TranslateAccelerator`.</span></span>  <span data-ttu-id="a7687-143">Das Grundprinzip ist zum Aufrufen der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Funktion `IsDialogMessage` so viele Verarbeitungen wie möglich zu tun, aber `IsDialogMessage` hat keinen Zugriff auf irgendetwas außerhalb des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="a7687-143">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="a7687-144">Während eine Benutzer-Registerkarte, um das Dialogfeld, wenn die TAB-Taste direkt hinter das letzte Steuerelement in unser Dialogfeld ausgeführt wird, müssen Sie den Fokus festgelegt werden, um die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil durch Aufrufen von `IKeyboardInputSite::OnNoMoreStops`.</span><span class="sxs-lookup"><span data-stu-id="a7687-144">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>  
  
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
  
 <span data-ttu-id="a7687-145">Rufen Sie abschließend `IsDialogMessage` auf.</span><span class="sxs-lookup"><span data-stu-id="a7687-145">Finally, call `IsDialogMessage`.</span></span>  <span data-ttu-id="a7687-146">Aber zu den Aufgaben von einem `TranslateAccelerator` Methode teilt [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt an, ob die Tastatureingabe oder nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="a7687-146">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="a7687-147">Wenn Sie es nicht verarbeitet hat, kann das Eingabeereignis Tunneln und bubblen in der Rest der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a7687-147">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="a7687-148">Sie werden hier der verfügbar machen, eine Eigenart von Messange Tastaturbehandlung und der Art der Eingabe-Architektur in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a7687-148">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="a7687-149">Leider `IsDialogMessage` gibt keine in keiner Weise zurück, ob es sich um eine bestimmte Tastatureingabe behandelt.</span><span class="sxs-lookup"><span data-stu-id="a7687-149">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span>  <span data-ttu-id="a7687-150">Schlimmer noch, er ruft `DispatchMessage()` Tastatureingaben nicht behandelt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a7687-150">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="a7687-151">Daher Sie die Reverse-Engineering müssen `IsDialogMessage`, und ihn nur aufrufen, für die Schlüssel, die Sie wissen es behandelt:</span><span class="sxs-lookup"><span data-stu-id="a7687-151">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>  
  
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
  
### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="a7687-152">Überschreiben Sie TabInto-Methode, um Unterstützung für TAB-Taste</span><span class="sxs-lookup"><span data-stu-id="a7687-152">Override TabInto Method to Support Tabbing</span></span>  
 <span data-ttu-id="a7687-153">Nun, da Sie implementiert haben `TranslateAccelerator`, Benutzer kann auf tab-Taste im Dialogfeld im Feld und den Wechsel in die größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a7687-153">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="a7687-154">Aber ein Benutzer kann nicht wieder in das Dialogfeld Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="a7687-154">But a user cannot tab back into the dialog box.</span></span>  <span data-ttu-id="a7687-155">Um dieses Problem Sie außer Kraft setzen `TabInto`:</span><span class="sxs-lookup"><span data-stu-id="a7687-155">To solve that, you override `TabInto`:</span></span>  
  
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
  
 <span data-ttu-id="a7687-156">Die `TraversalRequest` -Parameter erfahren Sie, ob die Tab-Aktion auf einer Registerkarte oder UMSCHALT ist.</span><span class="sxs-lookup"><span data-stu-id="a7687-156">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="a7687-157">Überschreiben Sie OnMnemonic-Methode, um Zugriffstasten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="a7687-157">Override OnMnemonic Method to Support Mnemonics</span></span>  
 <span data-ttu-id="a7687-158">Tastaturbehandlung ist fast abgeschlossen, aber es gibt ein, was fehlt: mnemonischen Code des funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="a7687-158">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span>  <span data-ttu-id="a7687-159">Wenn ein Benutzer Alt + F drücken, springt Doe der Fokus nicht auf die "First Name:" "Bearbeiten".</span><span class="sxs-lookup"><span data-stu-id="a7687-159">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="a7687-160">Überschreiben Sie daher die `OnMnemonic` Methode:</span><span class="sxs-lookup"><span data-stu-id="a7687-160">So, you override the `OnMnemonic` method:</span></span>  
  
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
  
 <span data-ttu-id="a7687-161">Warum nicht aufrufen `IsDialogMessage` hier?</span><span class="sxs-lookup"><span data-stu-id="a7687-161">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="a7687-162">Wie zuvor – Sie darüber zu informieren können müssen, müssen Sie das gleiche Problem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code, ob Ihr Code die Tastatureingabe oder nicht behandelt und `IsDialogMessage` nicht.</span><span class="sxs-lookup"><span data-stu-id="a7687-162">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span>  <span data-ttu-id="a7687-163">Es gibt auch ein zweites Problem, da `IsDialogMessage` verweigert das mnemonische Zeichen verarbeitet, wenn das fokussierte HWND nicht innerhalb des Dialogfelds ist.</span><span class="sxs-lookup"><span data-stu-id="a7687-163">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>  
  
### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="a7687-164">Instanziieren der HwndHost abgeleitete Klasse</span><span class="sxs-lookup"><span data-stu-id="a7687-164">Instantiate the HwndHost Derived Class</span></span>  
 <span data-ttu-id="a7687-165">Nun, dass alle Schlüssel und die Registerkarte Unterstützung vorhanden ist, Sie können schließlich Ihre <xref:System.Windows.Interop.HwndHost> in den größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a7687-165">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="a7687-166">Wenn die Hauptassembly der Anwendung, im geschrieben wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], ist die einfachste Möglichkeit, die sie in der richtigen Stelle platzieren lassen Sie eine leere <xref:System.Windows.Controls.Border> Element eingefügt werden sollen die <xref:System.Windows.Interop.HwndHost>.</span><span class="sxs-lookup"><span data-stu-id="a7687-166">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span>  <span data-ttu-id="a7687-167">Hier erstellen Sie eine <xref:System.Windows.Controls.Border> mit dem Namen `insertHwndHostHere`:</span><span class="sxs-lookup"><span data-stu-id="a7687-167">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>  
  
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
  
 <span data-ttu-id="a7687-168">Dann bleibt, besteht darin, einen guten Ausgangspunkt in Codesequenz instanziiert finden die <xref:System.Windows.Interop.HwndHost> und eine Verbindung mit der <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="a7687-168">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span>  <span data-ttu-id="a7687-169">In diesem Beispiel fügen Sie ihn in den Konstruktor für die <xref:System.Windows.Window> abgeleitete Klasse:</span><span class="sxs-lookup"><span data-stu-id="a7687-169">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>  
  
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
  
 <span data-ttu-id="a7687-170">So erhalten Sie:</span><span class="sxs-lookup"><span data-stu-id="a7687-170">Which gives you:</span></span>  
  
 <span data-ttu-id="a7687-171">![WPF-Anwendung Screenshot](./media/interoparch09.PNG "InteropArch09")</span><span class="sxs-lookup"><span data-stu-id="a7687-171">![WPF application screen shot](./media/interoparch09.PNG "InteropArch09")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7687-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7687-172">See also</span></span>
- [<span data-ttu-id="a7687-173">Interaktion zwischen WPF und Win32</span><span class="sxs-lookup"><span data-stu-id="a7687-173">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
