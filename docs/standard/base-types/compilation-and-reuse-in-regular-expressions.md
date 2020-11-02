---
title: Kompilierung und Wiederverwendung in regulären Ausdrücken
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing text with regular expressions, compilation
- searching with regular expressions, compilation
- .NET regular expressions, engines
- .NET regular expressions, compilation
- regular expressions, compilation
- compilation, regular expressions
- pattern-matching with regular expressions, compilation
- regular expressions, engines
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
ms.openlocfilehash: fbf10c7f3b4ebf4db97b18b2a2ef165226a48027
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889477"
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>Kompilierung und Wiederverwendung in regulären Ausdrücken
Sie können die Leistung von Anwendungen optimieren, die umfangreichen Gebrauch von regulären Ausdrücken machen, wenn Sie verstehen, wie die Engine für reguläre Ausdrücke kompiliert, und wie reguläre Ausdrücke zwischengespeichert werden. Dieses Thema behandelt das Kompilieren und das Zwischenspeichern.  
  
## <a name="compiled-regular-expressions"></a>Kompilierte reguläre Ausdrücke  
 Standardmäßig kompiliert die Engine für reguläre Ausdrücke einen regulären Ausdruck in eine Sequenz von internen Anweisungen (hierbei handelt es sich um Codes auf höherer Ebene, die sich von Microsoft Intermediate Language – MSIL – unterscheiden). Wenn die Engine einen regulären Ausdruck ausführt, interpretiert sie die internen Codes.  
  
 Wenn ein <xref:System.Text.RegularExpressions.Regex>-Objekt mit der <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>-Option erstellt wird, kompiliert es den regulären Ausdruck in expliziten MSIL-Code und nicht in interne Anweisungen in regulären Ausdrücken auf hoher Ebene. So kann der Just-in-Time-Compiler (JIT) von .NET den Ausdruck zur Leistungssteigerung in nativen Maschinencode konvertieren.  Die Kosten für das Erstellen eines <xref:System.Text.RegularExpressions.Regex>-Objekts sind möglicherweise höher, aber die Kosten für die Durchführung eines Abgleichs sind wahrscheinlich deutlich geringer.

 Eine Alternative ist die Verwendung von vorkompilierten regulären Ausdrücken. Mit der <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>-Methode können Sie all Ihre Ausdrücke in eine wiederverwendbare DLL kompilieren. Hierdurch entfällt die Notwendigkeit für eine Kompilierung zur Laufzeit, und Sie profitieren gleichzeitig von der Schnelligkeit kompilierter regulärer Ausdrücke.  
  
## <a name="the-regular-expressions-cache"></a>Der Cache für reguläre Ausdrücke  
 Zur Verbesserung der Leistung verwaltet die Engine für reguläre Ausdrücke einen anwendungsweiten Cache kompilierter regulärer Ausdrücke. Der Cache speichert Muster für reguläre Ausdrücke, die nur in statischen Methodenaufrufen verwendet werden. (An Instanzmethoden übergebene Muster für reguläre Ausdrücke werden nicht zwischengespeichert.) Dadurch wird vermieden, dass Ausdrücke bei jeder Verwendung erneut analysiert und in Bytecode höherer Ebene kompiliert werden müssen.  
  
 Die maximale Anzahl der zwischengespeicherten regulären Ausdrücke wird durch den Wert der `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType>-Eigenschaft festgelegt. Standardmäßig speichert die Engine für reguläre Ausdrücke bis zu 15 kompilierte reguläre Ausdrücke zwischen. Wenn die Anzahl der kompilierten regulären Ausdrücke die Cachegröße überschreitet, wird der am längsten nicht verwendete reguläre Ausdruck verworfen und der neue reguläre Ausdruck zwischengespeichert.  
  
 Es gibt zwei Möglichkeiten, wie Ihre Anwendung reguläre Ausdrücke wiederverwenden kann:  
  
- Durch die Verwendung einer statischen Methode des <xref:System.Text.RegularExpressions.Regex>-Objekts zum Definieren des regulären Ausdrucks. Wenn Sie ein Muster für reguläre Ausdrücke verwenden, das bereits durch einen anderen statischen Methodenaufruf definiert wurde, ruft die Engine für reguläre Ausdrücke dieses aus dem Cache ab. Sofern nicht im Cache verfügbar, kompiliert die Engine den regulären Ausdruck und fügt ihn dem Cache hinzu.
  
- Durch die Wiederverwendung eines vorhandenen <xref:System.Text.RegularExpressions.Regex>-Objekts, solange sein Muster des regulären Ausdrucks benötigt wird.  
  
 Aufgrund des Mehraufwands, der durch die Objektinstanziierung und Kompilierung von regulären Ausdrücken anfällt, stellt das Erstellen und schnelle Löschen zahlreicher <xref:System.Text.RegularExpressions.Regex>-Objekte einen sehr kostspieligen Prozess dar. Sie können die Leistung von Anwendungen optimieren, die zahlreiche verschiedene reguläre Ausdrücke verwenden, indem Sie Aufrufe statischer `Regex`-Methoden verwenden und gegebenenfalls den Cache für reguläre Ausdrücke vergrößern.  
  
## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET](regular-expressions.md)
