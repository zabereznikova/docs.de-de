---
title: Schwache Verweise
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a>Schwache Verweise
Der Garbage Collector kann kein Objekt sammeln, das von einer Anwendung verwendet wird, während der Anwendungscode dieses Objekt erreichen kann. Dies wird als starker Verweis der Anwendung auf das Objekt bezeichnet.  
  
 Bei einem schwachen Verweis kann der Garbage Collector das Objekt sammeln, während die Anwendung nach wie vor auf das Objekt zugreifen kann. Ein schwacher Verweis ist nur während der unbestimmten Zeitspanne gültig, bis das Objekt gesammelt wurde, wenn keine starken Verweise vorhanden sind. Wenn Sie einen schwachen Verweis verwenden, kann die Anwendung immer noch einen starken Verweis auf das Objekt erhalten, sodass es nicht gesammelt werden kann. Es besteht jedoch immer das Risiko, dass der Garbage Collector das Objekt zuerst erreicht, bevor ein starker Verweis erneut hergestellt wird.  
  
 Schwache Verweise sind hilfreich für Objekte, die viel Speicher belegen, aber leicht wieder erstellt werden können, wenn sie von der Garbage Collection freigegeben werden.  
  
 Angenommen Sie, eine Strukturansicht, in einer Windows Forms-Anwendung eine komplexe hierarchische Auswahl von Optionen für den Benutzer angezeigt. Wenn die zugrunde liegenden Daten umfangreich sind, ist es ineffizient, die Strukturansicht im Speicher zu behalten, wenn der Benutzer mit einem anderen Teil der Anwendung beschäftigt ist.  
  
 Wenn der Benutzer sofort auf einen anderen Teil der Anwendung gewechselt wird, können Sie die <xref:System.WeakReference> Klasse erstellen einen schwachen Verweis auf die Struktur und alle starken Verweise zerstören. Wenn der Benutzer wieder zur Strukturansicht zurückwechselt, versucht die Anwendung, einen starken Verweis auf die Strukturansicht zu erhalten und vermeidet, wenn dies gelingt, eine Neuerstellung der Strukturansicht.  
  
 Um einen schwachen Verweis mit einem Objekt einzurichten, erstellen Sie eine <xref:System.WeakReference> mit der Instanz des Objekts nachverfolgt werden soll. Legen Sie Sie dann die <xref:System.WeakReference.Target%2A> -Eigenschaft auf dieses Objekt und die ursprüngliche einen Verweis auf das Objekt, das `null`. Ein Codebeispiel finden Sie unter <xref:System.WeakReference> in der Klassenbibliothek.  
  
## <a name="short-and-long-weak-references"></a>Kurze und lange schwache Verweise  
 Sie können einen kurzen schwachen Verweis oder einen langen schwachen Verweis erstellen:  
  
-   Short  
  
     Das Ziel eines kurzen schwachen Verweises wird `null`, wenn das Objekt von der Garbage Collection freigegeben wird. Der schwache Verweis ist selbst ein verwaltetes Objekt und unterliegt wie jedes andere verwaltete Objekt der Garbage Collection.  Ein kurzer schwacher Verweis ist der Standardkonstruktor für <xref:System.WeakReference>.  
  
-   Long  
  
     Ein schwacher Verweis wird beibehalten, nach der objektspezifischen <xref:System.Object.Finalize%2A> -Methode aufgerufen wurde. Dadurch kann das Objekt neu erstellt werden, aber der Zustand des Objekts bleibt unvorhersehbar. Um einen langen Verweis zu verwenden, geben `true` in die <xref:System.WeakReference> Konstruktor.  
  
     Wenn der Typ des Objekts keine <xref:System.Object.Finalize%2A> -Methode, die Funktionen des kurzen schwachen Verweises angewendet, und der schwache Verweis ist nur dann gültig, bis das Ziel gesammelt werden, die auftreten kann, können Sie jederzeit nach der Finalizer ausgeführt werden.  
  
 Um einen starken Verweis herstellen und das Objekt erneut zu verwenden, wandeln Sie die <xref:System.WeakReference.Target%2A> Eigenschaft eine <xref:System.WeakReference> in den Typ des Objekts. Wenn die <xref:System.WeakReference.Target%2A> -Eigenschaft gibt `null`, das Objekt wurde, andernfalls gesammelt, Sie können weiterhin das Objekt zu verwenden, da die Anwendung einen starken Verweis darauf wiederhergestellt hat.  
  
## <a name="guidelines-for-using-weak-references"></a>Richtlinien für die Verwendung von schwachen Verweisen  
 Verwenden Sie lange schwache Verweise nur, wenn dies notwendig ist, da der Zustand des Objekts nach Abschluss unvorhersehbar ist.  
  
 Vermeiden Sie, schwache Verweise auf kleine Objekte zu verwenden, da der Zeiger selbst möglicherweise genauso groß oder größer ist.  
  
 Vermeiden Sie, schwache Verweise als automatische Lösung für Speicherverwaltungsprobleme zu verwenden. Entwickeln Sie stattdessen eine wirksame Richtlinie zum Zwischenspeichern für die Behandlung von Objekten der Anwendung.  
  
## <a name="see-also"></a>Siehe auch  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)
