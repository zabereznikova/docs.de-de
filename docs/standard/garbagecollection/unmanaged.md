---
title: Bereinigen von nicht verwalteten Ressourcen
description: Bereinigen von nicht verwalteten Ressourcen
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/18/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 8c97c3e2-8619-47ce-ae29-d6a3140bfa83
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: c0600eb27c27261f6496fb45310514f7f716b3b3

---

# <a name="cleaning-up-unmanaged-resources"></a>Bereinigen von nicht verwalteten Ressourcen

Für die meisten von der App erstellten Objekte führt der Garbage Collector von .NET die Speicherverwaltung aus. Wenn Sie jedoch Objekte erstellen, die nicht verwaltete Ressourcen enthalten, müssen Sie diese Ressourcen explizit freigeben, wenn diese nicht mehr von der App verwendet werden. Die geläufigsten Typen von nicht verwalteten Ressourcen sind Objekte, die Betriebssystemressourcen umschließen, wie etwa Dateien, Fenster, Netzwerkverbindungen oder Datenbankverbindungen. Der Garbage Collector kann die Lebensdauer eines Objekts nachverfolgen, das eine nicht verwaltete Ressource kapselt, er kann jedoch die nicht verwaltete Ressource nicht freigeben und bereinigen. 

Wenn Ihre Typen nicht verwaltete Ressourcen verwenden, gehen Sie wie folgt vor: 

* Implementieren Sie das Dispose-Muster. Hierfür müssen Sie eine [IDisposable.Dispose](xref:System.IDisposable.Dispose)-Implementierung bereitstellen, um die deterministische Freigabe von nicht verwalteten Ressourcen zu ermöglichen. Ein Consumer Ihres Typs ruft [Dispose](xref:System.IDisposable.Dispose) auf, wenn das Objekt (und die Ressourcen, die es verwendet), nicht mehr benötigt wird. Die [Dispose](xref:System.IDisposable.Dispose)-Methode gibt die nicht verwalteten Ressourcen sofort frei. 

* Sorgen Sie dafür, dass die nicht verwalteten Ressourcen freigegeben werden können, falls ein Consumer Ihres Typs vergisst, [Dispose](xref:System.IDisposable.Dispose) aufzurufen. Hierfür gibt es zwei Möglichkeiten: 

    * Verwenden Sie ein SafeHandle, um die nicht verwaltete Ressource zu umschließen. Dies ist das empfohlene Verfahren. SafeHandles werden von der [System.Runtime.InteropServices.SafeHandle](xref:System.Runtime.InteropServices.SafeHandle)-Klasse abgeleitet und enthalten eine robuste [Finalize](xref:System.Object.Finalize)-Methode. Wenn Sie ein SafeHandle verwenden, implementieren Sie einfach die [IDisposable](xref:System.IDisposable)-Schnittstelle, und rufen Sie die [Dispose](xref:System.IDisposable.Dispose)-Methode des SafeHandle in der [IDisposable.Dispose](xref:System.IDisposable.Dispose)-Implementierung auf. Der Finalizer des SafeHandle wird automatisch vom Garbage Collector aufgerufen, wenn dessen [Dispose](xref:System.IDisposable.Dispose)-Methode nicht aufgerufen wird. 

      – oder –

    * Überschreiben Sie die [Object.Finalize](xref:System.Object.Finalize)-Methode. Der Abschluss aktiviert die nicht deterministische Freigabe von nicht verwalteten Ressourcen, wenn der Consumer eines Typs [IDisposable.Dispose](xref:System.IDisposable.Dispose) nicht aufrufen kann, um sie deterministisch freizugeben. Da aber der Objektabschluss ein komplexer und fehleranfälliger Vorgang sein kann, wird empfohlen, ein SafeHandle zu verwenden, anstatt einen eigenen Finalizer bereitzustellen. 

Consumer Ihres Typs können dann die [IDisposable.Dispose](xref:System.IDisposable.Dispose)-Implementierung direkt aufrufen, um Arbeitsspeicher freizugeben, der von nicht verwalteten Ressourcen verwendet wird. Wenn Sie eine [Dispose](xref:System.IDisposable.Dispose)-Methode ordnungsgemäß implementieren, stellt entweder die [Finalize](xref:System.Object.Finalize)-Methode des SafeHandle oder Ihre eigene Überschreibung der [Object.Finalize](xref:System.Object.Finalize)-Methode eine Absicherung zur Bereinigung der Ressourcen für den Fall dar, dass die [Dispose](xref:System.IDisposable.Dispose)-Methode nicht aufgerufen wird. 

## <a name="in-this-section"></a>In diesem Abschnitt

[Implementieren einer Dispose-Methode](implementing-dispose.md): Beschreibt, wie das Dispose-Muster für die Freigabe von nicht verwalteten Ressourcen implementiert wird.

[Verwenden von Objekten, die IDisposable implementieren](using-objects.md): Beschreibt, wie Consumer eines Typs sicherstellen, dass dessen Dispose-Implementierung aufgerufen wird. Es wird empfohlen, die using-Anweisung in C# oder die Using-Anweisung in Visual Basic zu verwenden, um dies durchzuführen.

## <a name="reference"></a>Verweis

[System.IDisposable](xref:System.IDisposable): Definiert die `Dispose`-Methode zum Freigeben von nicht verwalteten Ressourcen.

[Object.Finalize](xref:System.Object.Finalize): Ermöglicht den Objektabschluss, wenn nicht verwaltete Ressourcen nicht durch die `Dispose`-Methode freigegeben werden. 

[GC. SuppressFinalize](xref:System.GC#System_GC_SuppressFinalize_System_Object_): Unterdrückt einen Abschluss. Diese Methode wird normalerweise von einer `Dispose`-Methode aufgerufen, um zu verhindern, dass ein Finalizer ausgeführt wird. 



<!--HONumber=Nov16_HO3-->


