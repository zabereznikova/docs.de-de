---
title: Induzierte Sammlungen
description: Induzierte Sammlungen
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3e09b9dd-a800-4e56-b468-619f910ae22e
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: e120ba44f16b7e4c697d94d270b2ddcc9ae83c48
ms.lasthandoff: 03/02/2017

---

# <a name="induced-collections"></a>Induzierte Sammlungen

In den meisten Fällen können Sie es dem Garbage Collector überlassen, den am besten geeigneten Zeitpunkt für eine Collection zu bestimmen. In seltenen Fällen kann das Erzwingen einer Auflistung jedoch die Leistung der Anwendung erhöhen. In diesen Fällen können Sie die Garbage Collection auslösen, indem Sie die [GC.Collect](xref:System.GC.Collect)-Methode zum Erzwingen einer Garbage Collection wählen. 

Verwenden Sie die [Collect](xref:System.GC.Collect)-Methode, wenn es zu einem bestimmten Zeitpunkt während der Ausführung des Anwendungscodes zu einer erheblichen Reduzierung des verwendeten Arbeitsspeichers kommt. Wenn die Anwendung zum Beispiel ein kompliziertes Dialogfeld mit mehreren Steuerelementen verwendet, kann der Aufruf von [Collect](xref:System.GC.Collect) beim Schließen des Dialogfelds die Leistung erhöhen, indem der vom Dialogfeld verwendete Speicher sofort freigegeben wird. Stellen Sie sicher, dass die Anwendung nicht zu häufig eine Garbage Collection durchführt, das sich dies negativ auf die Leistung auswirken kann, wenn der Garbage Collector vergeblich versucht, Objekte zu ungünstigen Zeitpunkten freizugeben. Sie können einen [GCCollectionMode.Optimized](xref:System.GCCollectionMode.Optimized)-Enumerationswert an die [Collect](xref:System.GC.Collect)-Methode liefern, um nur zu sammeln, wenn die Sammlung produktiv ist, wie im nächsten Abschnitt erläutert wird.

## <a name="gc-collection-mode"></a>Der GC-Sammlungsmodus

Sie können eine der [GC.Collect](xref:System.GC.Collect)-Methodenüberladungen verwenden, die einen [GCCollectionMode](xref:System.GCCollectionMode)-Wert enthält, um das Verhalten einer erzwungenen Sammlung wie folgt zu anzugeben.

GCCollectionMode-Wert | Beschreibung
---------------------- | ----------- 
[Default](xref:System.GCCollectionMode.Default) | Verwendet die Standard-Garbage Collection-Einstellung für die ausgeführte .NET Framework-Version.
[Forced](xref:System.GCCollectionMode.Forced) | Erzwingt die sofortige Durchführung der Garbage Collection. Dies entspricht dem Aufruf der [GC.Collect()](xref:System.GC.Collect)-Überladung. Dies führt zu einer vollständigen blockierenden Auflistung aller Generationen. Sie können auch den großen Objektheap komprimieren, indem Sie die [GCSettings.LargeObjectHeapCompactionMode](xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode)-Eigenschaft auf [GCLargeObjectHeapCompactionMode.CompactOnce](xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce) festlegen, bevor Sie eine unmittelbare vollständige blockierende Garbage Collection erzwingen. 
[Optimized](xref:System.GCCollectionMode.Optimized) | Ermöglicht dem Garbage Collector zu bestimmten, oder der aktuelle Zeitpunkt zum Freigeben von Objekten optimal ist. Der Garbage Collector kann ermitteln, dass eine Auflistung nicht produktiv genug wäre. In diesem Fall kehrt er zurück, ohne Objekte freizugeben.
 
## <a name="background-or-blocking-collections"></a>Hintergrund oder blockierende Auflistungen

Sie können die Methodenüberladung [GC.Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) aufrufen, um anzugeben, ob eine induzierte Sammlung blockiert oder nicht. Der Typ der ausgeführten Sammlung hängt von einer Kombination der *mode*- und *blocking*-Parameter der Methode ab. *mode* ist ein Member der [GCCollectionMode](xref:System.GCCollectionMode)-Enumeration, und *blocking* ist ein [boolescher](xref:System.Boolean) Wert. In der folgenden Tabelle wird die Interaktion der Argumente „mode“ und „blocking“ zusammengefasst. 

*mode* | *blocking* = true | *blocking* = false
------ | ----------------- | ------------------
[Forced](xref:System.GCCollectionMode.Forced) oder [Default](xref:System.GCCollectionMode.Default) | Eine blockierende Auflistung wird so schnell wie möglich ausgeführt. Wenn eine Hintergrundsammlung ausgeführt wird und die Generation 0 oder 1 ist, löst die Methode [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) sofort eine blockierende Sammlung aus und wird zurückgegeben, wenn die Sammlung abgeschlossen ist. Wenn eine Hintergrundsammlung ausgeführt wird und der Generationsparameter 2 lautet, wartet die Methode, bis die Hintergrundsammlung beendet ist, löst eine blockierende Sammlung der Generation 2 aus und gibt dann zurück. | Eine Auflistung wird so schnell wie möglich ausgeführt. Die [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean))-Methode fordert eine Hintergrundsammlung an, dies ist jedoch nicht garantiert. Je nach den Umständen wird eine blockierende Sammlung möglicherweise weiterhin ausgeführt. Wenn eine Hintergrundauflistung bereits ausgeführt wird, gibt die Methode sofort zurück. 
[Optimized](xref:System.GCCollectionMode.Optimized) | Eine blockierende Sammlung kann je nach Zustand des Garbage Collectors und des Generationsparameters ausgeführt werden. Der Garbage Collector versucht, eine optimale Leistung bereitzustellen. | Eine Auflistung kann ausgeführt werden, je nach Zustand des Garbage Collectors. Die [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean))-Methode fordert eine Hintergrundsammlung an, dies ist jedoch nicht garantiert. Je nach den Umständen wird eine blockierende Sammlung möglicherweise weiterhin ausgeführt. Der Garbage Collector versucht, eine optimale Leistung bereitzustellen. Wenn eine Hintergrundauflistung bereits ausgeführt wird, gibt die Methode sofort zurück. 
 
## <a name="see-also"></a>Siehe auch

[Latenzmodi](latency.md)

[Garbage Collection in .NET](index.md)

