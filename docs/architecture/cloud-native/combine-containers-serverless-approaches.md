---
title: Kombinieren von Containern und Server losen Ansätzen für cloudnative Dienste
description: Kombinieren von Containern und Kubernetes mit Server losen Ansätzen
ms.date: 04/23/2020
ms.openlocfilehash: fe9e9fd5d07132971d64bc6433a762fb7bd22048
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199663"
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

Azure Functions wird automatisch skaliert, um die Nachfrage basierend auf der Ereignisrate zu erfüllen. AKS kann immer verwendet werden, um ihre Funktionen zu hosten und die Kubernetes-basierte, ereignisgesteuerte automatische Skalierung oder Keda zu verwenden. Wenn keine Ereignisse auftreten, kann Keda auf null Instanzen Herunterskalieren. [Erfahren Sie mehr über das Skalieren von Azure Functions mit Keda](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).

>[!div class="step-by-step"]
>[Zurück](leverage-serverless-functions.md)
>[Weiter](deploy-containers-azure.md)
