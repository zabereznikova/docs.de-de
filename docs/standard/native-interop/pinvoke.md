---
title: Plattformaufruf (P/Invoke)
description: Erfahren Sie, wie Sie native Funktionen über P/Invoke in .Net aufrufen.
author: jkoritzinsky
ms.author: jekoritz
ms.date: 01/18/2019
ms.openlocfilehash: 51026eab92ae4fd47ccdd78321be21bdbb5ecf49
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981256"
---
# <a name="platform-invoke-pinvoke"></a><span data-ttu-id="4a3e0-103">Plattformaufruf (P/Invoke)</span><span class="sxs-lookup"><span data-stu-id="4a3e0-103">Platform Invoke (P/Invoke)</span></span>

<span data-ttu-id="4a3e0-104">P/Invoke ist eine Technologie, die Ihnen den Zugriff auf Strukturen, Rückrufe und Funktionen in nicht verwalteten Bibliotheken von verwaltetem Code aus ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-104">P/Invoke is a technology that allows you to access structs, callbacks, and functions in unmanaged libraries from your managed code.</span></span> <span data-ttu-id="4a3e0-105">Der Großteil der P/Invoke-API ist in zwei Namespaces enthalten: `System` und `System.Runtime.InteropServices`.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-105">Most of the P/Invoke API is contained in two namespaces: `System` and `System.Runtime.InteropServices`.</span></span> <span data-ttu-id="4a3e0-106">Über diese beiden Namespaces können Sie auf die Tools zugreifen, die beschreiben, wie Sie mit der nativen Komponente kommunizieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-106">Using these two namespaces give you the tools to describe how you want to communicate with the native component.</span></span>

<span data-ttu-id="4a3e0-107">Beginnen wir mit dem gängigsten Beispiel, dem Aufruf nicht verwalteter Funktionen im Ihrem verwalteten Code.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-107">Let’s start from the most common example, and that is calling unmanaged functions in your managed code.</span></span> <span data-ttu-id="4a3e0-108">Wir zeigen ein Meldungsfeld aus einer Befehlszeilenanwendung:</span><span class="sxs-lookup"><span data-stu-id="4a3e0-108">Let’s show a message box from a command-line application:</span></span>

```csharp
using System.Runtime.InteropServices;

public class Program {

    // Import user32.dll (containing the function we need) and define
    // the method corresponding to the native function.
    [DllImport("user32.dll")]
    public static extern int MessageBox(IntPtr hWnd, String text, String caption, int options);

    public static void Main(string[] args) {
        // Invoke the function as a regular managed method.
        MessageBox(IntPtr.Zero, "Command-line message box", "Attention!", 0);
    }
}
```

<span data-ttu-id="4a3e0-109">Das obige Beispiel ist recht einfach, zeigt jedoch, was zum Aufrufen nicht verwalteter Funktionen von verwaltetem Code aus erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-109">The previous example is simple, but it does show off what's needed to invoke unmanaged functions from managed code.</span></span> <span data-ttu-id="4a3e0-110">Gehen wir das Beispiel schrittweise durch:</span><span class="sxs-lookup"><span data-stu-id="4a3e0-110">Let’s step through the example:</span></span>

*   <span data-ttu-id="4a3e0-111">Zeile 1 zeigt die using-Anweisung für `System.Runtime.InteropServices`. Dies ist der Namespace, der alle benötigten Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-111">Line #1 shows the using statement for the `System.Runtime.InteropServices` namespace that holds all the items needed.</span></span>
*   <span data-ttu-id="4a3e0-112">In Zeile 7 wird das `DllImport`-Attribut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-112">Line #7 introduces the `DllImport` attribute.</span></span> <span data-ttu-id="4a3e0-113">Dieses Attribut ist äußerst wichtig, da es der Runtime mitteilt, dass die nicht verwaltete DLL geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-113">This attribute is crucial, as it tells the runtime that it should load the unmanaged DLL.</span></span> <span data-ttu-id="4a3e0-114">Die übergebene Zeichenfolge ist die DLL, in der sich unsere Zielfunktion befindet.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-114">The string passed in is the DLL our target function is in.</span></span>
*   <span data-ttu-id="4a3e0-115">Zeile 8 ist der Kern der P/Invoke-Funktion.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-115">Line #8 is the crux of the P/Invoke work.</span></span> <span data-ttu-id="4a3e0-116">Sie definiert eine verwaltete Methode, die **genau dieselbe Signatur** aufweist wie die nicht verwaltete Methode.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-116">It defines a managed method that has the **exact same signature** as the unmanaged one.</span></span> <span data-ttu-id="4a3e0-117">Wie Sie sehen, enthält die Deklaration ein neues Schlüsselwort, `extern`. Dieses teilt der Runtime mit, dass es sich um eine externe Methode handelt und dass die Runtime die Methode bei Aufruf in der im `DllImport`-Attribut angegebenen DLL findet.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-117">The declaration has a new keyword that you can notice, `extern`, which tells the runtime this is an external method, and that when you invoke it, the runtime should find it in the DLL specified in `DllImport` attribute.</span></span>

<span data-ttu-id="4a3e0-118">Der Rest des Beispiels besteht nur aus dem Aufruf der Methode, der wie bei jeder anderen verwalteten Methode erfolgt.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-118">The rest of the example is just invoking the method as you would any other managed method.</span></span>

<span data-ttu-id="4a3e0-119">Das Beispiel ist für macOS ähnlich.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-119">The sample is similar for macOS.</span></span> <span data-ttu-id="4a3e0-120">Der Name der Bibliothek im `DllImport`-Attribut muss geändert werden, da macOS ein anderes Schema für die Benennung dynamischer Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-120">The name of the library in the `DllImport` attribute needs to change since macOS has a different scheme of naming dynamic libraries.</span></span> <span data-ttu-id="4a3e0-121">Das folgende Beispiel verwendet die `getpid(2)`-Funktion, um die Prozess-ID der Anwendung abzurufen und in der Konsole auszugeben.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-121">The following sample uses the `getpid(2)` function to get the process ID of the application and print it out to the console:</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libSystem shared library and define the method corresponding to the native function.
        [DllImport("libSystem.dylib")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

<span data-ttu-id="4a3e0-122">Bei Linux ist es ähnlich.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-122">It is also similar on Linux.</span></span> <span data-ttu-id="4a3e0-123">Der Funktionsname ist identisch, da es sich bei `getpid(2)` um einen standardmäßigen [POSIX](https://en.wikipedia.org/wiki/POSIX)-Systemaufruf handelt.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-123">The function name is the same, since `getpid(2)` is a standard [POSIX](https://en.wikipedia.org/wiki/POSIX) system call.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc shared library and define the method corresponding to the native function.
        [DllImport("libc.so.6")]
        private static extern int getpid();

        public static void Main(string[] args){
            // Invoke the function and get the process ID.
            int pid = getpid();
            Console.WriteLine(pid);
        }
    }
}
```

## <a name="invoking-managed-code-from-unmanaged-code"></a><span data-ttu-id="4a3e0-124">Aufrufen von verwaltetem Code von nicht verwaltetem Code aus</span><span class="sxs-lookup"><span data-stu-id="4a3e0-124">Invoking managed code from unmanaged code</span></span>

<span data-ttu-id="4a3e0-125">Die Runtime ermöglicht den Kommunikationsfluss in beide Richtungen, sodass Sie verwalteten Code mithilfe von Funktionszeigern aus nativen Funktionen zurückrufen können.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-125">The runtime allows communication to flow in both directions, enabling you to call back into managed code from native functions by using function pointers.</span></span> <span data-ttu-id="4a3e0-126">Einem Funktionszeiger in verwaltetem Code kommt ein **Delegat** am nächsten. Dieser wird verwendet, um Rückrufe von nativem Code an verwalteten Code zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-126">The closest thing to a function pointer in managed code is a **delegate**, so this is what is used to allow callbacks from native code into managed code.</span></span>

<span data-ttu-id="4a3e0-127">Dieses Feature wird ähnlich dem oben beschriebenen Verfahren von verwaltetem zu nativem Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-127">The way to use this feature is similar to the managed to native process previously described.</span></span> <span data-ttu-id="4a3e0-128">Für einen bestimmten Rückruf definieren Sie einen Delegaten, der der Signatur entspricht, und übergeben Sie ihn an die externe Methode.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-128">For a given callback, you define a delegate that matches the signature and pass that into the external method.</span></span> <span data-ttu-id="4a3e0-129">Die Runtime übernimmt alles Weitere.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-129">The runtime will take care of everything else.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace ConsoleApplication1 {

    class Program {

        // Define a delegate that corresponds to the unmanaged function.
        delegate bool EnumWC(IntPtr hwnd, IntPtr lParam);

        // Import user32.dll (containing the function we need) and define
        // the method corresponding to the native function.
        [DllImport("user32.dll")]
        static extern int EnumWindows(EnumWC lpEnumFunc, IntPtr lParam);

        // Define the implementation of the delegate; here, we simply output the window handle.
        static bool OutputWindow(IntPtr hwnd, IntPtr lParam) {
            Console.WriteLine(hwnd.ToInt64());
            return true;
        }

        static void Main(string[] args) {
            // Invoke the method; note the delegate as a first parameter.
            EnumWindows(OutputWindow, IntPtr.Zero);
        }
    }
}
```

<span data-ttu-id="4a3e0-130">Bevor wir unser Beispiel durchgehen, sollten wir die Signaturen der nicht verwalteten Funktionen betrachten, mit denen wir arbeiten müssen.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-130">Before walking through the example, it's good to review the signatures of the unmanaged functions you need to work with.</span></span> <span data-ttu-id="4a3e0-131">Die Funktion, die wir zum Auflisten aller Fenster aufrufen möchten, weist folgende Signatur auf: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="4a3e0-131">The function to be called to enumerate all of the windows has the following signature: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`</span></span>

<span data-ttu-id="4a3e0-132">Der erste Parameter ist ein Rückruf.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-132">The first parameter is a callback.</span></span> <span data-ttu-id="4a3e0-133">Dieser Rückruf besitzt die folgende Signatur: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span><span class="sxs-lookup"><span data-stu-id="4a3e0-133">The said callback has the following signature: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`</span></span>

<span data-ttu-id="4a3e0-134">Schauen wir uns jetzt das Beispiel an:</span><span class="sxs-lookup"><span data-stu-id="4a3e0-134">Now, let’s walk through the example:</span></span>

*   <span data-ttu-id="4a3e0-135">Zeile 9 im Beispiel definiert einen Delegaten, der der Signatur des Rückrufs von nicht verwaltetem Code aus entspricht.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-135">Line #9 in the example defines a delegate that matches the signature of the callback from unmanaged code.</span></span> <span data-ttu-id="4a3e0-136">Beachten Sie, wie die Typen LPARAM und HWND über `IntPtr` im verwalteten Code dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-136">Notice how the LPARAM and HWND types are represented using `IntPtr` in the managed code.</span></span>
*   <span data-ttu-id="4a3e0-137">In den Zeilen 13 und 14 wird die `EnumWindows`-Funktion über die user32.dll-Bibliothek eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-137">Lines #13 and #14 introduce the `EnumWindows` function from the user32.dll library.</span></span>
*   <span data-ttu-id="4a3e0-138">In den Zeilen 17 bis 20 wird der Delegat implementiert.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-138">Lines #17 - 20 implement the delegate.</span></span> <span data-ttu-id="4a3e0-139">In diesem einfachen Beispiel möchten wir nur das Handle an die Konsole ausgeben.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-139">For this simple example, we just want to output the handle to the console.</span></span>
*   <span data-ttu-id="4a3e0-140">Abschließend wird in Zeile 24 die externe Methode aufgerufen und an den Delegaten übergeben.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-140">Finally, in line #24, the external method is called and passed in the delegate.</span></span>

<span data-ttu-id="4a3e0-141">Die Beispiele für Linux und macOS werden im Folgenden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-141">The Linux and macOS examples are shown below.</span></span> <span data-ttu-id="4a3e0-142">Hierfür verwenden wir die `ftw`-Funktion, die in `libc` zu finden ist, der C-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-142">For them, we use the `ftw` function that can be found in `libc`, the C library.</span></span> <span data-ttu-id="4a3e0-143">Anhand dieser Funktion werden die Verzeichnishierarchien durchlaufen. Sie verwendet einen Zeiger auf eine Funktion als einen ihrer Parameter.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-143">This function is used to traverse directory hierarchies and it takes a pointer to a function as one of its parameters.</span></span> <span data-ttu-id="4a3e0-144">Diese Funktion besitzt die folgende Signatur: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-144">The said function has the following signature: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

            // Define a delegate that has the same signature as the native function.
            delegate int DirClbk(string fName, StatClass stat, int typeFlag);

            // Import the libc and define the method to represent the native function.
            [DllImport("libc.so.6")]
            static extern int ftw(string dirpath, DirClbk cl, int descriptors);

            // Implement the above DirClbk delegate;
            // this one just prints out the filename that is passed to it.
            static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                    Console.WriteLine(fName);
                    return 0;
            }

            public static void Main(string[] args){
                    // Call the native function.
                    // Note the second parameter which represents the delegate (callback).
                    ftw(".", DisplayEntry, 10);
            }
    }

    // The native callback takes a pointer to a struct. The below class
    // represents that struct in managed code. You can find more information
    // about this in the section on marshalling below.
    [StructLayout(LayoutKind.Sequential)]
    public class StatClass {
            public uint DeviceID;
            public uint InodeNumber;
            public uint Mode;
            public uint HardLinks;
            public uint UserID;
            public uint GroupID;
            public uint SpecialDeviceID;
            public ulong Size;
            public ulong BlockSize;
            public uint Blocks;
            public long TimeLastAccess;
            public long TimeLastModification;
            public long TimeLastStatusChange;
    }
}
```

<span data-ttu-id="4a3e0-145">Im macOS-Beispiel wird die gleiche Funktion verwendet. Der einzige Unterschied ist das Argument für das `DllImport`-Attribut, da macOS `libc` an einer anderen Stelle speichert.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-145">macOS example uses the same function, and the only difference is the argument to the `DllImport` attribute, as macOS keeps `libc` in a different place.</span></span>

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
        public static class Program {

                // Define a delegate that has the same signature as the native function.
                delegate int DirClbk(string fName, StatClass stat, int typeFlag);

                // Import the libc and define the method to represent the native function.
                [DllImport("libSystem.dylib")]
                static extern int ftw(string dirpath, DirClbk cl, int descriptors);

                // Implement the above DirClbk delegate;
                // this one just prints out the filename that is passed to it.
                static int DisplayEntry(string fName, StatClass stat, int typeFlag) {
                        Console.WriteLine(fName);
                        return 0;
                }

                public static void Main(string[] args){
                        // Call the native function.
                        // Note the second parameter which represents the delegate (callback).
                        ftw(".", DisplayEntry, 10);
                }
        }

        // The native callback takes a pointer to a struct. The below class
        // represents that struct in managed code.
        [StructLayout(LayoutKind.Sequential)]
        public class StatClass {
                public uint DeviceID;
                public uint InodeNumber;
                public uint Mode;
                public uint HardLinks;
                public uint UserID;
                public uint GroupID;
                public uint SpecialDeviceID;
                public ulong Size;
                public ulong BlockSize;
                public uint Blocks;
                public long TimeLastAccess;
                public long TimeLastModification;
                public long TimeLastStatusChange;
        }
}
```

<span data-ttu-id="4a3e0-146">Beide oben aufgeführten Beispiele hängen von Parametern ab, und in beiden Fällen werden die Parameter als verwaltete Typen angegeben.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-146">Both of the previous examples depend on parameters, and in both cases, the parameters are given as managed types.</span></span> <span data-ttu-id="4a3e0-147">Die Runtime reagiert demgemäß und verarbeitet diese in ihren Entsprechungen auf der anderen Seite.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-147">Runtime does the "right thing" and processes these into its equivalents on the other side.</span></span> <span data-ttu-id="4a3e0-148">Weitere Informationen dazu, wie Typen in nativen Code auf unserer Seite gemarshallt werden, finden Sie unter [Marshalling von Typen](type-marshalling.md).</span><span class="sxs-lookup"><span data-stu-id="4a3e0-148">Learn about how types are marshalled to native code in our page on [Type marshalling](type-marshalling.md).</span></span>


## <a name="more-resources"></a><span data-ttu-id="4a3e0-149">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="4a3e0-149">More resources</span></span>

*   <span data-ttu-id="4a3e0-150">[PInvoke.NET-Wiki](https://www.pinvoke.net/) ist eine ausgezeichnete Wiki-Seite mit Informationen zu gängigen Win32-APIs und deren Aufruf.</span><span class="sxs-lookup"><span data-stu-id="4a3e0-150">[PInvoke.net wiki](https://www.pinvoke.net/) an excellent Wiki with information on common Win32 APIs and how to call them.</span></span>
*   [<span data-ttu-id="4a3e0-151">P/Invoke auf MSDN</span><span class="sxs-lookup"><span data-stu-id="4a3e0-151">P/Invoke on MSDN</span></span>](/cpp/dotnet/native-and-dotnet-interoperability)
*   [<span data-ttu-id="4a3e0-152">Mono-Dokumentation zu P/Invoke</span><span class="sxs-lookup"><span data-stu-id="4a3e0-152">Mono documentation on P/Invoke</span></span>](https://www.mono-project.com/docs/advanced/pinvoke/)
