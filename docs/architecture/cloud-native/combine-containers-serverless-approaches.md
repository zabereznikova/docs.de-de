---
title: Kombinieren von Containern und Server losen Ansätzen für cloudnative Dienste
description: Kombinieren von Containern und Kubernetes mit Server losen Ansätzen
ms.date: 04/23/2020
ms.openlocfilehash: a6ae17543c9075ca84126a4c19f9f51887f7fe9a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895638"
---
# <a name="combining-containers-and-serverless-approaches"></a>Kombinieren von Containern und serverlosen Ansätzen

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Native Cloud-Anwendungen implementieren normalerweise Dienste, die Container und Orchestrierung nutzen. Es gibt oft Möglichkeiten, einige der Dienste der Anwendung als Azure Functions verfügbar zu machen. Bei einer in Kubernetes bereitgestellten cloudbasierten App wäre es jedoch sinnvoll, Azure Functions innerhalb desselben Toolsets zu nutzen. Glücklicherweise können Sie Azure Functions in docker-Containern einschließen und diese mithilfe der gleichen Prozesse und Tools bereitstellen, wie Sie es auch im Rest ihrer Kubernetes-basierten APP tun.

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>Wann ist es sinnvoll, Container mit Serverless zu verwenden?

Ihre Azure-Funktion kennt die Plattform, auf der Sie bereitgestellt ist, nicht. In einigen Szenarien haben Sie möglicherweise bestimmte Anforderungen und müssen die Umgebung anpassen, in der der Funktionscode ausgeführt wird. Sie benötigen ein benutzerdefiniertes Image, das Abhängigkeiten oder eine Konfiguration unterstützt, die vom Standard Image nicht unterstützt wird. In diesen Fällen ist es sinnvoll, ihre Funktion in einem benutzerdefinierten docker-Container bereitzustellen.

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>Wann sollten Sie die Verwendung von Containern mit Azure Functions vermeiden?

Wenn Sie die Verbrauchs Abrechnung verwenden möchten, können Sie die Funktion nicht in einem Container ausführen. Wenn Sie Ihre Funktion in einem Kubernetes-Cluster bereitstellen, profitieren Sie nicht mehr von der integrierten Skalierung, die von Azure Functions bereitgestellt wird. Sie müssen die Skalierungs Features von Kubernetes verwenden, die weiter oben in diesem Kapitel beschrieben werden.

## <a name="how-to-combine-serverless-and-docker-containers"></a>Kombinieren von Server losen und docker-Containern

Wenn Sie eine Azure-Funktion in einem docker-Container einbinden möchten, installieren Sie die [Azure Functions Core Tools](https://github.com/Azure/azure-functions-core-tools) , und führen Sie dann den folgenden Befehl aus:

```console
func init ProjectName --worker-runtime dotnet --docker
```

Wenn das Projekt erstellt wird, enthält es eine dockerfile-Datei und die Worker-Laufzeit `dotnet`, die für konfiguriert ist. Nun können Sie Ihre Funktion lokal erstellen und testen. Erstellen Sie Sie, und führen `docker build` Sie `docker run` Sie mit den Befehlen und aus. Ausführliche Schritte zum Erstellen von Azure Functions mit der Docker-Unterstützung finden Sie im Tutorial [Erstellen einer Funktion unter Linux mithilfe eines benutzerdefinierten Images](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) .

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>Kombinieren von Server lose und Kubernetes mit Keda

In diesem Kapitel haben Sie gesehen, dass die Azure Functions-Plattform automatisch horizontal hochskaliert wird, um die Nachfrage zu erfüllen. Beim Bereitstellen von containerisierten Funktionen in AKS verlieren Sie jedoch die integrierte Skalierungs Funktionalität. Zur Rettung kommt [Kubernetes-basiertes ereignisgesteuert (Keda)](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)vor. Sie ermöglicht eine fein abgestimmte automatische Skalierung `event-driven Kubernetes workloads,` für das Einschließen von containerisierten Funktionen.

Keda bietet eine ereignisgesteuerte Skalierungs Funktion für die Functions-Laufzeit in einem docker-Container. Keda kann auf der Grundlage der Auslastung von 0 (null) Instanzen skaliert `n instances`werden (wenn keine Ereignisse eintreten). Sie ermöglicht die automatische Skalierung durch das verfügbar machen von benutzerdefinierten Metriken für die Kubernetes automatische Skalierungs Funktion (horizontale Pod automatische Skalierungs Funktion). Durch Verwendung von Functions-Container mit KEDA können serverlose Funktionen in jedem Kubernetes-Cluster repliziert werden.

Beachten Sie, dass das Keda-Projekt jetzt von der Cloud Native Computing Foundation (cncf) verwaltet wird.

>[!div class="step-by-step"]
>[Zurück](leverage-serverless-functions.md)
>[Weiter](deploy-containers-azure.md)
