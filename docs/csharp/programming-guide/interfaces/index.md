---
title: Schnittstellen (C#-Programmierhandbuch)
ms.date: 08/21/2018
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
ms.openlocfilehash: 1365b3e0dbc2ae095698b66f2b527301fe474a00
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/19/2018
ms.locfileid: "49454433"
---
# <a name="interfaces-c-programming-guide"></a>Schnittstellen (C#-Programmierhandbuch)

Eine Schnittstelle enthält Definitionen für eine Gruppe von zugehörigen Funktionalitäten, die von einer [Klasse](../../language-reference/keywords/class.md) oder einer [Struktur](../../language-reference/keywords/struct.md) implementiert werden können.
  
Durch die Verwendung von Schnittstellen können Sie beispielsweise das Verhalten aus mehreren Quellen in einer Klasse einbeziehen. Diese Funktion ist wichtig in C#, da die Sprache die mehrfache Vererbung von Klassen nicht unterstützt. Zudem müssen Sie eine Schnittstelle verwenden, wenn Sie die Vererbung für Strukturen simulieren möchten, da sie tatsächlich nicht von einer anderen Struktur oder Klasse erben können.  
  
Sie definieren eine Schnittstelle durch die Verwendung des Schlüsselworts [interface](../../language-reference/keywords/interface.md), wie im folgenden Beispiel gezeigt.  
  
[!code-csharp[csProgGuideInheritance#47](../classes-and-structs/codesnippet/CSharp/interfaces_1.cs)]  

Der Name der Struktur muss ein gültiger C#- [Bezeichnername](../inside-a-program/identifier-names.md) sein. Gemäß Konvention beginnen Schnittstellennamen mit dem Großbuchstaben `I`.

Jede die <xref:System.IEquatable%601>-Schnittstelle implementierende Klasse oder Struktur muss eine Definition für eine <xref:System.IEquatable%601.Equals%2A>-Methode enthalten, die mit der Signatur übereinstimmt, die durch die Schnittstelle angegeben wird. Daher können Sie auf eine Klasse zählen, die `IEquatable<T>` für die Einbeziehung einer `Equals`-Methode implementiert, mit der eine Instanz der Klasse bestimmen kann, ob es sich zu einer anderen Instanz derselben Klasse identisch verhält.  
  
Die Definition für `IEquatable<T>` stellt keine Implementierung für `Equals` bereit. Die Schnittstelle definiert nur die Signatur. Auf diese Weise ähnelt eine Schnittstelle in C# einer abstrakten Klasse, in der alle Methoden abstrakt sind. Eine Klasse oder Struktur kann jedoch mehrere Schnittstellen implementieren. Eine Klasse kann jedoch nur eine einzelne Klasse, ein Abstrakt oder nichts erben. Daher können Sie durch die Verwendung von Schnittstellen das Verhalten von mehreren Quellen in einer Klasse einbeziehen.  
  
Weitere Informationen zu abstrakten Klassen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
Schnittstellen können Methoden, Eigenschaften, Ereignisse, Indexer oder eine beliebige Kombination aus diesen vier Membertypen enthalten. Links zu den Beispielen finden Sie unter [Verwandte Abschnitte](../interfaces/index.md#BKMK_RelatedSections). Eine Schnittstelle kann weder Konstanten, Felder, Operatoren, Instanzkonstruktoren, Finalizer noch Typen enthalten. Schnittstellenmember sind automatisch öffentlich, und sie können keine Zugriffsmodifizierer enthalten. Member können zudem nicht [statisch](../../language-reference/keywords/static.md) sein.  
  
Zum Implementieren eines Schnittstellenmembers muss das entsprechende Member der Implementierungsklasse öffentlich und nicht statisch sein und muss über denselben Namen und die Signatur wie das Schnittstellenmember verfügen.  
  
Wenn eine Klasse oder Struktur eine Schnittstelle implementiert, muss die Klasse oder Struktur eine Implementierung für alle Member bereitstellen, die durch die Schnittstelle definiert wird. Die Schnittstelle an sich stellt keine Funktionalität bereit, die eine Klasse oder Struktur dergestalt erben kann, sodass es die Funktionalität der Basisklasse erben kann Wenn eine Basisklasse jedoch eine Schnittstelle implementiert, erbt jede aus der Basisklasse abgeleitete Klasse diese Implementierung.  
  
Im folgenden Beispiel wird eine Implementierung der <xref:System.IEquatable%601>-Schnittstelle veranschaulicht. Die Implementierungsklasse `Car` muss die Implementierung der <xref:System.IEquatable%601.Equals%2A>-Methode bereitstellen.  
  
[!code-csharp[csProgGuideInheritance#48](../classes-and-structs/codesnippet/CSharp/interfaces_2.cs)]  
  
Eigenschaften und Indexer einer Klasse können zusätzliche Accessors für eine Eigenschaft oder einen in einer Schnittstelle definierten Indexer definieren. Beispielsweise kann eine Schnittstelle eine Eigenschaft deklarieren, die einen [Get](../../language-reference/keywords/get.md)-Accessor aufweist. Die Klasse zur Implementierung der Schnittstelle kann dieselbe Eigenschaft mit einem `get`- und einem [set](../../language-reference/keywords/set.md)-Accessor deklarieren. Wenn die Eigenschaft oder der Indexer jedoch die explizite Implementierung verwendet, müssen die Accessors übereinstimmen. Weitere Informationen zur expliziten Implementierung finden Sie unter [Explizite Schnittstellenimplementierung](explicit-interface-implementation.md) und unter [Schnittstelleneigenschaften](../classes-and-structs/interface-properties.md).  

Schnittstellen können andere Schnittstellen implementieren. Eine Klasse kann eine Schnittstelle mehrfach über geerbte Basisklassen einbeziehen, die sie erbt, oder über Schnittstellen, die von anderen Schnittstellen implementiert werden. Die Klasse kann jedoch nur einmal eine Implementierung einer Schnittstelle bereitstellen und auch nur dann, wenn die Klasse die Schnittstelle als Bestandteil der Definition der Klasse (`class ClassName : InterfaceName`) deklariert. Wenn die Schnittstelle geerbt wurde, da Sie eine Basisklasse geerbt haben, die die Schnittstelle implementiert, bietet die Basisklasse die Implementierung der Member der Schnittstelle. Die abgeleitete Klasse kann jedoch anstelle der Verwendung der geerbten Implementierung die Schnittstellenmember erneut implementieren.  
  
Eine Basisklasse kann zudem Schnittstellenmember mithilfe von virtuellen Membern implementieren. In diesem Fall kann eine abgeleitete Klasse das Schnittstellenverhalten durch das Überschreiben der virtuellen Member ändern. Weitere Informationen über virtuelle Member finden Sie unter [Polymorphie](../classes-and-structs/polymorphism.md).  
  
## <a name="interfaces-summary"></a>Zusammenfassung zu Schnittstellen

Eine Schnittstelle verfügt über die folgenden Eigenschaften:  

- Eine Schnittstelle ähnelt einer abstrakten Basisklasse. Jede die Schnittstelle implementierende Klasse oder Struktur muss alle zugehörigen Member implementieren.
- Eine Schnittstelle kann nicht direkt instanziiert werden. Die zugehörigen Member werden durch die die Schnittstelle implementierende Klasse oder Struktur implementiert.
- Schnittstellen können Ereignisse, Indexer, Methoden und Eigenschaften enthalten.
- Schnittstellen enthalten keine Implementierung von Methoden.
- Eine Klasse oder Struktur kann mehrere Schnittstellen implementieren. Eine Klasse kann eine Basisklasse erben und zudem eine oder mehrere Schnittstellen implementieren.

## <a name="in-this-section"></a>In diesem Abschnitt

[Explizite Schnittstellenimplementierung](explicit-interface-implementation.md)  
 Erläutert das Erstellen eines für eine Schnittstelle spezifischen Klassenmembers.  
  
 [Gewusst wie: Explizites Implementieren von Schnittstellenmembern](how-to-explicitly-implement-interface-members.md)  
 Enthält ein Beispiel über das explizite Implementieren von Schnittstellenmembern.  
  
 [Gewusst wie: Explizites Implementieren von Membern zweier Schnittstellen](how-to-explicitly-implement-members-of-two-interfaces.md)  
 Enthält ein Beispiel über das explizite Implementieren von Schnittstellenmembern mit Vererbung.  
  
##  <a name="BKMK_RelatedSections"></a> Verwandte Abschnitte

- [Schnittstelleneigenschaften](../classes-and-structs/interface-properties.md)  
- [Indexer in Schnittstellen](../indexers/indexers-in-interfaces.md)  
- [Gewusst wie: Implementieren von Schnittstellenereignissen](../events/how-to-implement-interface-events.md)  
- [Klassen und Strukturen](../classes-and-structs/index.md)  
- [Vererbung](../classes-and-structs/inheritance.md)  
- [Methoden](../classes-and-structs/methods.md)  
- [Polymorphismus](../classes-and-structs/polymorphism.md)  
- [Abstrakte und versiegelte Klassen und Klassenmember](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [Eigenschaften](../classes-and-structs/properties.md)  
- [Ereignisse](../events/index.md)  
- [Indexer](../indexers/index.md)  
  
## <a name="featured-book-chapter"></a>Enthaltenes Buchkapitel

[Interfaces (Schnittstellen)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652489%28v%3Dorm.10%29) in [Learning C# 3.0: Master the Fundamentals of C# 3.0 (C# 3.0 lernen: Die Grundlagen von C# 3.0 meistern)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652493%28v%253dorm.10%29)

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Vererbung](../classes-and-structs/inheritance.md)
- [Bezeichnernamen](../inside-a-program/identifier-names.md)
