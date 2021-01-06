---
title: Kubernetes-GrpC für WCF-Entwickler
description: Ausführen ASP.net Core GrpC-Dienste in einem Kubernetes-Cluster.
ms.date: 12/15/2020
ms.openlocfilehash: 0b457d6fa982b5f5b983194d4aedbff0eb782f36
ms.sourcegitcommit: 655f8a16c488567dfa696fc0b293b34d3c81e3df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "97938057"
---
# <a name="kubernetes"></a>Kubernetes

Obwohl es möglich ist, Container auf docker-Hosts manuell auszuführen, empfiehlt es sich, eine Container Orchestrierungs-Engine zu verwenden, um mehrere Instanzen zu verwalten, die auf mehreren Servern in einem Cluster ausgeführt werden. Es sind verschiedene Container Orchestrierungs-Engines verfügbar, einschließlich Kubernetes, docker Swarm und Apache mesos. Aber von diesen Engines entfernt sich Kubernetes weitgehend von der am häufigsten verwendeten und ist daher der Schwerpunkt dieses Kapitels.

Kubernetes umfasst die folgenden Funktionen:

- Bei der **Planung** werden Container auf mehreren Knoten in einem Cluster ausgeführt, und es wird sichergestellt, dass die verfügbare Ressource ausgeglichen genutzt wird, dass Container bei Ausfällen ausgeführt werden und parallele Updates für neue Versionen von Images oder neue Konfigurationen verarbeitet werden.
- Integritäts **Prüfungen** überwachen Container, um den kontinuierlichen Dienst sicherzustellen.
- Die **DNS-& Dienst** Ermittlung übernimmt das Routing zwischen Diensten innerhalb eines Clusters.
- Der Eingang **macht** ausgewählte Dienste extern verfügbar und bietet im allgemeinen Lastenausgleich über Instanzen dieser Dienste hinweg.
- Die **Ressourcenverwaltung** fügt externe Ressourcen wie den Speicher an Container an.

In diesem Kapitel wird ausführlich beschrieben, wie Sie einen ASP.net Core GrpC-Dienst und eine Website bereitstellen, die den Dienst in einem Kubernetes-Cluster verwendet. Die verwendete Beispielanwendung ist im Repository [dotnet-Architecture/GrpC-for-WCF-Developers](https://github.com/dotnet-architecture/grpc-for-wcf-developers/tree/master/KubernetesSample) auf GitHub verfügbar.

## <a name="kubernetes-terminology"></a>Kubernetes-Terminologie

Kubernetes verwendet *die Konfiguration des gewünschten Zustands*: die API wird verwendet, um Objekte wie *Pods*, bereit *Stellungen* und *Dienste* zu beschreiben, und die *Steuerungsebene* übernimmt die Implementierung des gewünschten Zustands auf allen *Knoten* in einem *Cluster*. Ein Kubernetes-Cluster verfügt über einen *Master* Knoten, der die *Kubernetes-API* ausführt, mit der Sie Programm gesteuert oder über das `kubectl` Befehlszeilen Tool kommunizieren können. `kubectl` kann Objekte mit Befehlszeilen Argumenten erstellen und verwalten, funktioniert aber am besten mit YAML-Dateien, die Deklarations Daten für Kubernetes-Objekte enthalten.

### <a name="kubernetes-yaml-files"></a>Kubernetes-YAML-Dateien

Jede Kubernetes YAML-Datei verfügt über mindestens drei Eigenschaften der obersten Ebene:

```yaml
apiVersion: v1
kind: Namespace
metadata:
  # Object properties
```

Die- `apiVersion` Eigenschaft wird verwendet, um anzugeben, für welche Version (und welche API) die Datei vorgesehen ist. Die- `kind` Eigenschaft gibt die Art des Objekts an, das YAML darstellt. Die `metadata` -Eigenschaft enthält Objekteigenschaften wie `name` , `namespace` und `labels` .

Die meisten Kubernetes YAML-Dateien enthalten außerdem einen `spec` Abschnitt, in dem die Ressourcen und die Konfiguration beschrieben werden, die zum Erstellen des Objekts erforderlich sind.

### <a name="pods"></a>Pods

Pods sind die grundlegenden Ausführungs Einheiten in Kubernetes. Sie können mehrere Container ausführen, aber auch zum Ausführen einzelner Container verwendet werden. Der Pod umfasst auch alle Speicherressourcen, die für die Container erforderlich sind, und die Netzwerk-IP-Adresse.

### <a name="services"></a>Dienste

Dienste sind Metadatenobjekte, die Pods (oder Gruppen von Pods) beschreiben und eine Möglichkeit bieten, auf diese innerhalb des Clusters zuzugreifen, wie z. b. das Mapping eines Dienst namens zu einem Satz von Pod-IP-Adressen mithilfe des Cluster-DNS-Diensts.

### <a name="deployments"></a>Bereitstellungen

Bereit Stellungen sind die *gewünschten Zustands* Objekte für Pods. Wenn Sie einen Pod manuell erstellen, wird er nicht neu gestartet, wenn er beendet wird. Mithilfe von bereit Stellungen wird dem Cluster mitgeteilt, welche Pods und wie viele Replikate dieser Pods zum aktuellen Zeitpunkt ausgeführt werden sollen.

### <a name="other-objects"></a>Andere Objekte

Pods, Dienste und bereit Stellungen sind nur drei der grundlegendsten Objekttypen. Es gibt Dutzende von anderen Objekttypen, die von Kubernetes-Clustern verwaltet werden. Weitere Informationen finden Sie in der Dokumentation zu [Kubernetes Concepts](https://kubernetes.io/docs/concepts/) .

### <a name="namespaces"></a>Namespaces

Kubernetes-Cluster sind so konzipiert, dass Sie auf Hunderte oder Tausende von Knoten skaliert werden und eine ähnliche Anzahl von Diensten ausführen. Zum Vermeiden von Konflikten zwischen Objektnamen werden Namespaces zum Gruppieren von Objekten als Teil größerer Anwendungen verwendet. Eigene Dienste von Kubernetes werden in einem `default` Namespace ausgeführt. Alle Benutzer Objekte sollten in ihren eigenen Namespaces erstellt werden, um potenzielle Konflikte mit Standardobjekten oder anderen Mandanten im Cluster zu vermeiden.

## <a name="get-started-with-kubernetes"></a>Erste Schritte mit Kubernetes

Wenn Sie docker Desktop für Windows oder docker Desktop für Mac ausführen, ist Kubernetes bereits verfügbar. Aktivieren Sie Sie einfach im Abschnitt " **Kubernetes** " des Fensters " **Einstellungen** ":

![Aktivieren von Kubernetes in docker Desktop](media/kubernetes/enable-kubernetes-docker-desktop-v2.png)

Wenn Sie einen lokalen Kubernetes-Cluster unter Linux ausführen möchten, sollten Sie [minikube](https://github.com/kubernetes/minikube)oder [MicroK8s](https://microk8s.io/) in Erwägung gezogen, wenn die Linux-Distribution [dockt](https://snapcraft.io/)unterstützt.

Führen Sie den folgenden Befehl aus, um zu bestätigen, dass der Cluster ausgeführt wird und erreichbar ist `kubectl version` :

```console
kubectl version
Client Version: version.Info{Major:"1", Minor:"19", GitVersion:"v1.19.3", GitCommit:"1e11e4a2108024935ecfcb2912226cedeafd99df", GitTreeState:"clean", BuildDate:"2020-10-14T12:50:19Z", GoVersion:"go1.15.2", Compiler:"gc", Platform:"windows/amd64"}
Server Version: version.Info{Major:"1", Minor:"19", GitVersion:"v1.19.3", GitCommit:"1e11e4a2108024935ecfcb2912226cedeafd99df", GitTreeState:"clean", BuildDate:"2020-10-14T12:41:49Z", GoVersion:"go1.15.2", Compiler:"gc", Platform:"linux/amd64"}
```

In diesem Beispiel werden sowohl auf der `kubectl` CLI als auch auf dem Kubernetes-Server Version 1.14.6 ausgeführt. Jede Version von `kubectl` soll die vorherige und die nächste Version des Servers unterstützen `kubectl` . 1,14 sollte also auch mit den Serverversionen 1,13 und 1,15 funktionieren.

## <a name="run-services-on-kubernetes"></a>Ausführen von Diensten auf Kubernetes

Die Beispielanwendung verfügt über ein `kube` Verzeichnis, das drei YAML-Dateien enthält. Die `namespace.yml` Datei deklariert einen benutzerdefinierten Namespace: `stocks` . Die `stockdata.yml` Datei deklariert die Bereitstellung und den Dienst für die GrpC-Anwendung, und die `stockweb.yml` Datei deklariert die Bereitstellung und den Dienst für eine ASP.net Core 5,0 MVC-Webanwendung, die den GrpC-Dienst nutzt.

Um eine `YAML` Datei mit zu verwenden `kubectl` , führen Sie den folgenden Befehl aus `apply -f` :

```console
kubectl apply -f object.yml
```

Der `apply` Befehl überprüft die Gültigkeit der YAML-Datei und zeigt alle Fehler an, die von der API empfangen werden. es wird jedoch nicht gewartet, bis alle in der Datei deklarierten Objekte erstellt wurden, da dieser Schritt einige Zeit in Anspruch nehmen kann. Verwenden Sie den- `kubectl get` Befehl mit den relevanten Objekttypen, um die Objekt Erstellung im Cluster zu überprüfen.

### <a name="the-namespace-declaration"></a>Die Namespace Deklaration

Die Namespace Deklaration ist einfach und erfordert nur das Zuweisen einer `name` :

```yaml
apiVersion: v1
kind: Namespace
metadata:
  name: stocks
```

Verwenden `kubectl` Sie, um die `namespace.yml` Datei anzuwenden und zu bestätigen, dass der Namespace erfolgreich erstellt wurde:

```console
> kubectl apply -f namespace.yml
namespace/stocks created

> kubectl get namespaces
NAME              STATUS   AGE
stocks            Active   2m53s
```

### <a name="the-stockdata-application"></a>Die StockData-Anwendung

Die `stockdata.yml` Datei deklariert zwei Objekte: eine Bereitstellung und einen Dienst.

#### <a name="the-stockdata-deployment"></a>Die StockData-Bereitstellung

Der Bereitstellungs Teil der YAML-Datei stellt den `spec` für die Bereitstellung selbst bereit, einschließlich der Anzahl der erforderlichen Replikate und einer `template` für die von der Bereitstellung zu erstellenden und zu verwaltenden Pod-Objekte. Beachten Sie, dass Bereitstellungs Objekte von der-API verwaltet werden `apps` , die in `apiVersion` anstelle der Kubernetes-Haupt-API angegeben ist.

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
  replicas: 1
  template:
    metadata:
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

Die- `spec.selector` Eigenschaft wird verwendet, um die Ausführung von Pods mit der Bereitstellung abzugleichen. Die-Eigenschaft des Pods `metadata.labels` muss mit der-Eigenschaft verglichen werden, `matchLabels` oder der API-Befehl schlägt fehl.

Der- `template.spec` Abschnitt deklariert den Container, der ausgeführt werden soll. Wenn Sie einen lokalen Kubernetes-Cluster wie den von Docker Desktop bereitstellen, können Sie Images angeben, die lokal erstellt wurden, sofern Sie über ein Versionstag verfügen.

> [!IMPORTANT]
> Standardmäßig sucht Kubernetes immer nach und versucht, ein neues Bild abzurufen. Wenn das Image in keinem der bekannten Depots gefunden werden kann, tritt bei der Pod-Erstellung ein Fehler auf. Legen Sie zum Arbeiten mit lokalen Images den `imagePullPolicy` auf fest `Never` .

Die- `ports` Eigenschaft gibt an, welche containerports auf dem Pod veröffentlicht werden sollen. Das `stockservice` Image führt den Dienst auf dem HTTP-Standardport aus, sodass Port 80 veröffentlicht wird.

Der- `resources` Abschnitt wendet Ressourcen Limits auf den Container an, der im Pod ausgeführt wird. Dies ist eine bewährte Vorgehensweise, da Sie verhindert, dass ein einzelner Pod die gesamte verfügbare CPU oder den Arbeitsspeicher auf einem Knoten verbraucht.

> [!NOTE]
> ASP.net Core 5,0 wurde optimiert und optimiert, um in ressourcenbeschränkten Containern ausgeführt zu werden. Das `dotnet/core/aspnet` docker-Image legt eine Umgebungsvariable fest, um der `dotnet` Laufzeit mitzuteilen, dass Sie sich in einem Container befindet.

#### <a name="the-stockdata-service"></a>Der StockData-Dienst

Der Dienst Teil der YAML-Datei deklariert den Dienst, der Zugriff auf die Pods im Cluster bereitstellt.

```yaml
apiVersion: v1
kind: Service
metadata:
  name: stockdata
  namespace: stocks
spec:
  ports:
  - port: 80
  selector:
    run: stockdata
```

Der Dienst `spec` verwendet die- `selector` Eigenschaft, um die Ausführung abzugleichen `Pods` . in diesem Fall wird nach Pods gesucht, die über eine Bezeichnung verfügen `run: stockdata` . Der angegebene `port` auf übereinstimmenden Pods wird vom benannten Dienst veröffentlicht. Andere Pods, die im- `stocks` Namespace ausgeführt werden, können über diesen Dienst auf http zugreifen, indem Sie `http://stockdata` als Adresse verwenden. Pods, die in anderen Namespaces ausgeführt werden, können den `http://stockdata.stocks` Hostnamen verwenden. Sie können den Namespace-Dienst Zugriff mithilfe von [Netzwerk Richtlinien](https://kubernetes.io/docs/concepts/services-networking/network-policies/)steuern.

#### <a name="deploy-the-stockdata-application"></a>Bereitstellen der StockData-Anwendung

Verwenden `kubectl` Sie, um die `stockdata.yml` Datei anzuwenden und zu bestätigen, dass die Bereitstellung und der Dienst erstellt wurden:

```console
> kubectl apply -f .\stockdata.yml
deployment.apps/stockdata created
service/stockdata created

> kubectl get deployment stockdata --namespace stocks
NAME        READY   UP-TO-DATE   AVAILABLE   AGE
stockdata   1/1     1            1           17s

> kubectl get service stockdata --namespace stocks
NAME        TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
stockdata   ClusterIP   10.97.132.103   <none>        80/TCP    33s
```

### <a name="the-stockweb-application"></a>Die stockweb-Anwendung

Die `stockweb.yml` Datei deklariert die Bereitstellung und den Dienst für die MVC-Anwendung.

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockweb
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockweb
  replicas: 1
  template:
    metadata:
      labels:
        run: stockweb
    spec:
      containers:
      - name: stockweb
        image: stockweb:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
        env:
        - name: StockData__Address
          value: "http://stockdata"
        - name: DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT
          value: "true"

---

apiVersion: v1
kind: Service
metadata:
  name: stockweb
  namespace: stocks
spec:
  type: NodePort
  ports:
  - port: 80
  selector:
    run: stockweb
```

#### <a name="environment-variables"></a>Umgebungsvariablen

Der- `env` Abschnitt des Bereitstellungs Objekts gibt die Umgebungsvariablen an, die in dem Container festgelegt werden sollen, der die Images ausgeführt wird `stockweb:1.0.0` .

Die **`StockData__Address`** Umgebungsvariable wird der `StockData:Address` Konfigurationseinstellung Dank des Umgebungsvariablen-Konfigurations Anbieters zugeordnet. Diese Einstellung verwendet doppelte Unterstriche zwischen Namen zum Trennen von Abschnitten. Die Adresse verwendet den Dienstnamen des `stockdata` Dienstanbieter, der im gleichen Kubernetes-Namespace ausgeführt wird.

Die **`DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT`** Umgebungsvariable legt einen <xref:System.AppContext> Switch fest, der unverschlüsselte http/2-Verbindungen für ermöglicht <xref:System.Net.Http.HttpClient> . Diese Umgebungsvariable bewirkt dasselbe wie das Festlegen des Schalters im Code, wie hier gezeigt:

```csharp
AppContext.SetSwitch("System.Net.Http.SocketsHttpHandler.Http2UnencryptedSupport", true);
```

Wenn Sie eine Umgebungsvariable für den-Schalter verwenden, können Sie den Kontext leicht ändern, je nachdem, in welchem Kontext die Anwendung ausgeführt wird.

#### <a name="service-types"></a>Diensttypen

Die- `type: NodePort` Eigenschaft wird verwendet, um die Webanwendung von außerhalb des Clusters zugänglich zu machen. Dieser Eigenschaftentyp bewirkt, dass Kubernetes Port 80 für den Dienst an einem beliebigen Port auf den externen Netzwerksockets des Clusters veröffentlicht. Sie finden den zugewiesenen Port mit dem `kubectl get service` Befehl.

Der `stockdata` Dienst sollte nicht von außerhalb des Clusters zugänglich sein, daher wird der Standardtyp verwendet `ClusterIP` .

Produktionssysteme verwenden wahrscheinlich einen integrierten Load Balancer, um öffentliche Anwendungen für externe Consumer verfügbar zu machen. Dienste, die auf diese Weise verfügbar gemacht werden, sollten den `LoadBalancer` Typ verwenden.

Weitere Informationen zu Dienst Typen finden Sie in der Dokumentation zu [Kubernetes Publishing Services](https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services-service-types) .

#### <a name="deploy-the-stockweb-application"></a>Bereitstellen der stockweb-Anwendung

Verwenden `kubectl` Sie, um die `stockweb.yml` Datei anzuwenden und zu bestätigen, dass die Bereitstellung und der Dienst erstellt wurden:

```console
> kubectl apply -f .\stockweb.yml
deployment.apps/stockweb created
service/stockweb created

> kubectl get deployment stockweb --namespace stocks
NAME       READY   UP-TO-DATE   AVAILABLE   AGE
stockweb   1/1     1            1           8s

> kubectl get service stockweb --namespace stocks
NAME       TYPE       CLUSTER-IP     EXTERNAL-IP   PORT(S)        AGE
stockweb   NodePort   10.106.141.5   <none>        80:32564/TCP   13s
```

Die Ausgabe des `get service` Befehls zeigt, dass der HTTP-Port im externen Netzwerk an Port veröffentlicht wurde `32564` . Für docker Desktop lautet diese IP-Adresse "localhost". Sie können auf die Anwendung zugreifen, indem Sie zu navigieren `http://localhost:32564` .

### <a name="test-the-application"></a>Testen der App

Die stockweb-Anwendung zeigt eine Liste der von einem einfachen Anforderung-Antwort-Dienst abgerufenen NASDAQ-Bestände an. Für diese Demonstration zeigt jede Zeile auch die eindeutige ID der Dienst Instanz an, die Sie zurückgegeben hat.

![Stockweb-Bildschirmfoto](media/kubernetes/stockweb-screenshot.png)

Wenn die Anzahl der Replikate des `stockdata` Dienstanbieter zunimmt, können Sie davon ausgehen, dass der Wert des **Servers** von Zeile zu Zeile geändert wird, aber tatsächlich werden alle 100-Datensätze immer von derselben Instanz zurückgegeben. Wenn Sie die Seite alle paar Sekunden aktualisieren, bleibt die Server-ID unverändert. Was ist dafür die Ursache? Hier gibt es zwei Faktoren.

Zuerst verwendet das Kubernetes-Dienst Ermittlungssystem standardmäßig Roundrobin-Lastenausgleich. Beim ersten Abfragen des DNS-Servers wird die erste übereinstimmende IP-Adresse für den Dienst zurückgegeben. Beim nächsten Mal wird die nächste IP-Adresse in der Liste usw. bis zum Ende zurückgegeben. An diesem Punkt werden Sie zurück zum Start.

Zweitens wird die `HttpClient` für den GrpC-Client der stockweb-Anwendung verwendet, die vom [ASP.net Core httpclientfactory](../microservices/implement-resilient-applications/use-httpclientfactory-to-implement-resilient-http-requests.md)erstellt und verwaltet wird, und eine einzelne Instanz dieses Clients wird für jeden Aufrufe der Seite verwendet. Der Client führt nur eine DNS-Suche durch, sodass alle Anforderungen an dieselbe IP-Adresse weitergeleitet werden. Da der `HttpClientHandler` aus Leistungsgründen zwischengespeichert wird, verwenden mehrere Anforderungen in schneller Folge *alle* die gleiche IP-Adresse, bis der zwischengespeicherte DNS-Eintrag abläuft oder die Handlerinstanz aus irgendeinem Grund verworfen wird.

Das Ergebnis ist, dass Anforderungen an einen GrpC-Dienst standardmäßig nicht über alle Instanzen dieses Dienstanbieter im Cluster hinweg ausgeglichen werden. Verschiedene Consumer verwenden verschiedene Instanzen, aber dies garantiert keine gute Verteilung von Anforderungen oder eine ausgeglichene Nutzung von Ressourcen.

Im nächsten Kapitel, [Service Netzen](service-mesh.md), wird dieses Problem behandelt.

>[!div class="step-by-step"]
>[Zurück](docker.md)
>[Weiter](service-mesh.md)
