---
title: Hashtable-Sammlungstyp und Dictionary-Sammlungstyp
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Hashtable class, grouping data in collections
- Hashtable collection type
- hash tables
- grouping data in collections, Hashtable collection type
- hash function
- collections [.NET Framework], Hashtable collection type
ms.assetid: bfc20837-3d02-4fc7-8a8f-c5215b6b7913
ms.openlocfilehash: b228f5db16ba01969b77d601becfb94ac0506d1e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287964"
---
# <a name="hashtable-and-dictionary-collection-types"></a>Hashtable-Sammlungstyp und Dictionary-Sammlungstyp
Die Klasse <xref:System.Collections.Hashtable?displayProperty=nameWithType> und die generischen Klassen <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType> implementieren die <xref:System.Collections.IDictionary?displayProperty=nameWithType>-Schnittstelle. Die generische Klasse <xref:System.Collections.Generic.Dictionary%602> implementiert außerdem die generische <xref:System.Collections.Generic.IDictionary%602>-Schnittstelle. Daher ist jedes Element in diesen Auflistungen ein Schlüssel-Wert-Paar.  
  
 Ein <xref:System.Collections.Hashtable>-Objekt besteht aus Buckets, die die Elemente der Auflistung enthalten. Ein Buckets ist eine virtuelle Untergruppe von Elementen innerhalb der <xref:System.Collections.Hashtable>, der das Suchen und Abrufen schneller und einfacher als in den meisten Auflistungen ermöglicht. Jedem Bucket ist ein Hashcode zugeordnet, der mithilfe einer Hashfunktion generiert wird und auf dem Schlüssel des Elements basiert.  
  
 Die generische Klasse <xref:System.Collections.Generic.HashSet%601> ist eine ungeordnete Auflistung für eindeutige Elemente.  
  
 Eine Hashfunktion ist ein Algorithmus, der einen numerischen Hashcode anhand eines Schlüssels zurückgibt. Der Schlüssel ist der Wert einer Eigenschaft des Objekts, das gespeichert wird. Eine Hashfunktion muss immer denselben Hashcode für denselben Schlüssel zurückgeben. Es ist möglich, dass eine Hashfunktion, den gleichen Hashcode für zwei verschiedene Schlüssel generiert. Eine Hashfunktion, die einen eindeutigen Hashcode für jeden eindeutigen Schlüssel generiert, führt jedoch zu besserer Leistung beim Abrufen von Elementen aus der Hashtabelle.  
  
 Jedes Objekt, das als ein Element in einer <xref:System.Collections.Hashtable> verwendet wird, muss in der Lage sein, einen Hashcode für sich selbst zu generieren, indem eine Implementierung der Methode <xref:System.Object.GetHashCode%2A> verwendet wird. Allerdings können Sie auch eine Hashfunktion für alle Elemente in einer <xref:System.Collections.Hashtable> mithilfe eines <xref:System.Collections.Hashtable>-Konstruktors angeben, der eine <xref:System.Collections.IHashCodeProvider>-Implementierung als einen seiner Parameter akzeptiert.  
  
 Wenn ein Objekt einer <xref:System.Collections.Hashtable> hinzugefügt wird, wird es in dem Bucket gespeichert, der dem Hashcode zugeordnet ist, der mit dem Hashcode des Objekts übereinstimmt. Wenn in der <xref:System.Collections.Hashtable> nach einem Wert gesucht wird, wird der Hashcode für diesen Wert generiert, dann wird der diesem Hashcode zugeordnete Bucket durchsucht.  
  
 Eine Hashfunktion für eine Zeichenfolge kann z. B. die ASCII-Codes jedes Zeichens in der Zeichenfolge annehmen und sie dann zusammen hinzufügen, um einen Hashcode zu generieren. Die Zeichenfolge "Segel" besitzt z. B. einen anderen Hashcode als die Zeichenfolge "Seife". Daher werden die Zeichenfolgen "Segel" und "Seife" in verschiedenen Buckets gespeichert. Im Gegensatz dazu weisen "nie" und "ein" den gleichen Hashcode auf und befinden sich im gleichen Bucket.  
  
 Die Klassen <xref:System.Collections.Generic.Dictionary%602> und <xref:System.Collections.Concurrent.ConcurrentDictionary%602> weisen die gleiche Funktionalität wie die Klasse <xref:System.Collections.Hashtable> auf. Ein <xref:System.Collections.Generic.Dictionary%602> eines bestimmten Typs (außer <xref:System.Object>) bietet eine bessere Leistung als eine <xref:System.Collections.Hashtable> für Werttypen. Der Grund hierfür ist, dass die Elemente von <xref:System.Collections.Hashtable> vom Typ <xref:System.Object> sind. Daher treten das Boxing und das Unboxing in der Regel beim Speichern oder Abrufen eines Werttyps auf. Die Klasse <xref:System.Collections.Concurrent.ConcurrentDictionary%602> sollte verwendet werden, wenn mehrere Threads möglicherweise gleichzeitig auf die Auflistung zugreifen.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IDictionary>
- <xref:System.Collections.IHashCodeProvider>
- <xref:System.Collections.Generic.Dictionary%602>
- <xref:System.Collections.Generic.IDictionary%602?displayProperty=nameWithType>
- <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>
- [Häufig verwendete Auflistungstypen](commonly-used-collection-types.md)
