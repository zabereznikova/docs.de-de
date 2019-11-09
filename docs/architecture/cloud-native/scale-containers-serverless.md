---
title: Skalieren von Containern und serverlosen Anwendungen
description: Skalieren Sie Native Cloud-Anwendungen mit dem Azure Kubernetes-Dienst, um die Benutzer Nachfrage zu erfüllen, indem Sie die einzelnen Computerressourcen erhöhen oder die Anzahl der Computer in einem Anwendungs Cluster erhöhen.
ms.date: 09/23/2019
ms.openlocfilehash: 2d0537fb3ed56beb4eccbf9b8c34a5d87793413b
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841012"
---
# <a name="scaling-containers-and-serverless-applications"></a>Skalieren von Containern und serverlosen Anwendungen

Es gibt zwei typische Möglichkeiten, eine Anwendung zu skalieren: zentrales hochskalieren und horizontales hochskalieren. Das erste bezieht sich auf das Hinzufügen von Funktionen zu einem Host, während Letzteres auf das Hinzufügen zur Gesamtzahl der Hosts verweist. Eine gängige Analogie, um dies zu berücksichtigen, ist die Art und Weise, wie Sie sich und einige Freunde innerhalb der Stadt vorstellen können. Wenn es nur einen Freund gibt, können Sie in ihr zwei sitzungdrennwagen springen. Wenn es jedoch drei oder vier ist, müssen Sie möglicherweise einen ihrer SUVs oder minimieren, um die Kapazität zu erhöhen. Wenn die Gesamtzahl allerdings auf ein Dutzend oder mehr erhöht wird, müssen Sie wahrscheinlich mehrere Fahrzeuge nehmen (es sei denn, jemand fährt einen Bus), der das horizontale hochskalieren durch Hinzufügen von weiteren Instanzen (in diesem Fall mehr Fahrzeuge) veranschaulicht. Sehen wir uns an, wie dies für unsere Anwendungen gilt.

## <a name="the-simple-solution-scaling-up"></a>Einfache Lösung: zentrales hochskalieren

Das Aktualisieren vorhandener Server, um Ihnen mehr Ressourcen (CPU, Arbeitsspeicher, Datenträger-e/a-Geschwindigkeit, Netzwerk-e/a-Geschwindigkeit) bereitzustellen, wird als zentrales *hochskalieren*bezeichnet. In nativen cloudanwendungen bezieht sich das zentrales hochskalieren in der Regel nicht auf den Erwerb und die Installation tatsächlicher Hardware auf physischen Computern, sondern auf die Auswahl eines besser verfügbaren Plans aus einer Liste der verfügbaren Optionen Native Cloud-apps werden in der Regel durch Ändern der Größe des virtuellen Computers (VM) zum Hosten der einzelnen Knoten in Ihrem Kubernetes-Knoten Pool zentral hochskaliert. Kubernetes-Konzepte wie Knoten, Cluster und Pods werden im [nächsten Abschnitt](leverage-containers-orchestrators.md)ausführlicher beschrieben. Azure unterstützt eine Vielzahl von VM-Größen, die unter [Windows](https://docs.microsoft.com/azure/virtual-machines/windows/sizes?toc=%2fazure%2fvirtual-machines%2fwindows%2ftoc.json) und [Linux](https://docs.microsoft.com/azure/virtual-machines/linux/sizes)ausgeführt werden. Um Ihre Anwendung vertikal zu skalieren, erstellen Sie einen neuen Knoten Pool mit einer größeren VM-Größe, und migrieren Sie dann Workloads in den neuen Pool. Hierfür sind [mehrere Knoten Pools für Ihren AKS-Cluster](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)erforderlich, eine Funktion, die sich derzeit in der Vorschau Phase befindet. Server Lose apps werden zentral hochskaliert, indem Sie eine [Premium-Plan](https://docs.microsoft.com/azure/azure-functions/functions-scale) -und Premium-instanzgröße auswählen oder einen anderen dedizierten App Service-Plan auswählen.

## <a name="scaling-out-cloud-native-apps"></a>Horizontales Skalieren von Cloud-Native apps

Native Cloud-apps unterstützen das horizontale hochskalieren durch Hinzufügen zusätzlicher Knoten oder Pods zu Service Requests. Dies kann manuell erreicht werden, indem die Konfigurationseinstellungen für die APP (z. b. das [Skalieren eines Knoten Pools](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually)) oder die *Automatische Skalierung*angepasst werden. Die automatische Skalierung passt die Ressourcen an, die von einer App verwendet werden, um auf Anforderungen zu reagieren. Dies ähnelt der Art und Weise, in der ein Thermostat auf Temperatur reagiert, indem eine zusätzliche Heizung oder Kühlung Wenn Sie die automatische Skalierung verwenden, ist die manuelle Skalierung deaktiviert.

AKS-Cluster können auf eine von zwei Arten skaliert werden:

- Der [Cluster automatische Skalierungs Funktion](https://docs.microsoft.com/azure/aks/cluster-autoscaler) achtet auf Pods, die aufgrund von Ressourceneinschränkungen nicht auf Knoten geplant werden können. Nach Bedarf werden zusätzliche Knoten hinzugefügt.
- Der **horizontale Pod automatische Skalierungs Funktion** verwendet den Metrics-Server in einem Kubernetes-Cluster, um die Ressourcenanforderungen von Pods zu überwachen. Wenn ein Dienst mehr Ressourcen benötigt, erhöht automatische Skalierungs Funktion die Anzahl von Pods.

In Abbildung 3-13 wird die Beziehung zwischen diesen beiden Skalierungs Diensten veranschaulicht.

![Horizontales hochskalieren eines App Service Plans.](./media/aks-cluster-autoscaler.png)

**Abbildung 3-13**. Horizontales hochskalieren eines App Service Plans.

Diese Dienste können auch die Anzahl von Pods oder Knoten nach Bedarf verringern. Diese beiden Dienste können zusammenarbeiten und häufig zusammen in einem Cluster bereitgestellt werden. In Kombination mit der horizontalen Pod-automatische Skalierungs Funktion liegt der Schwerpunkt auf der Ausführung der Anzahl von Pods, die zur Erfüllung der Anwendungsanforderungen erforderlich sind. Der Cluster-automatische Skalierungs Funktion konzentriert sich auf die Ausführung der Anzahl der für die Unterstützung der geplanten Pods erforderlichen Knoten.

### <a name="scaling-azure-functions"></a>Skalierungs Azure Functions

Azure Functions unterstützt das horizontale hochskalieren automatisch. Der Standard Verbrauchs Plan fügt Ressourcen basierend auf der Anzahl der auslösenden Ereignisse dynamisch hinzu (und entfernt Sie). Ihnen werden nur computeressourcen in Rechnung gestellt, die verwendet werden, wenn ihre Funktionen ausgeführt werden, basierend auf der Anzahl von Ausführungen, der Ausführungszeit und dem verwendeten Arbeitsspeicher. Mit dem Premium-Plan erhalten Sie dieselben Features, Sie können jedoch auch die verwendeten instanzgrößen steuern, Instanzen bereits erwärmen (um die Verzögerung bei Kaltstarts zu vermeiden) und dedizierte VMS konfigurieren, auf denen die Funktionen ausgeführt werden sollen. Obwohl die Standardkonfiguration für die meisten apps eine wirtschaftliche und skalierbare Lösung bereitstellen sollte, bietet die Premium-Option Entwicklern die Flexibilität, benutzerdefinierte Azure Functions Anforderungen zu erfüllen.

## <a name="references"></a>Verweise

- [AKS-Pools mit mehreren Knoten](https://docs.microsoft.com/azure/aks/use-multiple-node-pools)
- [AKS-Cluster-AutoScaler](https://docs.microsoft.com/azure/aks/cluster-autoscaler)
- [Tutorial: Skalieren von Anwendungen in AKS](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale)
- [Azure Functions skalieren und Hosting](https://docs.microsoft.com/azure/azure-functions/functions-scale)

>[!div class="step-by-step"]
>[Zurück](deploy-containers-azure.md)
>[Weiter](other-deployment-options.md)
