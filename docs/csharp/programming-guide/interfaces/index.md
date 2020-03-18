---
title: Schnittstellen – C#-Programmierhandbuch
ms.date: 02/20/2020
helpviewer_keywords:
- interfaces [C#]
- C# language, interfaces
ms.assetid: 2feda177-ce11-432d-81b4-d50f5f35fd37
ms.openlocfilehash: f4ee269f41e79562c113a7627816f797b083095e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "79157077"
---
# <a name="interfaces-c-programming-guide"></a>Schnittstellen (C#-Programmierhandbuch)

Eine Schnittstelle enthält Definitionen für eine Gruppe von zugehörigen Funktionalitäten, die von einer nicht abstrakten [Klasse](../../language-reference/keywords/class.md) oder einer [Struktur](../../language-reference/builtin-types/struct.md) implementiert werden müssen. Eine Schnittstelle kann `static`-Methoden definieren, die über eine Implementierung verfügen müssen. Eine Schnittstelle kann eine Standardimplementierung für beliebige oder alle deklarierten Instanzmember bereitstellen. Eine Schnittstelle kann keine Instanzdaten wie Felder, automatisch implementierte Eigenschaften oder eigenschaftsähnliche Ereignisse deklarieren.

Durch die Verwendung von Schnittstellen können Sie beispielsweise das Verhalten aus mehreren Quellen in einer Klasse einbeziehen. Diese Funktion ist wichtig in C#, da die Sprache die mehrfache Vererbung von Klassen nicht unterstützt. Zudem müssen Sie eine Schnittstelle verwenden, wenn Sie die Vererbung für Strukturen simulieren möchten, da sie tatsächlich nicht von einer anderen Struktur oder Klasse erben können.

Sie definieren eine Schnittstelle durch die Verwendung des Schlüsselworts [interface](../../language-reference/keywords/interface.md), wie im folgenden Beispiel gezeigt.

[!code-csharp[Equatable](~/samples/snippets/csharp/objectoriented/interfaces.cs#Equatable)]

Der Name der Schnittstelle muss ein gültiger C#-[Bezeichnername](../inside-a-program/identifier-names.md) sein. Gemäß Konvention beginnen Schnittstellennamen mit dem Großbuchstaben `I`.

Jede die <xref:System.IEquatable%601>-Schnittstelle implementierende Klasse oder Struktur muss eine Definition für eine <xref:System.IEquatable%601.Equals%2A>-Methode enthalten, die mit der Signatur übereinstimmt, die durch die Schnittstelle angegeben wird. Daher können Sie auf eine Klasse zählen, die `IEquatable<T>` für die Einbeziehung einer `Equals`-Methode implementiert, mit der eine Instanz der Klasse bestimmen kann, ob es sich zu einer anderen Instanz derselben Klasse identisch verhält.

Die Definition für `IEquatable<T>` stellt keine Implementierung für `Equals` bereit. Eine Klasse oder Struktur kann mehrere Schnittstellen implementieren. Eine Klasse kann jedoch nur von einer einzelnen Klasse erben.

Weitere Informationen zu abstrakten Klassen finden Sie unter [Abstrakte und versiegelte Klassen und Klassenmember](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md).

Schnittstellen können Instanzmethoden, Eigenschaften, Ereignisse, Indexer oder eine beliebige Kombination aus diesen vier Membertypen enthalten. Schnittstellen können statische Konstruktoren, Felder, Konstanten oder Operatoren enthalten. Links zu den Beispielen finden Sie unter [Verwandte Abschnitte](./index.md#BKMK_RelatedSections). Eine Schnittstelle kann keine Instanzfelder, Instanzkonstruktoren oder FInalizer enthalten. Schnittstellenmember sind standardmäßig öffentlich.

Zum Implementieren eines Schnittstellenmembers muss das entsprechende Member der Implementierungsklasse öffentlich und nicht statisch sein und muss über denselben Namen und die Signatur wie das Schnittstellenmember verfügen.

Wenn eine Klasse oder Struktur eine Schnittstelle implementiert, muss die Klasse oder Struktur eine Implementierung für alle Member bereitstellen, die durch die Schnittstelle deklariert wurden, aber dafür keine Standardimplementierung bereitstellt wurden. Wenn eine Basisklasse jedoch eine Schnittstelle implementiert, erbt jede aus der Basisklasse abgeleitete Klasse diese Implementierung.

Im folgenden Beispiel wird eine Implementierung der <xref:System.IEquatable%601>-Schnittstelle veranschaulicht. Die Implementierungsklasse `Car` muss die Implementierung der <xref:System.IEquatable%601.Equals%2A>-Methode bereitstellen.

[!code-csharp[ImplementEquatable](~/samples/snippets/csharp/objectoriented/interfaces.cs#ImplementEquatable)]

Eigenschaften und Indexer einer Klasse können zusätzliche Accessors für eine Eigenschaft oder einen in einer Schnittstelle definierten Indexer definieren. Beispielsweise kann eine Schnittstelle eine Eigenschaft deklarieren, die einen [Get](../../language-reference/keywords/get.md)-Accessor aufweist. Die Klasse zur Implementierung der Schnittstelle kann dieselbe Eigenschaft mit einem `get`- und einem [set](../../language-reference/keywords/set.md)-Accessor deklarieren. Wenn die Eigenschaft oder der Indexer jedoch die explizite Implementierung verwendet, müssen die Accessors übereinstimmen. Weitere Informationen zur expliziten Implementierung finden Sie unter [Explizite Schnittstellenimplementierung](explicit-interface-implementation.md) und unter [Schnittstelleneigenschaften](../classes-and-structs/interface-properties.md).

Schnittstellen können von einer oder mehreren Schnittstellen erben. Die abgeleitete Schnittstelle erbt die Member von den Basisschnittstellen. Eine Klasse, die eine abgeleitete Schnittstelle implementiert, muss alle Member in der abgeleiteten Schnittstelle implementieren, einschließlich alle Member der Basisschnittstellen der abgeleiteten Schnittstelle. Diese Klasse kann implizit in die abgeleitete Schnittstelle oder deren Basisschnittstellen konvertiert werden. Eine Klasse kann eine Schnittstelle mehrfach über geerbte Basisklassen einbeziehen, die sie erbt, oder über Schnittstellen, die von anderen Schnittstellen geerbt werden. Die Klasse kann jedoch nur einmal eine Implementierung einer Schnittstelle bereitstellen und auch nur dann, wenn die Klasse die Schnittstelle als Bestandteil der Definition der Klasse (`class ClassName : InterfaceName`) deklariert. Wenn die Schnittstelle geerbt wurde, da Sie eine Basisklasse geerbt haben, die die Schnittstelle implementiert, bietet die Basisklasse die Implementierung der Member der Schnittstelle. Die abgeleitete Klasse kann jedoch anstelle der Verwendung der geerbten Implementierung jegliche virtuellen Schnittstellenmember erneut implementieren. Wenn Schnittstellen eine Standardimplementierung einer Methode deklarieren, erbt jede Klasse, die eine Schnittstelle implementiert, diese Implementierung. Implementierungen, die in Schnittstellen definiert sind, sind virtuell, und die implementierende Klasse kann diese Implementierung außer Kraft setzen.

Eine Basisklasse kann zudem Schnittstellenmember mithilfe von virtuellen Membern implementieren. In diesem Fall kann eine abgeleitete Klasse das Schnittstellenverhalten durch das Überschreiben der virtuellen Member ändern. Weitere Informationen über virtuelle Member finden Sie unter [Polymorphie](../classes-and-structs/polymorphism.md).

## <a name="interfaces-summary"></a>Zusammenfassung zu Schnittstellen

Eine Schnittstelle verfügt über die folgenden Eigenschaften:

- Eine Schnittstelle ähnelt in der Regel einer abstrakten Basisklasse, die nur abstrakte Member enthält. Jede die Schnittstelle implementierende Klasse oder Struktur muss alle zugehörigen Member implementieren. Optional kann eine Schnittstelle die Standardimplementierungen für einige ihrer Member definieren.
- Eine Schnittstelle kann nicht direkt instanziiert werden. Die zugehörigen Member werden durch die die Schnittstelle implementierende Klasse oder Struktur implementiert.
- Eine Klasse oder Struktur kann mehrere Schnittstellen implementieren. Eine Klasse kann eine Basisklasse erben und zudem eine oder mehrere Schnittstellen implementieren.

## <a name="BKMK_RelatedSections"></a> Verwandte Abschnitte

- [Schnittstelleneigenschaften](../classes-and-structs/interface-properties.md)  
- [Indexer in Schnittstellen](../indexers/indexers-in-interfaces.md)  
- [Implementieren von Schnittstellenereignissen](../events/how-to-implement-interface-events.md)
- [Klassen und Strukturen](../classes-and-structs/index.md)  
- [Vererbung](../classes-and-structs/inheritance.md)  
- [Methoden](../classes-and-structs/methods.md)  
- [Polymorphismus](../classes-and-structs/polymorphism.md)  
- [Abstrakte und versiegelte Klassen und Klassenmember](../classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
- [Eigenschaften](../classes-and-structs/properties.md)  
- [Ereignisse](../events/index.md)  
- [Indexer](../indexers/index.md)  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Vererbung](../classes-and-structs/inheritance.md)
- [Bezeichnernamen](../inside-a-program/identifier-names.md)
