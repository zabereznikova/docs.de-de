---
title: event – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
ms.openlocfilehash: eb1805ed55921497fea88e6b39989c876ef003d1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713555"
---
# <a name="event-c-reference"></a>event (C#-Referenz)

Das `event`-Schlüsselwort wird verwendet, um ein Ereignis in einer Publisher-Klasse zu deklarieren.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt das Deklarieren und Auslösen eines Ereignisses, das <xref:System.EventHandler> als zugrunde liegenden Delegattyp verwendet. Für das vollständige Codebeispiel, das auch veranschaulicht, wie der generische Delegattyp <xref:System.EventHandler%601> verwendet wird und wie ein Ereignis abonniert und eine Ereignishandlermethode erstellt wird, finden Sie unter [Vorgehensweise: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen](../../programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).

[!code-csharp[csrefKeywordsModifiers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#7)]

Ereignisse sind eine besondere Art von Multicastdelegaten, die nur aus der Klasse oder Struktur, in der sie deklariert sind (Publisher-Klasse), aufgerufen werden können. Wenn andere Klassen oder Strukturen das Ereignis abonnieren, werden ihre Ereignishandlermethoden aufgerufen werden, wenn die Publisher-Klasse das Ereignis auslöst. Weitere Informationen und Codebeispiele finden Sie unter [Ereignisse](../../programming-guide/events/index.md) und [Delegaten](../../programming-guide/delegates/index.md).

Ereignisse können als [public](./public.md), [private](./private.md), [protected](./protected.md), [internal](./internal.md), [protected internal](./protected-internal.md) oder [private protected](./private-protected.md) markiert werden. Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf das Ereignis zugreifen können. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).

## <a name="keywords-and-events"></a>Schlüsselwörter und Ereignisse

Die folgenden Schlüsselwörter gelten für Ereignisse.

|Schlüsselwort|Beschreibung|Weitere Informationen|
|-------------|-----------------|--------------------------|
|[static](./static.md)|Stellt das Ereignis Aufrufern jederzeit zur Verfügung, auch wenn keine Instanz der Klasse vorhanden ist.|[Statische Klassen und statische Klassenmember](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|
|[virtual](./virtual.md)|Ermöglicht abgeleiteten Klassen, das Ereignisverhalten mithilfe des [override](./override.md)-Schlüsselworts zu überschreiben.|[Vererbung](../../programming-guide/classes-and-structs/inheritance.md)|
|[sealed](./sealed.md)|Gibt an, dass für abgeleitete Klassen „virtual“ nicht mehr gilt.||
|[abstract](./abstract.md)|Der Compiler wird keine `add`- und `remove`-Ereignisaccessorblöcke generieren und daher müssen abgeleitete Klassen ihre eigene Implementierung bereitstellen.||

Ein Ereignis kann mithilfe des [static](./static.md)-Schlüsselworts als statisches Ereignis deklariert werden. Dadurch steht das Ereignis Aufrufern jederzeit zur Verfügung, auch wenn keine Instanz der Klasse vorhanden ist. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).

Ein Ereignis kann mithilfe des [virtual](./virtual.md)-Schlüsselworts als virtuelles Ereignis gekennzeichnet werden. Dies ermöglicht abgeleiteten Klassen, das Ereignisverhalten mithilfe des [override](./override.md)-Schlüsselworts zu überschreiben. Weitere Informationen finden Sie unter [Inheritance (Vererbung)](../../programming-guide/classes-and-structs/inheritance.md). Ein Ereignis, das ein virtuelles Ereignis überschreibt, kann auch [sealed](./sealed.md) sein, was angibt, dass für abgeleitete Klassen „virtual“ nicht mehr gilt. Schließlich kann ein Ereignis als [abstract](./abstract.md) deklariert werden, d.h., dass der Compiler die `add`- und `remove`-Ereignisaccessorblöcke nicht generieren wird. Daher müssen abgeleitete Klassen ihre eigene Implementierung bereitstellen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [add](./add.md)
- [remove](./remove.md)
- [Modifizierer](index.md)
- [Kombinieren von Delegaten (Multicastdelegaten)](../../programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
