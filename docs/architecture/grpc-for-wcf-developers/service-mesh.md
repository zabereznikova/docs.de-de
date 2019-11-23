---
title: Dienst-Netzen-GrpC für WCF-Entwickler
description: Verwenden eines Dienst Netzes zum Weiterleiten und Ausgleichen von Anforderungen an GrpC-Dienste in einem Kubernetes-Cluster.
ms.date: 09/02/2019
ms.openlocfilehash: d20275082973f30bddbb342da90454401d4f019b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966968"
---
# <a name="service-meshes"></a>Dienst-Netzen

Ein Dienst Netz ist eine Infrastrukturkomponente, die die Steuerung der Routing Dienst Anforderungen innerhalb eines Netzwerks übernimmt. Dienst-Netzen können alle Arten von Problemen auf Netzwerkebene in einem Kubernetes-Cluster verarbeiten, einschließlich:

- Dienst Ermittlung
- Lastenausgleich
- Fehlertoleranz
- Verschlüsselung
- Überwachung

Kubernetes Service-Netzen arbeiten durch Hinzufügen eines zusätzlichen Containers ( *Sidecar Proxy*) zu jedem Pod, der im Mesh enthalten ist. Der Proxy übernimmt die Verarbeitung aller eingehenden und ausgehenden Netzwerk Anforderungen, sodass die Konfiguration und Verwaltung von Netzwerken von den Anwendungs Containern getrennt gehalten werden und in vielen Fällen, ohne dass Änderungen am Anwendungscode erforderlich sind.

Nehmen Sie im vorherigen Kapitel das Beispiel, in dem die GrpC-Anforderungen von der Webanwendung an eine einzelne Instanz des GrpC [-Diensts](kubernetes.md#testing-the-application)weitergeleitet wurden. Dies liegt daran, dass der Hostname des Dienstanbieter in eine IP-Adresse aufgelöst wird und diese IP-Adresse für die Lebensdauer der `HttpClientHandler` Instanz zwischengespeichert wird. Es kann möglich sein, dieses Problem zu umgehen, indem DNS-Suchen manuell verarbeitet oder mehrere Clients erstellt werden. Dies würde jedoch den Anwendungscode erheblich erschweren, ohne einen geschäftlichen oder Kunden Wert hinzuzufügen.

Mithilfe eines Dienst Netzes werden die Anforderungen aus dem Anwendungs Container an den Sidecar-Proxy gesendet, der Sie auf intelligente Weise über alle Instanzen des anderen Dienstanbieter verteilen kann. Das Mesh kann auch folgende Aktionen ausführen:

- Reagieren Sie nahtlos auf Fehler einzelner Instanzen eines Dienstanbieter.
- Verarbeiten von Wiederholungs Semantik für fehlgeschlagene Aufrufe oder Timeouts
- Umleiten fehlgeschlagener Anforderungen an eine Alternative Instanz, ohne dass an die Client Anwendung zurückgegeben wird.

Der folgende Screenshot zeigt die stockweb-Anwendung, die mit dem Dienst Netz linkerd ausgeführt wird, ohne Änderungen am Anwendungscode oder sogar das verwendete docker-Image. Die einzige Änderung, die erforderlich war, war das Hinzufügen einer Anmerkung zur Bereitstellung in den YAML-Dateien für die `stockdata`-und `stockweb` Dienste.

![Stockweb mit Service Mesh](media/service-mesh/stockweb-servicemesh-screenshot.png)

Sie können in der Spalte Server sehen, dass die Anforderungen aus der stockweb-Anwendung an beide Replikate des StockData-Diensts weitergeleitet wurden, obwohl Sie aus einer einzelnen `HttpClient` Instanz im Anwendungscode stammen. Wenn Sie den Code überprüfen, werden Sie feststellen, dass alle 100-Anforderungen an den StockData-Dienst gleichzeitig mit der gleichen `HttpClient` Instanz erstellt werden, aber mit dem Dienst Mesh werden diese Anforderungen über mehrere Dienst Instanzen hinweg ausgeglichen.

Dienst-Netzen gelten nur für Datenverkehr innerhalb eines Clusters. Informationen zu externen Clients finden Sie [im nächsten Kapitel, Lastenausgleich](load-balancing.md).

## <a name="service-mesh-options"></a>Dienst Gitter Optionen

Es gibt drei allgemeine dienstmesh-Implementierungen, die derzeit für die Verwendung mit Kubernetes verfügbar sind: istio, linkerd und Consul Connect. Alle drei Stellen Anforderungs Routing/Proxy Funktion, Verschlüsselung von Datenverkehr, Ausfallsicherheit, Host-zu-Host-Authentifizierung und Steuerung des Datenverkehrs bereit.

Die Auswahl eines Dienst Netzes hängt von mehreren Faktoren ab:

- Die spezifischen Anforderungen der Organisation hinsichtlich Kosten, Compliance, kostenpflichtigen Support Plänen usw.
- Die Art des Clusters, seine Größe, die Anzahl der bereitgestellten Dienste und die Menge des Datenverkehrs innerhalb des Cluster Netzwerks.
- Einfache Bereitstellung und Verwaltung des Netzes und dessen Verwendung mit Diensten.

Weitere Informationen zu den einzelnen Dienst Netzen finden Sie auf den jeweiligen Websites.

- [**Istio** -istio.IO](https://istio.io)
- [**Linkerd** -linkerd.IO](https://linkerd.io)
- [**Konsul** -Consul.IO/Mesh.html](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a>Beispiel: Hinzufügen von linkerd zu einer Bereitstellung

In diesem Beispiel erfahren Sie, wie Sie das linkerd-Dienst Mesh mit der *stockkube* -Anwendung aus [dem vorherigen Abschnitt](kubernetes.md)verwenden.
Zum Befolgen dieses Beispiels müssen Sie [die linkerd-CLI installieren](https://linkerd.io/2/getting-started/#step-1-install-the-cli). Windows-Binärdateien können im Abschnitt "GitHub-Releases" heruntergeladen werden. Stellen Sie sicher, dass Sie die neueste **stabile** Version und nicht eine der Edge-Releases verwenden.

Wenn die linkerd-CLI installiert ist, befolgen Sie die Anweisungen unter [*Getting Started* for the linkerd Web Site], um die linkerd-Komponenten auf Ihrem Kubernetes-Cluster zu installieren. Die Anweisungen sind direkt vorwärts, und die Installation sollte nur einige Minuten in einer lokalen Kubernetes-Instanz dauern.

### <a name="add-linkerd-to-kubernetes-deployments"></a>Hinzufügen von linkerd zu Kubernetes-bereit Stellungen

Die linkerd-CLI stellt einen `inject` Befehl zum Hinzufügen der erforderlichen Abschnitte und Eigenschaften zu Kubernetes-Dateien bereit. Sie können den Befehl ausführen und die Ausgabe in eine neue Datei schreiben.

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

Sie können die neuen Dateien überprüfen, um festzustellen, welche Änderungen vorgenommen wurden. Bei Bereitstellungs Objekten wird eine metadatenanmerkung hinzugefügt, um linkerd mitzuteilen, dass ein Sidecar-Proxy Container in den Pod eingefügt werden soll, wenn er erstellt wird.

Es ist auch möglich, die Ausgabe des `linkerd inject`-Befehls direkt an `kubectl` zu übergeben. Die folgenden Befehle funktionieren in PowerShell oder einer beliebigen Linux-Shell.

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a>Überprüfen von Diensten im linkerd-Dashboard

Starten Sie das linkerd-Dashboard mithilfe der `linkerd` CLI.

```console
linkerd dashboard
```

Das Dashboard enthält ausführliche Informationen zu allen Diensten, die mit dem Mesh verbunden sind.

![Linkerd-Dashboard mit stockkube-Anwendungen](media/service-mesh/linkerd-screenshot.png)

Wenn Sie die Anzahl der Replikate des StockData-GrpC-Diensts erhöhen, wie im folgenden Beispiel gezeigt, und die stockweb-Seite im Browser aktualisieren, sollte eine Mischung aus IDs in der Spalte Server angezeigt werden, die darauf hinweist, dass Anforderungen von allen verfügbaren Instanzen bedient werden. .

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
