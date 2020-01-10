---
title: Hosten von Win32-Inhalt in WPF
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: a9d9de1f35375e48981f895d096e46fd501ef8ec
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740372"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="fd7ec-102">Hosten von Win32-Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="fd7ec-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fd7ec-103">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="fd7ec-103">Prerequisites</span></span>

<span data-ttu-id="fd7ec-104">Siehe [WPF-und Win32-Interoperation](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="fd7ec-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="fd7ec-105">Exemplarische Vorgehensweise von Win32 in Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="fd7ec-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="fd7ec-106">Um Win32-Inhalte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen wiederzuverwenden, verwenden Sie <xref:System.Windows.Interop.HwndHost>, bei dem es sich um ein Steuerelement handelt, mit dem HWNDs [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt aussehen.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-106">To reuse Win32 content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="fd7ec-107"><xref:System.Windows.Interop.HwndHost> ist wie <xref:System.Windows.Interop.HwndSource>einfach zu verwenden: leiten Sie von <xref:System.Windows.Interop.HwndHost> ab, implementieren Sie `BuildWindowCore` und `DestroyWindowCore` Methoden, instanziieren Sie Ihre <xref:System.Windows.Interop.HwndHost> abgeleitete Klasse, und platzieren Sie Sie in ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="fd7ec-108">Wenn die Win32-Logik bereits als Steuerelement gepackt ist, ist die `BuildWindowCore` Implementierung kaum mehr als ein `CreateWindow`.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-108">If your Win32 logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="fd7ec-109">So erstellen Sie z. b. ein Win32-ListBox-Steuerelement in C++:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-109">For example, to create a Win32 LISTBOX control in C++:</span></span>

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

<span data-ttu-id="fd7ec-110">Angenommen, der Win32-Code ist nicht ganz so eigenständig?</span><span class="sxs-lookup"><span data-stu-id="fd7ec-110">But suppose the Win32 code is not quite so self-contained?</span></span> <span data-ttu-id="fd7ec-111">Wenn dies der Fall ist, können Sie ein Win32-Dialogfeld erstellen und seinen Inhalt in eine größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung einbetten.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-111">If so, you can create a Win32 dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="fd7ec-112">Das Beispiel zeigt dies in Visual Studio und C++, auch wenn es möglich ist, dies in einer anderen Sprache oder in der Befehlszeile zu tun.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-112">The sample shows this in Visual Studio and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="fd7ec-113">Beginnen Sie mit einem einfachen Dialogfeld, das in ein C++ DLL-Projekt kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-113">Start with a simple dialog, which is compiled into a C++ DLL project.</span></span>

<span data-ttu-id="fd7ec-114">Führen Sie als nächstes den Dialog in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ein:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="fd7ec-115">Kompilieren der dll als verwaltet (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="fd7ec-115">Compile the DLL as managed (`/clr`)</span></span>

- <span data-ttu-id="fd7ec-116">Dialogfeld in ein Steuerelement umwandeln</span><span class="sxs-lookup"><span data-stu-id="fd7ec-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="fd7ec-117">Hiermit wird die abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost> mit `BuildWindowCore` und `DestroyWindowCore` Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="fd7ec-118">Überschreiben `TranslateAccelerator` Methode zum Behandeln von Dialog Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="fd7ec-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="fd7ec-119">Überschreiben `TabInto` Methode zur Unterstützung von Tabstopps</span><span class="sxs-lookup"><span data-stu-id="fd7ec-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="fd7ec-120">Überschreiben der `OnMnemonic` Methode zur Unterstützung von mnetmonics</span><span class="sxs-lookup"><span data-stu-id="fd7ec-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="fd7ec-121">Instanziieren Sie die <xref:System.Windows.Interop.HwndHost> Unterklasse, und legen Sie Sie unter dem rechten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element ab.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="fd7ec-122">Dialog Feld in ein Steuerelement umwandeln</span><span class="sxs-lookup"><span data-stu-id="fd7ec-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="fd7ec-123">Mithilfe der Stile WS_CHILD und DS_CONTROL können Sie ein Dialogfeld in ein untergeordnetes HWND umwandeln.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="fd7ec-124">Wechseln Sie in die Ressourcen Datei (RC-Datei), in der das Dialogfeld definiert ist, und suchen Sie den Anfang der Definition des Dialog Felds:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="fd7ec-125">Ändern Sie die zweite Zeile in:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-125">Change the second line to:</span></span>

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="fd7ec-126">Mit dieser Aktion wird Sie nicht vollständig in ein eigenständiges Steuerelement paketieren. Sie müssen weiterhin `IsDialogMessage()` aufzurufen, damit Win32 bestimmte Nachrichten verarbeiten kann, aber die Steuerelement Änderung bietet eine einfache Möglichkeit, diese Steuerelemente in einem anderen HWND zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so Win32 can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="fd7ec-127">Unterklasse HwndHost</span><span class="sxs-lookup"><span data-stu-id="fd7ec-127">Subclass HwndHost</span></span>

<span data-ttu-id="fd7ec-128">Importieren Sie die folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="fd7ec-129">Erstellen Sie dann eine abgeleitete Klasse von <xref:System.Windows.Interop.HwndHost>, und überschreiben Sie die Methoden `BuildWindowCore` und `DestroyWindowCore`:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="fd7ec-130">Hier verwenden Sie die `CreateDialog`, um das Dialogfeld zu erstellen, das tatsächlich ein Steuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="fd7ec-131">Da dies eine der ersten Methoden ist, die in der dll aufgerufen werden, sollten Sie auch eine standardmäßige Win32-Initialisierung durchführen, indem Sie eine Funktion aufrufen, die Sie später definieren, so genannte `InitializeGlobals()`:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-131">Since this is one of the first methods called inside the DLL, you should also do some standard Win32 initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="fd7ec-132">Überschreiben der TranslateAccelerator-Methode zum Behandeln von Dialog Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="fd7ec-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="fd7ec-133">Wenn Sie dieses Beispiel jetzt ausgeführt haben, erhalten Sie ein Dialogfeld Steuerelement, das angezeigt wird, aber es würde die gesamte Tastatur Verarbeitung ignorieren, durch die ein Dialogfeld zu einem funktionalen Dialogfeld wird.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="fd7ec-134">Nun sollten Sie die `TranslateAccelerator`-Implementierung überschreiben (die aus `IKeyboardInputSink`stammt, eine Schnittstelle, die implementiert <xref:System.Windows.Interop.HwndHost>).</span><span class="sxs-lookup"><span data-stu-id="fd7ec-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="fd7ec-135">Diese Methode wird aufgerufen, wenn die Anwendung WM_KEYDOWN und WM_SYSKEYDOWN empfängt.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="fd7ec-136">Dabei handelt es sich um einen großen Code in einem Teil, der einige Ausführlichere Erläuterungen verwenden könnte.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="fd7ec-137">Erstens: der Code mit C++ den C++ Makros und. Sie müssen beachten, dass bereits ein Makro mit dem Namen `TranslateAccelerator`vorhanden ist, das in winuser. h definiert ist:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="fd7ec-138">Stellen Sie daher sicher, dass Sie eine `TranslateAccelerator` Methode und keine `TranslateAcceleratorW` Methode definieren.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="fd7ec-139">Ebenso gibt es sowohl die nicht verwaltete Winuser. h-Meldung als auch die verwaltete `Microsoft::Win32::MSG`-Struktur.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="fd7ec-140">Mit dem C++ `::`-Operator können Sie zwischen den beiden unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

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

<span data-ttu-id="fd7ec-141">Zurück zum `TranslateAccelerator`.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-141">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="fd7ec-142">Das Grundprinzip besteht darin, die Win32-Funktion `IsDialogMessage` aufzurufen, um so viel Arbeit wie möglich zu tun, `IsDialogMessage` aber keinen Zugriff auf etwas außerhalb des Dialog Felds hat.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-142">The basic principle is to call the Win32 function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="fd7ec-143">Wenn im Dialogfeld die Registerkarte Benutzer im Dialogfeld angezeigt wird, müssen Sie den Fokus auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Teil durch Aufrufen von `IKeyboardInputSite::OnNoMoreStops`festlegen.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-143">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="fd7ec-144">Rufen Sie abschließend `IsDialogMessage` auf.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-144">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="fd7ec-145">Aber eine der Zuständigkeiten einer `TranslateAccelerator` Methode ist [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ob Sie den Tastatureingaben behandelt haben.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-145">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="fd7ec-146">Wenn Sie es nicht behandelt haben, kann das Eingabe Ereignis einen Tunnel durchlaufen und durch den Rest der Anwendung Blasen.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-146">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="fd7ec-147">Hier machen Sie eine Voreinstellung von Tastatur Messange-Behandlung und die Art der Eingabe Architektur in Win32 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-147">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in Win32.</span></span> <span data-ttu-id="fd7ec-148">Leider wird `IsDialogMessage` nicht in irgendeiner Weise zurückgegeben, unabhängig davon, ob eine bestimmte Tastatureingabe verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-148">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="fd7ec-149">Noch schlimmer ist, dass `DispatchMessage()` bei Tastatureingaben aufgerufen wird, die nicht behandelt werden sollten!</span><span class="sxs-lookup"><span data-stu-id="fd7ec-149">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="fd7ec-150">Daher müssen Sie `IsDialogMessage`rückgängig machen und nur für die Schlüssel anrufen, die Sie behandeln werden:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-150">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="fd7ec-151">TabInto-Methode zur Unterstützung von Tabstopps überschreiben</span><span class="sxs-lookup"><span data-stu-id="fd7ec-151">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="fd7ec-152">Nachdem Sie `TranslateAccelerator`implementiert haben, kann ein Benutzer im Dialogfeld mit der Tab-Taste navigieren und in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung darauf klicken.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-152">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="fd7ec-153">Ein Benutzer kann jedoch nicht zurück in das Dialogfeld zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-153">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="fd7ec-154">Um dieses Problem zu beheben, überschreiben Sie `TabInto`:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-154">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="fd7ec-155">Der `TraversalRequest`-Parameter gibt an, ob die Registerkarten Aktion eine Registerkarte oder eine UMSCHALT Registerkarte ist.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-155">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="fd7ec-156">Überschreiben der onmnetmonic-Methode zur Unterstützung von mnetmonics</span><span class="sxs-lookup"><span data-stu-id="fd7ec-156">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="fd7ec-157">Die Tastatur Behandlung ist fast vollständig, aber es fehlt eine Sache, – mnetmonics funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-157">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="fd7ec-158">Wenn ein Benutzer ALT + F drückt, springt der Fokus "Doe" nicht in das Bearbeitungsfeld "First Name:".</span><span class="sxs-lookup"><span data-stu-id="fd7ec-158">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="fd7ec-159">Daher überschreiben Sie die `OnMnemonic`-Methode:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-159">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="fd7ec-160">Warum werden hier keine `IsDialogMessage` aufgerufen?</span><span class="sxs-lookup"><span data-stu-id="fd7ec-160">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="fd7ec-161">Sie haben dasselbe Problem wie zuvor. Sie müssen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Code informieren können, ob der Code die Tastatureingaben behandelt hat, und `IsDialogMessage` dies nicht tun können.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-161">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="fd7ec-162">Es gibt auch ein zweites Problem, weil `IsDialogMessage` die Verarbeitung des mnetmonischen verweigert, wenn sich das fokussierte HWND nicht innerhalb des Dialog Felds befindet.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-162">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="fd7ec-163">Instanziieren der abgeleiteten HwndHost-Klasse</span><span class="sxs-lookup"><span data-stu-id="fd7ec-163">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="fd7ec-164">Nachdem Sie nun alle Schlüssel-und Registerkarten Unterstützung eingerichtet haben, können Sie Ihre <xref:System.Windows.Interop.HwndHost> in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-164">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="fd7ec-165">Wenn die Hauptanwendung in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]geschrieben ist, besteht die einfachste Möglichkeit, Sie an der richtigen Stelle zu platzieren, darin, ein leeres <xref:System.Windows.Controls.Border> Element zu belassen, wo Sie die <xref:System.Windows.Interop.HwndHost>platzieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-165">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="fd7ec-166">Hier erstellen Sie eine <xref:System.Windows.Controls.Border> mit dem Namen `insertHwndHostHere`:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-166">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="fd7ec-167">Dann müssen Sie nur noch einen guten Speicherort in der Code Sequenz finden, um den <xref:System.Windows.Interop.HwndHost> zu instanziieren und ihn mit dem <xref:System.Windows.Controls.Border>zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="fd7ec-167">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="fd7ec-168">In diesem Beispiel fügen Sie Sie in den Konstruktor für die <xref:System.Windows.Window> abgeleitete Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-168">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="fd7ec-169">So erhalten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="fd7ec-169">Which gives you:</span></span>

![Screenshot der WPF-App, die ausgeführt wird.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="fd7ec-171">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd7ec-171">See also</span></span>

- [<span data-ttu-id="fd7ec-172">Interaktion zwischen WPF und Win32</span><span class="sxs-lookup"><span data-stu-id="fd7ec-172">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
