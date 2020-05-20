---
title: Generics zur Laufzeit – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], at run time
ms.assetid: 119df7e6-9ceb-49df-af36-24f8f8c0747f
ms.openlocfilehash: a53a21d3028e588f5c4d5ce7bf35fad8d3720a08
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75702986"
---
# <a name="generics-in-the-run-time-c-programming-guide"></a>Generics zur Laufzeit (C#-Programmierhandbuch)
Beim Kompilieren eines generischen Typs oder einer generischen Methode in Microsoft Intermediate Language (MSIL) wird über Metadaten auf das Vorkommen von Typparametern hingewiesen. Die Art der Verwendung von MSIL für einen generischen Typ hängt davon ab, ob es sich bei dem übergebenen Typparameter um einen Werttyp oder einen Referenztyp handelt.  
  
 Wenn das erste Mal ein generischer Typ mit einem Werttyp als Parameter erstellt wird, erstellt die Laufzeit einen spezialisierten generischen Typ, bei dem übergebene Parameter an den entsprechenden Stellen in MSIL ersetzt werden. Spezialisierte generische Typen werden für jeden eindeutigen Werttyp, der als Parameter verwendet wird, einmal erstellt.  
  
 Angenommen, im Programmcode wurde ein Stapel deklariert, der aus ganzen Zahlen erstellt wurde:  
  
 [!code-csharp[csProgGuideGenerics#42](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#42)]  
  
 An diesem Punkt generiert die Laufzeit eine spezialisierte Version der Klasse <xref:System.Collections.Generic.Stack%601>, in der der Parameter durch die entsprechende ganze Zahl ersetzt wird. Bei Verwendung eines Stapels aus ganzen Zahlen wird jetzt immer die generierte spezialisierte Klasse <xref:System.Collections.Generic.Stack%601> verwendet. Im folgenden Beispiel werden zwei Instanzen eines Stapels aus ganzen Zahlen erstellt, die eine Instanz des `Stack<int>`-Codes gemeinsam nutzen:  
  
 [!code-csharp[csProgGuideGenerics#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#43)]  
  
 Angenommen, dass an anderer Stelle im Code jedoch eine weitere <xref:System.Collections.Generic.Stack%601>-Klasse erstellt wird, mit einem anderen Werttyp, z.B. `long`, oder einer benutzerdefinierten Struktur als Parameter. Daraufhin generiert die Laufzeit eine andere Version des generischen Typs und ersetzt `long` an den entsprechenden Stellen in MSIL. Konvertierungen sind nicht mehr notwendig, da jede spezialisierte generische Klasse den Werttyp nativ enthält.  
  
 Bei Referenztypen unterscheidet sich die Funktionsweise von Generics geringfügig. Wenn das erste Mal ein generischer Typ mit einem beliebigem Referenztyp erstellt wird, erstellt die Laufzeit einen spezialisierten generischen Typ, bei dem die Parameter durch Objektverweise in MSIL ersetzt werden. Wenn jetzt ein konstruierter Typ mit einem Referenztyp als Parameter instanziiert wird (unabhängig davon, um welchen Typ es sich dabei handelt), wird die zuvor erstellte spezialisierte Version des generischen Typs verwendet. Dies ist möglich, da alle Verweise die gleiche Größe haben.  
  
 Angenommen, Sie verfügen über zwei Referenztypen, eine `Customer`-Klasse und eine `Order`-Klasse, und Sie haben einen Stapel von `Customer`-Typen erstellt:  
  
 [!code-csharp[csProgGuideGenerics#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#47)]  
  
 [!code-csharp[csProgGuideGenerics#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#44)]  
  
 An dieser Stelle generiert die Laufzeit eine spezialisierte Version der Klasse <xref:System.Collections.Generic.Stack%601>, die anstelle von Daten Objektverweise speichert, die zu einem späteren Zeitpunkt mit Daten gefüllt werden. Angenommen, die nächste Codezeile erstellt einen Stapel eines anderen Referenztyps mit dem Namen `Order`:  
  
 [!code-csharp[csProgGuideGenerics#45](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#45)]  
  
 Anders als bei Werttypen wird für den Typ <xref:System.Collections.Generic.Stack%601> keine weitere spezialisierte Version der Klasse `Order` erstellt. Stattdessen wird eine Instanz der spezialisierten Version der Klasse <xref:System.Collections.Generic.Stack%601> erstellt und die Variable `orders` so festgelegt, dass sie darauf verweist. Angenommen, Sie würden dann auf eine Codezeile stoßen, die einen Stapel des Typs `Customer` erstellt:  
  
 [!code-csharp[csProgGuideGenerics#46](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#46)]  
  
 Wie auch bei der vorherigen Verwendung der mit dem Typ `Order` erstellten Klasse <xref:System.Collections.Generic.Stack%601> wird eine weitere Instanz der spezialisierten Klasse <xref:System.Collections.Generic.Stack%601> erstellt. Die darin enthaltenen Zeiger werden so festgelegt, dass sie auf einen Arbeitsspeicherbereich von der Größe eines `Customer`-Typs verweisen. Da die Anzahl der Referenztypen von Programm zu Programm sehr unterschiedlich sein kann, wird bei der C#-Implementierung von Generics eine übermäßige Zunahme des Codeumfangs dadurch verhindert, dass die Anzahl der spezialisierten Klassen, die vom Compiler für generische Klassen von Referenztypen erstellt werden, auf eine reduziert wird.  
  
 Weiterhin gilt, dass eine mit einem Werttyp- oder Referenztypparameter instanziierte generische C#-Klasse zur Laufzeit mittels Reflektion abgefragt werden kann. Dabei können sowohl der tatsächliche Typ als auch der Typparameter ermittelt werden.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic>
- [C#-Programmierhandbuch](../index.md)
- [Einführung in Generics](./index.md)
- [Generics](../../../standard/generics/index.md)
