---
title: "Native Interoperabilität"
description: "Native Interoperabilität"
keywords: .NET, .NET Core
author: blackdwarf
ms.author: ronpet
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3c357112-35fb-44ba-a07b-6a1c140370ac
translationtype: Human Translation
ms.sourcegitcommit: d18b21b67c154c4a8cf8211aa5d1473066c53656
ms.openlocfilehash: 13a4e4e7a588d55e82c5c4cde8f825c3b4502bb4
ms.lasthandoff: 03/02/2017

---

# <a name="native-interoperability"></a>Native Interoperabilität

In diesem Dokument werden alle drei Möglichkeiten für „native Interoperabilität“ im Detail untersucht, die auf der .NET-Plattform verfügbar sind.

Es gibt einige Gründe für das Aufrufen von nativem Code:

*   Im Lieferumfang von Betriebssystemen ist eine große Anzahl von APIs enthalten, die in den verwalteten Klassenbibliotheken nicht vorhanden sind. Ein gutes Beispiel hierfür ist der Zugriff auf Hardware- oder Betriebssystem-Verwaltungsfunktionen.
*   Die Kommunikation mit anderen Komponenten, die über ABIs im C-Format (native ABIs) verfügen oder diese erstellen können. Hierzu gehört beispielsweise Java-Code, der über die [Java Native Interface (JNI)](http://docs.oracle.com/javase/8/docs/technotes/guides/jni/) verfügbar gemacht wird, oder eine beliebige andere verwaltete Sprache, die eine native Komponente erstellen kann.
*   Unter Windows werden für den Großteil der installierten Software (z.B. Microsoft Office-Suite) COM-Komponenten registriert, die ihre Programme darstellen und den Entwicklern deren Automatisierung oder Verwendung ermöglichen. Auch hierfür ist native Interoperabilität erforderlich.

Natürlich deckt die obige Liste nicht alle möglichen Situationen und Szenarios ab, in denen ein Entwickler eine Schnittstelle mit nativen Komponenten benötigt. Die .NET-Klassenbibliothek verwendet zum Beispiel die Unterstützung für native Interoperabilität, um eine große Anzahl ihrer APIs zu implementieren, z.B. die Unterstützung und Bearbeitung der Konsole, Dateisystemzugriff und mehr. Es ist jedoch unbedingt zu beachten, dass es eine Option gibt, wenn man sie benötigen sollte.

> [!NOTE]
> Die meisten Beispiele in diesem Dokument werden für alle drei unterstützten Plattformen für .NET Core (Windows, Linux und macOS) aufgeführt. Bei einigen kurzen und anschaulichen Beispielen wird allerdings nur ein Beispiel gezeigt, das Windows-Dateinamen und -Erweiterungen (d.h. „DLL“ für Bibliotheken) verwendet. Dies wurde nur der Einfachheit halber so gehandhabt und bedeutet nicht, dass diese Funktionen unter Linux oder macOS nicht verfügbar sind.

## <a name="platform-invoke-pinvoke"></a>Plattformaufruf (P/Invoke)

P/Invoke ist eine Technologie, die Ihnen den Zugriff auf Strukturen, Rückrufe und Funktionen in nicht verwalteten Bibliotheken von verwaltetem Code aus ermöglicht. Der Großteil der P/Invoke-API ist in zwei Namespaces enthalten: `System` und `System.Runtime.InteropServices`. Über diese beiden Namespaces können Sie auf die Attribute zugreifen, die beschreiben, wie Sie mit der nativen Komponente kommunizieren möchten.

Beginnen wir mit dem gängigsten Beispiel, dem Aufruf nicht verwalteter Funktionen im Ihrem verwalteten Code. Wir zeigen ein Meldungsfeld aus einer Befehlszeilenanwendung:

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

Das obige Beispiel ist recht einfach, zeigt jedoch, was zum Aufrufen nicht verwalteter Funktionen von verwaltetem Code aus erforderlich ist. Gehen wir das Beispiel schrittweise durch:

*   Zeile 1 zeigt die using-Anweisung für `System.Runtime.InteropServices`. Dies ist der Namespace, der alle benötigten Elemente enthält.
*   In Zeile 5 wird das `DllImport`-Attribut eingeführt. Dieses Attribut ist äußerst wichtig, da es der Runtime mitteilt, dass die nicht verwaltete DLL geladen werden soll. Dabei handelt es sich um die DLL, in der der Aufruf erfolgen soll.
*   Zeile 6 ist der Kern der P/Invoke-Funktion. Sie definiert eine verwaltete Methode, die **genau dieselbe Signatur** aufweist wie die nicht verwaltete Methode. Wie Sie sehen, enthält die Deklaration ein neues Schlüsselwort, `extern`. Dieses teilt der Runtime mit, dass es sich um eine externe Methode handelt und dass die Runtime die Methode bei Aufruf in der im `DllImport`-Attribut angegebenen DLL findet.

Der Rest des Beispiels besteht nur aus dem Aufruf der Methode, der wie bei jeder anderen verwalteten Methode erfolgt.

Das Beispiel ist für macOS ähnlich. Eine Sache, die geändert werden muss, ist natürlich der Name der Bibliothek im `DllImport`-Attribut, da macOS ein anderes Schema für die Benennung dynamischer Bibliotheken verwendet. Das Beispiel unten verwendet die `getpid(2)`-Funktion, um die Prozess-ID der Anwendung abzurufen und in der Konsole auszugeben.

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc and define the method corresponding to the native function.
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

Unter Linux verhält es sich natürlich ähnlich. Der Funktionsname ist identisch, da es sich bei `getpid(2)` um einen [POSIX](https://en.wikipedia.org/wiki/POSIX)-Systemaufruf handelt.

```csharp
using System;
using System.Runtime.InteropServices;

namespace PInvokeSamples {
    public static class Program {

        // Import the libc and define the method corresponding to the native function.
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

### <a name="invoking-managed-code-from-unmanaged-code"></a>Aufrufen von verwaltetem Code von nicht verwaltetem Code aus

Selbstverständlich ermöglicht die Runtime die Kommunikation in beide Richtungen, sodass Sie verwaltete Artefakte über Funktionszeiger von nativen Funktionen aus aufrufen können. Einem Funktionszeiger in verwaltetem Code kommt ein **Delegat** am nächsten. Dieser wird verwendet, um Rückrufe von nativem Code an verwalteten Code zu ermöglichen.

Dieses Feature wird ähnlich dem oben beschriebenen Verfahren von verwaltetem zu nativem Code verwendet. Für einen bestimmten Rückruf definieren Sie einen Delegaten, der der Signatur entspricht, und übergeben Sie ihn an die externe Methode. Die Runtime übernimmt alles Weitere.

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
        static extern int EnumWindows(EnumWC hWnd, IntPtr lParam);

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

Bevor wir unser Beispiel durchgehen, sollten wir die Signaturen der nicht verwalteten Funktionen betrachten, mit denen wir arbeiten müssen. Die Funktion, die wir zum Auflisten aller Fenster aufrufen möchten, weist folgende Signatur auf: `BOOL EnumWindows (WNDENUMPROC lpEnumFunc, LPARAM lParam);`

Der erste Parameter ist ein Rückruf. Dieser Rückruf besitzt die folgende Signatur: `BOOL CALLBACK EnumWindowsProc (HWND hwnd, LPARAM lParam);`

In diesem Sinn betrachten wir das Beispiel:

*   Zeile 8 im Beispiel definiert einen Delegaten, der der Signatur des Rückrufs von nicht verwaltetem Code aus entspricht. Beachten Sie, wie die Typen LPARAM und HWND über `IntPtr` im verwalteten Code dargestellt werden.
*   In den Zeilen 10 und 11 wird die `EnumWindows`-Funktion über die user32.dll-Bibliothek eingeführt.
*   In den Zeilen 13 bis 16 wird der Delegat implementiert. In diesem einfachen Beispiel möchten wir nur das Handle an die Konsole ausgeben.
*   Abschließend wird in Zeile 19 die externe Methode aufgerufen und an den Delegaten übergeben.

Die Beispiele für Linux und macOS werden im Folgenden angezeigt. Hierfür verwenden wir die `ftw`-Funktion, die in `libc` zu finden ist, der C-Bibliothek. Anhand dieser Funktion werden die Verzeichnishierarchien durchlaufen. Sie verwendet einen Zeiger auf eine Funktion als einen ihrer Parameter. Diese Funktion besitzt die folgende Signatur: `int (*fn) (const char *fpath, const struct stat *sb, int typeflag)`.

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

Im macOS-Beispiel wird die gleiche Funktion verwendet. Der einzige Unterschied ist das Argument für das `DllImport`-Attribut, da macOS `libc` an einer anderen Stelle speichert.

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

Beide oben aufgeführten Beispiele hängen von Parametern ab, und in beiden Fällen werden die Parameter als verwaltete Typen angegeben. Die Runtime reagiert demgemäß und verarbeitet diese in ihren Entsprechungen auf der anderen Seite. Da dieser Vorgang für das Schreiben von hochwertigem nativem Interopcode entscheidend ist, sehen wir uns an, was beim _Marshallen_ der Typen durch die Runtime geschieht.

## <a name="type-marshalling"></a>Marshallen von Typen

Das **Marshallen** bezeichnet den Vorgang zum Umwandeln von Typen, wenn diese die verwaltete Grenze zu nativem Code und umgekehrt überschreiten.

Das Marshallen ist erforderlich, weil sich die Typen in verwaltetem und nicht verwaltetem Code unterscheiden. In verwaltetem Code verwenden Sie z.B. einen `String`-Typ, während Zeichenfolgen im nicht verwalteten Bereich Unicode (Breitzeichen), Nicht-Unicode, mit Null endend, ASCII usw. sein können. Standardmäßig versucht das P/Invoke-Subsystem, die richtige Aktion basierend auf dem Standardverhalten durchzuführen, das in [MSDN](https://msdn.microsoft.com/library/zah6xy75.aspx) beschrieben wird. In Situationen, in denen Sie eine zusätzliche Kontrolle benötigen, können Sie jedoch das `MarshalAs`-Attribut verwenden, um anzugeben, welcher Typ auf der nicht verwalteten Seite erwartet wird. Wenn die Zeichenfolge beispielsweise als nicht mit Null endende ANSI-Zeichenfolge gesendet werden soll, können wir dies folgendermaßen erreichen:

```csharp
[DllImport("somenativelibrary.dll"]
static extern int MethodA([MarshalAs(UnmanagedType.LPStr)] string parameter);

```

### <a name="marshalling-classes-and-structs"></a>Marshallen von Klassen und Strukturen

Ein weiterer Aspekt des Marshallens von Typen ist die Übergabe einer Struktur an eine nicht verwaltete Methode. Einige der nicht verwalteten Methoden erfordern beispielsweise eine Struktur als Parameter. In diesen Fällen müssen wir eine entsprechende Struktur oder eine Klasse im verwalteten Bereich erstellen, um sie als Parameter zu verwenden. Allerdings reicht das Definieren der Klasse nicht aus, wir müssen dem Marshaller außerdem mitteilen, wie Felder in der Klasse der nicht verwalteten Struktur zuzuordnen sind. An dieser Stelle komm das `StructLayout`-Attribut ins Spiel.

```csharp
[DllImport("kernel32.dll")]
static extern void GetSystemTime(SystemTime systemTime);

[StructLayout(LayoutKind.Sequential)]
class SystemTime {
    public ushort Year;
    public ushort Month;
    public ushort DayOfWeek;
    public ushort Day;
    public ushort Hour;
    public ushort Minute;
    public ushort Second;
    public ushort Milsecond;
}

public static void Main(string[] args) {
    SystemTime st = new SystemTime();
    GetSystemTime(st);
    Console.WriteLine(st.Year);
}

```

Das obige Beispiel zeigt ein einfaches Beispiel für einen Aufruf in der `GetSystemTime()`-Funktion. Der interessante Teil befindet sich in Zeile 4\. Das Attribut gibt an, dass die Felder der Klasse sequenziell der Struktur auf der anderen (nicht verwalteten) Seite zugeordnet werden sollen. Dies bedeutet, dass die Benennung der Felder nicht wichtig ist, sondern nur deren Reihenfolge, da diese der nicht verwalteten Struktur entsprechen muss, wie unten gezeigt:

```c
typedef struct _SYSTEMTIME {
  WORD wYear;
  WORD wMonth;
  WORD wDayOfWeek;
  WORD wDay;
  WORD wHour;
  WORD wMinute;
  WORD wSecond;
  WORD wMilliseconds;
} SYSTEMTIME, *PSYSTEMTIME*;

```

Das Linux- und macOS-Beispiel hierfür haben wir bereits im vorherigen Beispiel gesehen. Es wird unten noch einmal aufgeführt.

```csharp
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

```

Die `StatClass`-Klasse stellt eine Struktur dar, die vom `stat`-Systemaufruf auf UNIX-Systemen zurückgegeben wird. Sie stellt Informationen über eine bestimmte Datei dar. Die oben gezeigte Klasse ist die stat-Strukturdarstellung in verwaltetem Code. Wiederum müssen die Felder in der Klasse derselben Reihenfolge entsprechen wie die native Struktur. (Sie finden diese über Manpages in Ihrer bevorzugten UNIX-Implementierung.) Zudem müssen Sie denselben zugrunde liegenden Typ aufweisen.

## <a name="more-resources"></a>Weitere Ressourcen

*   [PInvoke.NET-Wiki](http://www.pinvoke.net) ist eine ausgezeichnete Wiki-Seite mit Informationen zu gängigen Win32-APIs und deren Aufruf.
*   [P/Invoke auf MSDN](https://msdn.microsoft.com/library/zbz07712.aspx)
*   [Mono-Dokumentation zu P/Invoke](http://www.mono-project.com/docs/advanced/pinvoke/)

