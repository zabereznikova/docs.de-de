---
title: "Gewusst wie: Hinzufügen von Begrenzungs- und Blockadefunktionen zu einer Sammlung | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, custom blocking collections
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: df159b1ab3f7c16564ce493a585246c4c461a8f9
ms.lasthandoff: 04/18/2017

---
# <a name="how-to-add-bounding-and-blocking-functionality-to-a-collection"></a>Gewusst wie: Hinzufügen von Begrenzungs- und Blockadefunktionen zu einer Sammlung
Dieses Beispiel zeigt, wie Sie einer benutzerdefinierten Sammlungsklasse begrenzende und blockierende Funktionen hinzufügen, indem Sie die <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName>-Schnittstelle in der Klasse implementieren und dann eine Klasseninstanz als internen Speichermechanismus für eine <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> verwenden. Weitere Informationen zu Begrenzungen und Blockierungen finden Sie unter [Übersicht über BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
## <a name="example"></a>Beispiel  
 Die benutzerdefinierte Sammlungsklasse ist eine einfache Prioritätswarteschlange, in der die Prioritätsstufen als Array aus <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>-Objekten dargestellt werden. Innerhalb der Warteschlangen erfolgt keine weitere Sortierung.  
  
 Im Clientcode werden drei Tasks gestartet. Der erste Task fragt nur Tastenanschläge ab, um zu jedem Zeitpunkt während der Ausführung einen Abbruch zu ermöglichen. Der zweite Task ist der Producerthread, der neue Elemente zur blockierenden Auflistung hinzufügt und jedem Element basierend auf einem zufälligen Wert eine Priorität zuweist. Der dritte Task entfernt Elemente aus der Auflistung, sobald sie verfügbar werden.  
  
 Sie können das Verhalten einer Anwendung anpassen, indem Sie dafür sorgen, dass ein Thread schneller ausgeführt wird als der andere. Wenn der Producer schneller ausgeführt wird, macht sich die begrenzende Funktionalität bemerkbar, da die blockierende Auflistung verhindert, dass Elemente hinzugefügt werden, wenn bereits die im Konstruktor angegebene Anzahl von Elementen in der Auflistung enthalten ist. Wenn der Consumer schneller ausgeführt wird, macht sich die blockierende Funktionalität bemerkbar, da der Consumer darauf wartet, dass ein neues Element hinzugefügt wird.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 Standardmäßig ist der Speicher für eine <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>-Sammlung <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.  
  
## <a name="see-also"></a>Siehe auch  
 [threadsichere Auflistungen](../../../../docs/standard/collections/thread-safe/index.md)
