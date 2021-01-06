---
title: Dienst-Netzen-GrpC für WCF-Entwickler
description: Verwenden eines Dienst Netzes zum Weiterleiten und Ausgleichen von Anforderungen an GrpC-Dienste in einem Kubernetes-Cluster.
ms.date: 12/15/2020
ms.openlocfilehash: a1c72a4facf1c133af912bbee242328653a051b6
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938129"
---
# <a name="service-meshes"></a>Dienstmeshes

Ein Dienst Netz ist eine Infrastrukturkomponente, die die Steuerung der Routing Dienst Anforderungen innerhalb eines Netzwerks übernimmt. Dienst-Netzen können alle Arten von Problemen auf Netzwerkebene in einem Kubernetes-Cluster verarbeiten, einschließlich:

- Dienstermittlung
- Lastenausgleich
- Fehlertoleranz
- Verschlüsselung
- Überwachung

Kubernetes Service-Netzen arbeiten durch Hinzufügen eines zusätzlichen Containers ( *Sidecar Proxy*) zu jedem Pod, der im Mesh enthalten ist. Der Proxy übernimmt die Verarbeitung aller eingehenden und ausgehenden Netzwerk Anforderungen. Anschließend können Sie die Konfiguration und Verwaltung der Netzwerkprobleme getrennt von den Anwendungs Containern behalten. In vielen Fällen erfordern diese Trennung keine Änderungen am Anwendungscode.

Im [Beispiel im vorherigen Kapitel](kubernetes.md#test-the-application)wurden die GrpC-Anforderungen aus der Webanwendung alle an eine einzelne Instanz des GrpC-Diensts weitergeleitet. Dies liegt daran, dass der Hostname des Diensts in eine IP-Adresse aufgelöst wird und diese IP-Adresse für die Lebensdauer der Instanz zwischengespeichert wird `HttpClientHandler` . Möglicherweise kann dieses Verhalten umgangen werden, indem DNS-Suchvorgänge manuell verarbeitet oder mehrere Clients erstellt werden. Diese Problem Umgehung erschwert jedoch den Anwendungscode, ohne einen geschäftlichen oder Kunden Wert hinzuzufügen.

Wenn Sie ein Dienst Netz verwenden, werden die Anforderungen aus dem Anwendungs Container an den Sidecar-Proxy gesendet. Der Sidecar-Proxy kann Sie dann intelligent über alle Instanzen des anderen Dienstanbieter verteilen. Das Mesh kann auch folgende Aktionen ausführen:

- Reagieren Sie nahtlos auf Fehler einzelner Instanzen eines Dienstanbieter.
- Verarbeiten Sie Wiederholungs Semantik für fehlgeschlagene Aufrufe oder Timeouts.
- Umleiten fehlgeschlagener Anforderungen an eine Alternative Instanz, ohne zur Client Anwendung zurückzukehren.

Der folgende Screenshot zeigt die stockweb-Anwendung, die mit dem Dienst Netz linkerd ausgeführt wird. Es gibt keine Änderungen am Anwendungscode, und das docker-Image wird nicht verwendet. Die einzige Änderung, die erforderlich war, war das Hinzufügen einer Anmerkung zur Bereitstellung in den YAML-Dateien für die `stockdata` -und- `stockweb` Dienste.

![Stockweb mit Service Mesh](media/service-mesh/stockweb-servicemesh-screenshot.png)

Sie können in der Spalte **Server** sehen, dass die Anforderungen aus der stockweb-Anwendung an beide Replikate des StockData-Diensts weitergeleitet wurden, obwohl Sie aus einer einzelnen `HttpClient` Instanz im Anwendungscode stammen. Wenn Sie den Code überprüfen, werden Sie feststellen, dass alle 100-Anforderungen an den StockData-Dienst gleichzeitig mithilfe derselben- `HttpClient` Instanz hergestellt werden. Bei Verwendung des Dienst Netzes sind diese Anforderungen so ausgeglichen, dass viele Dienst Instanzen verfügbar sind.

Dienst-Netzen gelten nur für Datenverkehr innerhalb eines Clusters. Informationen zu externen Clients finden Sie im nächsten Kapitel, [Lastenausgleich](load-balancing.md).

## <a name="service-mesh-options"></a>Dienst Gitter Optionen

Drei allgemeine dienstmesh-Implementierungen sind zurzeit für die Verwendung mit Kubernetes: [istio](https://istio.io), [linkerd](https://linkerd.io)und [Consul Connect](https://consul.io/mesh.html)verfügbar. Alle drei Stellen Anforderungs Routing/Proxy Funktion, Verschlüsselung von Datenverkehr, Ausfallsicherheit, Host-zu-Host-Authentifizierung und Steuerung des Datenverkehrs bereit.

Die Auswahl eines Dienst Netzes hängt von mehreren Faktoren ab:

- Die spezifischen Anforderungen der Organisation hinsichtlich Kosten, Compliance, kostenpflichtigen Support Plänen usw.
- Die Art des Clusters, seine Größe, die Anzahl der bereitgestellten Dienste und die Menge des Datenverkehrs innerhalb des Cluster Netzwerks.
- Einfache Bereitstellung und Verwaltung des Netzes und dessen Verwendung mit Diensten.

## <a name="example-add-linkerd-to-a-deployment"></a>Beispiel: Hinzufügen von linkerd zu einer Bereitstellung

In diesem Beispiel erfahren Sie, wie Sie das linkerd-Dienst Mesh mit der *stockkube* -Anwendung aus [dem vorherigen Abschnitt](kubernetes.md)verwenden.
Zum Befolgen dieses Beispiels müssen Sie [die linkerd-CLI installieren](https://linkerd.io/2/getting-started/#step-1-install-the-cli). Sie können Windows-Binärdateien aus dem Abschnitt herunterladen, in dem GitHub-Releases aufgeführt sind. Stellen Sie sicher, dass Sie die neueste *stabile* Version und nicht eine der Edge-Releases verwenden.

Wenn die linkerd-CLI installiert ist, befolgen Sie [die Anweisungen für die ersten](https://linkerd.io/2/getting-started/index.html) Schritte, um die linkerd-Komponenten auf Ihrem Kubernetes-Cluster zu installieren. Die Anweisungen sind einfach, und die Installation sollte in einer lokalen Kubernetes-Instanz nur einige Minuten dauern.

### <a name="add-linkerd-to-kubernetes-deployments"></a>Hinzufügen von linkerd zu Kubernetes-bereit Stellungen

Die linkerd-CLI stellt einen `inject` Befehl zum Hinzufügen der erforderlichen Abschnitte und Eigenschaften zu Kubernetes-Dateien bereit. Sie können den Befehl ausführen und die Ausgabe in eine neue Datei schreiben.

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

Sie können die neuen Dateien überprüfen, um festzustellen, welche Änderungen vorgenommen wurden. Bei Bereitstellungs Objekten wird eine metadatenanmerkung hinzugefügt, um linkerd mitzuteilen, dass ein Sidecar-Proxy Container in den Pod eingefügt werden soll, wenn er erstellt wird.

Es ist auch möglich, die Ausgabe des `linkerd inject` Befehls direkt an die Pipeline zu übergeben `kubectl` . Die folgenden Befehle funktionieren in PowerShell oder einer beliebigen Linux-Shell.

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a>Überprüfen von Diensten im linkerd-Dashboard

Öffnen Sie das linkerd-Dashboard mithilfe der `linkerd` CLI.

```console
linkerd dashboard
```

Das Dashboard enthält ausführliche Informationen zu allen Diensten, die mit dem Mesh verbunden sind.

![Linkerd-Dashboard mit stockkube-Anwendungen](media/service-mesh/linkerd-screenshot.png)

Wenn Sie die Anzahl der Replikate des StockData-GrpC-Diensts erhöhen, wie im folgenden Beispiel gezeigt, und die stockweb-Seite im Browser aktualisieren, sollten Sie eine Mischung aus IDs in der Spalte **Server** sehen. Diese Mischung zeigt an, dass alle verfügbaren Instanzen Anforderungen erfüllen.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

>[!div class="step-by-step"]
>[Zurück](kubernetes.md)
>[Weiter](load-balancing.md)
