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
# <a name="line-c-reference"></a>#line (C#-Referenz)
Mit `#line` können Sie die Zeilennummer des Compilers und (optional) die Dateinamenausgabe für Fehler und Warnungen bearbeiten. Dieses Beispiel zeigt, wie Sie zwei Warnungen melden können, die Zeilennummern zugeordnet sind. Die `#line 200`-Anweisung erzwingt die Zeilennummer 200 (obwohl der Standardwert #7 ist), und bis zur nächsten #line-Anweisung wird der Dateiname als „Special“ gemeldet. Die #line-Standardanweisung legt die Zeilennummerierung auf deren Standardnummerierung fest, bei der die Zeilen gezählt werden, die von der vorherigen Anweisung neu nummeriert wurden.  
  
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
  
## <a name="remarks"></a>Hinweise  
 Die `#line`-Anweisung könnte in einem automatischen Zwischenschritt im Buildprozess verwendet werden. Wenn beispielsweise Zeilen aus der ursprünglichen Quellcodedatei entfernt würden, Sie jedoch trotzdem möchten, dass der Compiler eine Ausgabe basierend auf der ursprünglichen Zeilennummerierung in der Datei generiert, könnten Sie Zeilen entfernen und anschließend die ursprüngliche Zeilennummerierung mit `#line` simulieren.  
  
 Die `#line hidden`-Anweisung blendet die aufeinander folgenden Zeilen im Debugger aus, sodass alle Zeilen zwischen einer `#line hidden`-Anweisung und der nächsten `#line`-Anweisung (vorausgesetzt es handelt sich nicht um eine weitere `#line hidden`-Anweisung) übersprungen werden, wenn der Entwickler den Code durchläuft. Diese Option kann auch dazu verwendet werden, ASP.NET die Möglichkeit zu geben, zwischen benutzerdefiniertem und computergeneriertem Code zu unterscheiden. Obwohl ASP.NET der primäre Anwender dieser Funktion ist, ist es wahrscheinlich, dass mehr Quellgeneratoren sich diese zunutze machen werden.  
  
 Ein `#line hidden`-Anweisung hat keine Auswirkung auf Dateinamen oder Zeilennummern bei der Fehlerberichterstattung. Das bedeutet, wenn ein Fehler in einem ausgeblendeten Block gefunden wird, meldet der Compiler den aktuellen Dateinamen und die Zeilennummer des Fehlers.  
  
 Die `#line filename`-Anweisung gibt den Dateinamen an, von dem Sie möchten, dass er in der Compilerausgabe erscheint. Standardmäßig wird der tatsächliche Name der Quellcodedatei verwendet. Der Dateiname muss in doppelten Anführungszeichen ("") und hinter einer Zeilennummer stehen.  
  
 Eine Quellcodedatei kann über eine beliebige Anzahl von `#line`-Anweisungen verfügen.  
  
## <a name="example-1"></a>Beispiel 1  
 Das folgende Beispiel zeigt, wie der Debugger die ausgeblendeten Zeilen im Code ignoriert. Wenn Sie das Beispiel ausführen, werden drei Textzeilen angezeigt. Wenn Sie jedoch wie im Beispiel gezeigt einen Haltepunkt setzen und F10 drücken, um den Code zu durchlaufen, werden Sie feststellen, dass der Debugger die ausgeblendete Zeile ignoriert. Beachten Sie zudem, dass die ausgeblendete Zeile selbst dann vom Debugger ignoriert wird, wenn Sie einen Haltepunkt an dieser Zeile setzen.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Präprozessoranweisungen](../../../csharp/language-reference/preprocessor-directives/index.md)
