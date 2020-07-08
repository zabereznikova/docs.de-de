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
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="c2d32-102">Hosten von Win32-Inhalt in WPF</span><span class="sxs-lookup"><span data-stu-id="c2d32-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2d32-103">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c2d32-103">Prerequisites</span></span>

<span data-ttu-id="c2d32-104">Siehe [WPF-und Win32-Interoperation](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="c2d32-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="c2d32-105">Exemplarische Vorgehensweise von Win32 in Windows Presentation Framework (HwndHost)</span><span class="sxs-lookup"><span data-stu-id="c2d32-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="c2d32-106">Verwenden Sie zum wieder verwenden von Win32-Inhalt in- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendungen <xref:System.Windows.Interop.HwndHost> . Hierbei handelt es sich um ein Steuerelement, das HWNDs als [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt ansieht.</span><span class="sxs-lookup"><span data-stu-id="c2d32-106">To reuse Win32 content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="c2d32-107">Wie <xref:System.Windows.Interop.HwndSource> <xref:System.Windows.Interop.HwndHost> ist einfach zu verwenden: leiten Sie von ab <xref:System.Windows.Interop.HwndHost> `BuildWindowCore` , implementieren `DestroyWindowCore` Sie die-Methode und die-Methode, instanziieren <xref:System.Windows.Interop.HwndHost> Sie Ihre abgeleitete Klasse, und platzieren Sie Sie in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="c2d32-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="c2d32-108">Wenn die Win32-Logik bereits als Steuerelement gepackt ist, `BuildWindowCore` ist die Implementierung kaum mehr als ein-Befehl `CreateWindow` .</span><span class="sxs-lookup"><span data-stu-id="c2d32-108">If your Win32 logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="c2d32-109">So erstellen Sie z. b. ein Win32-ListBox-Steuerelement in C++:</span><span class="sxs-lookup"><span data-stu-id="c2d32-109">For example, to create a Win32 LISTBOX control in C++:</span></span>

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

<span data-ttu-id="c2d32-110">Angenommen, der Win32-Code ist nicht ganz so eigenständig?</span><span class="sxs-lookup"><span data-stu-id="c2d32-110">But suppose the Win32 code is not quite so self-contained?</span></span> <span data-ttu-id="c2d32-111">Wenn dies der Fall ist, können Sie ein Win32-Dialogfeld erstellen und seinen Inhalt in eine größere Anwendung einbetten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2d32-111">If so, you can create a Win32 dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="c2d32-112">Das Beispiel zeigt dies in Visual Studio und C++, obwohl dies auch in einer anderen Sprache oder über die Befehlszeile möglich ist.</span><span class="sxs-lookup"><span data-stu-id="c2d32-112">The sample shows this in Visual Studio and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="c2d32-113">Beginnen Sie mit einem einfachen Dialogfeld, das in ein C++-DLL-Projekt kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="c2d32-113">Start with a simple dialog, which is compiled into a C++ DLL project.</span></span>

<span data-ttu-id="c2d32-114">Führen Sie als nächstes den Dialog in der größeren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung ein:</span><span class="sxs-lookup"><span data-stu-id="c2d32-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="c2d32-115">Kompilieren Sie die dll als verwaltet ( `/clr` ).</span><span class="sxs-lookup"><span data-stu-id="c2d32-115">Compile the DLL as managed (`/clr`)</span></span>

- <span data-ttu-id="c2d32-116">Dialogfeld in ein Steuerelement umwandeln</span><span class="sxs-lookup"><span data-stu-id="c2d32-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="c2d32-117">Definieren der abgeleiteten Klasse von <xref:System.Windows.Interop.HwndHost> mit `BuildWindowCore` -und- `DestroyWindowCore` Methoden</span><span class="sxs-lookup"><span data-stu-id="c2d32-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="c2d32-118">Überschreibungs `TranslateAccelerator` Methode zum Behandeln von Dialog Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="c2d32-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="c2d32-119">Außerkraftsetzungs `TabInto` Methode zur Unterstützung von Tabstopps</span><span class="sxs-lookup"><span data-stu-id="c2d32-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="c2d32-120">Überschreibungs `OnMnemonic` Methode zur Unterstützung von mnetmonics</span><span class="sxs-lookup"><span data-stu-id="c2d32-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="c2d32-121">Instanziieren <xref:System.Windows.Interop.HwndHost> Sie die Unterklasse, und legen Sie Sie unter dem rechten Element ab. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d32-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="c2d32-122">Dialog Feld in ein Steuerelement umwandeln</span><span class="sxs-lookup"><span data-stu-id="c2d32-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="c2d32-123">Mithilfe der Stile WS_CHILD und DS_CONTROL können Sie ein Dialogfeld in ein untergeordnetes HWND umwandeln.</span><span class="sxs-lookup"><span data-stu-id="c2d32-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="c2d32-124">Wechseln Sie in die Ressourcen Datei (RC-Datei), in der das Dialogfeld definiert ist, und suchen Sie den Anfang der Definition des Dialog Felds:</span><span class="sxs-lookup"><span data-stu-id="c2d32-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="c2d32-125">Ändern Sie die zweite Zeile in:</span><span class="sxs-lookup"><span data-stu-id="c2d32-125">Change the second line to:</span></span>

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="c2d32-126">Mit dieser Aktion wird Sie nicht vollständig in ein eigenständiges Steuerelement paketieren. Sie müssen trotzdem aufzurufen `IsDialogMessage()` , damit Win32 bestimmte Nachrichten verarbeiten kann, aber die Steuerelement Änderung bietet eine einfache Möglichkeit, diese Steuerelemente in einem anderen HWND zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="c2d32-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so Win32 can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="c2d32-127">Unterklasse HwndHost</span><span class="sxs-lookup"><span data-stu-id="c2d32-127">Subclass HwndHost</span></span>

<span data-ttu-id="c2d32-128">Importieren Sie die folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="c2d32-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="c2d32-129">Erstellen Sie dann eine abgeleitete Klasse von, <xref:System.Windows.Interop.HwndHost> und überschreiben Sie die `BuildWindowCore` `DestroyWindowCore` Methoden und:</span><span class="sxs-lookup"><span data-stu-id="c2d32-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="c2d32-130">Hier verwenden Sie `CreateDialog` , um das Dialogfeld zu erstellen, das tatsächlich ein Steuerelement ist.</span><span class="sxs-lookup"><span data-stu-id="c2d32-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="c2d32-131">Da dies eine der ersten Methoden ist, die in der dll aufgerufen werden, sollten Sie auch eine standardmäßige Win32-Initialisierung durchführen, indem Sie eine Funktion aufrufen, die Sie später definieren `InitializeGlobals()` :</span><span class="sxs-lookup"><span data-stu-id="c2d32-131">Since this is one of the first methods called inside the DLL, you should also do some standard Win32 initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="c2d32-132">Überschreiben der TranslateAccelerator-Methode zum Behandeln von Dialog Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="c2d32-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="c2d32-133">Wenn Sie dieses Beispiel jetzt ausgeführt haben, erhalten Sie ein Dialogfeld Steuerelement, das angezeigt wird, aber es würde die gesamte Tastatur Verarbeitung ignorieren, durch die ein Dialogfeld zu einem funktionalen Dialogfeld wird.</span><span class="sxs-lookup"><span data-stu-id="c2d32-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="c2d32-134">Jetzt sollten Sie die- `TranslateAccelerator` Implementierung überschreiben (aus `IKeyboardInputSink` einer Schnittstelle, die <xref:System.Windows.Interop.HwndHost> implementiert).</span><span class="sxs-lookup"><span data-stu-id="c2d32-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="c2d32-135">Diese Methode wird aufgerufen, wenn die Anwendung WM_KEYDOWN und WM_SYSKEYDOWN empfängt.</span><span class="sxs-lookup"><span data-stu-id="c2d32-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="c2d32-136">Dabei handelt es sich um einen großen Code in einem Teil, der einige Ausführlichere Erläuterungen verwenden könnte.</span><span class="sxs-lookup"><span data-stu-id="c2d32-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="c2d32-137">Zuerst der Code, der C++-und C++-Makros verwendet. Sie müssen beachten, dass bereits ein Makro mit dem Namen vorhanden ist `TranslateAccelerator` , das in winuser. h definiert ist:</span><span class="sxs-lookup"><span data-stu-id="c2d32-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="c2d32-138">Stellen Sie daher sicher, dass Sie eine `TranslateAccelerator` Methode und keine `TranslateAcceleratorW` Methode definieren.</span><span class="sxs-lookup"><span data-stu-id="c2d32-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="c2d32-139">Ebenso gibt es sowohl die nicht verwaltete Winuser. h-Meldung als auch die verwaltete `Microsoft::Win32::MSG` Struktur.</span><span class="sxs-lookup"><span data-stu-id="c2d32-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="c2d32-140">Mit dem C++-Operator können Sie zwischen den beiden unterschieden werden `::` .</span><span class="sxs-lookup"><span data-stu-id="c2d32-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}
```

<span data-ttu-id="c2d32-141">Beide Msgs verfügen über dieselben Daten. manchmal ist es jedoch einfacher, mit der nicht verwalteten Definition zu arbeiten. in diesem Beispiel können Sie also die offensichtliche Konvertierungsroutine definieren:</span><span class="sxs-lookup"><span data-stu-id="c2d32-141">Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:</span></span>

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

<span data-ttu-id="c2d32-142">Zurück zu `TranslateAccelerator` .</span><span class="sxs-lookup"><span data-stu-id="c2d32-142">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="c2d32-143">Das Grundprinzip besteht darin, die Win32-Funktion aufzurufen `IsDialogMessage` , um so viel Arbeit wie möglich zu erledigen, aber keinen `IsDialogMessage` Zugriff auf etwas außerhalb des Dialog Felds.</span><span class="sxs-lookup"><span data-stu-id="c2d32-143">The basic principle is to call the Win32 function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="c2d32-144">Wenn im Dialogfeld die Registerkarte Benutzer im Dialogfeld angezeigt wird, müssen Sie den Fokus auf den Teil festlegen, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] indem Sie aufrufen `IKeyboardInputSite::OnNoMoreStops` .</span><span class="sxs-lookup"><span data-stu-id="c2d32-144">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="c2d32-145">Rufen Sie abschließend `IsDialogMessage` auf.</span><span class="sxs-lookup"><span data-stu-id="c2d32-145">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="c2d32-146">Aber eine der Verantwortlichkeiten einer `TranslateAccelerator` Methode gibt Aufschluss darüber, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ob Sie den Tastatureingaben behandelt haben.</span><span class="sxs-lookup"><span data-stu-id="c2d32-146">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="c2d32-147">Wenn Sie es nicht behandelt haben, kann das Eingabe Ereignis einen Tunnel durchlaufen und durch den Rest der Anwendung Blasen.</span><span class="sxs-lookup"><span data-stu-id="c2d32-147">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="c2d32-148">Hier machen Sie eine Voreinstellung von Tastatur Messange-Behandlung und die Art der Eingabe Architektur in Win32 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c2d32-148">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in Win32.</span></span> <span data-ttu-id="c2d32-149">Leider wird `IsDialogMessage` nicht in irgendeiner Weise zurückgegeben, unabhängig davon, ob ein bestimmter Tastatur Strich verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="c2d32-149">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="c2d32-150">Noch schlimmer ist, dass Sie bei Tastatureingaben aufgerufen wird, die `DispatchMessage()` nicht behandelt werden sollten!</span><span class="sxs-lookup"><span data-stu-id="c2d32-150">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="c2d32-151">Sie müssen sich also rückgängig machen `IsDialogMessage` und müssen nur für die Schlüssel aufgerufen werden, die er behandelt:</span><span class="sxs-lookup"><span data-stu-id="c2d32-151">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="c2d32-152">TabInto-Methode zur Unterstützung von Tabstopps überschreiben</span><span class="sxs-lookup"><span data-stu-id="c2d32-152">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="c2d32-153">Nachdem Sie nun implementiert haben `TranslateAccelerator` , kann ein Benutzer im Dialogfeld mit der Tab-Taste navigieren und in der größeren Anwendung darauf klicken [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c2d32-153">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="c2d32-154">Ein Benutzer kann jedoch nicht zurück in das Dialogfeld zurückkehren.</span><span class="sxs-lookup"><span data-stu-id="c2d32-154">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="c2d32-155">Um dieses Problem zu beheben, überschreiben Sie Folgendes `TabInto` :</span><span class="sxs-lookup"><span data-stu-id="c2d32-155">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="c2d32-156">Der- `TraversalRequest` Parameter gibt an, ob die Registerkarten Aktion eine Registerkarte oder eine UMSCHALT Registerkarte ist.</span><span class="sxs-lookup"><span data-stu-id="c2d32-156">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="c2d32-157">Überschreiben der onmnetmonic-Methode zur Unterstützung von mnetmonics</span><span class="sxs-lookup"><span data-stu-id="c2d32-157">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="c2d32-158">Die Tastatur Behandlung ist fast vollständig, aber es fehlt eine Sache, – mnetmonics funktioniert nicht.</span><span class="sxs-lookup"><span data-stu-id="c2d32-158">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="c2d32-159">Wenn ein Benutzer ALT + F drückt, springt der Fokus "Doe" nicht in das Bearbeitungsfeld "First Name:".</span><span class="sxs-lookup"><span data-stu-id="c2d32-159">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="c2d32-160">Daher überschreiben Sie die- `OnMnemonic` Methode:</span><span class="sxs-lookup"><span data-stu-id="c2d32-160">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="c2d32-161">Warum wird hier nicht aufgerufen `IsDialogMessage` ?</span><span class="sxs-lookup"><span data-stu-id="c2d32-161">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="c2d32-162">Sie haben dasselbe Problem wie zuvor. Sie müssen in der Lage sein, Code darüber zu informieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , ob der Code die Tastatureingaben behandelt hat, und dies nicht `IsDialogMessage` .</span><span class="sxs-lookup"><span data-stu-id="c2d32-162">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="c2d32-163">Es gibt auch ein zweites Problem, da `IsDialogMessage` die Verarbeitung des mnetmonischen, wenn sich das fokussierte HWND nicht innerhalb des Dialog Felds befindet.</span><span class="sxs-lookup"><span data-stu-id="c2d32-163">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="c2d32-164">Instanziieren der abgeleiteten HwndHost-Klasse</span><span class="sxs-lookup"><span data-stu-id="c2d32-164">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="c2d32-165">Nachdem nun alle Schlüssel-und Registerkarten Unterstützung vorhanden sind, können Sie Ihren <xref:System.Windows.Interop.HwndHost> in die größere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung einfügen.</span><span class="sxs-lookup"><span data-stu-id="c2d32-165">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="c2d32-166">Wenn die Hauptanwendung in geschrieben ist [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , besteht die einfachste Möglichkeit, Sie an der richtigen Stelle zu platzieren, darin, ein leeres Element zu verlassen, <xref:System.Windows.Controls.Border> in das Sie die platzieren möchten <xref:System.Windows.Interop.HwndHost> .</span><span class="sxs-lookup"><span data-stu-id="c2d32-166">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="c2d32-167">Hier erstellen Sie einen mit dem <xref:System.Windows.Controls.Border> Namen `insertHwndHostHere` :</span><span class="sxs-lookup"><span data-stu-id="c2d32-167">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="c2d32-168">Dann müssen Sie nur noch einen guten Speicherort in der Code Sequenz finden, um die zu instanziieren <xref:System.Windows.Interop.HwndHost> und eine Verbindung mit dem herzustellen <xref:System.Windows.Controls.Border> .</span><span class="sxs-lookup"><span data-stu-id="c2d32-168">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="c2d32-169">In diesem Beispiel fügen Sie Sie in den Konstruktor für die <xref:System.Windows.Window> abgeleitete Klasse ein:</span><span class="sxs-lookup"><span data-stu-id="c2d32-169">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="c2d32-170">So erhalten Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c2d32-170">Which gives you:</span></span>

![Screenshot der WPF-App, die ausgeführt wird.](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="c2d32-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2d32-172">See also</span></span>

- [<span data-ttu-id="c2d32-173">Interaktion zwischen WPF und Win32</span><span class="sxs-lookup"><span data-stu-id="c2d32-173">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
