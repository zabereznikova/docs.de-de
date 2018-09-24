---
title: Auswählen einer Auflistungsklasse
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- last-in-first-out collections
- first-in-first-out collections
- collections [.NET Framework], selecting collection class
- indexed collections
- Collections classes
- grouping data in collections, selecting collection class
ms.assetid: ba049f9a-ce87-4cc4-b319-3f75c8ddac8a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d84bc5ac2256139626311ff7c848170c28ffbd5b
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46580660"
---
# <a name="selecting-a-collection-class"></a>Auswählen einer Auflistungsklasse
Achten Sie darauf, dass Sie Ihre Auflistungsklasse sorgfältig auswählen. Ein falscher Typ kann die Verwendung der Auflistung einschränken. Vermeiden Sie im Allgemeinen die Verwendung der Typen im <xref:System.Collections>-Namespace - es sei denn, Ihr Ziel ist ausdrücklich .NET Framework, Version 1.1. Die generischen und parallelen Versionen der Auflistungen sind vorzuziehen, weil sie größere Typsicherheit und andere Optimierungen aufweisen.  
  
 Stellen Sie sich die folgenden Fragen:  
  
-   Benötigen Sie eine sequenzielle Liste, in der das Element normalerweise verworfen wird, nachdem sein Wert abgerufen wurde?  
  
    -   Wenn dies der Fall ist, können Sie ggf. die Klasse <xref:System.Collections.Queue> oder die generische Klasse <xref:System.Collections.Generic.Queue%601> verwenden, wenn Sie FIFO-Verhalten (First In, First Out) benötigen. Sie können ggf. die Klasse <xref:System.Collections.Stack> oder die generische Klasse <xref:System.Collections.Generic.Stack%601> verwenden, wenn Sie LIFO-Verhalten (Last In, First Out) benötigen. Verwenden Sie für sicheren Zugriff aus mehreren Threads die parallelen Versionen <xref:System.Collections.Concurrent.ConcurrentQueue%601> und <xref:System.Collections.Concurrent.ConcurrentStack%601>.  
  
    -   Wenn dies nicht der Fall ist, ziehen Sie die Verwendung anderer Auflistungen in Betracht.  
  
-   Benötigen Sie Zugriff auf die Elemente in einer bestimmten Reihenfolge, z. B. FIFO, LIFO oder zufällig?  
  
    -   Die Klassen <xref:System.Collections.Queue> und <xref:System.Collections.Generic.Queue%601> und die generische Klasse <xref:System.Collections.Concurrent.ConcurrentQueue%601> ermöglichen FIFO-Zugriff. Weitere Informationen finden Sie unter [Verwendung einer threadsicheren Sammlung](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).  
  
    -   Die Klassen <xref:System.Collections.Stack> und <xref:System.Collections.Generic.Stack%601> und die generische Klasse <xref:System.Collections.Concurrent.ConcurrentStack%601> ermöglichen LIFO-Zugriff. Weitere Informationen finden Sie unter [Verwendung einer threadsicheren Sammlung](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).  
  
    -   Die generische Klasse <xref:System.Collections.Generic.LinkedList%601> ermöglicht sequenziellen Zugriff von oben nach unten oder von unten nach oben.  
  
-   Benötigen Sie Zugriff auf jedes Element über den Index?  
  
    -   Die Klassen <xref:System.Collections.ArrayList> und <xref:System.Collections.Specialized.StringCollection> und die generische Klasse <xref:System.Collections.Generic.List%601> bieten Zugriff auf ihre Elemente über den nullbasierten Index des Elements.  
  
    -   Die Klassen <xref:System.Collections.Hashtable>, <xref:System.Collections.SortedList>, <xref:System.Collections.Specialized.ListDictionary> und <xref:System.Collections.Specialized.StringDictionary> sowie die generischen Klassen <xref:System.Collections.Generic.Dictionary%602> und <xref:System.Collections.Generic.SortedDictionary%602> bieten Zugriff auf ihre Elemente über den Schlüssel des Elements.  
  
    -   Die Klassen <xref:System.Collections.Specialized.NameObjectCollectionBase> und <xref:System.Collections.Specialized.NameValueCollection> sowie die generischen Klassen <xref:System.Collections.ObjectModel.KeyedCollection%602> und <xref:System.Collections.Generic.SortedList%602> bieten Zugriff auf ihre Elemente über den nullbasierten Index oder den Schlüssel des Elements.  
  
-   Enthält jedes Element einen Wert, eine Kombination aus einem Schlüssel und einem Wert oder eine Kombination aus einem Schlüssel und mehreren Werten?  
  
    -   Ein Wert: Verwenden Sie eine beliebige auf der <xref:System.Collections.IList>-Schnittstelle oder der generischen Schnittstelle <xref:System.Collections.Generic.IList%601> basierende Auflistung.  
  
    -   Ein Schlüssel und ein Wert: Verwenden Sie eine beliebige auf der <xref:System.Collections.IDictionary>-Schnittstelle oder der generischen Schnittstelle <xref:System.Collections.Generic.IDictionary%602> basierende Auflistung.  
  
    -   Ein Wert mit eingebettetem Schlüssel: Verwenden Sie die generische Klasse <xref:System.Collections.ObjectModel.KeyedCollection%602>.  
  
    -   Ein Schlüssel und mehrere Werte: Verwenden Sie die Klasse <xref:System.Collections.Specialized.NameValueCollection>.  
  
-   Müssen Sie die Elemente abweichend von ihrer Eingabereihenfolge sortieren?  
  
    -   Die Klasse <xref:System.Collections.Hashtable> sortiert ihre Elemente anhand ihrer Hashcodes.  
  
    -   Die Klasse <xref:System.Collections.SortedList> und die generischen Klassen <xref:System.Collections.Generic.SortedDictionary%602> und <xref:System.Collections.Generic.SortedList%602> sortieren ihre Elemente nach dem Schlüssel basierend auf Implementierungen der <xref:System.Collections.IComparer>-Schnittstelle und der generische <xref:System.Collections.Generic.IComparer%601>-Schnittstelle.  
  
    -   <xref:System.Collections.ArrayList> stellt eine Methode <xref:System.Collections.ArrayList.Sort%2A> bereit, die eine <xref:System.Collections.IComparer>-Implementierung als Parameter annimmt. Ihre generische Entsprechung, diegenerische Klasse  <xref:System.Collections.Generic.List%601> stellt eine Methode <xref:System.Collections.Generic.List%601.Sort%2A> bereit, die eine Implementierung der generischen <xref:System.Collections.Generic.IComparer%601>-Schnittstelle als Parameter annimmt.  
  
-   Benötigen Sie schnelle Suchvorgänge und schnellen Abruf von Informationen?  
  
    -   <xref:System.Collections.Specialized.ListDictionary> ist schneller als <xref:System.Collections.Hashtable> bei kleinen Auflistungen (mit höchstens 10 Elementen). Die generische Klasse <xref:System.Collections.Generic.Dictionary%602> stellt schnellere Suchvorgänge als die generische Klasse <xref:System.Collections.Generic.SortedDictionary%602> bereit. Die Multithreadimplementierung ist <xref:System.Collections.Concurrent.ConcurrentDictionary%602>. <xref:System.Collections.Concurrent.ConcurrentBag%601> stellt schnelle Multithreadeinfügung für unsortierte Daten bereit. Weitere Informationen zu beiden Multithreadtypen finden Sie unter [Verwendung einer threadsicheren Auflistung](../../../docs/standard/collections/thread-safe/when-to-use-a-thread-safe-collection.md).  
  
-   Benötigen Sie Auflistungen, die nur Zeichenfolgen annehmen?  
  
    -   <xref:System.Collections.Specialized.StringCollection> (basierend auf <xref:System.Collections.IList>) und <xref:System.Collections.Specialized.StringDictionary> (basierend auf <xref:System.Collections.IDictionary>) befinden sich im <xref:System.Collections.Specialized>-Namespace.  
  
    -   Darüber hinaus können Sie eine beliebige generische Auflistungsklasse im <xref:System.Collections.Generic>-Namespace als stark typisierte Zeichenfolgenauflistungen verwenden, indem Sie die Klasse <xref:System.String> für ihre generischen Typargumente angeben.  
  
## <a name="linq-to-objects-and-plinq"></a>LINQ to Objects und PLINQ  
 Mit der LINQ to Objects-Funktion können Entwickler LINQ-Abfragen für den Zugriff auf Objekte im Arbeitsspeicher verwenden, wenn der Objekttyp <xref:System.Collections.IEnumerable> oder <xref:System.Collections.Generic.IEnumerable%601> implementiert. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff, sind normalerweise präziser und besser lesbar als standardmäßige `foreach`-Schleifen und stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. Weitere Informationen finden Sie unter [LINQ-zu-Objekte](https://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9).  
  
 PLINQ stellt eine parallele Implementierung von LINQ to Objects bereit, die in vielen Szenarien eine schnellere Abfrageausführung durch eine effizientere Verwendung von Computern mit mehreren Kernen bietet. Weitere Informationen finden Sie unter [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Collections>  
- <xref:System.Collections.Specialized>  
- <xref:System.Collections.Generic>  
- [Threadsichere Sammlungen](../../../docs/standard/collections/thread-safe/index.md)
