---
title: Kombinieren von Containern und Server losen Ansätzen für cloudnative Dienste
description: Kombinieren von Containern und Kubernetes mit Server losen Ansätzen
ms.date: 05/13/2020
ms.openlocfilehash: b1b85519ce02ddd1d69735d872cf24fadcc81ef7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91160891"
---
# <a name="combining-containers-and-serverless-approaches"></a>Kombinieren von Containern und serverlosen Ansätzen

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

Wenn das Projekt erstellt wird, enthält es eine dockerfile-Datei und die Worker-Laufzeit, die für konfiguriert ist `dotnet` . Nun können Sie Ihre Funktion lokal erstellen und testen. Erstellen Sie Sie, und führen Sie Sie mit den  `docker build` Befehlen und aus `docker run` . Ausführliche Schritte zum Erstellen von Azure Functions mit der Docker-Unterstützung finden Sie im Tutorial [Erstellen einer Funktion unter Linux mithilfe eines benutzerdefinierten Images](/azure/azure-functions/functions-create-function-linux-custom-image) .

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>Kombinieren von Server lose und Kubernetes mit Keda

In diesem Kapitel haben Sie gesehen, dass die Azure Functions-Plattform automatisch horizontal hochskaliert wird, um die Nachfrage zu erfüllen. Beim Bereitstellen von containerisierten Funktionen in AKS verlieren Sie jedoch die integrierte Skalierungs Funktionalität. Zur Rettung kommt [Kubernetes-basiertes ereignisgesteuert (Keda)](/azure/azure-functions/functions-kubernetes-keda)vor. Sie ermöglicht eine fein abgestimmte automatische Skalierung für das `event-driven Kubernetes workloads,` einschließen von containerisierten Funktionen.

Keda bietet eine ereignisgesteuerte Skalierungs Funktion für die Functions-Laufzeit in einem docker-Container. Keda kann auf der Grundlage der Auslastung von 0 (null) Instanzen skaliert werden (wenn keine Ereignisse eintreten) `n instances` . Sie ermöglicht die automatische Skalierung durch das verfügbar machen von benutzerdefinierten Metriken für die Kubernetes automatische Skalierungs Funktion (horizontale Pod automatische Skalierungs Funktion). Durch Verwendung von Functions-Container mit KEDA können serverlose Funktionen in jedem Kubernetes-Cluster repliziert werden.

Beachten Sie, dass das Keda-Projekt jetzt von der Cloud Native Computing Foundation (cncf) verwaltet wird.

>[!div class="step-by-step"]
>[Zurück](leverage-serverless-functions.md)
>[Weiter](deploy-containers-azure.md)
