---
title: Bereinigen von nicht verwalteten Ressourcen
ms.date: 05/13/2020
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
ms.openlocfilehash: aeb39f32c97424646b85b26ed9c4ed0e350d196b
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287609"
---
# <a name="cleaning-up-unmanaged-resources"></a>Bereinigen von nicht verwalteten Ressourcen

Für die meisten von der App erstellten Objekte führt der [Garbage Collector von .NET](index.md) die Speicherverwaltung aus. Wenn Sie jedoch Objekte erstellen, die nicht verwaltete Ressourcen enthalten, müssen Sie diese Ressourcen explizit freigeben, wenn sie nicht mehr verwendet werden. Die geläufigsten Typen nicht verwalteter Ressourcen sind Objekte, die Betriebssystemressourcen umschließen, wie etwa Dateien, Fenster, Netzwerkverbindungen oder Datenbankverbindungen. Der Garbage Collector kann die Lebensdauer eines Objekts nachverfolgen, das eine nicht verwaltete Ressource kapselt, er kann jedoch die nicht verwaltete Ressource nicht freigeben und bereinigen.

Wenn Ihre Typen nicht verwaltete Ressourcen verwenden, gehen Sie wie folgt vor:

- Implementieren Sie das [Dispose-Muster](implementing-dispose.md). Hierfür müssen Sie eine <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung bereitstellen, um die deterministische Freigabe nicht verwalteter Ressourcen zu ermöglichen. Ein Consumer Ihres Typs ruft <xref:System.IDisposable.Dispose%2A> auf, wenn das Objekt (und die Ressourcen, die es verwendet) nicht mehr benötigt wird. Die <xref:System.IDisposable.Dispose%2A>-Methode gibt die nicht verwalteten Ressourcen sofort frei.

- Falls ein Consumer Ihres Typs vergisst, <xref:System.IDisposable.Dispose%2A> aufzurufen, sorgen Sie dafür, dass die nicht verwalteten Ressourcen freigegeben werden. Hierfür gibt es zwei Möglichkeiten:

  - Verwenden Sie ein SafeHandle, um die nicht verwaltete Ressource zu umschließen. Dies ist das empfohlene Verfahren. SafeHandles werden von der abstrakten <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>-Klasse abgeleitet und enthalten eine robuste <xref:System.Object.Finalize%2A>-Methode. Wenn Sie ein SafeHandle verwenden, implementieren Sie einfach die <xref:System.IDisposable>-Schnittstelle, und rufen Sie die <xref:System.Runtime.InteropServices.SafeHandle.Dispose%2A>-Methode des SafeHandle in der <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung auf. Der Finalizer des SafeHandle wird automatisch vom Garbage Collector aufgerufen, wenn dessen <xref:System.IDisposable.Dispose%2A>-Methode nicht aufgerufen wird.

    – **oder** –

  - Überschreiben Sie die <xref:System.Object.Finalize%2A?displayProperty=nameWithType> -Methode. Der Abschluss aktiviert die nicht deterministische Freigabe von nicht verwalteten Ressourcen, wenn der Consumer eines Typs <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> nicht aufrufen kann, um sie deterministisch freizugeben. Definieren Sie einen [Finalizer](../../csharp/programming-guide/classes-and-structs/destructors.md), indem Sie die <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode überschreiben.

  > [!WARNING]
  > Da aber der Objektabschluss ein komplexer und fehleranfälliger Vorgang sein kann, sollten Sie ein SafeHandle verwenden, anstatt einen eigenen Finalizer bereitzustellen.

Consumer Ihres Typs können dann die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung direkt aufrufen, um Arbeitsspeicher freizugeben, der von nicht verwalteten Ressourcen verwendet wird. Wenn Sie eine <xref:System.IDisposable.Dispose%2A>-Methode ordnungsgemäß implementieren, stellt entweder die <xref:System.Object.Finalize%2A>-Methode des SafeHandles oder Ihre eigene Überschreibung der <xref:System.Object.Finalize%2A?displayProperty=nameWithType>-Methode eine Absicherung zur Bereinigung der Ressourcen für den Fall dar, dass die <xref:System.IDisposable.Dispose%2A>-Methode nicht aufgerufen wird.

## <a name="in-this-section"></a>In diesem Abschnitt

[Implementieren einer Dispose-Methode](implementing-dispose.md) beschreibt, wie das Dispose-Muster für die Freigabe nicht verwalteter Ressourcen implementiert wird.

[Verwenden von Objekten, die IDisposable implementieren`IDisposable`](using-objects.md) beschreibt, wie Consumer eines Typs sicherstellen, dass dessen <xref:System.IDisposable.Dispose%2A>-Implementierung aufgerufen wird. Sie sollten die `using`-Anweisung in C# (oder die `Using`-Anweisung in Visual Basic) verwenden, um dies durchzuführen.

## <a name="reference"></a>Referenz

| Typ/Member | Beschreibung |
|--|--|
| <xref:System.IDisposable?displayProperty=nameWithType> | Definiert die <xref:System.IDisposable.Dispose%2A>-Methode zum Freigeben von nicht verwalteten Ressourcen. |
| <xref:System.Object.Finalize%2A?displayProperty=nameWithType> | Ermöglicht den Objektabschluss, wenn nicht verwaltete Ressourcen nicht durch die <xref:System.IDisposable.Dispose%2A>-Methode freigegeben werden. |
| <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType> | Unterdrückt einen Abschluss. Diese Methode wird normalerweise von einer `Dispose`-Methode aufgerufen, um zu verhindern, dass ein Finalizer ausgeführt wird. |
