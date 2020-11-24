---
title: Timer
description: Erfahren Sie, welche .NET-Timer in einer Multithreadumgebung verwendet werden können.
ms.date: 07/03/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
author: pkulikov
ms.openlocfilehash: 1ab612bc32a84c1248d311b0603a01a32a25199f
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826104"
---
# <a name="timers"></a>Timer

.NET stellt zwei Timer zur Verfügung, die in einer Multithreadumgebung verwendet werden können:

- <xref:System.Threading.Timer?displayProperty=nameWithType>, der eine einmalige Callbackmethode in regelmäßigen Intervallen für einen <xref:System.Threading.ThreadPool>-Thread ausführt.
- <xref:System.Timers.Timer?displayProperty=nameWithType>, der standardmäßig in regelmäßigen Intervallen ein Ereignis in einem <xref:System.Threading.ThreadPool>-Thread auslöst.

> [!NOTE]
> Einige .NET-Implementierungen können zusätzliche Timer enthalten:
>
> - <xref:System.Windows.Forms.Timer?displayProperty=nameWithType>: eine Windows Forms-Komponente, die in regelmäßigen Abständen ein Ereignis auslöst. Die Komponente besitzt keine Benutzeroberfläche und wurde für die Verwendung in einer Singlethreadumgebung entwickelt.  
> - <xref:System.Web.UI.Timer?displayProperty=nameWithType>: eine ASP.NET-Komponente, die asynchrone oder synchrone Webseitenpostbacks in regelmäßigen Intervallen ausführt.
> - <xref:System.Windows.Threading.DispatcherTimer?displayProperty=nameWithType>: ein Timer, der in die <xref:System.Windows.Threading.Dispatcher>-Warteschlange integriert ist. Diese wird in einem festgelegten Zeitintervall und mit einer festgelegten Priorität verarbeitet.

## <a name="the-systemthreadingtimer-class"></a>Die System.Threading.Timer-Klasse

Mithilfe der <xref:System.Threading.Timer?displayProperty=nameWithType>-Klasse können Sie einen Delegaten kontinuierlich in bestimmten Zeitintervallen aufrufen. Sie können diese Klasse auch verwenden, um einen einzelnen Aufruf eines Delegaten in einem bestimmten Zeitintervall zu planen. Der Delegat wird in einem <xref:System.Threading.ThreadPool>-Thread ausgeführt.

Wenn Sie ein <xref:System.Threading.Timer?displayProperty=nameWithType>-Objekt erstellen, geben Sie einen <xref:System.Threading.TimerCallback>-Delegaten an, der die Callbackmethode definiert, ein optionales Zustandsobjekt, das an die Callbackmethode übergeben wird, die Verzögerung vor dem ersten Aufruf der Callbackmethode und das Zeitintervall zwischen den Aufrufen der Callbackmethode. Wenn Sie einen anstehenden Timer löschen möchten, rufen Sie die <xref:System.Threading.Timer.Dispose%2A?displayProperty=nameWithType>-Methode auf.

Im folgenden Beispiel wird ein Timer erstellt, der den bereitgestellten Delegaten zum ersten Mal nach einer Sekunde (1000 Millisekunden) und dann alle zwei Sekunden aufruft. Das Zustandsobjekt im Beispiel wird verwendet, um die Häufigkeit der Aufrufe des Delegaten zu zählen. Der Timer wird beendet, wenn der Delegat mindestens zehnmal aufgerufen wurde.

[!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
[!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
[!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]

Weitere Informationen und Beispiele finden Sie unter <xref:System.Threading.Timer?displayProperty=nameWithType>.

## <a name="the-systemtimerstimer-class"></a>Die System.Timers.Timer-Klasse

Ein weiterer Timer, der in einer Multithreadumgebung verwendet werden kann, ist <xref:System.Timers.Timer?displayProperty=nameWithType>. Dieser löst standardmäßig ein Ereignis in einem <xref:System.Threading.ThreadPool>-Thread aus.

Wenn Sie ein <xref:System.Timers.Timer?displayProperty=nameWithType>-Objekt erstellen, können Sie das Zeitintervall angeben, in dem ein <xref:System.Timers.Timer.Elapsed>-Ereignis ausgelöst werden soll. Verwenden Sie die <xref:System.Timers.Timer.Enabled%2A>-Eigenschaft, um anzugeben, ob ein Timer ein <xref:System.Timers.Timer.Elapsed>-Ereignis auslösen soll. Wenn ein <xref:System.Timers.Timer.Elapsed>-Event nur ausgelöst werden soll, nachdem das angegebene Intervall verstrichen ist, legen Sie <xref:System.Timers.Timer.AutoReset%2A> auf `false` fest. Der Standardwert der <xref:System.Timers.Timer.AutoReset%2A>-Eigenschaft ist `true`. Das bedeutet, dass ein <xref:System.Timers.Timer.Elapsed>-Ereignis regelmäßig in dem von der <xref:System.Timers.Timer.Interval%2A>-Eigenschaft angegebenen Intervall ausgelöst wird.

Weitere Informationen und Beispiele finden Sie unter <xref:System.Timers.Timer?displayProperty=nameWithType>.
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Timer?displayProperty=nameWithType>
- <xref:System.Timers.Timer?displayProperty=nameWithType>
- [Threading Objects and Features (Threadingobjekte und -funktionen)](threading-objects-and-features.md)
