---
title: Kombinieren von Containern und serverlosen Ansätzen
description: Kombinieren von Containern und Kubernetes mit Server losen Ansätzen
ms.date: 06/30/2019
ms.openlocfilehash: 58aff43adbdd2e629370cc685f32c7b61c25f85e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73840592"
---
# <a name="combining-containers-and-serverless-approaches"></a>Kombinieren von Containern und serverlosen Ansätzen

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Häufig basieren auf auf Anwendungen basierende Anwendungen stark auf Containern, Orchestrierungen und Nachrichten Übergabe für die Kommunikation zwischen Knoten. Dieses Messaging ist eine ideale Aufgabe für Azure Functions, aber mit dem Rest der Anwendung, die mit Kubernetes und zugehörigen Tools konfiguriert und bereitgestellt wird, wäre es sinnvoll, Azure Functions innerhalb desselben Toolsets zu nutzen. Glücklicherweise können Sie Azure Functions in docker-Containern einschließen und diese mithilfe der gleichen Prozesse und Tools bereitstellen, wie Sie es auch im Rest ihrer Kubernetes-basierten APP tun.

## <a name="when-does-it-make-sense-to-use-containers-with-serverless"></a>Wann ist es sinnvoll, Container mit Serverless zu verwenden?

Standardmäßig haben Ihre Server losen Funktionen keine Kenntnis von der Plattform, auf der Sie ausgeführt werden. In einigen Fällen haben Sie jedoch möglicherweise bestimmte Anforderungen, die es Ihnen wichtig machen, das Container Image anzupassen, in dem der Code ausgeführt wird. Möglicherweise möchten Sie ein benutzerdefiniertes Image verwenden, da ihre Funktion auf einer bestimmten Sprachversion basiert oder Abhängigkeiten oder Konfigurations Anforderungen aufweist, die vom Standard Image nicht unterstützt werden. In diesen Fällen ist es möglicherweise sinnvoll, ihren eigenen Container anzupassen und die Funktion in einem benutzerdefinierten docker-Container bereitzustellen.

## <a name="when-should-you-avoid-using-containers-with-azure-functions"></a>Wann sollten Sie die Verwendung von Containern mit Azure Functions vermeiden?

Wenn Sie von der Abrechnung des Verbrauchs Plans für ihre Funktion profitieren möchten, können Sie dies nicht tun, wenn Sie Ihren eigenen Container verwenden. Wenn Sie über die Verwendung eines docker-Containers hinausgehen und ihre Funktionen in Ihrem eigenen Kubernetes-Cluster bereitstellen, profitieren Sie nicht mehr von der integrierten Skalierung, die von Azure Functions bereitgestellt wird. Sie müssen die Skalierungs Features von Kubernetes verwenden, die unten beschrieben werden.

## <a name="how-to-combine-serverless-and-docker-containers"></a>Kombinieren von Server losen und docker-Containern

Wenn Sie eine Azure-Funktion in einem docker-Container einbinden möchten, installieren Sie die Azure Functions Core Tools, und führen Sie dann den folgenden Befehl aus:

```console
func init ProjectName --docker
```

Wählen Sie aus den folgenden Optionen die gewünschte workerlaufzeit aus:

- `dotnet` (C#)
- `node` (JavaScript)
- `python`

Wenn das Projekt erstellt wird, enthält es eine dockerfile-Datei. Nun können Sie Ihre Funktion lokal erstellen und testen. Erstellen und führen Sie es mithilfe der Befehle `docker build` und `docker run` aus. Ausführliche Schritte zum Erstellen von Azure Functions mit der Docker-Unterstützung finden Sie im Tutorial [Erstellen einer Funktion unter Linux mithilfe eines benutzerdefinierten Images](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image) .

## <a name="how-to-combine-serverless-and-kubernetes-with-keda"></a>Kombinieren von Server lose und Kubernetes mit Keda

Azure Functions wird automatisch skaliert, um die Nachfrage basierend auf der Rate der Ereignisse zu erfüllen, die eine bestimmte Funktion als Ziel haben. Darüber hinaus können Sie Kubernetes nutzen, um ihre Funktionen zu hosten und die Kubernetes-basierte ereignisgesteuerte automatische Skalierung oder Keda zu verwenden. Wenn keine Ereignisse auftreten, kann Keda auf 0 Instanzen herunterskaliert werden. Anschließend kann es als Reaktion auf Ereignisse die Anzahl der Container zentral hochskalieren, um die Anforderung mithilfe der horizontalen Pod-AutoScaler zu erfüllen. [Erfahren Sie mehr über das Skalieren von Azure Functions mit Keda](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda).

## <a name="references"></a>Verweise

- [Ausführen von Azure Functions in einem docker-Container](https://markheath.net/post/azure-functions-docker)
- [Erstellen einer Funktion unter Linux mithilfe eines benutzerdefinierten Images](https://docs.microsoft.com/azure/azure-functions/functions-create-function-linux-custom-image)
- [Azure Functions mit Kubernetes-ereignisgesteuerte automatische Skalierung](https://docs.microsoft.com/azure/azure-functions/functions-kubernetes-keda)

>[!div class="step-by-step"]
>[Zurück](leverage-serverless-functions.md)
>[Weiter](deploy-containers-azure.md)
