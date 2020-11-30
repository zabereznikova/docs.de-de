---
title: Schwache Verweise
description: Erfahren Sie mehr über schwache Verweise. Diese ermöglichen es dem Garbage Collector von .NET, eine Garbage Collection für ein Objekt durchzuführen, während die Anwendung weiterhin auf dieses Objekt zugreifen kann.
ms.date: 03/30/2017
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
ms.openlocfilehash: 1eb5e57f5cc1065f1b8510e4fb0a980a85abca29
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714210"
---
# <a name="weak-references"></a>Schwache Verweise

Der Garbage Collector kann kein Objekt sammeln, das von einer Anwendung verwendet wird, während der Anwendungscode dieses Objekt erreichen kann. Dies wird als starker Verweis der Anwendung auf das Objekt bezeichnet.  
  
 Bei einem schwachen Verweis kann der Garbage Collector das Objekt sammeln, während die Anwendung nach wie vor auf das Objekt zugreifen kann. Ein schwacher Verweis ist nur während der unbestimmten Zeitspanne gültig, bis das Objekt gesammelt wurde, wenn keine starken Verweise vorhanden sind. Wenn Sie einen schwachen Verweis verwenden, kann die Anwendung immer noch einen starken Verweis auf das Objekt erhalten, sodass es nicht gesammelt werden kann. Es besteht jedoch immer das Risiko, dass der Garbage Collector das Objekt zuerst erreicht, bevor ein starker Verweis erneut hergestellt wird.  
  
 Schwache Verweise sind hilfreich für Objekte, die viel Speicher belegen, aber leicht wieder erstellt werden können, wenn sie von der Garbage Collection freigegeben werden.  
  
 Nehmen Sie an, dass in der Strukturansicht in einer Windows Forms-Anwendung für den Benutzer eine komplexe hierarchische Optionsauswahl dargestellt wird. Wenn die zugrunde liegenden Daten umfangreich sind, ist es ineffizient, die Strukturansicht im Speicher zu behalten, wenn der Benutzer mit einem anderen Teil der Anwendung beschäftigt ist.  
  
 Wenn der Benutzer sich mit einem anderen Teil der Anwendung befasst, können Sie mit der <xref:System.WeakReference>-Klasse einen schwachen Verweis auf die Strukturansicht erstellen und alle starken Verweise zerstören. Wenn der Benutzer wieder zur Strukturansicht zurückwechselt, versucht die Anwendung, einen starken Verweis auf die Strukturansicht zu erhalten und vermeidet, wenn dies gelingt, eine Neuerstellung der Strukturansicht.  
  
 Um einen schwachen Verweis auf ein Objekt zu erstellen, erstellen Sie mit der Instanz des zu verfolgenden Objekts einen <xref:System.WeakReference>. Sie legen dann die <xref:System.WeakReference.Target%2A>-Eigenschaft für dieses Objekt fest und legen den ursprünglichen Verweis auf das Objekt auf `null` fest. Ein Codebeispiel finden Sie unter <xref:System.WeakReference> in der Klassenbibliothek.  
  
## <a name="short-and-long-weak-references"></a>Kurze und lange schwache Verweise  

 Sie können einen kurzen schwachen Verweis oder einen langen schwachen Verweis erstellen:  
  
- Short  
  
     Das Ziel eines kurzen schwachen Verweises wird `null`, wenn das Objekt von der Garbage Collection freigegeben wird. Der schwache Verweis ist selbst ein verwaltetes Objekt und unterliegt wie jedes andere verwaltete Objekt der Garbage Collection.  Ein kurzer schwacher Verweis ist der parameterlose Konstruktor für <xref:System.WeakReference>.  
  
- Long  
  
     Ein langer schwacher Verweis wird beibehalten, nachdem die <xref:System.Object.Finalize%2A>-Methode des Objekts aufgerufen wurde. Dadurch kann das Objekt neu erstellt werden, aber der Zustand des Objekts bleibt unvorhersehbar. Um einen langen Verweis zu verwenden, geben Sie `true` im <xref:System.WeakReference>-Konstruktor an.  
  
     Wenn der Objekttyp keine <xref:System.Object.Finalize%2A>-Methode besitzt, werden die Funktionen des kurzen schwachen Verweises angewendet, und der schwache Verweis ist nur so lange gültig, bis das Ziel gesammelt wurde. Dies ist nach der Ausführung des Finalizers jederzeit möglich.  
  
 Um einen starken Verweis zu erstellen und das Objekt erneut zu verwenden, wandeln Sie die <xref:System.WeakReference.Target%2A>-Eigenschaft eines <xref:System.WeakReference> in den Typ des Objekts um. Wenn die <xref:System.WeakReference.Target%2A>-Eigenschaft `null` zurückgibt, wurde das Objekt gesammelt. Andernfalls können Sie das Objekt weiterhin verwenden, weil die Anwendung einen starken Verweis darauf wiederhergestellt hat.  
  
## <a name="guidelines-for-using-weak-references"></a>Richtlinien für die Verwendung von schwachen Verweisen  

 Verwenden Sie lange schwache Verweise nur, wenn dies notwendig ist, da der Zustand des Objekts nach Abschluss unvorhersehbar ist.  
  
 Vermeiden Sie, schwache Verweise auf kleine Objekte zu verwenden, da der Zeiger selbst möglicherweise genauso groß oder größer ist.  
  
 Vermeiden Sie, schwache Verweise als automatische Lösung für Speicherverwaltungsprobleme zu verwenden. Entwickeln Sie stattdessen eine wirksame Richtlinie zum Zwischenspeichern für die Behandlung von Objekten der Anwendung.  
  
## <a name="see-also"></a>Siehe auch

- [Garbage Collection](index.md)
