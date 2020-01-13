---
title: '#line – C#-Referenz'
ms.date: 07/20/2015
f1_keywords:
- '#line'
helpviewer_keywords:
- '#line directive [C#]'
ms.assetid: 6439e525-5dd5-4acb-b8ea-efabb32ff95b
ms.openlocfilehash: 79033fa652af62c76d54737fbf0a0b47cf3aae99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712493"
---
# <a name="line-c-reference"></a>#line (C#-Referenz)

Mit `#line` können Sie die Zeilennummer des Compilers und (optional) die Dateinamensausgabe für Fehler und Warnungen bearbeiten.

Das folgende Beispiel zeigt, wie Sie zwei Warnungen melden können, die Zeilennummern zugeordnet sind. Die `#line 200`-Anweisung erzwingt die Nummer 200 der nächsten Zeile (obwohl der Standardwert #6 ist), und bis zur nächsten `#line`-Anweisung wird der Dateiname als „Special“ gemeldet. Die `#line default`-Standardanweisung legt die Zeilennummerierung auf deren Standardnummerierung fest, bei der die Zeilen gezählt werden, die von der vorherigen Anweisung neu nummeriert wurden.

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

Bei der Kompilierung wird die folgende Ausgabe erzeugt:

```console
Special(200,13): warning CS0168: The variable 'i' is declared but never used
Special(201,13): warning CS0168: The variable 'j' is declared but never used
MainClass.cs(9,14): warning CS0168: The variable 'c' is declared but never used
MainClass.cs(10,15): warning CS0168: The variable 'f' is declared but never used
MainClass.cs(12,16): warning CS0168: The variable 's' is declared but never used
MainClass.cs(13,16): warning CS0168: The variable 'd' is declared but never used
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

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Präprozessoranweisungen](./index.md)
