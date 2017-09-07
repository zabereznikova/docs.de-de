---
title: Generika zur Laufzeit (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], at run time
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 661dff2d8ec2e12ab6a459660a5378f74e93b9c5
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="generics-in-the-run-time-c-programming-guide"></a>Generika zur Laufzeit (C#-Programmierhandbuch)
Beim Kompilieren eines generischen Typs oder einer generischen Methode in Microsoft Intermediate Language (MSIL) wird über Metadaten auf das Vorkommen von Typparametern hingewiesen. Die Art der Verwendung von MSIL für einen generischen Typ hängt davon ab, ob es sich bei dem übergebenen Typparameter um einen Werttyp oder einen Referenztyp handelt.  
  
 Wenn das erste Mal ein generischer Typ mit einem Werttyp als Parameter erstellt wird, erstellt die Laufzeit einen spezialisierten generischen Typ, bei dem übergebene Parameter an den entsprechenden Stellen in MSIL ersetzt werden. Spezialisierte generische Typen werden für jeden eindeutigen Werttyp, der als Parameter verwendet wird, einmal erstellt.  
  
 Angenommen, im Programmcode wurde ein Stapel deklariert, der aus ganzen Zahlen erstellt wurde:  
  
 [!code-cs[csProgGuideGenerics#42](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_1.cs)]  
  
 An diesem Punkt generiert die Laufzeit eine spezialisierte Version der Klasse <xref:System.Collections.Generic.Stack%601>, in der der Parameter durch die entsprechende ganze Zahl ersetzt wird. Bei Verwendung eines Stapels aus ganzen Zahlen wird jetzt immer die generierte spezialisierte Klasse <xref:System.Collections.Generic.Stack%601> verwendet. Im folgenden Beispiel werden zwei Instanzen eines Stapels aus ganzen Zahlen erstellt, die eine Instanz des `Stack<int>`-Codes gemeinsam nutzen:  
  
 [!code-cs[csProgGuideGenerics#43](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_2.cs)]  
  
 Angenommen, dass an anderer Stelle im Code jedoch eine weitere <xref:System.Collections.Generic.Stack%601>-Klasse erstellt wird, mit einem anderen Werttyp, z.B. `long`, oder einer benutzerdefinierten Struktur als Parameter. Daraufhin generiert die Laufzeit eine andere Version des generischen Typs und ersetzt `long` an den entsprechenden Stellen in MSIL. Konvertierungen sind nicht mehr notwendig, da jede spezialisierte generische Klasse den Werttyp nativ enthält.  
  
 Bei Referenztypen unterscheidet sich die Funktionsweise von Generika geringfügig. Wenn das erste Mal ein generischer Typ mit einem beliebigem Referenztyp erstellt wird, erstellt die Laufzeit einen spezialisierten generischen Typ, bei dem die Parameter durch Objektverweise in MSIL ersetzt werden. Wenn jetzt ein konstruierter Typ mit einem Referenztyp als Parameter instanziiert wird (unabhängig davon, um welchen Typ es sich dabei handelt), wird die zuvor erstellte spezialisierte Version des generischen Typs verwendet. Dies ist möglich, da alle Verweise die gleiche Größe haben.  
  
 Angenommen, Sie verfügen über zwei Referenztypen, eine `Customer`-Klasse und eine `Order`-Klasse, und Sie haben einen Stapel von `Customer`-Typen erstellt:  
  
 [!code-cs[csProgGuideGenerics#47](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_3.cs)]  
  
 [!code-cs[csProgGuideGenerics#44](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_4.cs)]  
  
 An dieser Stelle generiert die Laufzeit eine spezialisierte Version der Klasse <xref:System.Collections.Generic.Stack%601>, die anstelle von Daten Objektverweise speichert, die zu einem späteren Zeitpunkt mit Daten gefüllt werden. Angenommen, die nächste Codezeile erstellt einen Stapel eines anderen Referenztyps mit dem Namen `Order`:  
  
 [!code-cs[csProgGuideGenerics#45](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_5.cs)]  
  
 Anders als bei Werttypen wird für den Typ <xref:System.Collections.Generic.Stack%601> keine weitere spezialisierte Version der Klasse `Order` erstellt. Stattdessen wird eine Instanz der spezialisierten Version der Klasse <xref:System.Collections.Generic.Stack%601> erstellt und die Variable `orders` so festgelegt, dass sie darauf verweist. Angenommen, Sie würden dann auf eine Codezeile stoßen, die einen Stapel des Typs `Customer` erstellt:  
  
 [!code-cs[csProgGuideGenerics#46](../../../csharp/programming-guide/generics/codesnippet/CSharp/generics-in-the-run-time_6.cs)]  
  
 Wie auch bei der vorherigen Verwendung der mit dem Typ `Order` erstellten Klasse <xref:System.Collections.Generic.Stack%601> wird eine weitere Instanz der spezialisierten Klasse <xref:System.Collections.Generic.Stack%601> erstellt. Die darin enthaltenen Zeiger werden so festgelegt, dass sie auf einen Arbeitsspeicherbereich von der Größe eines `Customer`-Typs verweisen. Da die Anzahl der Referenztypen von Programm zu Programm sehr unterschiedlich sein kann, wird bei der C#-Implementierung von Generika eine übermäßige Zunahme des Codeumfangs dadurch verhindert, dass die Anzahl der spezialisierten Klassen, die vom Compiler für generische Klassen von Referenztypen erstellt werden, auf eine reduziert wird.  
  
 Weiterhin gilt, dass eine mit einem Werttyp- oder Referenztypparameter instanziierte generische C#-Klasse zur Laufzeit mittels Reflektion abgefragt werden kann. Dabei können sowohl der tatsächliche Typ als auch der Typparameter ermittelt werden.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Einführung in Generika](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [Generika](~/docs/standard/generics/index.md)

