---
title: Dienstvorgänge (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: 583a690a-e60f-4990-8991-d6efce069d76
ms.openlocfilehash: c254a7362c7bc28f4b38fc0189ae0ea763bc90cc
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74568849"
---
# <a name="service-operations-wcf-data-services"></a>Dienstvorgänge (WCF Data Services)

WCF Data Services ermöglicht es Ihnen, Dienst Vorgänge für einen Datendienst zu definieren, um Methoden auf dem Server verfügbar zu machen. Wie andere Datendienstressourcen werden Dienstvorgänge durch URIs adressiert. Dienstvorgänge ermöglichen es Ihnen, die Geschäftslogik in einem Datendienst verfügbar zu machen, z. B. um Validierungslogik zu implementieren, rollenbasierte Sicherheit anzuwenden oder spezielle Abfragefunktionen verfügbar zu machen. Dienstvorgänge sind der von <xref:System.Data.Services.DataService%601> abgeleiteten Datendienstklasse hinzugefügte Methoden. Wie allen anderen Datendienstressourcen können der Dienstvorgangsmethode Parameter übergeben werden. Beispielsweise übergibt der folgende Dienst Vorgangs-URI (basierend auf dem [Schnellstart](quickstart-wcf-data-services.md) -Datendienst) den Wert `London` an den `city`-Parameter:

```http
http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'
```

Die Definition für diesen Dienstvorgang lautet wie folgt:

[!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
[!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

Sie können mit der <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> des <xref:System.Data.Services.DataService%601> direkt auf die Datenquelle zugreifen, die der Datendienst verwendet. Weitere Informationen finden Sie unter Gewusst [wie: Definieren eines Dienst Vorgangs](how-to-define-a-service-operation-wcf-data-services.md).

Informationen zum Aufrufen eines Dienst Vorgangs aus einer .NET Framework Client Anwendung finden Sie unter Aufrufen von [Dienst Vorgängen](calling-service-operations-wcf-data-services.md).

## <a name="service-operation-requirements"></a>Anforderungen für Dienstvorgänge

Beim Definieren von Dienstvorgängen für den Datendienst gelten folgende Anforderungen. Wenn eine Methode diese Anforderungen nicht erfüllt, wird sie nicht als Dienstvorgang für den Datendienst verfügbar gemacht.

- Der Vorgang muss eine öffentliche Instanzmethode sein, die ein Member der Datendienstklasse ist.

- Die Vorgangsmethode akzeptiert möglicherweise nur Eingabeparameter. Auf im Nachrichtentext gesendete Daten kann der Datendienst nicht zugreifen.

- Wenn Parameter definiert wurden, muss der Typ eines jeden Parameters primitiv sein. Alle Daten eines nicht primitiven Typs müssen serialisiert werden und an einen Zeichenfolgenparameter übergeben werden.

- Die Methode muss einen der folgenden Werte zurückgeben:

  - `void` (`Nothing` in Visual Basic)

  - <xref:System.Collections.Generic.IEnumerable%601>

  - <xref:System.Linq.IQueryable%601>

  - Ein Entitätstyp im Datenmodell, das der Datendienst verfügbar macht.

  - Eine primitive Klasse wie eine ganze Zahl oder Zeichenfolge.

- Um Abfrageoptionen wie Sortieren, Paging und Filtern zu unterstützen, sollten die Methoden der Dienstvorgänge <xref:System.Linq.IQueryable%601> zurückgeben. Anforderungen an Dienstvorgänge, die Abfrageoptionen einschließen, werden für Vorgänge abgelehnt, die nur <xref:System.Collections.Generic.IEnumerable%601> zurückgeben.

- Um den Zugriff auf verknüpfte Entitäten mit Navigationseigenschaften zu unterstützen, muss der Dienstvorgang <xref:System.Linq.IQueryable%601> zurückgeben.

- Die Methode muss mit dem Attribut `[WebGet]` oder `[WebInvoke]` versehen sein.

  - `[WebGet]` aktiviert die aufgerufene Methode mit einer GET-Anforderung.

  - `[WebInvoke(Method = "POST")]` aktiviert die aufgerufene Methode mit einer POST-Anforderung. Andere <xref:System.ServiceModel.Web.WebInvokeAttribute>-Methoden werden nicht unterstützt.

- Ein Dienstvorgang kann mit <xref:System.Data.Services.SingleResultAttribute> versehen sein, das festlegt, dass der Rückgabewert der Methode eine einzelne Entität und keine Auflistung von Entitäten ist. Dieser Unterschied schreibt die resultierende Serialisierung der Antwort und die Weise vor, in der zusätzliche Navigationseigenschaftendurchläufe im URI dargestellt werden. Wenn zum Beispiel die AtomPub-Serialisierung verwendet wird, ist ein einzelner Ressourcentyp als Eingangselement dargestellt, und eine Gruppe von Instanzen als Feed-Element.

## <a name="addressing-service-operations"></a>Adressierung von Dienstvorgängen

Sie können Dienstvorgänge adressieren, indem Sie den Namen der Methode im ersten Pfadsegment eines URI platzieren. Als Beispiel greift der folgende URI auf einen `GetOrdersByState`-Vorgang zu, der eine <xref:System.Linq.IQueryable%601>-Auflistung von `Orders`-Objekten zurückgibt.

```http
http://localhost:12345/Northwind.svc/GetOrdersByState?state='CA'&includeItems=true
```

Wenn Sie einen Dienstvorgang aufrufen, werden Parameter als Abfrageoptionen angegeben. Der vorherige Dienstvorgang akzeptiert sowohl einen Zeichenfolgenparameter `state` als auch einen booleschen Parameter `includeItems`, der angibt, ob zugehörige `Order_Detail`-Objekte in die Antwort einbezogen werden.

Nachfolgend sind gültige Rückgabetypen für einen Dienstvorgang aufgeführt:

|Gültige Rückgabetypen|URI-Regeln|
|------------------------|---------------|
|`void` (`Nothing` in Visual Basic)<br /><br /> \- oder -<br /><br /> Entitätstypen<br /><br /> \- oder -<br /><br /> Primitive Typen|Der URI muss ein einzelnes Pfadsegment sein, das den Namen des Dienstvorgangs trägt. Abfrageoptionen sind nicht zulässig.|
|<xref:System.Collections.Generic.IEnumerable%601>|Der URI muss ein einzelnes Pfadsegment sein, das den Namen des Dienstvorgangs trägt. Da der Ergebnistyp kein <xref:System.Linq.IQueryable%601>-Typ ist, sind keine Abfrageoptionen zulässig.|
|<xref:System.Linq.IQueryable%601>|Abfragepfadsegmente zusätzlich zum Pfad, der der Name des Dienstvorgangs ist, sind zulässig. Abfrageoptionen sind ebenfalls zulässig.|

In Abhängigkeit vom Rückgabetyp des Dienstvorgangs können dem URI zusätzliche Pfadsegmente oder Abfrageoptionen hinzugefügt werden. Beispielsweise greift der folgende URI auf einen `GetOrdersByCity`-Vorgang zu, der eine <xref:System.Linq.IQueryable%601>-Auflistung von `Orders`-Objekten, sortiert nach `RequiredDate` in absteigender Reihenfolge, zusammen mit den verknüpften `Order_Details`-Objekten zurückgibt:

```http
http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc
```

## <a name="service-operations-access-control"></a>Zugriffssteuerung für Dienstvorgänge

Dienstweite Sichtbarkeit der Dienstvorgänge wird durch die <xref:System.Data.Services.IDataServiceConfiguration.SetServiceOperationAccessRule%2A>-Methode in der <xref:System.Data.Services.IDataServiceConfiguration>-Klasse gesteuert, und zwar auf ähnliche Weise, wie die Sichtbarkeit von Entitätenmengen durch die <xref:System.Data.Services.IDataServiceConfiguration.SetEntitySetAccessRule%2A>-Methode gesteuert wird. Die folgende Codezeile in der Datendienstdefinition ermöglicht z. B. den Zugriff auf den `CustomersByCity`-Dienstvorgang.

[!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
[!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

> [!NOTE]
> Wenn ein Dienstvorgang einen Rückgabetyp aufweist, der durch das Beschränken des Zugriff auf die zugrunde liegenden Entitätenmengen ausgeblendet wurde, dann steht der Dienstvorgang Clientanwendungen nicht zur Verfügung.

Weitere Informationen finden Sie unter Gewusst [wie: Definieren eines Dienst Vorgangs](how-to-define-a-service-operation-wcf-data-services.md).

## <a name="raising-exceptions"></a>Auslösen von Ausnahmen

Es empfiehlt sich, dass Sie die <xref:System.Data.Services.DataServiceException>-Klasse immer dann verwenden, wenn Sie eine Ausnahme in der Datendienstausführung auslösen. Das liegt daran, dass die Datendienstlaufzeit weiß, wie der HTTP-Antwortnachricht Eigenschaften dieses Ausnahmeobjekts ordnungsgemäß zugeordnet werden. Wenn Sie in einem Dienstvorgang eine <xref:System.Data.Services.DataServiceException> auslösen, wird die zurückgegebene Ausnahme in eine <xref:System.Reflection.TargetInvocationException> eingeschlossen. Um die Basis-<xref:System.Data.Services.DataServiceException> ohne die einschließende <xref:System.Reflection.TargetInvocationException> zurückzugeben, müssen Sie die <xref:System.Data.Services.DataService%601.HandleException%2A>-Methode im <xref:System.Data.Services.DataService%601> überschreiben und die <xref:System.Data.Services.DataServiceException> aus der <xref:System.Reflection.TargetInvocationException> extrahieren und als Fehler der obersten Ebene zurückgeben, wie im folgenden Beispiel gezeigt:

[!code-csharp[Astoria Northwind Service#HandleExceptions](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#handleexceptions)]
[!code-vb[Astoria Northwind Service#HandleExceptions](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#handleexceptions)]

## <a name="see-also"></a>Siehe auch

- [Interceptors](interceptors-wcf-data-services.md)
