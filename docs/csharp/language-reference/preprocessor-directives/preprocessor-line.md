---
title: '#line (C#-Referenz)'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: 08ba94ec3f1799f858e098bd2c0e059b7f45af2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289268"
---
# <a name="line-c-reference"></a><span data-ttu-id="c23a2-102">#line (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c23a2-102">#line (C# Reference)</span></span>
<span data-ttu-id="c23a2-103">Mit `#line` können Sie die Zeilennummer des Compilers und (optional) die Dateinamenausgabe für Fehler und Warnungen bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c23a2-103">`#line` lets you modify the compiler's line number and (optionally) the file name output for errors and warnings.</span></span> <span data-ttu-id="c23a2-104">Dieses Beispiel zeigt, wie Sie zwei Warnungen melden können, die Zeilennummern zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c23a2-104">This example shows how to report two warnings associated with line numbers.</span></span> <span data-ttu-id="c23a2-105">Die `#line 200`-Anweisung erzwingt die Zeilennummer 200 (obwohl der Standardwert #7 ist), und bis zur nächsten #line-Anweisung wird der Dateiname als „Special“ gemeldet.</span><span class="sxs-lookup"><span data-stu-id="c23a2-105">The `#line 200` directive forces the line number to be 200 (although the default is #7) and until the next #line directive, the filename will be reported as "Special".</span></span> <span data-ttu-id="c23a2-106">Die #line-Standardanweisung legt die Zeilennummerierung auf deren Standardnummerierung fest, bei der die Zeilen gezählt werden, die von der vorherigen Anweisung neu nummeriert wurden.</span><span class="sxs-lookup"><span data-stu-id="c23a2-106">The #line default directive returns the line numbering to its default numbering, which counts the lines that were renumbered by the previous directive.</span></span>  
  
```csharp
class MainClass  
{  
    static void Main()  
    {  
#line 200 "Special"  
        int i;    // CS0168 on line 200  
        int j;    // CS0168 on line 201  
#line default  
        char c;   // CS0168 on line 9  
        float f;  // CS0168 on line 10  
#line hidden // numbering not affected  
        string s;   
        double d; // CS0168 on line 13  
    }  
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="c23a2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c23a2-107">Remarks</span></span>  
 <span data-ttu-id="c23a2-108">Die `#line`-Anweisung könnte in einem automatischen Zwischenschritt im Buildprozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c23a2-108">The `#line` directive might be used in an automated, intermediate step in the build process.</span></span> <span data-ttu-id="c23a2-109">Wenn beispielsweise Zeilen aus der ursprünglichen Quellcodedatei entfernt würden, Sie jedoch trotzdem möchten, dass der Compiler eine Ausgabe basierend auf der ursprünglichen Zeilennummerierung in der Datei generiert, könnten Sie Zeilen entfernen und anschließend die ursprüngliche Zeilennummerierung mit `#line` simulieren.</span><span class="sxs-lookup"><span data-stu-id="c23a2-109">For example, if lines were removed from the original source code file, but you still wanted the compiler to generate output based on the original line numbering in the file, you could remove lines and then simulate the original line numbering with `#line`.</span></span>  
  
 <span data-ttu-id="c23a2-110">Die `#line hidden`-Anweisung blendet die aufeinander folgenden Zeilen im Debugger aus, sodass alle Zeilen zwischen einer `#line hidden`-Anweisung und der nächsten `#line`-Anweisung (vorausgesetzt es handelt sich nicht um eine weitere `#line hidden`-Anweisung) übersprungen werden, wenn der Entwickler den Code durchläuft.</span><span class="sxs-lookup"><span data-stu-id="c23a2-110">The `#line hidden` directive hides the successive lines from the debugger, such that when the developer steps through the code, any lines between a `#line hidden` and the next `#line` directive (assuming that it is not another `#line hidden` directive) will be stepped over.</span></span> <span data-ttu-id="c23a2-111">Diese Option kann auch dazu verwendet werden, ASP.NET die Möglichkeit zu geben, zwischen benutzerdefiniertem und computergeneriertem Code zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c23a2-111">This option can also be used to allow ASP.NET to differentiate between user-defined and machine-generated code.</span></span> <span data-ttu-id="c23a2-112">Obwohl ASP.NET der primäre Anwender dieser Funktion ist, ist es wahrscheinlich, dass mehr Quellgeneratoren sich diese zunutze machen werden.</span><span class="sxs-lookup"><span data-stu-id="c23a2-112">Although ASP.NET is the primary consumer of this feature, it is likely that more source generators will make use of it.</span></span>  
  
 <span data-ttu-id="c23a2-113">Ein `#line hidden`-Anweisung hat keine Auswirkung auf Dateinamen oder Zeilennummern bei der Fehlerberichterstattung.</span><span class="sxs-lookup"><span data-stu-id="c23a2-113">A `#line hidden` directive does not affect file names or line numbers in error reporting.</span></span> <span data-ttu-id="c23a2-114">Das bedeutet, wenn ein Fehler in einem ausgeblendeten Block gefunden wird, meldet der Compiler den aktuellen Dateinamen und die Zeilennummer des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="c23a2-114">That is, if an error is encountered in a hidden block, the compiler will report the current file name and line number of the error.</span></span>  
  
 <span data-ttu-id="c23a2-115">Die `#line filename`-Anweisung gibt den Dateinamen an, von dem Sie möchten, dass er in der Compilerausgabe erscheint.</span><span class="sxs-lookup"><span data-stu-id="c23a2-115">The `#line filename` directive specifies the file name you want to appear in the compiler output.</span></span> <span data-ttu-id="c23a2-116">Standardmäßig wird der tatsächliche Name der Quellcodedatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="c23a2-116">By default, the actual name of the source code file is used.</span></span> <span data-ttu-id="c23a2-117">Der Dateiname muss in doppelten Anführungszeichen ("") und hinter einer Zeilennummer stehen.</span><span class="sxs-lookup"><span data-stu-id="c23a2-117">The file name must be in double quotation marks ("") and must be preceded by a line number.</span></span>  
  
 <span data-ttu-id="c23a2-118">Eine Quellcodedatei kann über eine beliebige Anzahl von `#line`-Anweisungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="c23a2-118">A source code file can have any number of `#line` directives.</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="c23a2-119">Beispiel 1</span><span class="sxs-lookup"><span data-stu-id="c23a2-119">Example 1</span></span>  
 <span data-ttu-id="c23a2-120">Das folgende Beispiel zeigt, wie der Debugger die ausgeblendeten Zeilen im Code ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c23a2-120">The following example shows how the debugger ignores the hidden lines in the code.</span></span> <span data-ttu-id="c23a2-121">Wenn Sie das Beispiel ausführen, werden drei Textzeilen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c23a2-121">When you run the example, it will display three lines of text.</span></span> <span data-ttu-id="c23a2-122">Wenn Sie jedoch wie im Beispiel gezeigt einen Haltepunkt setzen und F10 drücken, um den Code zu durchlaufen, werden Sie feststellen, dass der Debugger die ausgeblendete Zeile ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c23a2-122">However, when you set a break point, as shown in the example, and hit F10 to step through the code, you will notice that the debugger ignores the hidden line.</span></span> <span data-ttu-id="c23a2-123">Beachten Sie zudem, dass die ausgeblendete Zeile selbst dann vom Debugger ignoriert wird, wenn Sie einen Haltepunkt an dieser Zeile setzen.</span><span class="sxs-lookup"><span data-stu-id="c23a2-123">Notice also that even if you set a break point at the hidden line, the debugger will still ignore it.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c23a2-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c23a2-124">See Also</span></span>  
 [<span data-ttu-id="c23a2-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c23a2-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="c23a2-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c23a2-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c23a2-127">C#-Präprozessoranweisungen</span><span class="sxs-lookup"><span data-stu-id="c23a2-127">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
