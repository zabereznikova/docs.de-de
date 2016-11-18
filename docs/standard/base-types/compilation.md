---
title: "Kompilierung und Wiederverwendung in regulären Ausdrücken"
description: "Kompilierung und Wiederverwendung in regulären Ausdrücken"
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3adea434-e2ed-4023-b4f5-b0608b4cf53f
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: e14e386a04c64726e4eacb63dc8855a356a18ba0

---

# <a name="compilation-and-reuse-in-regular-expressions"></a>Kompilierung und Wiederverwendung in regulären Ausdrücken

Sie können die Leistung von Anwendungen optimieren, die umfangreichen Gebrauch von regulären Ausdrücken machen, wenn Sie verstehen, wie das Modul für reguläre Ausdrücke Ausdrücke kompiliert, und wie reguläre Ausdrücke zwischengespeichert werden. Dieses Thema behandelt das Kompilieren und das Zwischenspeichern.

## <a name="compiled-regular-expressions"></a>Kompilierte reguläre Ausdrücke

Standardmäßig kompiliert das Modul für reguläre Ausdrücke einen regulären Ausdruck in eine Sequenz von internen Anweisungen (hierbei handelt es sich um Codes auf höherer Ebene, die sich von Microsoft Intermediate Language – MSIL – unterscheiden). Wenn das Modul einen regulären Ausdruck ausführt, interpretiert es die internen Codes.

Wenn ein [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt mit der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option erstellt wird, kompiliert es den regulären Ausdruck in expliziten MSIL-Code und nicht in interne Anweisungen in regulären Ausdrücken auf oberster Ebene. So kann der Just-in-Time-Compiler (JIT) von .NET den Ausdruck zur Leistungssteigerung in nativen Maschinencode konvertieren.

Allerdings kann generierte MSIL nicht entladen werden. Die einzige Möglichkeit zum Entladen von Code ist das Entladen einer gesamten Anwendungsdomäne (d.h., dass Sie Ihren gesamten Anwendungscode entladen). Wenn ein regulärer Ausdruck mit der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option kompiliert wurde, gibt .NET nie die von dem kompilierten Ausdruck verwendeten Ressourcen frei, auch wenn der reguläre Ausdruck von einem [Regex](xref:System.Text.RegularExpressions.Regex)-Objekt erstellt wurde, das selbst für die Garbage Collection freigegeben wird.

Begrenzen Sie die Anzahl der verschiedenen regulären Ausdrücke, die Sie mit der [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled)-Option kompilieren, um zu vermeiden, zu viele Ressourcen zu beanspruchen. Wenn eine Anwendung eine große bzw. unbegrenzte Zahl von regulären Ausdrücken verwenden muss, sollte jeder Ausdruck interpretiert, nicht kompiliert werden. Wenn jedoch eine kleine Anzahl von regulären Ausdrücken wiederholt verwendet wird, sollten sie zur Leistungsverbesserung mit [RegexOptions.Compiled](xref:System.Text.RegularExpressions.RegexOptions.Compiled) kompiliert werden. 

## <a name="the-regular-expressions-cache"></a>Der Cache für reguläre Ausdrücke

Zur Verbesserung der Leistung verwaltet das Modul für reguläre Ausdrücke einen anwendungsweiten Cache kompilierter regulärer Ausdrücke. Der Cache speichert Muster für reguläre Ausdrücke, die nur in statischen Methodenaufrufen verwendet werden. (An Instanzmethoden übergebene Muster für reguläre Ausdrücke werden nicht zwischengespeichert.) Dadurch wird vermieden, dass Ausdrücke bei jeder Verwendung erneut analysiert und in Bytecode höherer Ebene kompiliert werden müssen.

Die maximale Anzahl der zwischengespeicherten regulären Ausdrücke wird durch den Wert der `static` (`Shared` in Visual Basic) [Regex.CacheSize-Eigenschaft](xref:System.Text.RegularExpressions.Regex.CacheSize) festgelegt. Standardmäßig speichert das Modul für reguläre Ausdrücke bis zu 15 kompilierte reguläre Ausdrücke zwischen. Wenn die Anzahl der kompilierten regulären Ausdrücke die Cachegröße überschreitet, wird der am längsten nicht verwendete reguläre Ausdruck verworfen und der neue reguläre Ausdruck zwischengespeichert. 

Es gibt zwei Möglichkeiten, wie die Anwendung vorkompilierte reguläre Ausdrücke nutzen kann:

* Durch die Verwendung einer statischen Methode des [Regex](xref:System.Text.RegularExpressions.Regex)-Objekts zum Definieren des regulären Ausdrucks. Wenn Sie ein Muster für reguläre Ausdrücke verwenden, das bereits in einem anderen statischen Methodenaufruf definiert wurde, ruft das Modul für reguläre Ausdrücke dieses aus dem Cache ab. Ist dies nicht der Fall, kompiliert das Modul den regulären Ausdruck und fügt ihn dem Cache hinzu.

* Durch die Wiederverwendung eines vorhandenen [Regex](xref:System.Text.RegularExpressions.Regex)-Objekts, solange sein Muster des regulären Ausdrucks benötigt wird.


Aufgrund des Mehraufwands, der durch die Objektinstanziierung und Kompilierung von regulären Ausdrücken anfällt, stellt das Erstellen und schnelle Löschen zahlreicher [Regex](xref:System.Text.RegularExpressions.Regex)-Objekte einen sehr kostspieligen Prozess dar. Sie können die Leistung von Anwendungen, die zahlreiche verschiedene reguläre Ausdrücke verwenden, optimieren, indem Sie Aufrufe statischer [Regex](xref:System.Text.RegularExpressions.Regex)-Methoden verwenden und gegebenenfalls den Cache für reguläre Ausdrücke vergrößern.

## <a name="see-also"></a>Siehe auch

[Reguläre Ausdrücke in .NET](regular-expressions.md)




<!--HONumber=Nov16_HO3-->


