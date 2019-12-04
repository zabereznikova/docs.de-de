---
title: Verarbeiten von odata-Feeds aus einem Workflow (WF)
ms.date: 03/30/2017
ms.assetid: 1b26617c-53e9-476a-81af-675c36d95919
ms.openlocfilehash: c9780200d9b7c7bc89797b3c16b22bc38440fccc
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802660"
---
# <a name="consuming-odata-feeds-from-a-workflow"></a>Verarbeiten von odata-Feeds aus einem Workflow

WCF Data Services ist eine Komponente des .NET Framework, die es Ihnen ermöglicht, Dienste zu erstellen, die die Open Data Protocol (odata) verwenden, um Daten mithilfe der Semantik Representational State Transfer (Rest) über das Internet oder Intranet verfügbar zu machen und zu nutzen. OData macht Daten als Ressourcen verfügbar, die durch URIs adressierbar sind. Mit einem OData-basierten Datendienst kann jede Anwendung interagieren, die HTTP-Anforderungen senden und von einem Datendienst zurückgegebene OData-Feeds verarbeiten kann. Darüber hinaus enthält WCF Data Services Client Bibliotheken, die umfangreichere Programmierfunktionen bieten, wenn Sie odata-Feeds von .NET Framework Anwendungen verarbeiten. Dieses Thema bietet einen Überblick über die Verarbeitung von OData-Feeds in einem Workflow mit bzw. ohne Clientbibliotheken.

## <a name="using-the-sample-northwind-odata-service"></a>Verwenden des Beispiel-odata-Dienstanbieter Northwind

In den Beispielen in diesem Thema wird der Northwind-Beispiel Datendienst unter <https://services.odata.org/Northwind/Northwind.svc/>verwendet. Dieser Dienst wird als Teil des [OData-SDK](https://www.odata.org/wp-content/uploads/sites/21/odatasdkcodesamples.zip) bereitgestellt und bietet schreibgeschützten Zugriff auf die Beispieldatenbank Northwind. Wenn Schreibzugriff oder ein lokaler WCF-Datendienst gewünscht ist, können Sie die Schritte in [Schnellstart (WCF Data Services)](../data/wcf/quickstart-wcf-data-services.md) ausführen und einen lokalen OData-Dienst erstellen, der den Zugriff auf die Northwind-Datenbank ermöglicht. Ersetzen Sie bei Verwendung des Schnellstarts den lokalen URI durch den URI aus dem Beispielcode in diesem Thema.

## <a name="consuming-an-odata-feed-using-the-client-libraries"></a>Verarbeiten eines odata-Feeds mit Client Bibliotheken

WCF Data Services umfasst Client Bibliotheken, die es Ihnen ermöglichen, einen odata-Feed von .NET Framework und Client Anwendungen aus leichter zu nutzen. Diese Bibliotheken vereinfachen das Senden und Empfangen von HTTP-Nachrichten. Sie übersetzen außerdem die Nachrichtennutzlast in CLR-Objekte, die Entitätsdaten darstellen. Die Clientbibliotheken enthalten die beiden Kernklassen <xref:System.Data.Services.Client.DataServiceContext> und <xref:System.Data.Services.Client.DataServiceQuery%601>. Diese Klassen ermöglichen es Ihnen, einen Datendienst abzufragen und dann die zurückgegebenen Entitätsdaten als CLR-Objekte zu verarbeiten. In diesem Abschnitt werden zwei Ansätze zum Erstellen von Aktivitäten mit Clientbibliotheken vorgestellt.

### <a name="adding-a-service-reference-to-the-wcf-data-service"></a>Hinzufügen eines Dienst Verweises zum WCF-Datendienst

Zum Generieren der Northwind-Client Bibliotheken können Sie das Dialogfeld **Dienstverweis hinzufügen** in Visual Studio 2012 verwenden, um einen Verweis auf den Northwind-odata-Dienst hinzuzufügen.

![Screenshot, der das Dialogfeld "Dienstverweis hinzufügen" anzeigt.](./media/consuming-odata-feeds-from-a-workflow/add-service-reference-dialog.gif)

Beachten Sie Folgendes: Vom Dienst werden keine Dienstvorgänge verfügbar gemacht, und die Liste **Dienste** enthält Elemente, die die Entitäten darstellen, die vom Northwind-Datendienst verfügbar gemacht werden. Beim Hinzufügen des Dienstverweises werden Klassen für diese Entitäten generiert, die im Clientcode verwendet werden können. In den Beispielen in diesem Thema werden diese Klassen und die `NorthwindEntities` -Klasse für die Abfragen verwendet.

> [!NOTE]
> Weitere Informationen finden Sie unter [Erstellen der Datendienst-Client Bibliothek (WCF Data Services)](../data/wcf/generating-the-data-service-client-library-wcf-data-services.md).

### <a name="using-asynchronous-methods"></a>Verwenden von asynchronen Methoden

Es wird empfohlen, asynchron auf WCF Data Services zuzugreifen, um mögliche Latenzprobleme beim Zugriff auf Ressourcen über das Internet zu umgehen. Die WCF Data Services-Client Bibliotheken enthalten asynchrone Methoden zum Aufrufen von Abfragen, und Windows Workflow Foundation (WF) stellt die <xref:System.Activities.AsyncCodeActivity>-Klasse zum Erstellen von asynchronen Aktivitäten bereit. <xref:System.Activities.AsyncCodeActivity> abgeleitete Aktivitäten können so geschrieben werden, dass Sie .NET Framework Klassen, die asynchrone Methoden aufweisen, nutzen können, oder der Code, der asynchron ausgeführt werden soll, in eine Methode eingefügt und mithilfe eines Delegaten aufgerufen werden kann. Dieser Abschnitt enthält zwei Beispiele einer von <xref:System.Activities.AsyncCodeActivity> abgeleiteten Aktivität, von denen eine die asynchronen Methoden der Clientbibliotheken von WCF Data Services und die andere einen Delegaten verwendet.

> [!NOTE]
> Weitere Informationen finden Sie unter [asynchrone Vorgänge (WCF Data Services)](../data/wcf/asynchronous-operations-wcf-data-services.md) und [Erstellen von asynchronen Aktivitäten](creating-asynchronous-activities-in-wf.md).

### <a name="using-client-library-asynchronous-methods"></a>Verwenden von asynchronen Methoden für Client Bibliotheken

Die <xref:System.Data.Services.Client.DataServiceQuery%601> -Klasse stellt die <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> - und die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> -Methode zum asynchronen Abfragen eines OData-Diensts bereit. Diese Methoden können von der <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> - und der <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> -Überschreibung einer von <xref:System.Activities.AsyncCodeActivity> abgeleiteten Klasse aufgerufen werden. Wenn die Überschreibung für <xref:System.Activities.AsyncCodeActivity> <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> abgeschlossen wird, kann der Workflow in den Leerlauf übergehen (nicht jedoch beibehalten werden), und wenn die asynchrone Arbeit abgeschlossen ist, wird <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> von der Laufzeit aufgerufen.

Im folgenden Beispiel wird eine `OrdersByCustomer` -Aktivität definiert, die über zwei Eingabeargumente verfügt. Das `CustomerId` -Argument stellt den Kunden dar, der angibt, welche Aufträge zurückgegeben werden sollen, und das `ServiceUri` -Argument stellt den URI des OData-Diensts dar, der abgefragt werden soll. Da diese Aktivität von `AsyncCodeActivity<IEnumerable<Order>>` abgeleitet ist, ist auch ein <xref:System.Activities.Activity%601.Result%2A> -Ausgabeargument vorhanden, mit dem die Ergebnisse der Abfrage zurückgegeben werden. Mit der <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> -Überschreibung wird eine LINQ-Abfrage erstellt, die alle Aufträge des angegebenen Kunden auswählt. Diese Abfrage wird als <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> des übergebenen <xref:System.Activities.AsyncCodeActivityContext>angegeben. Anschließend wird die <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> -Methode der Abfrage aufgerufen. Beachten Sie, dass Rückruf und Zustand, die an <xref:System.Data.Services.Client.DataServiceQuery%601.BeginExecute%2A> der Abfrage übergeben werden, dem Rückruf bzw. Zustand entsprechen, die an die <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> -Methode der Aktivität übergeben werden. Nachdem die Ausführung der Abfrage abgeschlossen ist, wird die <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> -Methode der Aktivität aufgerufen. Die Abfrage wird vom <xref:System.Activities.AsyncCodeActivityContext.UserState%2A>abgerufen, und anschließend wird die <xref:System.Data.Services.Client.DataServiceQuery%601.EndExecute%2A> -Methode der Abfrage aufgerufen. Von dieser Methode wird ein <xref:System.Collections.Generic.IEnumerable%601> des angegebenen Entitätstyps zurückgegeben, hier: `Order`. Da `IEnumerable<Order>` der generische Typ der <xref:System.Activities.AsyncCodeActivity%601>ist, wird das <xref:System.Collections.IEnumerable> als <xref:System.Activities.Activity%601.Result%2A> <xref:System.Activities.OutArgument%601> der Aktivität festgelegt.

[!code-csharp[CFX_WCFDataServicesActivityExample#100](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#100)]

Im folgenden Beispiel wird von der `OrdersByCustomer` -Aktivität eine Liste mit Aufträgen für den angegebenen Kunden abgerufen, und von einer <xref:System.Activities.Statements.ForEach%601> -Aktivität werden die zurückgegebenen Bestellungen aufgelistet und die jeweiligen Daten in die Konsole geschrieben.

[!code-csharp[CFX_WCFDataServicesActivityExample#10](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#10)]

Beim Aufrufen des Workflows werden die folgenden Daten in die Konsole geschrieben:

```console
Calling WCF Data Service...
8/25/1997
10/3/1997
10/13/1997
1/15/1998
3/16/1998
4/9/1998
```

> [!NOTE]
> Wenn keine Verbindung zum OData-Server hergestellt werden kann, wird eine Ausnahme ähnlich der folgenden angezeigt:
>
> Unbehandelte Ausnahme: System.InvalidOperationException: Fehler beim Verarbeiten dieser Anforderung. ---> System.Net.WebException: Die Verbindung mit dem Remoteserver kann nicht hergestellt werden. ---> System.Net.Sockets.SocketException: Ein Verbindungsversuch ist fehlgeschlagen, da die Gegenstelle nach einer bestimmten Zeitspanne nicht richtig reagiert hat, oder die hergestellte Verbindung war fehlerhaft, da der verbundene Host nicht reagiert hat.

Eine weitere Verarbeitung der von der Abfrage zurückgegebenen Daten kann ggf. in der <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A> -Überschreibung der Aktivität erfolgen. <xref:System.Activities.AsyncCodeActivity%601.BeginExecute%2A> und <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A> werden mit dem Workflowthread aufgerufen, und Code in den Überschreibungen wird nicht asynchron ausgeführt. Wenn die zusätzliche Verarbeitung umfangreich oder langwierig ist, oder wenn die Abfrageergebnisse seitenweise angezeigt werden, kann es empfehlenswert sein, den Ansatz im nächsten Abschnitt zu berücksichtigen. Dabei wird ein Delegat zur Ausführung der Abfrage sowie für weitere asynchrone Verarbeitungen verwendet.

### <a name="using-a-delegate"></a>Verwenden eines Delegaten

Zusätzlich zum Aufrufen der asynchronen Methode einer .NET Framework Klasse kann eine <xref:System.Activities.AsyncCodeActivity>basierte Aktivität auch die asynchrone Logik in einer ihrer Methoden definieren. Diese Methode wird mit einem Delegaten in der <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> -Überschreibung der Aktivität angegeben. Nach dem Abschluss der Methode wird die <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> -Überschreibung der Methode von der Laufzeit aufgerufen. Beim Aufrufen eines OData-Diensts aus einem Workflow kann diese Methode zum Abfragen des Diensts verwendet werden und weitere Verarbeitungsmöglichkeiten bieten.

Im folgenden Beispiel wird eine `ListCustomers` -Aktivität definiert. Mit dieser Aktivität wird der Beispieldatendienst Northwind abgefragt und eine `List<Customer>` mit allen Kunden in der Northwind-Datenbank zurückgegeben. Der asynchrone Vorgang wird von der `GetCustomers` -Methode ausgeführt. Mit dieser Methode wird der Dienst für alle Kunden abgefragt, und das Ergebnis wird in eine `List<Customer>`kopiert. Im Anschluss wird überprüft, ob die Ergebnisse seitenweise angegeben sind. Wenn dies der Fall ist, wird die nachfolgende Ergebnisseite vom Dienst abgefragt, die Ergebnisse werden der Liste hinzugefügt, und der Vorgang wird fortgesetzt, bis alle Daten abgerufen wurden.

> [!NOTE]
> Weitere Informationen zum Paging in WCF Data Services finden Sie unter Gewusst wie: Laden von Auslagerungs [Ergebnissen (WCF Data Services)](../data/wcf/how-to-load-paged-results-wcf-data-services.md).

Sobald alle Kunden hinzugefügt wurden, wird die Liste zurückgegeben. Die `GetCustomers` -Methode wird in der <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> -Überschreibung der Aktivität angegeben. Da die Methode über einen Rückgabewert verfügt, wird eine `Func<string, List<Customer>>` erstellt, um die Methode anzugeben.

> [!NOTE]
> Wenn die Methode, mit der der asynchrone Vorgang ausgeführt wird, nicht über einen Rückgabewert verfügt, wird eine <xref:System.Action> anstelle einer <xref:System.Func%601> verwendet. Beispiele zum Erstellen eines asynchronen Beispiels mit beiden Ansätzen finden Sie unter [Erstellen von asynchronen Aktivitäten](creating-asynchronous-activities-in-wf.md).

Diese <xref:System.Func%601> wird dem <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> zugewiesen, und anschließend wird `BeginInvoke` aufgerufen. Da die aufzurufende Methode nicht auf die Argumentumgebung der Aktivität zugreifen kann, wird der Wert des `ServiceUri` -Arguments als erster Parameter zusammen mit dem Rückruf und dem Zustand übergeben, die in <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>übergeben wurden. Beim Abschluss von `GetCustomers` wird <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>von der Laufzeit aufgerufen. Mit dem Code in <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> wird der Delegat vom <xref:System.Activities.AsyncCodeActivityContext.UserState%2A>abgerufen, `EndInvoke`wird aufgerufen, und das Ergebnis (die Liste der Kunden, die von der `GetCustomers` -Methode zurückgegeben wurde) wird zurückgegeben.

[!code-csharp[CFX_WCFDataServicesActivityExample#200](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#200)]

Im folgenden Beispiel wird von der `ListCustomers` -Aktivität eine Liste mit Kunden abgerufen. Die <xref:System.Activities.Statements.ForEach%601> -Aktivität durchläuft die Kunden und schreibt den Namen des Unternehmens und den Ansprechpartner für jeden Kunden in die Konsole.

[!code-csharp[CFX_WCFDataServicesActivityExample#20](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#20)]

Beim Aufrufen des Workflows werden die folgenden Daten in die Konsole geschrieben. Da von dieser Abfrage zahlreiche Kunden zurückgegeben werden, wird an dieser Stelle nur ein Teil der Ausgabe angezeigt.

```console
Calling WCF Data Service...
Alfreds Futterkiste, Contact: Maria Anders
Ana Trujillo Emparedados y helados, Contact: Ana Trujillo
Antonio Moreno Taquería, Contact: Antonio Moreno
Around the Horn, Contact: Thomas Hardy
Berglunds snabbköp, Contact: Christina Berglund
...
```

## <a name="consuming-an-odata-feed-without-using-the-client-libraries"></a>Verarbeiten eines odata-Feeds ohne Verwendung der Client Bibliotheken

OData macht Daten als Ressourcen verfügbar, die durch URIs adressierbar sind. Diese URIs werden bei der Verwendung von Clientbibliotheken für Sie erstellt, eine Verwendung von Clientbibliotheken ist jedoch nicht erforderlich. Der Zugriff auf OData-Dienste ist auch direkt und ohne Clientbibliotheken möglich. Wenn Sie keine Clientbibliotheken verwenden, werden der Speicherort des Diensts sowie die gewünschten Daten durch den URI angegeben, und die Ergebnisse werden in der Antwort auf die HTTP-Anforderung zurückgegeben. Die Rohdaten können anschließend nach Bedarf verarbeitet oder geändert werden. Eine Möglichkeit, die Ergebnisse einer OData-Abfrage abzurufen, besteht in der Verwendung der <xref:System.Net.WebClient> -Klasse. In diesem Beispiel wird der Name des Ansprechpartners für den Kunden abgerufen, der durch Schlüssel ALFKI dargestellt wird.

[!code-csharp[CFX_WCFDataServicesActivityExample#2](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#2)]

Wenn dieser Code ausgeführt wird, wird die folgende Ausgabe in der Konsole angezeigt:

```console
Raw data returned:
<?xml version="1.0" encoding="utf-8" standalone="yes"?>
<ContactName xmlns="http://schemas.microsoft.com/ado/2007/08/dataservices">Maria Anders</ContactName>
```

Der Code aus diesem Beispiel kann in einem Workflow in die <xref:System.Activities.CodeActivity.Execute%2A>-Überschreibung einer <xref:System.Activities.CodeActivity>-basierten benutzerdefinierten Aktivität eingebunden werden. Dieselbe Funktionalität kann jedoch auch mit der <xref:System.Activities.Expressions.InvokeMethod%601>-Aktivität bereitgestellt werden. Mit der <xref:System.Activities.Expressions.InvokeMethod%601> -Aktivität können Workflowautoren statische Methoden und Instanzmethoden von Klassen aufrufen. Außerdem verfügen sie damit über eine Möglichkeit, die angegebene Methode asynchron aufzurufen. Im folgenden Beispiel wird eine <xref:System.Activities.Expressions.InvokeMethod%601> -Aktivität konfiguriert, um die <xref:System.Net.WebClient.DownloadString%2A> -Methode der <xref:System.Net.WebClient> -Klasse aufzurufen und eine Liste mit Kunden zurückzugeben.

[!code-csharp[CFX_WCFDataServicesActivityExample#3](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#3)]

Mit<xref:System.Activities.Expressions.InvokeMethod%601> können Sie statische Methoden und Instanzenmethoden von Klassen aufrufen. Da <xref:System.Net.WebClient.DownloadString%2A> eine Instanzmethode der <xref:System.Net.WebClient> -Klasse ist, wird eine neue Instanz der <xref:System.Net.WebClient> -Klasse für <xref:System.Activities.Expressions.InvokeMethod%601.TargetObject%2A>angegeben. `DownloadString` wird als <xref:System.Activities.Expressions.InvokeMethod%601.MethodName%2A>angegeben, der URI, der die Abfrage enthält, wird in der <xref:System.Activities.Expressions.InvokeMethod%601.Parameters%2A> -Auflistung angegeben, und der Rückgabewert wird dem <xref:System.Activities.Activity%601.Result%2A> -Wert zugewiesen. Der <xref:System.Activities.Expressions.InvokeMethod%601.RunAsynchronously%2A> -Wert wird auf `true`festgelegt, d. h., die Methode wird hinsichtlich des Workflows asynchron aufgerufen. Im folgenden Beispiel wird ein Workflow erstellt, in dem der Beispieldatendienst Northwind mit der <xref:System.Activities.Expressions.InvokeMethod%601> -Aktivität abgefragt wird, um eine Liste der Aufträge für einen bestimmten Kunden zurückzugeben und die zurückgegebenen Daten in die Konsole zu schreiben.

[!code-csharp[CFX_WCFDataServicesActivityExample#1](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_WCFDataServicesActivityExample/cs/Program.cs#1)]

Wenn dieser Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt. Da von dieser Abfrage zahlreiche Aufträge zurückgegeben werden, wird an dieser Stelle nur ein Teil der Ausgabe angezeigt.

```console
Calling WCF Data Service...
Raw data returned:

<?xml version="1.0" encoding="utf-8" standalone="yes"?>*
<feed
xml:base="http://services.odata.org/Northwind/Northwind.svc/"
xmlns:d="http://schemas.microsoft.com/ado/2007/08/dataservices"
xmlns:m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"
xmlns="http://www.w3.org/2005/Atom">
<title type="text">Orders\</title>
<id>http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders\</id>
<updated>2010-05-19T19:37:07Z\</updated>
<link rel="self" title="Orders" href="Orders" />
<entry>
<id>http://services.odata.org/Northwind/Northwind.svc/Orders(10643)\</id>
<title type="text">\</title>
<updated>2010-05-19T19:37:07Z\</updated>
<author>
<name />
</author>
<link rel="edit" title="Order" href="Orders(10643)" />
<link rel="http://schemas.microsoft.com/ado/2007/08/dataservices/related/Customer" type="application/atom+xml;type=entry" title="Customer" href="Orders(10643)/Customer" />
...
```

Dieses Beispiel enthält eine Methode, die Workflowanwendungsautoren verwenden können, um die Rohdaten zu nutzen, die von einem OData-Dienst zurückgegeben werden. Weitere Informationen zum Zugreifen auf WCF Data Services mithilfe von URIs finden Sie unter [zugreifen auf Datendienst Ressourcen (WCF Data Services)](../data/wcf/accessing-data-service-resources-wcf-data-services.md) und [odata: URI-Konventionen](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/).
