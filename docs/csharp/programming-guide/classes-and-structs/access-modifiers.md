---
title: Zugriffsmodifizierer – C#-Programmierhandbuch
description: Alle Typen und Typmember in C# verfügen über eine Zugriffsebene, die steuert, ob sie von anderem Code verwendet werden können. Sehen Sie sich diese Liste von Zugriffsmodifizierern an.
ms.date: 03/08/2020
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: 557f5d9f302b08d32896b462e86ce1d96710ff36
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474526"
---
# <a name="access-modifiers-c-programming-guide"></a>Zugriffsmodifizierer (C#-Programmierhandbuch)

Alle Typen und Typmember verfügen über eine Zugriffsebene. Diese Zugriffsebene steuert, ob sie von anderem Code in Ihrer Assembly oder anderen Assemblys verwendet werden können. Mithilfe der folgenden Zugriffsmodifizierer können Sie den Zugriff auf einen Typ oder Member festlegen, wenn Sie ihn deklarieren:

- [public:](../../language-reference/keywords/public.md) Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.
- [private:](../../language-reference/keywords/private.md) Der Zugriff auf den Typ oder Member kann nur über Code innerhalb derselben `class`- oder `struct`-Instanz erfolgen.
- [protected:](../../language-reference/keywords/protected.md) Der Zugriff auf den Typ oder Member kann nur über Code in derselben `class`- oder in einer `class`-Instanz erfolgen, die von dieser `class`-Instanz abgeleitet wurde.
- [internal:](../../language-reference/keywords/internal.md) Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.
- [protected internal:](../../language-reference/keywords/protected-internal.md) Der Zugriff auf den Typ oder Member kann über beliebigen Code in der Assembly, in der er deklariert wurde, oder innerhalb einer abgeleiteten `class`-Instanz in einer anderen Assembly erfolgen.
- [private protected:](../../language-reference/keywords/private-protected.md) Auf den Typ oder Member kann nur innerhalb der deklarierenden Assembly, von Code in derselben `class`-Instanz oder in einem Typ zugegriffen werden, der von dieser `class`-Instanz abgeleitet ist.

Die folgenden Beispiele veranschaulichen, wie Zugriffsmodifizierer für einen Typ und Member angegeben werden:

[!code-csharp[PublicAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#PublicAccess)]

Nicht alle Zugriffsmodifizierer sind für alle Typen oder Member in allen Kontexten gültig. In manchen Fällen wird der Zugriff auf ein Typmember durch den Zugriff des enthaltenden Typs eingeschränkt.

## <a name="class-and-struct-accessibility"></a>Zugriff auf Klassen und Strukturen  

Klassen und Strukturen, die innerhalb eines Namespace (mit anderen Worten, die nicht in anderen Klassen oder Strukturen geschachtelt sind) direkt deklariert werden, können die Zugriffsebenen `public` oder `internal` aufweisen. Wenn kein Zugriffsmodifizierer angegeben ist, wird standardmäßig `Internal` verwendet.  

Strukturmember, einschließlich geschachtelter Klassen und Strukturen, können als `public`, `internal` oder `private` deklariert werden. Für Klassenmember, einschließlich geschachtelter Klassen und Strukturen, kann `public`, `protected internal`, `protected`, `internal`, `private protected` oder `private` deklariert werden. Klassen und Strukturmember, einschließlich geschachtelter Klassen und Strukturen, weisen standardmäßig `private`-Zugriff auf. Auf private geschachtelte Typen kann nicht von außerhalb des enthaltenden Typs zugegriffen werden.

Abgeleitete Klassen können keine höhere Verfügbarkeit als ihre Basistypen aufweisen. Sie können keine öffentliche `B`-Klasse deklarieren, die von einer internen `A`-Klasse abgeleitet wird. Wenn dies zulässig wäre, würde `A` als öffentlich festgelegt werden, da der Zugriff auf alle `protected`- oder `internal`-Member von `A` über die abgeleitete Klasse möglich wäre.

Mithilfe von `InternalsVisibleToAttribute` können Sie den Zugriff auf Ihre internen Typen durch spezifische andere Assemblys ermöglichen. Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).

## <a name="class-and-struct-member-accessibility"></a>Zugriff auf Klassen- und Strukturmember  

Klassenmember (einschließlich geschachtelter Klassen und Strukturen) können mit einem der sechs Zugriffstypen deklariert werden. Strukturmember können nicht als `protected`, `protected internal` oder `private protected` deklariert werden, da Strukturen die Vererbung nicht unterstützen.

Normalerweise ist der Zugriff auf einen Member nicht höher als der Zugriff des Typs, der ihn enthält. Allerdings kann auf einen `public`-Member einer internen Klasse möglicherweise von außerhalb der Assembly zugegriffen werden, wenn der Member Schnittstellenmethoden implementiert oder virtuelle Methoden überschreibt, die in einer öffentlichen Basisklasse definiert sind.

Der Typ aller Memberfelder, -eigenschaften oder -ereignisse muss mindestens über den Member selbst zugänglich sein. Ebenso müssen der Rückgabetyp und die Parametertypen von Methoden, Indexer oder Delegaten mindestens so zugänglich wie der Member selbst sein. Sie können beispielsweise keine `M`-Methode mit der Zugriffsebene `public` verwenden, die eine `C`-Klasse zurückgibt, es sei denn, `C` verfügt ebenfalls über die Zugriffsebene `public`. Ebenso können Sie keine `protected`-Eigenschaft vom Typ `A` verwenden, wenn `A` als `private` deklariert ist.

Benutzerdefinierte Operatoren müssen immer als `public` und `static` deklariert werden. Weitere Informationen finden Sie unter [Operatorüberladung](../../language-reference/operators/operator-overloading.md).

Finalizer können nicht über Zugriffsmodifizierer verfügen.

Fügen Sie wie im folgenden Beispiel gezeigt das entsprechende Schlüsselwort zur Memberdeklaration hinzu, um die Zugriffsebene für einen `class`- oder `struct`-Member festzulegen.

[!code-csharp[MethodAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#MethodAccess)]

## <a name="other-types"></a>Andere Typen

Schnittstellen, die direkt in einem Namespace deklariert wurden, können die Zugriffsebene `public` oder `internal` aufweisen. Außerdem verfügen Schnittstellen wie Klassen und Strukturen standardmäßig über `internal`-Zugriff. Für Schnittstellenmember ist standardmäßig `public` festgelegt, da es der Zweck einer Schnittstelle ist, anderen Typen den Zugriff auf eine Klasse oder Struktur zu ermöglichen. Schnittstellenmemberdeklarationen können einen beliebigen Zugriffsmodifizierer aufweisen. Das ist für statische Methoden besonders nützlich, um allgemeine Implementierungen bereitzustellen, die von allen Implementierern einer Klasse benötigt werden.

Enumerationsmember weisen immer die Zugriffsebene `public` auf, und es können keine Zugriffsmodifizierer angewendet werden.

Delegaten verhalten sich wie Klassen und Strukturen. Sie verfügen standardmäßig über `internal`-Zugriff, wenn sie in einem Namespace deklariert wurden, sie verfügen über `private`-Zugriff, wenn sie geschachtelt sind.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Schnittstellen](../interfaces/index.md)
- [private](../../language-reference/keywords/private.md)
- [public](../../language-reference/keywords/public.md)
- [internal](../../language-reference/keywords/internal.md)
- [protected](../../language-reference/keywords/protected.md)
- [protected internal](../../language-reference/keywords/protected-internal.md)
- [private protected](../../language-reference/keywords/private-protected.md)
- [class](../../language-reference/keywords/class.md)
- [struct](../../language-reference/builtin-types/struct.md)
- [interface](../../language-reference/keywords/interface.md)
