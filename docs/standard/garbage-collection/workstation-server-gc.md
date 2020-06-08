---
title: Garbage Collection für Arbeitsstationen und Server im Vergleich
description: Informationen zur Garbage Collection für Arbeitsstationen und Server in .NET
ms.date: 04/21/2020
helpviewer_keywords:
- garbage collection, workstation
- garbage collection, server
- workstation garbage collection
- server garbage collection
ms.openlocfilehash: 5ff2b1fe2f997913e071f35ec5abb167ed757608
ms.sourcegitcommit: 5280b2aef60a1ed99002dba44e4b9e7f6c830604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "84306694"
---
# <a name="workstation-and-server-garbage-collection"></a>Garbage Collection für die Arbeitsstation und Garbage Collection auf dem Server

Der Garbage Collector optimiert sich selbst und kann in einer Vielzahl von Szenarien funktionieren. Sie können jedoch [die Art der Garbage Collection](../../core/run-time-config/garbage-collector.md#flavors-of-garbage-collection) anhand der Merkmale der Workload festlegen. Die CLR stellt mehrere Arten der Garbage Collection bereit:

- Die Garbage Collection (GC) für Arbeitsstationen, die für Client-Apps konzipiert ist. Dabei handelt es sich um die GC-Standardmethode für eigenständige Apps. Für gehostete Apps, z. B. die von ASP.NET gehosteten Apps, bestimmt der Host die GC-Standardkonfiguration.

  Die Garbage Collection für die Arbeitsstation kann gleichzeitig oder nicht gleichzeitig erfolgen. Die gleichzeitige (oder *im Hintergrund* stattfindende) Garbage Collection ermöglicht, dass verwaltete Threads während einer Garbage Collection Vorgänge fortsetzen können. Ab .NET Framework 4 wird die [gleichzeitige Garbage Collection](background-gc.md#concurrent-garbage-collection) durch die [Garbage Collection im Hintergrund](background-gc.md) ersetzt.

- Garbage Collection für Server, die für Serveranwendungen vorgesehen ist, die einen hohen Durchsatz und eine hohe Skalierbarkeit erfordern.

  - In .NET Core kann die Garbage Collection auf dem Server nicht-gleichzeitig oder im Hintergrund ausgeführt werden.

  - In .NET Framework 4.5 und höher kann die Garbage Collection auf dem Server nicht-gleichzeitig oder im Hintergrund ausgeführt werden. In .NET Framework 4 und früheren Versionen erfolgt die Garbage Collection auf dem Server gleichzeitig.

Die folgende Abbildung zeigt die dedizierten Threads, die die Garbage Collection auf einem Server ausführen:

![Threads für Garbage Collection auf dem Server](media/gc-server.png)

## <a name="performance-considerations"></a>Überlegungen zur Leistung

### <a name="workstation-gc"></a>Arbeitsstation-GC

Im Folgenden finden Sie Überlegungen zu Threading und Leistung der Garbage Collection auf Arbeitsstationen:

- Die Garbage Collection erfolgt auf dem Benutzerthread, der die Garbage Collection ausgelöst hat, und die Priorität bleibt unverändert. Da Benutzerthreads in der Regel mit normaler Priorität ausgeführt werden, muss der Garbage Collector (der auf einem Thread mit normaler Priorität ausgeführt wird) mit anderen Threads um CPU-Zeit konkurrieren. (Threads, die nativen Code ausführen, werden bei der Garbage Collection für die Arbeitsstation bzw. auf dem Server nicht angehalten.)

- Die Garbage Collection für die Arbeitsstation wird immer auf einem Computer verwendet, der nur einen Prozessor besitzt, unabhängig von der [Konfigurationseinstellung](../../core/run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).

### <a name="server-gc"></a>Server-GC

Im Folgenden finden Sie Überlegungen zu Threading und Leistung der Garbage Collection auf Servern:

- Die Garbage Collection erfolgt auf mehreren dedizierten Threads, die mit der Prioritätsebene `THREAD_PRIORITY_HIGHEST` ausgeführt werden.

- Für jede CPU werden ein Heap und ein dedizierter Thread zum Ausführen der Garbage Collection bereitgestellt, und die Auflistung für die Heaps findet zur gleichen Zeit statt. Jeder Heap enthält einen kleinen Objektheap und einen großen Objektheap, und auf alle Heaps kann über den Benutzercode zugegriffen werden. Objekte auf verschiedenen Heaps können aufeinander verweisen.

- Da mehrere Garbage Collection-Threads zusammenarbeiten, ist die Garbage Collection auf dem Server bei gleicher Heapgröße schneller als die Garbage Collection für die Arbeitsstation.

- Bei der Garbage Collection auf dem Server sind die Segmente häufig größer. Dies ist jedoch nur eine allgemeine Angabe: Die Segmentgröße ist implementierungsspezifisch und unterliegt möglicherweise Änderungen. Wenn Sie eine Anwendung optimieren, sollten Sie keine Annahmen über die Größe der Segmente machen, die vom Garbage Collector zugeordnet werden.

- Die Garbage Collection auf dem Server kann ressourcenintensiv sein. Nehmen Sie beispielsweise an, dass auf einem Computer mit vier Prozessoren zwölf Prozesse vorhanden sind, in denen die Garbage Collection auf dem Server ausgeführt wird. Wenn alle Prozesse die Garbage Collection gleichzeitig durchführen, würden sie sich gegenseitig behindern, da auf demselben Prozessor zwölf Threads geplant würden. Wenn die Prozesse aktiv sind, ist es nicht empfehlenswert, dass sie alle die Garbage Collection auf dem Server verwenden.

Wenn Sie Hunderte von Instanzen einer Anwendung ausführen, sollten Sie erwägen, eine Garbage Collection für die Arbeitsstation mit deaktivierter gleichzeitiger Garbage Collection zu verwenden. Dies führt zu weniger Kontextwechseln, wodurch die Leistung verbessert werden kann.

## <a name="see-also"></a>Siehe auch

- [Garbage Collection im Hintergrund](background-gc.md)
- [Runtimekonfigurationsoptionen für die Garbage Collection](../../core/run-time-config/garbage-collector.md)
