---
title: Skalieren von Containern und serverlosen Anwendungen
description: Skalieren von cloudbasierten Anwendungen mit dem Azure Kubernetes-Dienst, um die Benutzer Anforderungen zu erfüllen.
ms.date: 04/13/2020
ms.openlocfilehash: b4580e6994611ad394bbaa2d5bb07f64c2798569
ms.sourcegitcommit: 5988e9a29cedb8757320817deda3c08c6f44a6aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2020
ms.locfileid: "82199923"
---
# <a name="scaling-containers-and-serverless-applications"></a>Skalieren von Containern und serverlosen Anwendungen

Es gibt zwei Möglichkeiten, eine Anwendung zu skalieren: "up" oder "out". Das erste bezieht sich auf das Hinzufügen von Kapazität zu einer einzelnen Ressource, während Letzteres auf das Hinzufügen von weiteren Ressourcen zum Erhöhen der Kapazität verweist.

## <a name="the-simple-solution-scaling-up"></a>Einfache Lösung: zentrales hochskalieren

Das Upgrade eines vorhandenen Host Servers mit erhöhter CPU-, Arbeitsspeicher-, Datenträger-e/a-Geschwindigkeit und Netzwerk-e/a-Geschwindigkeit wird als zentrales *hochskalieren*bezeichnet. Das zentrales hochskalieren einer cloudbasierten Anwendung umfasst die Auswahl von Ressourcen, die vom cloudhersteller unterstützt werden. Beispielsweise können Sie einen neuen Knoten Pool mit größeren VMs in Ihrem Kubernetes-Cluster. Migrieren Sie dann Ihre containerisierten Dienste zum neuen Pool.

Server Lose apps werden zentral hochskaliert, indem Sie den [Premium Functions-Plan](https://docs.microsoft.com/azure/azure-functions/functions-scale) oder Premium-instanzgrößen aus einem dedizierten App Service-Plan auswählen.

## <a name="scaling-out-cloud-native-apps"></a>Horizontales Skalieren von Cloud-Native apps

In der Cloud native Anwendungen kommt es häufig zu großen Schwankungen bei Bedarf, und die Skalierung ist für einen bestimmten Zeitpunkt erforderlich. Sie bevorzugen das horizontale hochskalieren. Das horizontale hochskalieren erfolgt horizontal durch Hinzufügen zusätzlicher Computer (Knoten genannt) oder Anwendungs Instanzen zu einem vorhandenen Cluster. In Kubernetes können Sie manuell skalieren, indem Sie die Konfigurationseinstellungen für die APP (z. b. das [Skalieren eines Knoten Pools](https://docs.microsoft.com/azure/aks/use-multiple-node-pools#scale-a-node-pool-manually)) oder die automatische Skalierung anpassen.

AKS-Cluster können auf eine von zwei Arten automatisch skaliert werden:

Zuerst überwacht der [horizontale Pod AutoScaler](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale#autoscale-pods) die Ressourcennachfrage und skaliert ihre Pod-Replikate automatisch entsprechend. Wenn der Datenverkehr zunimmt, werden zusätzliche Replikate automatisch bereitgestellt, um ihre Dienste horizontal zu skalieren. Wenn die Nachfrage abnimmt, werden Sie auch entfernt, um ihre Dienste zu skalieren. Sie definieren die Metrik, für die skaliert werden soll, z. b. die CPU-Auslastung. Sie können auch die Mindest-und höchst Anzahl der Replikate angeben, die ausgeführt werden sollen. AKS überwacht diese Metrik und wird entsprechend skaliert.

Als nächstes können Sie mit dem Feature " [AKS-Cluster-AutoScaler](https://docs.microsoft.com/azure/aks/cluster-autoscaler) " Computeknoten in einem Kubernetes-Cluster automatisch skalieren, um die Anforderungen zu erfüllen. Damit können Sie automatisch neue virtuelle Computer zur zugrunde liegenden Azure-VM-Skalierungs Gruppe hinzufügen, wenn mehr computekapazität von erforderlich ist. Außerdem werden Knoten entfernt, wenn Sie nicht mehr benötigt werden.

In Abbildung 3-13 wird die Beziehung zwischen diesen beiden Skalierungs Diensten veranschaulicht.

![Horizontales hochskalieren eines App Service Plans.](./media/aks-cluster-autoscaler.png)

**Abbildung 3-13**. Horizontales hochskalieren eines App Service Plans.

Beides gewährleistet eine optimale Anzahl von Container Instanzen und Computeknoten zur Unterstützung von schwankenden Anforderungen. Die horizontale Pod automatische Skalierungs Funktion optimiert die Anzahl der benötigten Pods. Die automatische Scaler-Cluster Optimierung optimiert die Anzahl der erforderlichen Knoten.

### <a name="scaling-azure-functions"></a>Skalieren von Azure Functions

Azure Functions bei Bedarf automatisch horizontal hochskalieren. Server Ressourcen werden basierend auf der Anzahl ausgelöster Ereignisse dynamisch zugewiesen und entfernt. Ihnen werden nur computeressourcen in Rechnung gestellt, die beim Ausführen ihrer Funktionen verbraucht werden. Die Abrechnung basiert auf der Anzahl von Ausführungen, der Ausführungszeit und dem verwendeten Arbeitsspeicher.

Der Standard Verbrauchs Plan bietet zwar eine wirtschaftliche und skalierbare Lösung für die meisten apps, die Premium-Option ermöglicht Entwicklern jedoch die Flexibilität von benutzerdefinierten Azure Functions Anforderungen. Das Upgrade auf den Premium-Plan bietet Kontrolle über instanzgrößen, vorab erwärmte Instanzen (zur Vermeidung von Kaltstart Verzögerungen) und dedizierten VMS.

>[!div class="step-by-step"]
>[Zurück](deploy-containers-azure.md)
>[Weiter](other-deployment-options.md)
