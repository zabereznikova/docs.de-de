---
title: Schwache Verweise
description: Schwache Verweise
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/19/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 22319f2f-0008-4ace-815e-545892a0512a
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: a966f430c00f07d48f2210d64f03d6805f4e3097

---

# <a name="weak-references"></a>Schwache Verweise

Der Garbage Collector kann kein Objekt sammeln, das von einer Anwendung verwendet wird, während der Anwendungscode dieses Objekt erreichen kann. Dies wird als starker Verweis der Anwendung auf das Objekt bezeichnet. 

Bei einem schwachen Verweis kann der Garbage Collector das Objekt sammeln, während die Anwendung nach wie vor auf das Objekt zugreifen kann. Ein schwacher Verweis ist nur während der unbestimmten Zeitspanne gültig, bis das Objekt gesammelt wurde, wenn keine starken Verweise vorhanden sind. Wenn Sie einen schwachen Verweis verwenden, kann die Anwendung immer noch einen starken Verweis auf das Objekt erhalten, sodass es nicht gesammelt werden kann. Es besteht jedoch immer das Risiko, dass der Garbage Collector das Objekt zuerst erreicht, bevor ein starker Verweis erneut hergestellt wird.

Schwache Verweise sind hilfreich für Objekte, die viel Speicher belegen, aber leicht wieder erstellt werden können, wenn sie von der Garbage Collection freigegeben werden. 

Angenommen, in der Strukturansicht wird für den Benutzer eine komplexe hierarchische Optionsauswahl dargestellt. Wenn die zugrunde liegenden Daten umfangreich sind, ist es ineffizient, die Strukturansicht im Speicher zu behalten, wenn der Benutzer mit einem anderen Teil der Anwendung beschäftigt ist. 

Wenn der Benutzer sich mit einem anderen Teil der Anwendung befasst, können Sie mit der [WeakReference](xref:System.WeakReference)-Klasse oder der [WeakReference&lt;T&gt;](xref:System.WeakReference%601)-Klasse einen schwachen Verweis auf die Strukturansicht erstellen und alle starken Verweise zerstören. Wenn der Benutzer wieder zur Strukturansicht zurückwechselt, versucht die Anwendung, einen starken Verweis auf die Strukturansicht zu erhalten und vermeidet, wenn dies gelingt, eine Neuerstellung der Strukturansicht.

Um einen schwachen Verweis auf ein Objekt zu erstellen, erstellen Sie mit der Instanz des zu verfolgenden Objekts einen [WeakReference](xref:System.WeakReference). Sie legen dann die [Target](xref:System.WeakReference.Target)-Eigenschaft für dieses Objekt fest und legen den ursprünglichen Verweis auf das Objekt auf null fest. 

## <a name="short-and-long-weak-references"></a>Kurze und lange schwache Verweise

Sie können einen kurzen schwachen Verweis oder einen langen schwachen Verweis erstellen: 

* Short

  Das Ziel eines kurzen schwachen Verweises wird `null`, wenn das Objekt von der Garbage Collection freigegeben wird. Der schwache Verweis ist selbst ein verwaltetes Objekt und unterliegt wie jedes andere verwaltete Objekt der Garbage Collection. Ein kurzer schwacher Verweis ist der Standardkonstruktor für [WeakReference](xref:System.WeakReference). 

* Long

  Ein langer schwacher Verweis wird beibehalten, nachdem die [Finalize](xref:System.Object.Finalize)-Methode des Objekts aufgerufen wurde. Dadurch kann das Objekt neu erstellt werden, aber der Zustand des Objekts bleibt unvorhersehbar. Um einen langen Verweis zu verwenden, geben Sie `true` im [WeakReference](xref:System.WeakReference)-Konstruktor an. 

  Wenn der Objekttyp keine [Finalize](xref:System.Object.Finalize)-Methode besitzt, werden die Funktionen des kurzen schwachen Verweises angewendet, und der schwache Verweis ist nur so lange gültig, bis das Ziel gesammelt wurde, was nach der Ausführung des Finalizers jederzeit möglich ist.

Um einen starken Verweis zu erstellen und das Objekt erneut zu verwenden, wandeln Sie die [Target](xref:System.WeakReference.Target)-Eigenschaft eines [WeakReference](xref:System.WeakReference) in den Typ des Objekts um. Wenn die [Target](xref:System.WeakReference.Target)-Eigenschaft `null` zurückgibt, wurde das Objekt gesammelt. Andernfalls können Sie das Objekt weiterhin verwenden, weil die Anwendung einen starken Verweis darauf wiederhergestellt hat.

## <a name="guidelines-for-using-weak-references"></a>Richtlinien für die Verwendung von schwachen Verweisen

Verwenden Sie lange schwache Verweise nur, wenn dies notwendig ist, da der Zustand des Objekts nach Abschluss unvorhersehbar ist. 

Vermeiden Sie, schwache Verweise auf kleine Objekte zu verwenden, da der Zeiger selbst möglicherweise genauso groß oder größer ist. 

Vermeiden Sie, schwache Verweise als automatische Lösung für Speicherverwaltungsprobleme zu verwenden. Entwickeln Sie stattdessen eine wirksame Richtlinie zum Zwischenspeichern für die Behandlung von Objekten der Anwendung. 

## <a name="see-also"></a>Siehe auch

[Garbage Collection in .NET](index.md)



<!--HONumber=Nov16_HO3-->


