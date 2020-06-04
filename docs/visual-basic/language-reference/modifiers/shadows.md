---
title: Shadows
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 7aed6bec21bd484cca019b061bd5915de13a9eb8
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402706"
---
# <a name="shadows-visual-basic"></a>Shadows (Visual Basic)

Gibt an, dass ein deklariertes Programmier Element ein identisch benanntes Element oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert und verbirgt.

## <a name="remarks"></a>Bemerkungen

Der Hauptzweck von Shadowing(das auch als ausblenden *nach Name*bezeichnet wird) besteht darin, die Definition der Klassenmember beizubehalten. Die Basisklasse kann einer Änderung unterzogen werden, die ein Element mit dem gleichen Namen erstellt, den Sie bereits definiert haben. Wenn dies der Fall ist, `Shadows` erzwingt der-Modifizierer, dass Verweise durch Ihre Klasse in den von Ihnen definierten Member aufgelöst werden, anstatt das neue Basisklassen Element zu verwenden.

Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen. Weitere Informationen finden Sie unter [shadowingin Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md).

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Shadows` nur auf Klassenebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein `Shadows` -Element eine-Klasse sein muss und keine Quelldatei, ein Namespace, eine Schnittstelle, ein Modul, eine Struktur oder eine Prozedur sein darf.

  Sie können nur ein Shadowingelement in einer einzelnen Deklarations Anweisung deklarieren.

- **Kombinierte Modifizierer.** Sie können nicht `Shadows` mit `Overloads` , `Overrides` oder `Static` in derselben Deklaration angeben.

- **Element Typen.** Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen. Wenn Sie eine Eigenschaft oder Prozedur mit einer anderen Eigenschaft oder Prozedur überschatten, müssen die Parameter und der Rückgabetyp nicht mit denen in der Basisklassen Eigenschaft oder-Prozedur identisch sein.

- **Den.** Das Shadowing-Element in der Basisklasse ist normalerweise nicht in der abgeleiteten Klasse verfügbar, die es Shadowing durchführt. Es gelten jedoch die folgenden Überlegungen.

  - Wenn auf das Shadowing-Element nicht über den Code zugegriffen werden kann, auf das verwiesen wird, wird der Verweis in das Shadowing-Element aufgelöst. Wenn ein-Element z. b `Private` . einen Schatten für ein Basisklassen Element besitzt, greift Code, der nicht über die Berechtigung für den Zugriff auf das Element verfügt, `Private` stattdessen auf das Basisklassen Element

  - Wenn Sie einen Schatten für ein Element durchlaufen, können Sie weiterhin auf das Shadowing Element über ein Objekt zugreifen, das mit dem Typ der Basisklasse deklariert wurde. Sie können auch über auf Sie zugreifen `MyBase` .

Der `Shadows`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Class-Anweisung](../statements/class-statement.md)

- [Const-Anweisung](../statements/const-statement.md)

- [Declare Statement](../statements/declare-statement.md)

- [Delegate-Anweisung](../statements/delegate-statement.md)

- [Dim-Anweisung](../statements/dim-statement.md)

- [Enum-Anweisung](../statements/enum-statement.md)

- [Event-Anweisung](../statements/event-statement.md)

- [Function-Anweisung](../statements/function-statement.md)

- [Interface-Anweisung](../statements/interface-statement.md)

- [Property Statement](../statements/property-statement.md)

- [Structure Statement](../statements/structure-statement.md)

- [Sub-Anweisung](../statements/sub-statement.md)

## <a name="see-also"></a>Weitere Informationen

- [Freigegeben](shared.md)
- [Statisch](static.md)
- [Privat](private.md)
- [Me, My, MyBase und MyClass](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [MustOverride](mustoverride.md)
- [NotOverridable](notoverridable.md)
- [Overloads](overloads.md)
- [Overrides](overridable.md)
- [Überschreibt](overrides.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
