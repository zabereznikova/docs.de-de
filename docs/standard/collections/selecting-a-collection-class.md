---
title: "Auswählen einer Auflistungsklasse"
description: "Auswählen einer Auflistungsklasse"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 0a60fca7-e082-48d4-9dda-30b0d3e67ec7
translationtype: Human Translation
ms.sourcegitcommit: cfe65fcba1b3fdc09ffcac704a760d8ce29ea60b
ms.openlocfilehash: 38f5a970738103bd96c9570f4d6e8ee540af6ee1

---

# <a name="selecting-a-collection-class"></a>Auswählen einer Auflistungsklasse

Achten Sie darauf, dass Sie Ihre Auflistungsklasse sorgfältig auswählen. Ein falscher Typ kann die Verwendung der Auflistung einschränken. Die generischen und parallelen Versionen der Auflistungen sind vorzuziehen, weil sie größere Typsicherheit und andere Optimierungen aufweisen. Vermeiden Sie im Allgemeinen die Verwendung der Typen im System.Collections-Namespace – es sei denn, Sie richten sich ausdrücklich an .NET Framework, Version 1.1. 

Stellen Sie sich die folgenden Fragen:

* Benötigen Sie eine sequenzielle Liste, in der das Element normalerweise verworfen wird, nachdem sein Wert abgerufen wurde? 

    * Wenn dies der Fall ist, können Sie ggf. die generische Klasse [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) verwenden, wenn Sie FIFO-Verhalten (First In, First Out) benötigen. Ziehen Sie die Verwendung der generischen Klasse [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) in Betracht, wenn Sie LIFO-Verhalten (Last In, First Out) benötigen. Verwenden Sie für sicheren Zugriff auf mehrere Threads die parallelen Versionen [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) und [System.Collections.Concurrent.ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1).
    
    * Wenn dies nicht der Fall ist, ziehen Sie die Verwendung anderer Auflistungen in Betracht.
    
* Benötigen Sie Zugriff auf die Elemente in einer bestimmten Reihenfolge, z. B. FIFO, LIFO oder zufällig?

    * Die generische Klasse [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) bzw. [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) ermöglicht FIFO-Zugriff. Weitere Informationen finden Sie unter [Verwendung einer threadsicheren Sammlung](threadsafe/when-to-use-a-thread-safe-collection.md).
    
    * Die generische Klasse [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) bzw. [System.Collections.Concurrent.ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) ermöglicht LIFO-Zugriff. Weitere Informationen finden Sie unter [Verwendung einer threadsicheren Sammlung](threadsafe/when-to-use-a-thread-safe-collection.md).
    
    * Die generische Klasse [System.Collections.Generic.LinkedList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.LinkedList-1) ermöglicht sequenziellen Zugriff von oben nach unten oder von unten nach oben.
    
* Benötigen Sie Zugriff auf jedes Element über den Index? 

    * Die Klasse [System.Collections.Specialized.StringCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringCollection) und die generische Klasse [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) bieten Zugriff auf ihre Elemente über den nullbasierten Index des Elements. 
    
    * Die Klassen [System.Collections.Specialized.ListDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.ListDictionary) und [System.Collections.Specialized.StringDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringDictionary) sowie die generischen Klassen [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) und [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) bieten Zugriff auf ihre Elemente über den Schlüssel des Elements.
    
    * Die Klassen [System.Collections.Specialized.NameObjectCollectionBase](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameObjectCollectionBase) und [System.Collections.Specialized.NameValueCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameValueCollection) sowie die generischen Klassen [System.Collections.ObjectModel.KeyedCollection&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2) und [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) bieten Zugriff auf ihre Elemente entweder über den nullbasierten Index oder über den Schlüssel des Elements.
    
* Enthält jedes Element einen Wert, eine Kombination aus einem Schlüssel und einem Wert oder eine Kombination aus einem Schlüssel und mehreren Werten? 

    * Ein Wert: Verwenden Sie eine beliebige auf der generischen Schnittstelle [System.Collections.Generic.IList&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IList-1) basierende Sammlung.
    
    * Ein Schlüssel und ein Wert: Verwenden Sie eine beliebige auf der generischen Schnittstelle [System.Collections.Generic.IDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IDictionary-2) basierende Sammlung.
    
    * Ein Wert mit eingebettetem Schlüssel: Verwenden Sie die generische Klasse [System.Collections.ObjectModel.KeyedCollection&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.ObjectModel.KeyedCollection-2).
    
    * Ein Schlüssel und mehrere Werte: Verwenden Sie die Klasse [System.Collections.Specialized.NameValueCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.NameValueCollection).
    
* Müssen Sie die Elemente abweichend von ihrer Eingabereihenfolge sortieren? 

    * Die [System.Collections.Hashtable](https://docs.microsoft.com/dotnet/core/api/System.Collections.Hashtable)-Klasse sortiert ihre Elemente anhand ihrer Hashcodes.
    
    * Die generischen Klassen [System.Collections.Generic.SortedDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedDictionary-2) und [System.Collections.Generic.SortedList&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.SortedList-2) sortieren ihre Elemente nach dem Schlüssel, basierend auf Implementierungen der Schnittstelle [System.Collections.IComparer](https://docs.microsoft.com/dotnet/core/api/System.Collections.IComparer) und der generischen Schnittstelle [System.Collections.Generic.IComparer&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IComparer-1).
    
    * Die generische Klasse [System.Collections.Generic.List&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.List-1) stellt eine Methode `Sort` bereit, die eine Implementierung der generischen Schnittstelle `IComparer<T>` als Parameter annimmt.
    
* Benötigen Sie Auflistungen, die nur Zeichenfolgen annehmen? 

    * [StringCollection](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringCollection) (basierend auf [System.Collections.IList](https://docs.microsoft.com/dotnet/core/api/System.Collections.IList)) und [StringDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized.StringDictionary) (basierend auf [System.Collections.IDictionary](https://docs.microsoft.com/dotnet/core/api/System.Collections.IDictionary)) sind im Namespace [System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized) enthalten. 
    
    * Darüber hinaus können Sie eine beliebige generische Sammlungsklasse im Namespace [System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic) als stark typisierte Zeichenfolgensammlungen verwenden, indem Sie die Klasse `String` für ihre generischen Typargumente angeben.
    
## <a name="linq-to-objects"></a>LINQ to Objects

Mit LINQ to Objects können Entwickler LINQ-Abfragen für den Zugriff auf In-Memory-Objekte verwenden, sofern der Objekttyp [System.Collections.IEnumerable](https://docs.microsoft.com/dotnet/core/api/System.Collections.IEnumerable) oder [System.Collections.Generic.IEnumerable&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.IEnumerable-1) implementiert. LINQ-Abfragen bieten ein allgemeines Muster für den Datenzugriff, sind normalerweise präziser und besser lesbar als standardmäßige Foreach-Schleifen und stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. Weitere Informationen finden Sie unter [Sprachintegrierte Abfrage (Language-Integrated Query, LINQ)](../../csharp/linq.md).

## <a name="see-also"></a>Siehe auch

[System.Collections](https://docs.microsoft.com/dotnet/core/api/System.Collections)

[System.Collections.Specialized](https://docs.microsoft.com/dotnet/core/api/System.Collections.Specialized)

[System.Collections.Generic](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic)

[Threadsichere Sammlungen](threadsafe/index.md)



<!--HONumber=Nov16_HO3-->


