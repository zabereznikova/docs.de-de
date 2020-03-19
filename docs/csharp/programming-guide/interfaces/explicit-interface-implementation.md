---
title: Explizite Schnittstellenimplementierung – C#-Programmierhandbuch
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: ea32a279b7c464174a7fada5ef93ccf62ef39884
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167672"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>Explizite Schnittstellenimplementierung (C#-Programmierhandbuch)

Wenn eine [Klasse](../../language-reference/keywords/class.md) zwei Schnittstellen implementiert, die einen Member mit derselben Signatur enthalten, bewirkt die Implementierung dieses Members in der Klasse, dass beide Schnittstellen diesen Member als ihre Implementierung verwenden. Im folgenden Beispiel rufen alle Aufrufe von `Paint` dieselbe Methode auf. In diesem ersten Beispiel werden die Typen definiert:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

Im folgenden Beispiel werden die Methoden aufgerufen:

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

Wenn zwei Schnittstellenmember nicht dieselbe Funktion durchführen, führt dies zu einer fehlerhaften Implementierung von einer oder beiden Schnittstellen. Ein Schnittstellenmember kann explizit implementiert werden. Hierzu wird ein Klassenmember erstellt, der nur über die Schnittstelle aufgerufen wird und spezifisch auf diese Schnittstelle ausgelegt ist. Benennen Sie den Klassenmember hierzu mit dem Namen der Schnittstelle und einem Punkt. Zum Beispiel:

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

Der Klassenmember `IControl.Paint` ist nur über die Schnittstelle `IControl` verfügbar, und `ISurface.Paint` ist nur über `ISurface` verfügbar. Beide Methodenimplementierungen sind voneinander getrennt, und sie sind nicht direkt in der Klasse verfügbar. Zum Beispiel:

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

Die explizite Implementierung wird auch zum Lösen von Konflikten verwendet, bei denen zwei Schnittstellen verschiedene Member mit demselben Namen deklarieren, z. B. eine Eigenschaft und eine Methode. Zum Implementieren beider Schnittstellen muss eine Klasse die explizite Implementierung für die Eigenschaft `P`, die Methode `P` oder beide verwenden, um einen Compilerfehler zu vermeiden. Zum Beispiel:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

Ab [C# 8.0](../../whats-new/csharp-8.md#default-interface-methods) können Sie eine Implementierung für in einer Schnittstelle deklarierte Mitglieder definieren. Wenn eine Klasse eine Methodenimplementierung von einer Schnittstelle erbt, ist diese Methode nur über einen Verweis des Schnittstellentyps zugänglich. Der geerbte Member wird nicht als Teil der öffentlichen Schnittstelle angezeigt. Im folgenden Beispiel wird eine Standardimplementierung für eine Schnittstellenmethode definiert:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

Im folgenden Beispiel wird die Standardimplementierung aufgerufen:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

Alle Klassen, die die `IControl`-Schnittstelle implementieren, können die Standardmethode `Paint` überschreiben: entweder als öffentliche Methode oder als explizite Schnittstellenimplementierung.

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](../classes-and-structs/index.md)
- [Schnittstellen](./index.md)
- [Vererbung](../classes-and-structs/inheritance.md)
