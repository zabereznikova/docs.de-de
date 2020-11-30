---
title: 'Gewusst wie: Hinzufügen von Begrenzungs- und Blockadefunktionen zu einer Sammlung'
ms.date: 03/30/2017
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
ms.openlocfilehash: ba41176d87779fe673fa162d0bf04c10414cdd92
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733476"
---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>Gewusst wie: Hinzufügen von Begrenzungs- und Blockadefunktionen zu einer Sammlung

Dieses Beispiel zeigt, wie eine Begrenzungs- und Blockadefunktion zu einer benutzerdefinierten Auflistungsklasse hinzugefügt werden kann, indem die <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=nameWithType>-Schnittstelle in die Klasse implementiert und anschließend eine Klasseninstanz als interner Speichermechanismus für ein <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>-Objekt verwendet wird. Weitere Informationen zu Begrenzungen und Blockierungen finden Sie unter [Übersicht über BlockingCollection](blockingcollection-overview.md).  
  
## <a name="example"></a>Beispiel  

 Die benutzerdefinierte Auflistungsklasse ist eine grundlegende Prioritätswarteschlange, in der die Prioritätsstufen als Array von <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>-Objekten dargestellt werden. Innerhalb der Warteschlangen erfolgt keine weitere Sortierung.  
  
 Im Clientcode werden drei Tasks gestartet. Der erste Task fragt nur Tastenanschläge ab, um zu jedem Zeitpunkt während der Ausführung einen Abbruch zu ermöglichen. Der zweite Task ist der Producerthread, der neue Elemente zur blockierenden Auflistung hinzufügt und jedem Element basierend auf einem zufälligen Wert eine Priorität zuweist. Der dritte Task entfernt Elemente aus der Auflistung, sobald sie verfügbar werden.  
  
 Sie können das Verhalten einer Anwendung anpassen, indem Sie dafür sorgen, dass ein Thread schneller ausgeführt wird als der andere. Wenn der Producer schneller ausgeführt wird, macht sich die begrenzende Funktionalität bemerkbar, da die blockierende Auflistung verhindert, dass Elemente hinzugefügt werden, wenn bereits die im Konstruktor angegebene Anzahl von Elementen in der Auflistung enthalten ist. Wenn der Consumer schneller ausgeführt wird, macht sich die blockierende Funktionalität bemerkbar, da der Consumer darauf wartet, dass ein neues Element hinzugefügt wird.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 In der Standardeinstellung ist der Speicher für ein <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=nameWithType>-Objekt <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Weitere Informationen

- [Threadsichere Sammlungen](index.md)
