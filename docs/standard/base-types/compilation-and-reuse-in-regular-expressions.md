---
title: "Kompilierung und Wiederverwendung in regulären Ausdrücken"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 76acdf2d0d2f7805ec78ea44136bfc63441b9bc9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="compilation-and-reuse-in-regular-expressions"></a>Kompilierung und Wiederverwendung in regulären Ausdrücken
Sie können die Leistung von Anwendungen optimieren, die umfangreichen Gebrauch von regulären Ausdrücken machen, wenn Sie verstehen, wie das Modul für reguläre Ausdrücke Ausdrücke kompiliert, und wie reguläre Ausdrücke zwischengespeichert werden. Dieses Thema behandelt das Kompilieren und das Zwischenspeichern.  
  
## <a name="compiled-regular-expressions"></a>Kompilierte reguläre Ausdrücke  
 Standardmäßig kompiliert das Modul für reguläre Ausdrücke einen regulären Ausdruck in eine Sequenz von internen Anweisungen (hierbei handelt es sich um Codes auf höherer Ebene, die sich von Microsoft Intermediate Language – MSIL – unterscheiden). Wenn das Modul einen regulären Ausdruck ausführt, interpretiert es die internen Codes.  
  
 Wenn eine <xref:System.Text.RegularExpressions.Regex> -Objekt erstellt wird, mit der <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> Option kompiliert den regulären Ausdruck an explizite MSIL-Code anstelle auf hoher Ebene reguläre interne Anweisungen. So kann der Just-in-Time-Compiler (JIT) von .NET den Ausdruck zur Leistungssteigerung in nativen Maschinencode konvertieren.  
  
Allerdings kann generierte MSIL nicht entladen werden. Die einzige Möglichkeit zum Entladen von Code ist das Entladen einer gesamten Anwendungsdomäne (d.h., dass Sie Ihren gesamten Anwendungscode entladen). Effektiv, wenn ein regulärer Ausdruck mit kompiliert wurde der <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> aus, die nie die von den kompilierten Ausdruck verwendeten Ressourcen frei, auch wenn der reguläre Ausdruck erstellt wurde eine <xref:System.Text.RegularExpressions.Regex> -Objekt, das selbst in die Garbagecollection freigegeben wird.  
  
 Sie müssen darauf achten, um die Anzahl von anderen regulären Ausdrücken begrenzen Sie kompilieren Sie mit der <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> Option aus, um zu vermeiden, zu viele Ressourcen beanspruchen. Wenn eine Anwendung eine große bzw. unbegrenzte Zahl von regulären Ausdrücken verwenden muss, sollte jeder Ausdruck interpretiert, nicht kompiliert werden. Jedoch wenn wiederholt eine kleine Anzahl von regulären Ausdrücken verwendet werden, sie sollten mit kompiliert werden <xref:System.Text.RegularExpressions.RegexOptions.Compiled?displayProperty=nameWithType> für eine bessere Leistung. Eine Alternative ist die Verwendung von vorkompilierte reguläre Ausdrücke. Sie können alle Ihre Ausdrücke in eine wiederverwendbare DLL kompilieren Sie mithilfe der <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A> Methode. Dadurch müssen zur Laufzeit kompiliert, während noch profitieren von der Geschwindigkeit des kompilierte reguläre Ausdrücke.  
  
## <a name="the-regular-expressions-cache"></a>Der Cache für reguläre Ausdrücke  
 Zur Verbesserung der Leistung verwaltet das Modul für reguläre Ausdrücke einen anwendungsweiten Cache kompilierter regulärer Ausdrücke. Der Cache speichert Muster für reguläre Ausdrücke, die nur in statischen Methodenaufrufen verwendet werden. (An Instanzmethoden übergebene Muster für reguläre Ausdrücke werden nicht zwischengespeichert.) Dadurch wird vermieden, dass Ausdrücke bei jeder Verwendung erneut analysiert und in Bytecode höherer Ebene kompiliert werden müssen.  
  
 Die maximale Anzahl der zwischengespeicherten regulären Ausdrücke richtet sich nach dem Wert der `static` (`Shared` in Visual Basic) <xref:System.Text.RegularExpressions.Regex.CacheSize%2A?displayProperty=nameWithType> Eigenschaft. Standardmäßig speichert das Modul für reguläre Ausdrücke bis zu 15 kompilierte reguläre Ausdrücke zwischen. Wenn die Anzahl der kompilierten regulären Ausdrücke die Cachegröße überschreitet, wird der am längsten nicht verwendete reguläre Ausdruck verworfen und der neue reguläre Ausdruck zwischengespeichert.  
  
 Es gibt zwei Möglichkeiten, wie die Anwendung vorkompilierte reguläre Ausdrücke nutzen kann:  
  
-   Eine statische Methode mit der <xref:System.Text.RegularExpressions.Regex> Objekt, das den regulären Ausdruck definieren. Wenn Sie ein Muster für reguläre Ausdrücke verwenden, das bereits in einem anderen statischen Methodenaufruf definiert wurde, ruft das Modul für reguläre Ausdrücke dieses aus dem Cache ab. Ist dies nicht der Fall, kompiliert das Modul den regulären Ausdruck und fügt ihn dem Cache hinzu.  
  
-   Durch das Wiederverwenden einer vorhandenen <xref:System.Text.RegularExpressions.Regex> Objekt wie entsprechende Muster des regulären Ausdrucks benötigt wird.  
  
 Wegen des Aufwandes der Objektinstanziierung und Kompilierung regulärer Ausdrücke, erstellen und Zerstören von schnell zahlreiche <xref:System.Text.RegularExpressions.Regex> Objekte ist ein sehr aufwändiger Vorgang. Für Anwendungen, die eine große Anzahl von anderen regulären Ausdrücken verwendet, können Sie Optimieren der Leistung mithilfe der Aufrufe von statischen `Regex` Methoden und erhöhen die Größe des Caches für reguläre Ausdrücke durch.  
  
## <a name="see-also"></a>Siehe auch  
 [Reguläre Ausdrücke von .NET](../../../docs/standard/base-types/regular-expressions.md)
