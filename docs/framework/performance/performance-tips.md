---
title: .NET-Leistungstipps
description: Erkunden Sie Leistungs Tipps, um die Ausführungsgeschwindigkeit eines Programms in .net zu verbessern. Weitere Informationen finden Sie unter Tipps für Boxing und Unboxing, Zeichen folgen und debugktoren.
ms.date: 03/30/2017
helpviewer_keywords:
- C# language, performance
- performance [C#]
- Visual Basic, performance
- performance [Visual Basic]
ms.assetid: ae275793-857d-4102-9095-b4c2a02d57f4
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c5e3f692c2bf754ccd35324019246ee905e8c591
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554644"
---
# <a name="net-performance-tips"></a>.NET-Leistungstipps
Der Begriff *Leistung* bezieht sich im Allgemeinen auf die Ausführungsgeschwindigkeit eines Programms. In manchen Fällen können Sie die Ausführungsgeschwindigkeit erhöhen, indem Sie im Quellcode bestimmte Grundregeln befolgen. In einigen Programmen müssen Sie den Code genau untersuchen und mithilfe von Profilern sicherstellen, dass dieser so schnell wie möglich ausgeführt wird. In anderen Programmen müssen Sie keine solche Optimierung ausführen, da Code in der aktuellen Form mit akzeptabler Geschwindigkeit ausgeführt wird. Dieser Artikel beschreibt einige häufige Bereiche, in denen die Leistung abnehmen kann, und enthält Tipps zur Verbesserung sowie Links zu weiteren Leistungsthemen. Weitere Informationen zum Planen und Messen der Leistung finden Sie unter [Performance](index.md).  
  
## <a name="boxing-and-unboxing"></a>Boxing und Unboxing  
 Am besten verwenden Sie keine Werttypen in Situationen, in denen sie öfter geschachtelt werden müssen, z. B. in nicht generischen Auflistungsklassen wie <xref:System.Collections.ArrayList?displayProperty=nameWithType>. Sie können die Schachtelung von Werttypen vermeiden, indem Sie generische Auflistungen, z. B. <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, verwenden. Boxing und Unboxing sind rechenintensive Prozesse. Wenn ein Werttyp geschachtelt wird, muss ein völlig neues Objekt erstellt werden. Dies kann bis zu 20-mal länger dauern als eine einfache Zuweisung eines Verweises. Eine Umwandlung durch Unboxing kann vier Mal mehr Zeit beanspruchen als eine Zuweisung. Weitere Informationen finden Sie unter [Boxing und Unboxing](../../csharp/programming-guide/types/boxing-and-unboxing.md).  
  
## <a name="strings"></a>Zeichenfolgen  
 Wenn Sie eine große Anzahl von Zeichenfolgenvariablen verketten, z.B. in einer dichten Schleife, verwenden Sie <xref:System.Text.StringBuilder?displayProperty=nameWithType> anstelle des [+ Operators](../../csharp/language-reference/operators/addition-operator.md) in C# oder der Visual Basic-[Verkettungsoperatoren](../../visual-basic/language-reference/operators/concatenation-operators.md). Weitere Informationen finden Sie unter [How to verketten Multiple Strings](../../csharp/how-to/concatenate-multiple-strings.md) and [Concatenations Operators in Visual Basic](../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md).  
  
## <a name="destructors"></a>Destruktoren  
 Leere Destruktoren sollten nicht verwendet werden. Wenn eine Klasse einen Destruktor enthält, wird ein Eintrag in der Finalize-Warteschlange erstellt. Wenn der Destruktor aufgerufen wird, wird der Garbage Collector aufgerufen, um die Warteschlange zu verarbeiten. Wenn der Destruktor leer ist, führt dies einfach zu einem Leistungsverlust. Weitere Informationen finden Sie unter [Finalizer](../../csharp/programming-guide/classes-and-structs/destructors.md) und unter [Object Lifetime: How Objects Are Created and Destroyed (Objektlebensdauer: Erstellen und Zerstören von Objekten)](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).  
  
## <a name="other-resources"></a>Weitere Ressourcen  
  
- [Writing Faster Managed Code: Know What Things Cost (Schnelleren verwalteten Code schreiben: Überblick über Kosten behalten)](/previous-versions/dotnet/articles/ms973852(v=msdn.10))  
  
- [Schreiben von leistungsstarken verwalteten Anwendungen – Ein Leitfaden](/previous-versions/dotnet/articles/ms973858(v=msdn.10))  
  
- [Garbage Collector-Grundlagen und Tipps zur Leistung](/previous-versions/dotnet/articles/ms973837(v=msdn.10))  
  
- [Performance Tips and Tricks in .NET Applications (Tipps und Tricks zur Leistung in .NET-Anwendungen)](/previous-versions/dotnet/articles/ms973839(v=msdn.10))  

- [Rico Mariani's Performance Tidbits (Rico Marianis spezielle Leistungstipps)](/archive/blogs/ricom/)  

- [Blog von Vance Morrison](/archive/blogs/vancem/)
  
## <a name="see-also"></a>Siehe auch

- [Leistung](index.md)
- [Visual Basic-Programmierhandbuch](../../visual-basic/programming-guide/index.md)
- [C#-Programmierhandbuch](../../csharp/programming-guide/index.md)
