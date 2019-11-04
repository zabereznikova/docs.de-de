---
title: Kompilierung und Wiederverwendung in regulären Ausdrücken
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing text with regular expressions, compilation
- searching with regular expressions, compilation
- .NET Framework regular expressions, engines
- .NET Framework regular expressions, compilation
- regular expressions, compilation
- compilation, regular expressions
- pattern-matching with regular expressions, compilation
- regular expressions, engines
ms.assetid: 182ec76d-5a01-4d73-996c-0b0d14fcea18
ms.openlocfilehash: 3e1dfe8373145286b03e503f038e267ff0d4c4f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091728"
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>Kompilierung und Wiederverwendung in regulären Ausdrücken
Sie können die Leistung von Anwendungen optimieren, die umfangreichen Gebrauch von regulären Ausdrücken machen, wenn Sie verstehen, wie die Engine für reguläre Ausdrücke kompiliert, und wie reguläre Ausdrücke zwischengespeichert werden. Dieses Thema behandelt das Kompilieren und das Zwischenspeichern.  
  
## <a name="compiled-regular-expressions"></a>Kompilierte reguläre Ausdrücke  
 Standardmäßig kompiliert die Engine für reguläre Ausdrücke einen regulären Ausdruck in eine Sequenz von internen Anweisungen (hierbei handelt es sich um Codes auf höherer Ebene, die sich von Microsoft Intermediate Language – MSIL – unterscheiden). Wenn die Engine einen regulären Ausdruck ausführt, interpretiert sie die internen Codes.  
  
 Wenn ein <xref:System.Text.RegularExpressions.Regex>-Objekt mit der <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>-Option erstellt wird, kompiliert es den regulären Ausdruck in expliziten MSIL-Code und nicht in interne Anweisungen in regulären Ausdrücken auf hoher Ebene. So kann der Just-in-Time-Compiler (JIT) von .NET den Ausdruck zur Leistungssteigerung in nativen Maschinencode konvertieren.  
  
Allerdings kann generierte MSIL nicht entladen werden. Die einzige Möglichkeit zum Entladen von Code ist das Entladen einer gesamten Anwendungsdomäne (d.h., dass Sie Ihren gesamten Anwendungscode entladen). Wenn ein regulärer Ausdruck mit der <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>-Option kompiliert wurde, gibt   nie die von dem kompilierten Ausdruck verwendeten Ressourcen frei, auch wenn der reguläre Ausdruck von einem <xref:System.Text.RegularExpressions.Regex>-Objekt erstellt wurde, das selbst für die Garbage Collection freigegeben wird.  
  
 Begrenzen Sie die Anzahl der verschiedenen regulären Ausdrücke, die Sie mit der <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType>-Option kompilieren, um einen zu hohen Ressourcenverbrauch zu vermeiden. Wenn eine Anwendung eine große bzw. unbegrenzte Zahl von regulären Ausdrücken verwenden muss, sollte jeder Ausdruck interpretiert, nicht kompiliert werden. Wenn jedoch eine kleine Anzahl von regulären Ausdrücken wiederholt verwendet wird, sollten sie zur Leistungsverbesserung mit <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> kompiliert werden. Eine Alternative ist die Verwendung von vorkompilierten regulären Ausdrücken. Mit der <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A>-Methode können Sie all Ihre Ausdrücke in eine wiederverwendbare DLL kompilieren. Hierdurch entfällt die Notwendigkeit für eine Kompilierung zur Laufzeit, und Sie profitieren gleichzeitig von der Schnelligkeit kompilierter regulärer Ausdrücke.  
  
## <a name="the-regular-expressions-cache"></a>Der Cache für reguläre Ausdrücke  
 Zur Verbesserung der Leistung verwaltet die Engine für reguläre Ausdrücke einen anwendungsweiten Cache kompilierter regulärer Ausdrücke. Der Cache speichert Muster für reguläre Ausdrücke, die nur in statischen Methodenaufrufen verwendet werden. (An Instanzmethoden übergebene Muster für reguläre Ausdrücke werden nicht zwischengespeichert.) Dadurch wird vermieden, dass Ausdrücke bei jeder Verwendung erneut analysiert und in Bytecode höherer Ebene kompiliert werden müssen.  
  
 Die maximale Anzahl der zwischengespeicherten regulären Ausdrücke wird durch den Wert der `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType>-Eigenschaft festgelegt. Standardmäßig speichert die Engine für reguläre Ausdrücke bis zu 15 kompilierte reguläre Ausdrücke zwischen. Wenn die Anzahl der kompilierten regulären Ausdrücke die Cachegröße überschreitet, wird der am längsten nicht verwendete reguläre Ausdruck verworfen und der neue reguläre Ausdruck zwischengespeichert.  
  
 Es gibt zwei Möglichkeiten, wie die Anwendung vorkompilierte reguläre Ausdrücke nutzen kann:  
  
- Durch die Verwendung einer statischen Methode des <xref:System.Text.RegularExpressions.Regex>-Objekts zum Definieren des regulären Ausdrucks. Wenn Sie ein Muster für reguläre Ausdrücke verwenden, das bereits in einem anderen statischen Methodenaufruf definiert wurde, ruft die Engine für reguläre Ausdrücke dieses aus dem Cache ab. Ist dies nicht der Fall, kompiliert die Engine den regulären Ausdruck und fügt ihn dem Cache hinzu.  
  
- Durch die Wiederverwendung eines vorhandenen <xref:System.Text.RegularExpressions.Regex>-Objekts, solange sein Muster des regulären Ausdrucks benötigt wird.  
  
 Aufgrund des Mehraufwands, der durch die Objektinstanziierung und Kompilierung von regulären Ausdrücken anfällt, stellt das Erstellen und schnelle Löschen zahlreicher <xref:System.Text.RegularExpressions.Regex>-Objekte einen sehr kostspieligen Prozess dar. Sie können die Leistung von Anwendungen optimieren, die zahlreiche verschiedene reguläre Ausdrücke verwenden, indem Sie Aufrufe statischer `Regex`-Methoden verwenden und gegebenenfalls den Cache für reguläre Ausdrücke vergrößern.  
  
## <a name="see-also"></a>Siehe auch

- [Reguläre Ausdrücke von .NET](../../../docs/standard/base-types/regular-expressions.md)
