---
title: Generics – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: 330aa74538ab15d1de19d80b0f57b3d0921c5c55
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712155"
---
# <a name="generics-c-programming-guide"></a>Generics (C#-Programmierhandbuch)

Generics führen in das Konzept der Typparameter .NET Framework ein, wodurch Sie Klassen und Methoden entwerfen können, die die Angabe eines oder mehrerer Typen verzögern können, bis die Klasse oder Methode vom Clientcode deklariert und instanziiert wird. Indem Sie z. B. einen generischen Typparameter „`T`“ verwenden, können Sie eine einzelne Klasse schreiben, die von anderem Clientcode verwendet werden kann, ohne dass die Kosten und Risiken von Umwandlungen zur Laufzeit oder Boxingvorgängen anfallen, wie im Folgenden gezeigt:

[!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]

Generische Klassen und Methoden vereinen Wiederverwendbarkeit, Typsicherheit und Effizienz auf eine Weise, wie es ihre nicht generischen Gegenstücke nicht können. Generics werden am häufigsten für Auflistungen und deren Methoden verwendet. Der Namespace <xref:System.Collections.Generic> enthält eine Reihe von auf Generics basierenden Auflistungsklassen. Die nicht generischen Auflistungen wie <xref:System.Collections.ArrayList> werden nicht empfohlen und wurden aus Kompatibilitätsgründen beibehalten. Weitere Informationen finden Sie unter [Generics in .NET](../../../standard/generics/index.md).

Sie können selbstverständlich auch benutzerdefinierte generische Typen und Methoden erstellen, um Ihre eigenen typsicheren und effizienten Lösungen und Entwurfsmuster bereitzustellen. Das folgende Codebeispiel zeigt eine einfache generische linked-list-Klasse zur Veranschaulichung. (In den meisten Fällen sollten Sie die Klasse <xref:System.Collections.Generic.List%601> verwenden., die von der .NET Framework-Klassenbibliothek bereitgestellt wird, statt Ihre eigene zu erstellen.) Der Typparameter `T` wird an mehreren Stellen verwendet, wo für gewöhnlich ein konkreter Typ verwendet werden würde, um den Typ des Elements anzugeben, das in der Liste gespeichert wurde. Er wird wie folgt verwendet:

- Als Typ eines Methodenparameters in der Methode `AddHead`.
- Als Rückgabetyp der Eigenschaft `Data` in der geschachtelten Klasse `Node`.
- Als Typ des privaten Members `data` in der geschachtelten Klasse.

 Beachten Sie, dass `T` für die geschachtelte Klasse `Node` verfügbar ist. Wenn `GenericList<T>` mit einem konkreten Typ instanziiert wird, beispielsweise als `GenericList<int>`, wird jedes `T` durch `int` ersetzt.

[!code-csharp[csProgGuideGenerics#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#2)] 

Das folgende Codebeispiel zeigt, wie Clientcode die generische Klasse `GenericList<T>` verwendet, um eine Ganzzahlliste zu erstellen. Indem Sie einfach das Typargument ändern, kann der folgende Code ganz leicht so modifiziert werden, dass er Zeichenfolgenlisten oder jeden anderen benutzerdefinierten Typ erstellt:

[!code-csharp[csProgGuideGenerics#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#3)]

## <a name="generics-overview"></a>Übersicht über Generics

- Verwenden Sie Generics, um die Wiederverwendung von Code, Typsicherheit und Leistung zu maximieren.
- Generics werden am häufigsten zur Erstellung von Auflistungsklassen verwendet.
- Die Klassenbibliothek von .NET Framework enthält eine Reihe generischer Auflistungsklassen im <xref:System.Collections.Generic>-Namespace. Diese sollten wenn möglich anstatt Klassen wie z.B. <xref:System.Collections.ArrayList> im <xref:System.Collections>-Namespace verwendet werden.
- Sie können Ihre eigenen generischen Schnittstellen, Klassen, Methoden, Ereignisse und Delegaten erstellen.
- Generische Klassen sind womöglich in der Aktivierung des Zugriffs auf Methoden für bestimmte Datentypen beschränkt.
- Informationen zu den Typen, die in einem generischen Datentyp verwendet werden, können zur Laufzeit unter Verwendung von Reflektion abgerufen werden.

## <a name="related-sections"></a>Verwandte Abschnitte

- [Generische Typparameter](generic-type-parameters.md)
- [Einschränkungen für Typparameter](constraints-on-type-parameters.md)
- [Generische Klassen](generic-classes.md)
- [Generische Schnittstellen](generic-interfaces.md)
- [Generische Methoden](generic-methods.md)
- [Generische Delegate](generic-delegates.md)
- [Unterschiede zwischen C++-Vorlagen und C#-Generics](differences-between-cpp-templates-and-csharp-generics.md)
- [Generics und Reflexion](generics-and-reflection.md)
- [Generics zur Laufzeit](generics-in-the-run-time.md)

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/types.md#constructed-types).

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>
- [C#-Programmierhandbuch](../index.md)
- [Typen](../types/index.md)
- [\<typeparam>](../xmldoc/typeparam.md)
- [\<typeparamref>](../xmldoc/typeparamref.md)
- [Generics in .NET](../../../standard/generics/index.md)
