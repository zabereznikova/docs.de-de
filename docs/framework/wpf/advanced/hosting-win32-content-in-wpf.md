---
title: Hosten von Win32-Inhalt in WPF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c92e5b045b248337f1cb96c333ac38f1228dd90
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="e3d9a-102">Hosten von Win32-Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="e3d9a-102">Hosting Win32 Content in WPF</span></span>
## <a name="prerequisites"></a><span data-ttu-id="e3d9a-103">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="e3d9a-103">Prerequisites</span></span>  
 <span data-ttu-id="e3d9a-104">Finden Sie unter [WPF und Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="e3d9a-104">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="e3d9a-105">Eine exemplarische Vorgehensweise zur Win32 in Windows PresentationFramework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="e3d9a-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>  
 <span data-ttu-id="e3d9a-106">Wiederverwenden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Inhalte innerhalb von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Anwendungen verwenden <xref:System.Windows.Interop.HwndHost>, dies ist ein Steuerelement, das Aussehen HWNDs macht [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>  <span data-ttu-id="e3d9a-107">Wie <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> ist einfach zu verwenden: Ableiten von <xref:System.Windows.Interop.HwndHost> und implementieren `BuildWindowCore` und `DestroyWindowCore` Methoden, instanziieren Sie dann Ihre <xref:System.Windows.Interop.HwndHost> abgeleitete Klasse, und platzieren Sie ihn in Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  
  
 <span data-ttu-id="e3d9a-108">Wenn Ihre [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Logik wird als ein Steuerelement bereits verpackt die `BuildWindowCore` Implementierung ist etwas mehr als ein Aufruf von `CreateWindow`.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span>  <span data-ttu-id="e3d9a-109">Z. B. zum Erstellen einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX-Steuerelement in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-110">Aber nehmen Sie an der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Code ist nicht ganz so geschlossene?</span><span class="sxs-lookup"><span data-stu-id="e3d9a-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="e3d9a-111">Wenn also, Sie erstellen, können eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Dialogfeld Feld und dessen Inhalt in einen größeren einbetten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="e3d9a-112">Das Beispiel zeigt dies in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], obwohl es auch möglich ist, dies in einer anderen Sprache oder in der Befehlszeile durchführen.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], although it is also possible to do this in a different language or at the command line.</span></span>  
  
 <span data-ttu-id="e3d9a-113">Beginnen Sie mit einem einfachen Dialogfeld, das kompiliert wird eine [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] Projekt.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-113">Start with a simple dialog, which is compiled into a [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>  
  
 <span data-ttu-id="e3d9a-114">Als Nächstes das Dialogfeld "in den größeren einführen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>  
  
-   <span data-ttu-id="e3d9a-115">Kompilieren Sie die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] als verwaltet (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="e3d9a-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>  
  
-   <span data-ttu-id="e3d9a-116">Aktivieren Sie das Dialogfeld "in ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e3d9a-116">Turn the dialog into a control</span></span>  
  
-   <span data-ttu-id="e3d9a-117">Definieren die abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> mit `BuildWindowCore` und `DestroyWindowCore` Methoden</span><span class="sxs-lookup"><span data-stu-id="e3d9a-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>  
  
-   <span data-ttu-id="e3d9a-118">Überschreiben Sie `TranslateAccelerator` Methode zum Behandeln von Tastatureingaben im Dialogfeld</span><span class="sxs-lookup"><span data-stu-id="e3d9a-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>  
  
-   <span data-ttu-id="e3d9a-119">Überschreiben Sie `TabInto` -Methode zur Unterstützung der TAB-Taste</span><span class="sxs-lookup"><span data-stu-id="e3d9a-119">Override `TabInto` method to support tabbing</span></span>  
  
-   <span data-ttu-id="e3d9a-120">Überschreiben Sie `OnMnemonic` Methode, um Zugriffstasten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-120">Override `OnMnemonic` method to support mnemonics</span></span>  
  
-   <span data-ttu-id="e3d9a-121">Instanziieren der <xref:System.Windows.Interop.HwndHost> Unterklasse und platzieren Sie es unter dem richtigen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element</span><span class="sxs-lookup"><span data-stu-id="e3d9a-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>  
  
### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="e3d9a-122">Aktivieren Sie das Dialogfeld "in ein Steuerelement</span><span class="sxs-lookup"><span data-stu-id="e3d9a-122">Turn the Dialog into a Control</span></span>  
 <span data-ttu-id="e3d9a-123">Sie können ein untergeordnetes Element unter Verwendung der Formatvorlagen WS_CHILD und DS_CONTROL HWND ein Dialogfeld verwandeln.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span>  <span data-ttu-id="e3d9a-124">Wechseln Sie in der Ressourcendatei (.rc), in das Dialogfeld "definiert ist, und suchen Sie den Anfang der Definition des Dialogs:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 <span data-ttu-id="e3d9a-125">Ändern Sie die zweite Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-125">Change the second line to:</span></span>  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 <span data-ttu-id="e3d9a-126">Diese Aktion ist nicht vollständig es in eine geschlossene Steuerelement Paket; müssen Sie dennoch aufrufen `IsDialogMessage()` damit [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] bestimmte Nachrichten verarbeiten kann, aber die Änderung Steuerelement bietet eine einfache Möglichkeit, diese Steuerelemente in einem anderen HWND einfügen.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>  
  
## <a name="subclass-hwndhost"></a><span data-ttu-id="e3d9a-127">HwndHost-Unterklasse</span><span class="sxs-lookup"><span data-stu-id="e3d9a-127">Subclass HwndHost</span></span>  
 <span data-ttu-id="e3d9a-128">Importieren Sie die folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-128">Import the following namespaces:</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-129">Erstellen Sie eine abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> und überschreiben die `BuildWindowCore` und `DestroyWindowCore` Methoden:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-130">Hier verwenden Sie die `CreateDialog` um das Dialogfeld zu erstellen, die eigentlich ein Steuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span>  <span data-ttu-id="e3d9a-131">Da dies eine der ersten Methoden aufgerufen wird die [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], ergreifen Sie auch einige Standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Initialisierung durch Aufrufen einer Funktion, die Sie später definieren aufgerufen `InitializeGlobals()`:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>  
  
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
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="e3d9a-132">Überschreiben Sie TranslateAccelerator-Methode, um das Dialogfeld Schlüssel behandelt.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>  
 <span data-ttu-id="e3d9a-133">Wenn Sie dieses Beispiel ausgeführt haben jetzt erhalten Sie ein Dialogfeldsteuerelement, das anzeigt, aber es würde ignorieren all die Tastatur verarbeiten, wird ein Dialogfeld eine funktionale (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="e3d9a-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span>  <span data-ttu-id="e3d9a-134">Sie sollten jetzt Überschreiben der `TranslateAccelerator` Implementierung (die stammen aus `IKeyboardInputSink`, eine Schnittstelle, die <xref:System.Windows.Interop.HwndHost> implementiert).</span><span class="sxs-lookup"><span data-stu-id="e3d9a-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span>  <span data-ttu-id="e3d9a-135">Diese Methode wird aufgerufen, wenn die Anwendung WM_KEYDOWN und WM_SYSKEYDOWN empfängt.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-136">Dies ist viel Code in einem Stück daher einige ausführlichen Erklärungen verwendet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span>  <span data-ttu-id="e3d9a-137">Zunächst wird der Code mit [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] und [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] Makros; Sie müssen sich bewusst sein, dass es bereits ein Makro mit dem Namen ist `TranslateAccelerator`, winuser.h definiert:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-137">First, the code using [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 <span data-ttu-id="e3d9a-138">Achten Sie also zum Definieren einer `TranslateAccelerator` Methode und keine `TranslateAcceleratorW` Methode.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>  
  
 <span data-ttu-id="e3d9a-139">Auf ähnliche Weise vorhanden ist, die nicht verwaltete winuser.h MSG und die verwaltete `Microsoft::Win32::MSG` Struktur.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span>  <span data-ttu-id="e3d9a-140">Sie können die Mehrdeutigkeit zwischen den beiden mit Aufheben der [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` Operator.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-140">You can disambiguate between the two using the [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operator.</span></span>  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 <span data-ttu-id="e3d9a-141">Sowohl Meld haben die gleichen Daten, aber manchmal ist es einfacher, mit der nicht verwalteten Definition zu arbeiten, damit in diesem Beispiel die offensichtliche Konvertierungsroutine zu definieren:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-141">Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-142">Zurück zur `TranslateAccelerator`.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-142">Back to `TranslateAccelerator`.</span></span>  <span data-ttu-id="e3d9a-143">Das grundlegende Prinzip ist das Aufrufen der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Funktion `IsDialogMessage` so viel Arbeit wie möglich, aber `IsDialogMessage` verfügt nicht über Zugriff auf alle Elemente außerhalb der Dialog.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-143">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="e3d9a-144">Während eine Registerkarte "Benutzer", um das Dialogfeld, wenn die TAB-Taste hinter das letzte Steuerelement unsere im Dialogfeld "ausgeführt wird, müssen Sie zum Festlegen des Fokus auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil durch Aufrufen von `IKeyboardInputSite::OnNoMoreStops`.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-144">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-145">Rufen Sie abschließend `IsDialogMessage` auf.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-145">Finally, call `IsDialogMessage`.</span></span>  <span data-ttu-id="e3d9a-146">Aber zu den Aufgaben von einer `TranslateAccelerator` mitteilen, Methode [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] gibt an, ob Sie die Tastatureingabe behandelt.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-146">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="e3d9a-147">Wenn Sie noch nicht verarbeitet hat, das Eingabeereignis kann getunnelt und Blasendiagramme über den Rest der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-147">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="e3d9a-148">Sie werden hier der verfügbar machen, eine Besonderheit der Messange Tastaturbehandlung sowie die Art der Eingabe-Architektur in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e3d9a-148">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="e3d9a-149">Leider `IsDialogMessage` gibt keinen in keiner Weise zurück, ob es sich um eine bestimmte Tastatureingabe behandelt.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-149">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span>  <span data-ttu-id="e3d9a-150">Noch schlimmer, er ruft `DispatchMessage()` auf Tastatureingaben nicht behandeln sollte!</span><span class="sxs-lookup"><span data-stu-id="e3d9a-150">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="e3d9a-151">Daher Sie die Rückentwicklung müssen `IsDialogMessage`, und rufen sie nur für die Sie wissen, dass sie Schlüssel behandelt:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-151">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>  
  
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
  
### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="e3d9a-152">Außer Kraft setzen Sie TabInto-Methode, um Unterstützung TAB-Taste</span><span class="sxs-lookup"><span data-stu-id="e3d9a-152">Override TabInto Method to Support Tabbing</span></span>  
 <span data-ttu-id="e3d9a-153">Nun, da Sie implementiert haben `TranslateAccelerator`, ein Benutzer kann in das Dialogfeld um Registerkarte und es in den größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-153">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="e3d9a-154">Aber ein Benutzer kann nicht wieder in das Dialogfeld Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-154">But a user cannot tab back into the dialog box.</span></span>  <span data-ttu-id="e3d9a-155">Zum lösen, die Sie außer Kraft setzen `TabInto`:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-155">To solve that, you override `TabInto`:</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-156">Die `TraversalRequest` Parameter sehen Sie, ob die Registerkarte Aktion eine Registerkarte oder UMSCHALT ist.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-156">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="e3d9a-157">Überschreiben Sie OnMnemonic-Methode, um Zugriffstasten unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-157">Override OnMnemonic Method to Support Mnemonics</span></span>  
 <span data-ttu-id="e3d9a-158">Tastaturbehandlung ist fast abgeschlossen, aber es ist eine Sache fehlt – Mnemonik funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-158">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span>  <span data-ttu-id="e3d9a-159">Wenn ein Benutzer die Alt-D drückt, den Fokus Doe nicht wechseln Sie zu der "First Name:" Eingabefeld.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-159">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="e3d9a-160">Überschreiben Sie daher die `OnMnemonic` Methode:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-160">So, you override the `OnMnemonic` method:</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-161">Warum nicht aufrufen `IsDialogMessage` hier?</span><span class="sxs-lookup"><span data-stu-id="e3d9a-161">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="e3d9a-162">Wie zuvor – Sie informieren können müssen, müssen Sie das gleiche Problem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code, ob Ihr Code die Tastatureingabe behandelt wurde oder nicht, und `IsDialogMessage` , die nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-162">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span>  <span data-ttu-id="e3d9a-163">Es gibt auch ein zweites Problem, da `IsDialogMessage` lehnt das mnemonische Zeichen zu verarbeiten, wenn das fokussierte HWND nicht innerhalb des Dialogfelds "" ist.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-163">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>  
  
### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="e3d9a-164">Instanziieren der HwndHost abgeleitete Klasse</span><span class="sxs-lookup"><span data-stu-id="e3d9a-164">Instantiate the HwndHost Derived Class</span></span>  
 <span data-ttu-id="e3d9a-165">Nun, dass sämtliche Unterstützung für die Schlüssel und die Registerkarte vorhanden ist, Sie können schließlich Ihr <xref:System.Windows.Interop.HwndHost> in den größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-165">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  <span data-ttu-id="e3d9a-166">Wenn die Hauptassembly der Anwendung, in geschrieben wird [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], die einfachste Möglichkeit, am richtigen Ort eingefügt werden soll, lassen Sie eine leere ist <xref:System.Windows.Controls.Border> Element, in dem Sie aufnehmen möchten, die <xref:System.Windows.Interop.HwndHost>.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-166">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span>  <span data-ttu-id="e3d9a-167">Hier erstellen Sie eine <xref:System.Windows.Controls.Border> mit dem Namen `insertHwndHostHere`:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-167">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-168">Dann alle bleibt suchen, ist eine gute im Code Instanziieren der <xref:System.Windows.Interop.HwndHost> und eine Verbindung mit der <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-168">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span>  <span data-ttu-id="e3d9a-169">In diesem Beispiel fügen Sie es in den Konstruktor für die <xref:System.Windows.Window> abgeleitete Klasse:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-169">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>  
  
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
  
 <span data-ttu-id="e3d9a-170">Dadurch können Sie:</span><span class="sxs-lookup"><span data-stu-id="e3d9a-170">Which gives you:</span></span>  
  
 <span data-ttu-id="e3d9a-171">![WPF-Anwendung Screenshot](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")</span><span class="sxs-lookup"><span data-stu-id="e3d9a-171">![WPF application screen shot](../../../../docs/framework/wpf/advanced/media/interoparch09.PNG "InteropArch09")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d9a-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e3d9a-172">See Also</span></span>  
 [<span data-ttu-id="e3d9a-173">Interaktion zwischen WPF und Win32</span><span class="sxs-lookup"><span data-stu-id="e3d9a-173">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)
