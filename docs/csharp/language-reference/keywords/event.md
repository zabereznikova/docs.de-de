---
title: event – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
ms.openlocfilehash: a0729324131c5b3d5c49618c715fc4081af40964
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53240527"
---
# <a name="event-c-reference"></a>event (C#-Referenz)
Das `event`-Schlüsselwort wird verwendet, um ein Ereignis in einer Publisher-Klasse zu deklarieren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Deklarieren und Auslösen eines Ereignisses, das <xref:System.EventHandler> als zugrunde liegenden Delegattyp verwendet. Das vollständige Codebeispiel, das auch veranschaulicht, wie Sie den generischen Delegattyp <xref:System.EventHandler%601> verwenden, ein Ereignis abonnieren und eine Ereignishandlermethode erstellen, finden Sie unter [Vorgehensweise: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).  
  
 [!code-csharp[csrefKeywordsModifiers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#7)]
  
 Ereignisse sind eine besondere Art von Multicastdelegaten, die nur aus der Klasse oder Struktur, in der sie deklariert sind (Publisher-Klasse), aufgerufen werden können. Wenn andere Klassen oder Strukturen das Ereignis abonnieren, werden ihre Ereignishandlermethoden aufgerufen werden, wenn die Publisher-Klasse das Ereignis auslöst. Weitere Informationen und Codebeispiele finden Sie unter [Ereignisse](../../../csharp/programming-guide/events/index.md) und [Delegaten](../../../csharp/programming-guide/delegates/index.md).  
  
 Ereignisse können als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) oder [private protected](../../../csharp/language-reference/keywords/private-protected.md) markiert werden. Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf das Ereignis zugreifen können. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
## <a name="keywords-and-events"></a>Schlüsselwörter und Ereignisse  
 Die folgenden Schlüsselwörter gelten für Ereignisse.  
  
|Stichwort|Beschreibung|Weitere Informationen|  
|-------------|-----------------|--------------------------|  
|[static](../../../csharp/language-reference/keywords/static.md)|Stellt das Ereignis Aufrufern jederzeit zur Verfügung, auch wenn keine Instanz der Klasse vorhanden ist.|[Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)|  
|[virtual](../../../csharp/language-reference/keywords/virtual.md)|Ermöglicht abgeleiteten Klassen, das Ereignisverhalten mithilfe des [override](../../../csharp/language-reference/keywords/override.md)-Schlüsselworts zu überschreiben.|[Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md)|  
|[sealed](../../../csharp/language-reference/keywords/sealed.md)|Gibt an, dass für abgeleitete Klassen „virtual“ nicht mehr gilt.||  
|[abstract](../../../csharp/language-reference/keywords/abstract.md)|Der Compiler wird keine `add`- und `remove`-Ereignisaccessorblöcke generieren und daher müssen abgeleitete Klassen ihre eigene Implementierung bereitstellen.||  
  
 Ein Ereignis kann mithilfe des [static](../../../csharp/language-reference/keywords/static.md)-Schlüsselworts als statisches Ereignis deklariert werden. Dadurch steht das Ereignis Aufrufern jederzeit zur Verfügung, auch wenn keine Instanz der Klasse vorhanden ist. Weitere Informationen finden Sie unter [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Ein Ereignis kann mithilfe des [virtual](../../../csharp/language-reference/keywords/virtual.md)-Schlüsselworts als virtuelles Ereignis gekennzeichnet werden. Dies ermöglicht abgeleiteten Klassen, das Ereignisverhalten mithilfe des [override](../../../csharp/language-reference/keywords/override.md)-Schlüsselworts zu überschreiben. Weitere Informationen finden Sie unter [Vererbung](../../../csharp/programming-guide/classes-and-structs/inheritance.md). Ein Ereignis, das ein virtuelles Ereignis überschreibt, kann auch [sealed](../../../csharp/language-reference/keywords/sealed.md) sein, was angibt, dass für abgeleitete Klassen „virtual“ nicht mehr gilt. Schließlich kann ein Ereignis als [abstract](../../../csharp/language-reference/keywords/abstract.md) deklariert werden, d.h., dass der Compiler die `add`- und `remove`-Ereignisaccessorblöcke nicht generieren wird. Daher müssen abgeleitete Klassen ihre eigene Implementierung bereitstellen.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  

- [C#-Referenz](../../../csharp/language-reference/index.md)  
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)  
- [add](../../../csharp/language-reference/keywords/add.md)  
- [remove](../../../csharp/language-reference/keywords/remove.md)  
- [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)  
- [Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)
