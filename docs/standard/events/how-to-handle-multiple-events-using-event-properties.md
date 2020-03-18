---
title: 'Gewusst wie: Behandeln mehrerer Ereignisse mit Ereigniseigenschaften'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- event properties [.NET Framework]
- multiple events [.NET Framework]
- event handling [.NET Framework], with multiple events
- events [.NET Framework], multiple
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
ms.openlocfilehash: f74d75a09da350b34dfb067c3d0db8fc669116ac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73124770"
---
# <a name="how-to-handle-multiple-events-using-event-properties"></a>Gewusst wie: Behandeln mehrerer Ereignisse mit Ereigniseigenschaften
Zur Verwendung von Ereigniseigenschaften müssen Sie die Ereigniseigenschaften in der Klasse definieren, die die Ereignisse auslöst. Anschließend müssen Sie die Delegaten für die Ereigniseigenschaften in den Klassen festlegen, die die Ereignisse behandeln. Zum Implementieren mehrerer Ereigniseigenschaften in einer Klasse muss die Klasse den für jedes Ereignis definierten Delegaten intern speichern und verwalten. Ein typischer Ansatz ist, eine Delegatauflistung zu implementieren, die von einem Ereignisschlüssel indiziert wird.  
  
 Zum Speichern der Delegaten für jedes Ereignis können Sie die <xref:System.ComponentModel.EventHandlerList>-Klasse verwenden oder eine eigene Auflistung implementieren. Die Auflistungsklasse muss Methoden für das Festlegen, Aufrufen und Abrufen des Ereignishandlerdelegaten auf der Grundlage des Ereignisschlüssels bereitstellen. Zum Beispiel könnten Sie eine <xref:System.Collections.Hashtable>-Klasse verwenden oder eine benutzerdefinierte Klasse von der <xref:System.Collections.DictionaryBase>-Klasse ableiten. Die Implementierungsdetails der Delegatauflistung müssen nicht außerhalb der Klasse verfügbar gemacht werden.  
  
 Jede Ereigniseigenschaft innerhalb der Klasse definiert eine add-Accessor-Methode und eine remove-Accessor-Methode. Der add-Accessor für eine Ereigniseigenschaft fügt die Eingabedelegatinstanz der Delegatauflistung hinzu. Der remove-Accessor für eine Ereigniseigenschaft entfernt die Eingabedelegatinstanz aus der Delegatauflistung. Die Accessoren für Ereigniseigenschaften verwenden den vordefinierten Schlüssel für die Ereigniseigenschaft, um Instanzen der Delegatauflistung hinzuzufügen bzw. daraus zu entfernen.  
  
### <a name="to-handle-multiple-events-using-event-properties"></a>So behandeln Sie mehrere Ereignisse mit Ereigniseigenschaften  
  
1. Definieren Sie eine Delegatauflistung innerhalb der Klasse, die die Ereignisse auslöst.  
  
2. Definieren Sie einen Schlüssel für jedes Ereignis.  
  
3. Definieren Sie die Ereigniseigenschaften in der Klasse, die die Ereignisse auslöst.  
  
4. Verwenden Sie die Delegatauflistung, um die add- und die remove-Accessor-Methode für die Ereigniseigenschaften zu implementieren.  
  
5. Verwenden Sie die öffentlichen Ereigniseigenschaften, um Ereignishandlerdelegaten in den Klassen, die die Ereignisse auslösen, hinzuzufügen und zu entfernen.  
  
## <a name="example"></a>Beispiel  
 Das folgende C#-Beispiel implementiert die `MouseDown`-Ereigniseigenschaft und die `MouseUp`-Ereigniseigenschaft unter Verwendung einer <xref:System.ComponentModel.EventHandlerList>, um den Delegat jedes Ereignisses zu speichern. Die Schlüsselwörter der Eigenschaftenkonstrukte für Ereignisse sind fett dargestellt.  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ComponentModel.EventHandlerList?displayProperty=nameWithType>
- [Ereignisse](../../../docs/standard/events/index.md)
- <xref:System.Web.UI.Control.Events%2A?displayProperty=nameWithType>
- [Gewusst wie: Deklarieren von benutzerdefinierten Ereignissen, um Speicherplatz zu sparen](../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)
