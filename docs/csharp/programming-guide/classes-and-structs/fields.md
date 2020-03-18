---
title: Felder – C#-Programmierhandbuch
ms.date: 07/20/2015
helpviewer_keywords:
- fields [C#]
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
ms.openlocfilehash: 46d4f77a4a490b2acdb5da20b9a477f27c38d410
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628240"
---
# <a name="fields-c-programming-guide"></a>Felder (C#-Programmierhandbuch)

Ein *Feld* ist eine Variable eines beliebigen Typs, die direkt in einer [class](../../language-reference/keywords/class.md) oder [struct](../../language-reference/builtin-types/struct.md) deklariert ist. Felder sind *Member* Ihres enthaltenden Typs.

Eine Klasse oder Struktur kann über Instanzfelder, statische Felder oder beides verfügen. Instanzenfelder sind für eine Instanz eines Typs spezifisch. Wenn Sie eine Klasse T mit einem Instanzenfeld F haben, können Sie zwei Objekte vom Typ T erstellen und den Wert von F in jedem Objekt ändern, ohne dabei den Wert in dem anderen Objekt zu beeinflussen. Im Gegensatz dazu gehört ein statisches Feld zur Klasse selbst und wird in allen Instanzen dieser Klasse gemeinsam verwendet. Sie können nur auf das statische Feld zugreifen, indem Sie den Klassennamen verwenden. Wenn Sie über einen Instanznamen auf das statische Feld zugreifen, erhalten Sie den Kompilierzeitfehler [CS0176](../../misc/cs0176.md).

Im Allgemeinen sollten Sie Felder nur für Variablen verwenden, die private oder geschützte Zugriffsmöglichkeiten haben. Daten, die Ihre Klasse für Clientcode bereitstellt, sollten über [Methoden](./methods.md), [Eigenschaften](./properties.md) und [Indexer](../indexers/index.md) bereitgestellt werden. Sie können sich mit diesen Konstrukten für indirekten Zugriff auf interne Felder vor ungültigen Eingabewerten schützen. Ein privates Feld, das über eine öffentliche Eigenschaft bereitgestellte Daten speichert, wird als *Sicherungsspeicher* oder *Unterstützungsfeld* bezeichnet.

Felder speichern in der Regel die Daten, die über Zugriff auf mehr als eine Klassenmethode verfügen müssen und länger als die Lebensdauer einer einzelnen Methode gespeichert werden müssen. Z.B. verfügt eine Klasse, die ein Kalenderdatum darstellt, möglicherweise über drei Felder: Jeweils eines für Monat, Tag und Jahr. Variablen, die außerhalb des Bereichs einer einzelnen Methode nicht verwendet werden, sollten als *lokale Variablen* innerhalb des Methodentexts selbst deklariert werden.

Felder werden innerhalb des Class-Blocks deklariert, indem Sie die Zugriffsebene des Felds, gefolgt vom Typ des Felds, gefolgt vom Namen des Felds angeben. Beispiel:

[!code-csharp[csProgGuideObjects#61](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#61)]

Um auf ein Feld in einem Objekt zuzugreifen, fügen Sie einen Punkt hinter dem Objektnamen ein, gefolgt vom Namen des Felds, wie in `objectname.fieldname`. Beispiel:

[!code-csharp[csProgGuideObjects#62](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#62)]

Einem Feld kann ein Anfangswert durch Verwendung des Zuweisungsoperators zugewiesen werden, wenn das Feld deklariert wird. Sie würden z.B. `day` wie im folgenden Beispiel deklarieren, um das `"Monday"`-Feld automatisch `day` zuzuweisen:

[!code-csharp[csProgGuideObjects#63](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#63)]

Felder werden umgehend initialisiert, bevor der Konstruktor für die Objektinstanz aufgerufen wird. Wenn der Konstruktor den Wert eines Felds zuweist, überschreibt er jeden während der Felddeklaration angegebenen Wert. Weitere Informationen finden Sie unter [Verwenden von Konstruktoren](./using-constructors.md).

> [!NOTE]
> Ein Feldinitialisierer kann nicht auf andere Instanzfelder verweisen.

Felder können als [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) oder [private protected](../../language-reference/keywords/private-protected.md) markiert werden. Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf die Felder zugreifen können. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](./access-modifiers.md).

Ein Feld kann optional als [static](../../language-reference/keywords/static.md) deklariert werden. Dadurch steht das Feld Aufrufern jederzeit zur Verfügung, auch wenn keine Instanz der Klasse vorhanden ist. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](./static-classes-and-static-class-members.md).

Ein Feld kann als [readonly](../../language-reference/keywords/readonly.md) deklariert werden. Einem schreibgeschützten Feld kann nur ein Wert während der Initialisierung oder in einem Konstruktor zugewiesen werden. Ein `static readonly`-Feld ist einer Konstanten sehr ähnlich, außer dass der C#-Compiler nicht auf den Wert eines statischen schreibgeschützten Felds zur Kompilierzeit, sondern nur zur Laufzeit zugreifen kann. Weitere Informationen finden Sie unter [Konstanten](./constants.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Klassen und Strukturen](./index.md)
- [Verwenden von Konstruktoren](./using-constructors.md)
- [Vererbung](./inheritance.md)
- [Zugriffsmodifizierer](./access-modifiers.md)
- [Abstrakte und versiegelte Klassen und Klassenmember](./abstract-and-sealed-classes-and-class-members.md)
