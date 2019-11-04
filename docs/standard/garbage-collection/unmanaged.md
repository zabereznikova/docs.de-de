---
title: Bereinigen von nicht verwalteten Ressourcen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- Close method
- Dispose method
- garbage collector
- garbage collection, unmanaged resources
- cleanup operations
- explicit cleanups
- unmanaged resource cleanup
- Finalize method
ms.assetid: a17b0066-71c2-4ba4-9822-8e19332fc213
ms.openlocfilehash: e05cfb949ee3f206f212ca7015f3ff4c22cd2a12
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423041"
---
# <a name="cleaning-up-unmanaged-resources"></a>Bereinigen von nicht verwalteten Ressourcen

Für die meisten von der App erstellten Objekte führt der Garbage Collector von .NET die Speicherverwaltung aus. Wenn Sie jedoch Objekte erstellen, die nicht verwaltete Ressourcen enthalten, müssen Sie diese Ressourcen explizit freigeben, wenn diese nicht mehr von der App verwendet werden. Die geläufigsten Typen von nicht verwalteten Ressourcen sind Objekte, die Betriebssystemressourcen umschließen, wie etwa Dateien, Fenster, Netzwerkverbindungen oder Datenbankverbindungen. Der Garbage Collector kann die Lebensdauer eines Objekts nachverfolgen, das eine nicht verwaltete Ressource kapselt, er kann jedoch die nicht verwaltete Ressource nicht freigeben und bereinigen.

Wenn Ihre Typen nicht verwaltete Ressourcen verwenden, gehen Sie wie folgt vor:

- Implementieren Sie das [Dispose-Muster](implementing-dispose.md). Hierfür müssen Sie eine <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung bereitstellen, um die deterministische Freigabe von nicht verwalteten Ressourcen zu ermöglichen. Ein Consumer Ihres Typs ruft <xref:System.IDisposable.Dispose%2A> auf, wenn das Objekt (und die Ressourcen, die es verwendet), nicht mehr benötigt wird. Die <xref:System.IDisposable.Dispose%2A>-Methode gibt die nicht verwalteten Ressourcen sofort frei.

- Sorgen Sie dafür, dass die nicht verwalteten Ressourcen freigegeben werden können, falls ein Consumer Ihres Typs vergisst, <xref:System.IDisposable.Dispose%2A> aufzurufen. Hierfür gibt es zwei Möglichkeiten:

  - Verwenden Sie ein SafeHandle, um die nicht verwaltete Ressource zu umschließen. Dies ist das empfohlene Verfahren. SafeHandles werden von der <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>-Klasse abgeleitet und enthalten eine robuste <xref:System.Object.Finalize%2A>-Methode. Wenn Sie ein SafeHandle verwenden, implementieren Sie einfach die <xref:System.IDisposable>-Schnittstelle, und rufen Sie die <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A>-Methode des SafeHandle in der <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung auf. Der Finalizer des SafeHandle wird automatisch vom Garbage Collector aufgerufen, wenn dessen <xref:System.IDisposable.Dispose%2A>-Methode nicht aufgerufen wird.

    – oder –

  - Überschreiben Sie die <xref:System.Object.Finalize%2A?displayProperty=nameWithType> -Methode. Der Abschluss aktiviert die nicht deterministische Freigabe von nicht verwalteten Ressourcen, wenn der Consumer eines Typs <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> nicht aufrufen kann, um sie deterministisch freizugeben. Da aber der Objektabschluss ein komplexer und fehleranfälliger Vorgang sein kann, wird empfohlen, ein SafeHandle zu verwenden, anstatt einen eigenen Finalizer bereitzustellen.

Consumer Ihres Typs können dann die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung direkt aufrufen, um Arbeitsspeicher freizugeben, der von nicht verwalteten Ressourcen verwendet wird. Wenn Sie eine <xref:System.IDisposable.Dispose%2A>-Methode ordnungsgemäß implementieren, stellt entweder die <xref:System.Object.Finalize%2A>-Methode des SafeHandles oder Ihre eigene Überschreibung der <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode eine Absicherung zur Bereinigung der Ressourcen für den Fall dar, dass die <xref:System.IDisposable.Dispose%2A>-Methode nicht aufgerufen wird.

## <a name="in-this-section"></a>In diesem Abschnitt

[Implementieren einer Dispose-Methode](../../../docs/standard/garbage-collection/implementing-dispose.md): Beschreibt, wie das [Dispose-Muster](implementing-dispose.md) für die Freigabe von nicht verwalteten Ressourcen implementiert wird.

[Verwenden von Objekten, die IDisposable implementieren](../../../docs/standard/garbage-collection/using-objects.md): Beschreibt, wie Consumer eines Typs sicherstellen, dass dessen <xref:System.IDisposable.Dispose%2A>-Implementierung aufgerufen wird. Es wird empfohlen, die `using`-Anweisung in C# oder die `Using`-Anweisung in Visual Basic zu verwenden, um dies durchzuführen.

## <a name="reference"></a>Referenz

<xref:System.IDisposable?displayProperty=nameWithType>\
Definiert die <xref:System.IDisposable.Dispose%2A>-Methode zum Freigeben von nicht verwalteten Ressourcen.

<xref:System.Object.Finalize%2A?displayProperty=nameWithType>\
Ermöglicht den Objektabschluss, wenn nicht verwaltete Ressourcen nicht durch die <xref:System.IDisposable.Dispose%2A>-Methode freigegeben werden.

<xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>\
Unterdrückt einen Abschluss. Diese Methode wird normalerweise von einer `Dispose`-Methode aufgerufen, um zu verhindern, dass ein Finalizer ausgeführt wird.
