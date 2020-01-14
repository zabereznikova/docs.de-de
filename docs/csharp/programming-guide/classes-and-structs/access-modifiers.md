---
title: Zugriffsmodifizierer – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: 0d8e536902317c1e5b00dadde069dd6242189088
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705664"
---
# <a name="access-modifiers-c-programming-guide"></a>Zugriffsmodifizierer (C#-Programmierhandbuch)
Alle Typen und Typmember haben eine Zugriffsebene, die steuert, ob sie von anderem Code in Ihrer Assembly oder anderen Assemblys verwendet werden können. Sie können die folgenden Zugriffsmodifizierer verwenden, um den Zugriff auf einen Typ oder Member anzugeben, wenn Sie sie deklarieren:  
  
 [public](../../language-reference/keywords/public.md)  
 Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden. 
  
 [private](../../language-reference/keywords/private.md)  
 Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder Struktur zugegriffen werden.  
  
 [protected](../../language-reference/keywords/protected.md)  
 Auf den Typ oder Member kann nur von Code in derselben Klasse oder in einer Klasse zugegriffen werden, die von dieser Klasse abgeleitet ist.  
 [internal](../../language-reference/keywords/internal.md)  
 Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.  
  
 [protected internal](../../language-reference/keywords/protected-internal.md) Auf den Typ oder Member kann von beliebigem Code in der Assembly, in der er deklariert ist, oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden. 

 [private protected](../../language-reference/keywords/private-protected.md) Auf den Typ oder Member kann nur innerhalb der deklarierenden Assembly, von Code in derselben Klasse oder in einem Typ zugegriffen werden, der von dieser Klasse abgeleitet ist.
  
 Die folgenden Beispiele veranschaulichen, wie Zugriffsmodifizierer für einen Typ und Member angegeben werden:  
  
 [!code-csharp[csProgGuideObjects#72](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#72)]  
  
 Nicht alle Zugriffsmodifizierer können von allen Typen oder Membern in allen Kontexten verwendet werden, und in einigen Fällen wird der Zugriff auf einen Typmember vom Zugriff auf den enthaltenden Typ eingeschränkt. Die folgenden Abschnitte enthalten ausführlichere Informationen zu diesem Zugriff.  
  
## <a name="class-and-struct-accessibility"></a>Zugriff auf Klasse und Strukturen  
 Klassen und Strukturen, die innerhalb eines Namespace (mit anderen Worten, die nicht in anderen Klassen oder Strukturen geschachtelt sind) direkt deklariert werden, können entweder öffentlich oder intern sein. Wenn kein Modifizierer angegeben ist, wird standardmäßig „internal“ verwendet.  
  
 Strukturmember, einschließlich geschachtelter Klassen und Strukturen, können als öffentlich, intern oder privat deklariert werden. Klassenmember, einschließlich geschachtelter Klassen und Strukturen, können als öffentlich, intern geschützt, geschützt, intern, privat geschützt oder privat definiert werden. Die Zugriffsebene für Klassenmember und Strukturmember, einschließlich geschachtelter Klassen und Strukturen, ist standardmäßig privat. Auf private geschachtelte Typen kann nicht von außerhalb des enthaltenden Typs zugegriffen werden.  
  
 Abgeleitete Klassen können keine höhere Verfügbarkeit als ihre Basistypen aufweisen. Das heißt, dass Sie über keine öffentliche Klasse `B` verfügen können, die von einer internen Klasse `A` abgeleitet wird. Wenn dies zulässig wäre, müssten Sie `A` öffentlich machen, da auf alle geschützten oder internen Member von `A` aus der abgeleiteten Klasse zugegriffen werden kann.  
  
 Sie können mithilfe des InternalsVisibleTo-Attributs bestimmten anderen Assemblys den Zugriff auf die internen Typen ermöglichen. Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend.md).  
  
## <a name="class-and-struct-member-accessibility"></a>Zugriff auf Klassen- und Strukturmember  
 Klassenmember (einschließlich geschachtelter Klassen und Strukturen) können mit einem der sechs Zugriffstypen deklariert werden. Strukturmember können nicht als geschützt deklariert werden, da Strukturen keine Vererbung unterstützen.  
  
 Normalerweise ist der Zugriff auf einen Member nicht höher als der Zugriff des Typs, der ihn enthält. Allerdings kann auf einen öffentlichen Member einer internen Klasse möglicherweise von außerhalb der Assembly zugegriffen werden, wenn der Member Schnittstellenmethoden implementiert oder virtuelle Methoden überschreibt, die in einer öffentlichen Basisklasse definiert sind.  
  
 Der Typ jedes Members, der ein Feld, eine Eigenschaft oder ein Ereignis ist, muss mindestens über dieselben Zugriffstypen verfügen wie der Member selbst. Ebenso müssen der Rückgabetyp und die Parametertypen eines Members, der eine Methode, Indexer oder Delegat ist, mindestens über dieselben Zugriffstypen verfügen, wie der Member selbst. Zum Beispiel können Sie nicht über eine öffentliche Methode `M` verfügen, die eine Klasse `C` zurückgibt, außer wenn `C` ebenfalls öffentlich ist. Ebenso können Sie nicht über eine geschützte Eigenschaft des Typs `A` verfügen, wenn `A` als privat deklariert wurde.  
  
 Benutzerdefinierte Operatoren müssen immer als öffentlich und statisch deklariert werden. Weitere Informationen finden Sie unter [Operatorüberladung](../../language-reference/operators/operator-overloading.md).  
  
 Finalizer können nicht über Zugriffsmodifizierer verfügen.  
  
 Um die Zugriffsebene für eine Klasse oder Struktur festzulegen, fügen Sie das entsprechende Schlüsselwort zur Memberdeklaration hinzu, wie im folgenden Beispiel dargestellt.  
  
 [!code-csharp[csProgGuideObjects#73](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#73)]  
  
> [!NOTE]
> Die geschützte interne Zugriffsebene heißt geschützt ODER intern, nicht geschützt UND intern. Anders gesagt, kann auf einen geschützten internen Member aus einer Klasse in der gleichen Assembly, einschließlich der abgeleiteten Klassen, zugegriffen werden. Um Zugriff auf abgeleitete Klassen in derselben Assembly zu beschränken, deklarieren Sie die Klasse selbst als intern, und ihre Member als geschützt. Außerdem können Sie ab C# 7.2 den Zugriffsmodifizierer „private protected“ verwenden, um dasselbe Ergebnis zu erzielen, ohne die enthaltende Klasse als intern zu deklarieren.  
  
## <a name="other-types"></a>Andere Typen  
 Schnittstellen, die direkt innerhalb eines Namespace deklariert werden, können als öffentlich oder intern deklariert werden, und haben wie Klassen und Strukturen standardmäßig internen Zugriff. Schnittstellenmember sind immer öffentlich, da es der Zweck einer Schnittstelle ist, anderen Typen den Zugriff auf eine Klasse oder Struktur zu ermöglichen. Auf Schnittstellenmember können keine Zugriffsmodifizierer angewendet werden.  
  
 Enumerationsmember sind immer öffentlich, und es können keine Zugriffsmodifizierer angewendet werden.  
  
 Delegaten verhalten sich wie Klassen und Strukturen. Standardmäßig haben sie internen Zugriff, wenn Sie direkt innerhalb eines Namespace deklariert werden, und privaten Zugriff bei Schachtelung.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
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
- [struct](../../language-reference/keywords/struct.md)
- [interface](../../language-reference/keywords/interface.md)
