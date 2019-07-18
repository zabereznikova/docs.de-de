---
title: Generics – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generics
- generics [C#]
ms.assetid: 75ea8509-a4ea-4e7a-a2b3-cf72482e9282
ms.openlocfilehash: e32eb7c60e01ca72824ffb3a1e1269cf34650f5a
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423398"
---
# <a name="generics-c-programming-guide"></a>Generics (C#-Programmierhandbuch)
Generics wurden zur Version 2.0 der Sprache C# und der Common Language Runtime (CLR) hinzugefügt. Generics führen in .NET Framework das Konzept der Typparameter ein, wodurch Sie Klassen und Methoden entwerfen können, die die Spezialisierung einer oder mehr Typen verzögern können, bis die Klasse oder Methode vom Clientcode deklariert und instanziiert wird. Indem Sie z.B. einen generischen Parameter „T“ verwenden, können Sie eine einzelne Klasse schreiben, die anderer Clientcode verwenden kann, ohne die Kosten und Risiken von Umwandlungen zur Laufzeit oder Boxingvorgängen einzugehen, wie folgendermaßen gezeigt wird:  
  
 [!code-csharp[csProgGuideGenerics#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#1)]  

Generische Klassen und Methoden vereinen Wiederverwendbarkeit, Typsicherheit und Effizienz so, wie es ihre nicht generischen Gegenstücke nicht können. Generics werden am häufigsten für Auflistungen und deren Methoden verwendet. Version 2.0 der .NET Framework-Klassenbibliothek bietet einen neuen Namespace, <xref:System.Collections.Generic>, der mehrere neue generikabasierte Auflistungsklassen enthält. Es wird empfohlen, dass alle Anwendungen für .NET Framework 2.0 und höher die neue generische Auflistungsklasse statt der älteren nicht generischen Gegenstücke wie etwa <xref:System.Collections.ArrayList> verwenden. Weitere Informationen finden Sie unter [Generics in .NET](../../../standard/generics/index.md).  
  
 Sie können selbstverständlich auch benutzerdefinierte generische Typen und Methoden erstellen, um Ihre eigenen typsicheren und effizienten Lösungen und Entwurfsmuster bereitzustellen. Das folgende Codebeispiel zeigt eine einfache generische linked-list-Klasse zur Veranschaulichung. (In den meisten Fällen sollten Sie die Klasse <xref:System.Collections.Generic.List%601> verwenden., die von der .NET Framework-Klassenbibliothek bereitgestellt wird, statt Ihre eigene zu erstellen.) Der Typparameter `T` wird an mehreren Stellen verwendet, wo für gewöhnlich ein konkreter Typ verwendet werden würde, um den Typ des Elements anzugeben, das in der Liste gespeichert wurde. Er wird wie folgt verwendet:  
  
- Als Typ eines Methodenparameters in der Methode `AddHead`.  
  
- Als Rückgabetyp der Eigenschaft `Data` in der geschachtelten Klasse `Node`.  
  
- Als Typ des privaten Members `data` in der geschachtelten Klasse.  
  
 Beachten Sie, dass T für die geschachtelte Klasse `Node` zur Verfügung steht. Wenn `GenericList<T>` mit einem konkreten Typ instanziiert wird, beispielsweise als `GenericList<int>`, wird jedes `T` durch `int` ersetzt.  
  
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
 Weitere Informationen finden Sie unter:  
  
- [Generische Typparameter](../../../csharp/programming-guide/generics/generic-type-parameters.md)  
  
- [Einschränkungen für Typparameter](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)  
  
- [Generische Klassen](../../../csharp/programming-guide/generics/generic-classes.md)  
  
- [Generische Schnittstellen](../../../csharp/programming-guide/generics/generic-interfaces.md)  
  
- [Generische Methoden](../../../csharp/programming-guide/generics/generic-methods.md)  
  
- [Generische Delegate](../../../csharp/programming-guide/generics/generic-delegates.md)  
  
- [Unterschiede zwischen C++-Vorlagen und C#-Generics](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)  
  
- [Generics und Reflexion](../../../csharp/programming-guide/generics/generics-and-reflection.md)  
  
- [Generics zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 Weitere Informationen erhalten Sie unter [C#-Sprachspezifikation](~/_csharplang/spec/types.md#constructed-types).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Typen](../../../csharp/programming-guide/types/index.md)
- [\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)
- [\<typeparamref>](../../../csharp/programming-guide/xmldoc/typeparamref.md)
- [Generics in .NET](../../../standard/generics/index.md)
