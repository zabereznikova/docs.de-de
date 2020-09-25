---
title: Verwenden von Aktionen zum Implementieren des serverseitigen Verhaltens
ms.date: 03/30/2017
ms.assetid: 11a372db-7168-498b-80d2-9419ff557ba5
ms.openlocfilehash: 19139a7efd955448a1f97c492a7245c1bbfe6c3d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180594"
---
# <a name="using-actions-to-implement-server-side-behavior"></a>Verwenden von Aktionen zum Implementieren des serverseitigen Verhaltens

OData-Aktionen bieten eine Möglichkeit, ein Verhalten für eine aus einem OData-Dienst abgerufene Ressource zu implementieren. Nehmen wir als Beispiel für eine Ressource einen digitalen Film, den Sie auf viele verschiedene Weisen verwenden können: Auschecken, Bewerten/Kommentieren oder Einchecken. Das alles sind Beispiele für Aktionen, die von einem WCF Data Service implementiert werden können, der digitale Filme verwaltet. Aktionen werden in einer OData-Antwort beschrieben, die eine Ressource enthält, für die die Aktion aufgerufen werden kann. Wenn ein Benutzer eine Ressource anfordert, die einen digitalen Film darstellt, enthält die vom WCF Data Service zurückgegebene Antwort Informationen zu den Aktionen, die für diese Ressource verfügbar sind. Die Verfügbarkeit einer Aktion kann vom Zustand des Datendienstes oder der Ressource abhängen. Nachdem ein digitaler Film beispielsweise ausgecheckt wurde, kann er nicht von einem weiteren Benutzer ausgecheckt werden. Clients können eine Aktion aufrufen, indem sie einfach eine URL angeben. Beispielsweise wird `http://MyServer/MovieService.svc/Movies(6)` ein bestimmter digitaler Film identifiziert, `http://MyServer/MovieService.svc/Movies(6)/Checkout` der die Aktion für den jeweiligen Film aufruft. Mithilfe von Aktionen ist es möglich, das Dienstmodell ohne das Datenmodell verfügbar zu machen. Wir bleiben beim Beispiel mit dem Filmportal: Stellen Sie sich vor, dass Sie einem Benutzer die Bewertung eines Films ermöglichen möchten, ohne die Bewertungsdaten jedoch direkt als Ressource verfügbar zu machen. Sie könnten eine Bewertungsaktion implementieren, um dem Benutzer die Bewertung eines Films zu erlauben, ohne dass auf die Bewertungsdaten direkt als Ressource zugegriffen wird.

## <a name="implementing-an-action"></a>Implementieren einer Aktion

 Zum Implementieren einer Dienst Aktion müssen Sie die <xref:System.IServiceProvider> Schnittstellen, [idataserviceaction Provider](/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103))und [idataserviceinvokable](/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) implementieren. <xref:System.IServiceProvider> ermöglicht WCF Data Services, die Implementierung von [idataserviceaktionprovider](/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103))zu erhalten. [Idataserviceaktionprovider](/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) ermöglicht es WCF Data Services, Dienst Aktionen zu erstellen, zu suchen, zu beschreiben und aufzurufen. [Idataserviceinvokable](/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) ermöglicht es Ihnen, den Code aufzurufen, der das Verhalten der Dienst Aktionen implementiert, und ggf. die Ergebnisse zu erhalten. Bedenken Sie, dass die WCF Data Services pro Aufruf berechnet werden. Bei jedem Aufruf des Dienstes wird eine neue Dienstinstanz erstellt.  Stellen Sie sicher, dass mit dem Dienst keine unnötigen Arbeiten ausgeführt werden.

### <a name="iserviceprovider"></a>IServiceProvider

 <xref:System.IServiceProvider> enthält eine Methode mit dem Namen <xref:System.IServiceProvider.GetService%2A>. Diese Methode wird von den WCF Data Services aufgerufen, um eine Reihe von Dienstanbietern abzurufen, einschließlich Anbietern von Metadatendiensten und Anbietern von Datendienstaktionen. Wenn Sie nach einem Datendienst-Aktions Anbieter gefragt werden, geben Sie die [idataserviceaction Provider](/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) -Implementierung zurück.

### <a name="idataserviceactionprovider"></a>IDataServiceActionProvider

 [Idataserviceaktionprovider](/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) enthält Methoden, mit denen Sie Informationen zu den verfügbaren Aktionen abrufen können. Wenn Sie [idataserviceaktionprovider](/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) implementieren, erweitern Sie die Metadaten für den Dienst, der durch die Implementierung von [idataserviceaktionprovider Ihres Dienstanbieters](/previous-versions/dotnet/wcf-data-services/hh859915(v=vs.103)) definiert wird, durch Aktionen und die Verarbeitung der Verteilung an die entsprechenden Aktionen.

#### <a name="advertiseserviceaction"></a>AdvertiseServiceAction

 Die [Methode "werbeseserviceaction](/previous-versions/dotnet/wcf-data-services/hh859971(v=vs.103)) " wird aufgerufen, um zu bestimmen, welche Aktionen für die angegebene Ressource verfügbar sind. Diese Methode wird nur für Aktionen aufgerufen, die nicht immer verfügbar sind. Anhand der Methode wird überprüft, ob die Aktion in der OData-Antwort enthalten sein soll. Dies hängt jeweils vom Zustand der angeforderten Ressource bzw. dem Zustand des Dienstes ab. Wie Sie dies überprüfen, liegt völlig in Ihrer Hand. Wenn die Berechnung der Verfügbarkeit zu kostspielig ist und sich die aktuelle Ressource in einem Feed befindet, kann die Überprüfung auch übersprungen und die Aktion angekündigt werden. Der `inFeed`-Parameter ist auf `true` festgelegt, wenn die aktuelle, zurückgegebene Ressource Teil eines Feeds ist.

#### <a name="createinvokable"></a>CreateInvokable

 " [Kreateinvokable](/previous-versions/dotnet/wcf-data-services/hh859940(v=vs.103)) " wird aufgerufen, um ein [idataserviceinvokable](/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) -Element zu erstellen, das einen Delegaten enthält, der den Code kapselt, der das Verhalten der Aktion implementiert. Dadurch wird die [idataserviceinvokable](/previous-versions/dotnet/wcf-data-services/hh859893(v=vs.103)) -Instanz erstellt, aber die Aktion wird nicht aufgerufen. Die Aktionen von WCF Data Services weisen Nebeneffekte auf und sind auf den Updateanbieter angewiesen, um diese Änderungen auf dem Datenträger zu speichern. Die [idataserviceinvokable. aufrufen](/previous-versions/dotnet/wcf-data-services/hh859924(v=vs.103)) -Methode wird von der SaveChanges ()-Methode des Aktualisierungs Anbieters aufgerufen.

#### <a name="getserviceactions"></a>GetServiceActions

 Diese Methode gibt eine Auflistung von [serviceaction](/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) -Instanzen zurück, die alle Aktionen darstellen, die ein WCF Data Service verfügbar macht. [Serviceaction](/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) ist die Metadatendarstellung einer Aktion und umfasst Informationen wie den Aktions Namen, seine Parameter und den Rückgabetyp.

#### <a name="getserviceactionsbybindingparametertype"></a>GetServiceActionsByBindingParameterType

 Diese Methode gibt eine Auflistung aller [Service Action](/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) -Instanzen zurück, die an den angegebenen Bindungs Parametertyp gebunden werden können. Anders ausgedrückt: alle [serviceaction](/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103))s, die für den angegebenen Ressourcentyp (auch als Bindungs Parametertyp bezeichnet) fungieren können. Diese wird verwendet, wenn der Dienst eine Ressource zurückgibt, um Informationen zu Aktionen einzuschließen, die für diese Ressource aufgerufen werden können. Diese Methode sollte nur Aktionen zurückgeben, die an den exakten Bindungsparametertyp (keine abgeleiteten Typen) gebunden werden können. Die Methode wird einmal pro Anforderung jedes gefundenen Typs aufgerufen, und das Ergebnis wird von WCF Data Services zwischengespeichert.

#### <a name="tryresolveserviceaction"></a>TryResolveServiceAction

 Diese Methode sucht nach einer angegebenen [serviceaction](/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) und gibt zurück, `true` Wenn die [serviceaction](/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) gefunden wurde. Wenn Sie gefunden wird, wird die [serviceaction](/previous-versions/dotnet/wcf-data-services/hh544089(v=vs.103)) im-Parameter zurückgegeben `serviceAction` `out` .

### <a name="idataserviceinvokable"></a>IDataServiceInvokable

 Diese Schnittstelle bietet eine Möglichkeit zur Ausführung einer WCF Data Service-Aktion. Beim Implementieren von IDataServiceInvokable sind drei Dinge zu beachten:

1. Erfassen und potenzielles Marshallen der Parameter

2. Verteilen der Parameter an den Code, durch den die Aktion beim Aufruf von Invoke() tatsächlich implementiert wird

3. Speichern der Ergebnisse von Invoke(), sodass sie mit GetResult() abgerufen werden können

 Die Parameter können als Token übergeben werden. Das liegt daran, dass ein Datendienstanbieter mit Unterstützung für Token geschrieben werden kann, die Ressourcen darstellen. In diesem Fall müssen die Token u. U. in tatsächliche Ressourcen konvertiert (gemarshallt) werden, bevor sie an die tatsächliche Aktion verteilt werden. Nachdem der Parameter gemarshallt wurde, muss er sich in einem bearbeitbaren Zustand befinden, damit alle Änderungen an der Ressource, die beim Aufrufen der Aktion auftreten, gespeichert und auf den Datenträger geschrieben werden.

 Diese Schnittstelle erfordert zwei Methoden: Invoke und GetResult. Mit Invoke wird der Delegat aufgerufen, der das Verhalten der Aktion implementiert, und GetResult gibt das Ergebnis der Aktion zurück.

## <a name="invoking-a-wcf-data-service-action"></a>Aufrufen einer WCF Data Service-Aktion

 Aktionen werden mithilfe einer HTTP POST-Anforderung aufgerufen. In der URL wird die Ressource gefolgt vom Aktionsnamen angegeben. Parameter werden im Textkörper der Anforderung übergeben. Stellen Sie sich z. B. einen Dienst mit dem Namen MovieService vor, der die Bewertungsaktion (Rate) verfügbar macht. Sie sollten die folgende URL verwenden, um die Bewertungsaktion (Rate) für einen bestimmten Film aufzurufen:

 `http://MovieServer/MovieService.svc/Movies(1)/Rate`

 Movies(1) gibt den Film an, den Sie bewerten möchten, und Rate die Bewertungsaktion. Der tatsächliche Wert der Bewertung befindet sich im Textkörper der HTTP-Anforderung, wie im folgenden Beispiel dargestellt:

```http
POST http://MovieServer/MoviesService.svc/Movies(1)/Rate HTTP/1.1
Content-Type: application/json
Content-Length: 20
Host: localhost:15238
{
   "rating": 4
}
```

> [!WARNING]
> Der oben angegebene Beispielcode funktioniert nur mit WCF Data Services 5.2 und höher, da diese Versionen Unterstützung für JSON Light bieten. Wenn Sie eine frühere Version von WCF Data Services verwenden, müssen Sie den Inhaltstyp für "json verbose" wie folgt angeben: `application/json;odata=verbose`.

 Alternativ können Sie eine Aktion mit dem WCF Data Services-Client aufrufen, wie im folgenden Codeausschnitt dargestellt.

```csharp
MoviesModel context = new MoviesModel (new Uri("http://MyServer/MoviesService.svc/"));
//...
context.Execute(new Uri("http://MyServer/MoviesService.svc/Movies(1)/Rate"), "POST", new BodyOperationParameter("rating",4) );
```

 Im oben angegebenen Codeausschnitt wurde die `MoviesModel`-Klasse von Visual Studio generiert, um einem WCF Data Service einen Dienstverweis hinzuzufügen.

## <a name="see-also"></a>Weitere Informationen

- [WCF Data Services 4.5](index.md)
- [Definieren von WCF Data Services](defining-wcf-data-services.md)
- [Entwickeln und Bereitstellen von WCF Data Services](developing-and-deploying-wcf-data-services.md)
- [Benutzerdefinierte Datendienstanbieter](custom-data-service-providers-wcf-data-services.md)
