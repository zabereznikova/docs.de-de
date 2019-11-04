---
title: Implizit typisierte Arrays – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: ac47ec6e69b7910f474378eebd91d58c171a802e
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419551"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a>Implizit typisierte Arrays (C#-Programmierhandbuch)

Sie können ein implizit typisiertes Array erstellen, in dem der Typ der Arrayinstanz von den im Arrayinitialisierer angegebenen Elementen abgeleitet wird. Die Regeln für implizit typisierte Variablen gelten auch für implizit typisierte Arrays. Weitere Informationen zu finden Sie unter [Implizit typisierte lokale Variablen](../classes-and-structs/implicitly-typed-local-variables.md).

Implizit typisierte Arrays werden in der Regel in Abfrageausdrücken zusammen mit anonymen Typen sowie Objekt- und Auflistungsinitialisierern verwendet.

Die folgenden Beispiele zeigen, wie ein implizit typisiertes Array erstellt wird:

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

Beachten Sie im vorherigen Beispiel, dass bei implizit typisierten Arrays auf der linken Seite der Initialisierungsanweisung keine eckigen Klammern verwendet werden. Beachten Sie auch, dass verzweigte Arrays ebenso wie eindimensionale Arrays mithilfe von `new []` initialisiert werden.

## <a name="implicitly-typed-arrays-in-object-initializers"></a>Implizit typisierte Arrays in Objektinitialisierern

Beim Erstellen eines anonymen Typs, der ein Array enthält, muss das Array im Objektinitialisierer des Typs implizit typisiert werden. Im folgenden Beispiel ist `contacts` ein implizit typisiertes Array aus anonymen Typen, von denen jeder ein Array mit dem Namen `PhoneNumbers` enthält. Beachten Sie, dass das Schlüsselwort `var` nicht in den Objektinitialisierern verwendet wird.

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Implizit typisierte lokale Variablen](../classes-and-structs/implicitly-typed-local-variables.md)
- [Arrays](./index.md)
- [Anonyme Typen](../classes-and-structs/anonymous-types.md)
- [Objekt- und Auflistungsinitialisierer](../classes-and-structs/object-and-collection-initializers.md)
- [var](../../language-reference/keywords/var.md)
- [LINQ in C#](../../linq/index.md)
