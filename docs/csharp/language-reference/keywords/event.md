---
title: event (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- event
- remove
- event_CSharpKeyword
- add
dev_langs:
- CSharp
helpviewer_keywords:
- event keyword [C#]
ms.assetid: 7858fd85-153b-4259-85d0-6aa13c35f174
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 674e36625a68243afff75f6c5028309dc7aff02a
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="event-c-reference"></a>event (C#-Referenz)
Das `event`-Schlüsselwort wird verwendet, um ein Ereignis in einer Publisher-Klasse zu deklarieren.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt das Deklarieren und Auslösen eines Ereignisses, das <xref:System.EventHandler> als zugrunde liegenden Delegattyp verwendet. Für das vollständige Codebeispiel, das auch veranschaulicht, wie der generische Delegattyp <xref:System.EventHandler%601> verwendet wird und wie man ein Ereignis abonniert und eine Ereignishandlermethode erstellt, finden Sie unter [Vorgehensweise: Veröffentlichen von Ereignissen, die den .NET Framework-Richtlinien entsprechen](../../../csharp/programming-guide/events/how-to-publish-events-that-conform-to-net-framework-guidelines.md).  
  
 [!code-cs[csrefKeywordsModifiers#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/event_1.cs)]  
  
 Ereignisse sind eine besondere Art von Multicastdelegaten, die nur aus der Klasse oder Struktur, in der sie deklariert sind (Publisher-Klasse), aufgerufen werden können. Wenn andere Klassen oder Strukturen das Ereignis abonnieren, werden ihre Ereignishandlermethoden aufgerufen werden, wenn die Publisher-Klasse das Ereignis auslöst. Weitere Informationen und Codebeispiele finden Sie unter [Ereignisse](../../../csharp/programming-guide/events/index.md) und [Delegaten](../../../csharp/programming-guide/delegates/index.md).  
  
 Ereignisse können markiert werden als [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md) oder `protected internal`. Diese Zugriffsmodifizierer definieren, wie Benutzer der Klasse auf das Ereignis zugreifen können. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
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
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [add](../../../csharp/language-reference/keywords/add.md)   
 [remove](../../../csharp/language-reference/keywords/remove.md)   
 [Modifizierer](../../../csharp/language-reference/keywords/modifiers.md)   
 [Vorgehensweise: Kombinieren von Delegaten (Multicastdelegaten)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)

