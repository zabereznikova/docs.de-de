---
title: Generische Auflistungen in .NET
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- generics [.NET], collections
- generic collections [.NET]
- generic types [.NET]
ms.assetid: 5b646751-6ab7-465c-916c-b1a76aefa9f5
ms.openlocfilehash: dce0e38b0198396ec0dbc3ced7f2f59c2b112b56
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708409"
---
# <a name="generic-collections-in-net"></a>Generische Sammlungen in .NET

 Die Klassenbibliothek von .NET enthält eine Reihe generischer Auflistungsklassen in den Namespaces <xref:System.Collections.Generic> und <xref:System.Collections.ObjectModel>. Ausführliche Informationen zu diesen Klassen finden Sie unter [Häufig verwendete Auflistungstypen](../../../docs/standard/collections/commonly-used-collection-types.md).  
  
## <a name="systemcollectionsgeneric"></a>System.Collections.Generic

 Viele der generischen Auflistungstypen sind direkte Entsprechungen nicht generischer Typen. <xref:System.Collections.Generic.Dictionary%602> ist eine generische Version von <xref:System.Collections.Hashtable>. Sie verwendet die generische Struktur <xref:System.Collections.Generic.KeyValuePair%602> für die Enumeration anstelle von <xref:System.Collections.DictionaryEntry>.  
  
 <xref:System.Collections.Generic.List%601> ist eine generische Version von <xref:System.Collections.ArrayList>. Es gibt die generischen Klassen <xref:System.Collections.Generic.Queue%601> und <xref:System.Collections.Generic.Stack%601>, die nicht generischen Versionen entsprechen.  
  
 Es gibt generische und nicht generische Versionen von <xref:System.Collections.Generic.SortedList%602>. Beide Versionen sind eine Mischung aus einem Wörterbuch und einer Liste. Die generische <xref:System.Collections.Generic.SortedDictionary%602>-Klasse ist ein reines Wörterbuch und hat keine nicht generische Entsprechung.  
  
 Die generische <xref:System.Collections.Generic.LinkedList%601>-Klasse ist eine echte verknüpfte Liste. Sie hat keine nicht generische Entsprechung.  
  
## <a name="systemcollectionsobjectmodel"></a>System.Collections.ObjectModel

 Die generische <xref:System.Collections.ObjectModel.Collection%601>-Klasse stellt eine Basisklasse bereit, aus der Sie Ihre eigenen generischen Auflistungstypen ableiten können. Die <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>-Klasse bietet eine einfache Möglichkeit, eine schreibgeschützte Auflistung von jedem beliebigen Typ abzuleiten, der die generische <xref:System.Collections.Generic.IList%601>-Schnittstelle implementiert. Die generische <xref:System.Collections.ObjectModel.KeyedCollection%602>-Klasse bietet eine Möglichkeit, Objekte zu speichern, die ihre eigenen Schlüssel enthalten.  
  
## <a name="other-generic-types"></a>Andere generische Typen

 Die generische <xref:System.Nullable%601>Struktur ermöglicht es Ihnen, die Werttypen so zu verwenden, als ob ihnen `null` zugewiesen werden könnte. Dies kann nützlich sein, wenn Datenbankabfragen verwendet werden, für die möglicherweise Felder fehlen, die Werttypen enthalten. Der generische Typparameter kann ein beliebiger Werttyp sein.  
  
> [!NOTE]
> In C# und Visual Basic muss <xref:System.Nullable%601> nicht explizit verwendet werden, weil die Sprache eine Syntax für NULL-fähige Typen umfasst. Siehe [Nullable-Werttypen (C#-Referenz)](../../csharp/language-reference/builtin-types/nullable-value-types.md) und [Nullwerte zulassende Werttypen (Visual Basic)](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).
  
 Die generische <xref:System.ArraySegment%601>-Struktur bietet eine Möglichkeit, einen Bereich von Elementen in einem eindimensionalen nullbasierten Array eines beliebigen Typs abzugrenzen. Der generische Typparameter ist der Typ der Elemente des Arrays.  
  
 Wird der generische <xref:System.EventHandler%601>-Delegat verwendet, muss kein Delegattyp zum Behandeln von Ereignissen mehr deklariert werden, wenn für das Ereignis das von .NET Framework verwendete Muster für die Ereignisbehandlung befolgt wird. Angenommen, Sie haben die von <xref:System.EventArgs> abgeleitete `MyEventArgs`-Klasse erstellt, um die Daten für das Ereignis zu speichern. Sie können das Ereignis dann wie folgt deklarieren:  
  
 [!code-cpp[Conceptual.Generics.Overview#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.generics.overview/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Generics.Overview#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.generics.overview/cs/source2.cs#7)]
 [!code-vb[Conceptual.Generics.Overview#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.generics.overview/vb/source2.vb#7)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic?displayProperty=nameWithType>
- <xref:System.Collections.ObjectModel?displayProperty=nameWithType>
- [Generics](../../../docs/standard/generics/index.md)
- [Generische Delegaten zum Bearbeiten von Arrays und Listen](../../../docs/standard/generics/delegates-for-manipulating-arrays-and-lists.md)
- [Generische Schnittstellen](../../../docs/standard/generics/interfaces.md)
