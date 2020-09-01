---
description: '#line – C#-Referenz'
title: '#line – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: e2a5ecb6c29184123b8a88ae1b12caf24ec7296a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137993"
---
# <a name="line-c-reference"></a><span data-ttu-id="45c2a-103">#line (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="45c2a-103">#line (C# Reference)</span></span>

<span data-ttu-id="45c2a-104">Mit `#line` können Sie die Zeilennummer des Compilers und (optional) die Dateinamensausgabe für Fehler und Warnungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="45c2a-104">`#line` lets you modify the compiler's line numbering and (optionally) the file name output for errors and warnings.</span></span>

<span data-ttu-id="45c2a-105">Das folgende Beispiel zeigt, wie Sie zwei Warnungen melden können, die Zeilennummern zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="45c2a-105">The following example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="45c2a-106">Die `#line 200`-Anweisung erzwingt die Nummer 200 der nächsten Zeile (obwohl der Standardwert #6 ist), und bis zur nächsten `#line`-Anweisung wird der Dateiname als „Special“ gemeldet.</span><span class="sxs-lookup"><span data-stu-id="45c2a-106">The `#line 200` directive forces the next line's number to be 200 (although the default is #6), and until the next `#line` directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="45c2a-107">Die `#line default`-Standardanweisung legt die Zeilennummerierung auf deren Standardnummerierung fest, bei der die Zeilen gezählt werden, die von der vorherigen Anweisung neu nummeriert wurden.</span><span class="sxs-lookup"><span data-stu-id="45c2a-107">The `#line default` directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>

```csharp
class MainClass
{
    static void Main()
    {
#line 200 "Special"
        int i;
        int j;
#line default
        char c;
        float f;
#line hidden // numbering not affected
        string s;
        double d;
    }
}
```

<span data-ttu-id="45c2a-108">Bei der Kompilierung wird die folgende Ausgabe erzeugt:</span><span class="sxs-lookup"><span data-stu-id="45c2a-108">Compilation produces the following output:</span></span>

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
```

## <a name="remarks"></a><span data-ttu-id="45c2a-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="45c2a-109">Remarks</span></span>

<span data-ttu-id="45c2a-110">Die `#line`-Anweisung könnte in einem automatischen Zwischenschritt im Buildprozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="45c2a-110">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="45c2a-111">Wenn beispielsweise Zeilen aus der ursprünglichen Quellcodedatei entfernt würden, Sie jedoch trotzdem möchten, dass der Compiler eine Ausgabe basierend auf der ursprünglichen Zeilennummerierung in der Datei generiert, könnten Sie Zeilen entfernen und anschließend die ursprüngliche Zeilennummerierung mit `#line` simulieren.</span><span class="sxs-lookup"><span data-stu-id="45c2a-111">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>

<span data-ttu-id="45c2a-112">Die `#line hidden`-Anweisung blendet die aufeinander folgenden Zeilen im Debugger aus, sodass alle Zeilen zwischen einer `#line hidden`-Anweisung und der nächsten `#line`-Anweisung (vorausgesetzt es handelt sich nicht um eine weitere `#line hidden`-Anweisung) übersprungen werden, wenn der Entwickler den Code durchläuft.</span><span class="sxs-lookup"><span data-stu-id="45c2a-112">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="45c2a-113">Diese Option kann auch dazu verwendet werden, ASP.NET die Möglichkeit zu geben, zwischen benutzerdefiniertem und computergeneriertem Code zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="45c2a-113">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="45c2a-114">Obwohl ASP.NET der primäre Anwender dieser Funktion ist, ist es wahrscheinlich, dass mehr Quellgeneratoren sich diese zunutze machen werden.</span><span class="sxs-lookup"><span data-stu-id="45c2a-114">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>

<span data-ttu-id="45c2a-115">Ein `#line hidden`-Anweisung hat keine Auswirkung auf Dateinamen oder Zeilennummern bei der Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="45c2a-115">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="45c2a-116">Das bedeutet, wenn ein Fehler in einem ausgeblendeten Block gefunden wird, meldet der Compiler den aktuellen Dateinamen und die Zeilennummer des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="45c2a-116">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>

<span data-ttu-id="45c2a-117">Die `#line filename`-Anweisung gibt den Dateinamen an, von dem Sie möchten, dass er in der Compilerausgabe erscheint.</span><span class="sxs-lookup"><span data-stu-id="45c2a-117">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="45c2a-118">Standardmäßig wird der tatsächliche Name der Quellcodedatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="45c2a-118">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="45c2a-119">Der Dateiname muss in doppelten Anführungszeichen ("") und hinter einer Zeilennummer stehen.</span><span class="sxs-lookup"><span data-stu-id="45c2a-119">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>

<span data-ttu-id="45c2a-120">Eine Quellcodedatei kann über eine beliebige Anzahl von `#line`-Anweisungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="45c2a-120">A source code file can have any number of `#line` directives.</span></span>

## <a name="example-1"></a><span data-ttu-id="45c2a-121">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="45c2a-121">Example 1</span></span>

<span data-ttu-id="45c2a-122">Das folgende Beispiel zeigt, wie der Debugger die ausgeblendeten Zeilen im Code ignoriert.</span><span class="sxs-lookup"><span data-stu-id="45c2a-122">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="45c2a-123">Wenn Sie das Beispiel ausführen, werden drei Textzeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="45c2a-123">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="45c2a-124">Wenn Sie jedoch wie im Beispiel gezeigt einen Haltepunkt setzen und F10 drücken, um den Code zu durchlaufen, werden Sie feststellen, dass der Debugger die ausgeblendete Zeile ignoriert.</span><span class="sxs-lookup"><span data-stu-id="45c2a-124">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="45c2a-125">Beachten Sie zudem, dass die ausgeblendete Zeile selbst dann vom Debugger ignoriert wird, wenn Sie einen Haltepunkt an dieser Zeile setzen.</span><span class="sxs-lookup"><span data-stu-id="45c2a-125">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>

```csharp
// preprocessor_linehidden.cs
using System;
class MainClass
{
    static void Main()
    {
        Console.WriteLine("Normal line #1."); // Set break point here.
#line hidden
        Console.WriteLine("Hidden line.");
#line default
        Console.WriteLine("Normal line #2.");
    }
}
```

## <a name="see-also"></a><span data-ttu-id="45c2a-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45c2a-126">See also</span></span>

- [<span data-ttu-id="45c2a-127">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="45c2a-127">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="45c2a-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="45c2a-128">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="45c2a-129">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="45c2a-129">C# Preprocessor Directives</span></span>](./index.md)
