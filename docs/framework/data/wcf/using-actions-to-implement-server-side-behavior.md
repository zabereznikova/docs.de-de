---
title: "Verwenden von Aktionen zum Implementieren des serverseitigen Verhaltens | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11a372db-7168-498b-80d2-9419ff557ba5
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Verwenden von Aktionen zum Implementieren des serverseitigen Verhaltens
OData\-Aktionen bieten eine Möglichkeit, ein Verhalten für eine aus einem OData\-Dienst abgerufene Ressource zu implementieren.  Nehmen wir als Beispiel für eine Ressource einen digitalen Film, den Sie auf viele verschiedene Weisen verwenden können: Auschecken, Bewerten\/Kommentieren oder Einchecken.  Das alles sind Beispiele für Aktionen, die von einem WCF Data Service implementiert werden können, der digitale Filme verwaltet.  Aktionen werden in einer OData\-Antwort beschrieben, die eine Ressource enthält, für die die Aktion aufgerufen werden kann.  Wenn ein Benutzer eine Ressource anfordert, die einen digitalen Film darstellt, enthält die vom WCF Data Service zurückgegebene Antwort Informationen zu den Aktionen, die für diese Ressource verfügbar sind.  Die Verfügbarkeit einer Aktion kann vom Zustand des Datendienstes oder der Ressource abhängen.  Nachdem ein digitaler Film beispielsweise ausgecheckt wurde, kann er nicht von einem weiteren Benutzer ausgecheckt werden.  Clients können eine Aktion aufrufen, indem sie einfach eine URL angeben.  Mit der URL "http:\/\/MyServer\/MovieService.svc\/Movies\(6\)" wird beispielsweise ein bestimmter digitaler Film identifiziert, und mit "http:\/\/MyServer\/MovieService.svc\/Movies\(6\)\/Checkout" wird die Aktion für den jeweiligen Film aufgerufen.  Mithilfe von Aktionen ist es möglich, das Dienstmodell ohne das Datenmodell verfügbar zu machen.  Wir bleiben beim Beispiel mit dem Filmportal: Stellen Sie sich vor, dass Sie einem Benutzer die Bewertung eines Films ermöglichen möchten, ohne die Bewertungsdaten jedoch direkt als Ressource verfügbar zu machen.  Sie könnten eine Bewertungsaktion implementieren, um dem Benutzer die Bewertung eines Films zu erlauben, ohne dass auf die Bewertungsdaten direkt als Ressource zugegriffen wird.  
  
 Ein vollständiges Beispiel zum Implementieren einer WCF Data Service\-Aktion finden Sie unter [WCF Data Services\-Aktionsanbieter für Entity Framework](http://efactionprovider.codeplex.com/).  
  
## Implementieren einer Aktion  
 Zum Implementieren einer Dienstaktion müssen Sie die Schnittstellen <xref:System.IServiceProvider>, <xref:System.Data.Services.Providers.IDataServiceActionProvider> und <xref:System.Data.Services.Providers.IDataServiceInvokable> implementieren.  Mithilfe von <xref:System.IServiceProvider> sind WCF Data Services in der Lage, die Implementierung von <xref:System.Data.Services.Providers.IDataServiceActionProvider> abzurufen.  <xref:System.Data.Services.Providers.IDataServiceActionProvider> ermöglicht es WCF Data Services, Dienstaktionen zu erstellen, zu suchen, zu beschreiben und aufzurufen.  Mit <xref:System.Data.Services.Providers.IDataServiceInvokable> können Sie den Code aufrufen, der das Verhalten der Dienstaktionen implementiert, und ggf. die Ergebnisse abrufen.  Bedenken Sie, dass die WCF Data Services pro Aufruf berechnet werden. Bei jedem Aufruf des Dienstes wird eine neue Dienstinstanz erstellt.  Stellen Sie sicher, dass mit dem Dienst keine unnötigen Arbeiten ausgeführt werden.  
  
### IServiceProvider  
 <xref:System.IServiceProvider> enthält eine Methode mit dem Namen <xref:System.IServiceProvider.GetService%2A>.  Diese Methode wird von den WCF Data Services aufgerufen, um eine Reihe von Dienstanbietern abzurufen, einschließlich Anbietern von Metadatendiensten und Anbietern von Datendienstaktionen.  Wenn Sie nach dem Anbieter einer Datendienstaktion gefragt werden, geben Sie Ihre <xref:System.Data.Services.Providers.IDataServiceActionProvider>\-Implementierung zurück.  
  
### IDataServiceActionProvider  
 <xref:System.Data.Services.Providers.IDataServiceActionProvider> enthält Methoden, mit deren Hilfe Sie Informationen zu den verfügbaren Aktionen abrufen können.  Durch die Implementierung von <xref:System.Data.Services.Providers.IDataServiceActionProvider> erweitern Sie die Metadaten für den Dienst, der durch die <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>\-Implementierung des Diensts definiert ist, mittels Aktionen, und behandeln die Verteilung an diese Aktionen in der erforderlichen Weise.  
  
#### AdvertiseServiceAction  
 <xref:System.Data.Services.Providers.IDataServiceActionProvider.AdvertiseServiceAction%2A> wird aufgerufen, um zu ermitteln, welche Aktionen für die angegebene Ressource verfügbar sind.  Diese Methode wird nur für Aktionen aufgerufen, die nicht immer verfügbar sind.  Anhand der Methode wird überprüft, ob die Aktion in der OData\-Antwort enthalten sein soll. Dies hängt jeweils vom Zustand der angeforderten Ressource bzw. dem Zustand des Dienstes ab.  Wie Sie dies überprüfen, liegt völlig in Ihrer Hand.  Wenn die Berechnung der Verfügbarkeit zu kostspielig ist und sich die aktuelle Ressource in einem Feed befindet, kann die Überprüfung auch übersprungen und die Aktion angekündigt werden.  Der `inFeed`\-Parameter ist auf `true` festgelegt, wenn die aktuelle, zurückgegebene Ressource Teil eines Feeds ist.  
  
#### CreateInvokable  
 [M:System.Data.Services.Providers.IDataServiceActionProvider.CreateInvokable\(System.Data.Services.DataServiceOperationContext,System.Data.Services.Providers.ServiceAction,System.Object\<xref:System.Data.Services.Providers.IDataServiceActionProvider.CreateInvokable%2A> wird zum Erstellen von <xref:System.Data.Services.Providers.IDataServiceInvokable> aufgerufen. In dieser Klasse ist ein Delegat enthalten, der den Code kapselt, durch den das Verhalten der Aktion implementiert wird.  Dadurch wird die <xref:System.Data.Services.Providers.IDataServiceInvokable>\-Instanz erstellt, die Aktion jedoch nicht aufgerufen.  Die Aktionen von WCF Data Services weisen Nebeneffekte auf und sind auf den Updateanbieter angewiesen, um diese Änderungen auf dem Datenträger zu speichern.  Die <xref:System.Data.Services.Providers.IDataServiceInvokable.Invoke%2A>\-Methode wird beim Aufruf der SaveChanges\(\)\-Methode des Updateanbieters aufgerufen.  
  
#### GetServiceActions  
 Diese Methode gibt eine Auflistung von <xref:System.Data.Services.Providers.ServiceAction>\-Instanzen zurück. Diese stellen alle Aktionen dar, die von einem WCF Data Service verfügbar gemacht werden.  <xref:System.Data.Services.Providers.ServiceAction> ist die Metadatendarstellung einer Aktion, die Informationen wie den Aktionsnamen, die zugehörigen Parameter und den Rückgabetyp umfasst.  
  
#### GetServiceActionsByBindingParameterType  
 Diese Methode gibt eine Auflistung aller <xref:System.Data.Services.Providers.ServiceAction>\-Instanzen zurück, die an den angegebenen Bindungsparametertyp gebunden werden können.  Anders ausgedrückt, handelt es sich dabei um alle <xref:System.Data.Services.Providers.ServiceAction>, die auf den angegebenen Ressourcentyp \(auch als Bindungsparametertyp bezeichnet\) einwirken können. Diese Vorgehensweise wird verwendet, wenn der Dienst eine Ressource zurückgibt, um Informationen über Aktionen einzuschließen, die anhand dieser Ressource aufgerufen werden können.  Diese Methode sollte nur Aktionen zurückgeben, die an den exakten Bindungsparametertyp \(keine abgeleiteten Typen\) gebunden werden können.  Die Methode wird einmal pro Anforderung jedes gefundenen Typs aufgerufen, und das Ergebnis wird von WCF Data Services zwischengespeichert.  
  
#### TryResolveServiceAction  
 Diese Methode sucht eine angegebene <xref:System.Data.Services.Providers.ServiceAction> und gibt `true` zurück, wenn <xref:System.Data.Services.Providers.ServiceAction> gefunden wurde.  Falls gefunden, wird <xref:System.Data.Services.Providers.ServiceAction> im `serviceAction` `out`\-Parameter zurückgegeben.  
  
### IDataServiceInvokable  
 Diese Schnittstelle bietet eine Möglichkeit zur Ausführung einer WCF Data Service\-Aktion.  Beim Implementieren von IDataServiceInvokable sind drei Dinge zu beachten:  
  
1.  Erfassen und potenzielles Marshallen der Parameter  
  
2.  Verteilen der Parameter an den Code, durch den die Aktion beim Aufruf von Invoke\(\) tatsächlich implementiert wird  
  
3.  Speichern der Ergebnisse von Invoke\(\), sodass sie mit GetResult\(\) abgerufen werden können  
  
 Die Parameter können als Token übergeben werden.  Das liegt daran, dass ein Datendienstanbieter mit Unterstützung für Token geschrieben werden kann, die Ressourcen darstellen. In diesem Fall müssen die Token u. U. in tatsächliche Ressourcen konvertiert \(gemarshallt\) werden, bevor sie an die tatsächliche Aktion verteilt werden.  Nachdem der Parameter gemarshallt wurde, muss er sich in einem bearbeitbaren Zustand befinden, damit alle Änderungen an der Ressource, die beim Aufrufen der Aktion auftreten, gespeichert und auf den Datenträger geschrieben werden.  
  
 Diese Schnittstelle erfordert zwei Methoden: Invoke und GetResult.  Mit Invoke wird der Delegat aufgerufen, der das Verhalten der Aktion implementiert, und GetResult gibt das Ergebnis der Aktion zurück.  
  
## Aufrufen einer WCF Data Service\-Aktion  
 Aktionen werden mithilfe einer HTTP POST\-Anforderung aufgerufen.  In der URL wird die Ressource gefolgt vom Aktionsnamen angegeben.  Parameter werden im Textkörper der Anforderung übergeben.  Stellen Sie sich z. B. einen Dienst mit dem Namen MovieService vor, der die Bewertungsaktion \(Rate\) verfügbar macht.  Sie sollten die folgende URL verwenden, um die Bewertungsaktion \(Rate\) für einen bestimmten Film aufzurufen:  
  
 http:\/\/MovieServer\/MovieService.svc\/Movies\(1\)\/Rate  
  
 Movies\(1\) gibt den Film an, den Sie bewerten möchten, und Rate die Bewertungsaktion.  Der tatsächliche Wert der Bewertung befindet sich im Textkörper der HTTP\-Anforderung, wie im folgenden Beispiel dargestellt:  
  
```  
POST http://MovieServer/MoviesService.svc/Movies(1)/Rate HTTP/1.1   
Content-Type: application/json   
Content-Length: 20   
Host: localhost:15238  
{   
   "rating": 4   
}  
  
```  
  
> [!WARNING]
>  Der oben angegebene Beispielcode funktioniert nur mit WCF Data Services 5.2 und höher, da diese Versionen Unterstützung für JSON Light bieten.  Wenn Sie eine frühere Version von WCF Data Services verwenden, müssen Sie den Inhaltstyp für "json verbose" wie folgt angeben: `application/json;odata=verbose`.  
  
 Alternativ können Sie eine Aktion mit dem WCF Data Services\-Client aufrufen, wie im folgenden Codeausschnitt dargestellt.  
  
```  
MoviesModel context = new MoviesModel (new Uri("http://MyServer/MoviesService.svc/"));  
            //...  
            context.Execute(new Uri("http://MyServer/MoviesService.svc/Movies(1)/Rate"), "POST", new BodyOperationParameter("rating",4) );           
```  
  
 Im oben angegebenen Codeausschnitt wurde die `MoviesModel`\-Klasse von Visual Studio generiert, um einem WCF Data Service einen Dienstverweis hinzuzufügen.  
  
## Siehe auch  
 [WCF Data Services 4.5](../../../../docs/framework/data/wcf/index.md)   
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Entwickeln und Bereitstellen von WCF Data Services](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)   
 [Benutzerdefinierte Datendienstanbieter](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)