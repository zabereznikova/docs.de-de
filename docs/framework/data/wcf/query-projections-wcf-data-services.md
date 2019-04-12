---
title: Abfrageprojektionen (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: a09f4985-9f0d-48c8-b183-83d67a3dfe5f
ms.openlocfilehash: 2e4c40d6c71a254d5f40ea42788608e10c5872a7
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/12/2019
ms.locfileid: "59517173"
---
# <a name="query-projections-wcf-data-services"></a>Abfrageprojektionen (WCF Data Services)

Projektion stellt einen Mechanismus in der [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] reduzieren die Datenmenge im Feed zurückgegeben, die von einer Abfrage, indem Sie angeben, die nur bestimmte Eigenschaften einer Entität in der Antwort zurückgegeben werden. Weitere Informationen finden Sie unter [OData: Wählen Sie die System Query Option ($select)](https://go.microsoft.com/fwlink/?LinkId=186076).

In diesem Thema wird beschrieben, wie eine Abfrageprojektion definiert wird, welche Anforderungen Entitäts- und Nichtentitätstypen erfüllen müssen, wie projizierte Ergebnisse aktualisiert werden, wie projizierte Typen erstellt werden und was bei Projektionen zu berücksichtigen ist.

## <a name="defining-a-query-projection"></a>Definieren einer Abfrageprojektion

Sie können auf eine Abfrage eine Projektionsklausel hinzufügen, indem Sie entweder die `$select` -Abfrageoption in einem URI oder mithilfe der [wählen](~/docs/csharp/language-reference/keywords/select-clause.md) Klausel ([wählen](~/docs/visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in einer LINQ-Abfrage. Zurückgegebene Entitätsdaten können auf dem Client entweder in Entitätstypen oder in Nicht-Entitätstypen projiziert werden. In den Beispielen in diesem Thema wird gezeigt, wie die `select`-Klausel in einer LINQ-Abfrage verwendet wird.

> [!IMPORTANT]
> Im Datendienst können Datenverluste auftreten, wenn Sie Updates speichern, die an projizierten Typen vorgenommen wurden. Weitere Informationen finden Sie unter [Überlegungen zur Projektion](#considerations).

## <a name="requirements-for-entity-and-non-entity-types"></a>Anforderungen für Entitäts- und Nicht-Entitätstypen

Entitätstypen müssen eine oder mehrere IDENTITY-Eigenschaften besitzen, die den Entitätsschlüssel bilden. Entitätstypen werden unter Verwendung einer der folgenden Methoden auf Clients definiert:

- Durch Anwenden des <xref:System.Data.Services.Common.DataServiceKeyAttribute>-Attributs oder <xref:System.Data.Services.Common.DataServiceEntityAttribute>-Attributs auf den Typ.

- Wenn der Typ über eine Eigenschaft mit dem Namen `ID` verfügt.

- Wenn der Typ besitzt eine Eigenschaft namens *Typ*`ID`, wobei *Typ* ist der Name des Typs.

In der Standardeinstellung gilt, wenn Sie Projektabfrageergebnisse in einen auf dem Client definierten Typ projizieren, dann müssen die in der Projektion angeforderten Eigenschaften im Clienttyp vorhanden sein. Wenn Sie jedoch den Wert `true` für die <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A>-Eigenschaft des <xref:System.Data.Services.Client.DataServiceContext>-Kontexts angeben, müssen die in der Projektion angegebenen Eigenschaften nicht im Clienttyp vorhanden sein.

### <a name="making-updates-to-projected-results"></a>Vornehmen von Aktualisierungen an projizierten Ergebnissen

Wenn Sie Projektabfrageergebnisse auf dem Client in Entitätstypen projizieren, dann kann der <xref:System.Data.Services.Client.DataServiceContext>-Kontext aktualisierte Objekte verfolgen, die zum Datendienst zurückgeschickt werden sollen, wenn die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird. Aktualisierungen, die an Daten vorgenommen werden, die auf dem Client in Nicht-Entitätstypen projiziert wurden, können jedoch nicht an den Datendienst zurückgesendet werden. Der Grund hierfür ist, dass der Datendienst ohne Schlüssel zum Identifizieren der Entitätsinstanz nicht die richtige Entität in der Datenquelle aktualisieren kann. Nicht-Entitätstypen werden nicht an den <xref:System.Data.Services.Client.DataServiceContext> angefügt.

Wenn eine oder mehrere Eigenschaften eines Entitätstyps, der im Datendienst definiert wurde, nicht im Clienttyp vorhanden sind, in den die Entität projiziert wird, dann enthalten neu eingefügte Entitäten diese fehlenden Eigenschaften nicht. In diesem Fall werden der Updates, die an vorhandenen Entitäten vorgenommen werden **auch** diese fehlenden Eigenschaften nicht enthalten. Wenn ein Wert für eine solche Eigenschaft vorhanden ist, dann wird er während der Aktualisierung auf den Standardwert der Eigenschaft zurückgesetzt, der in der Datenquelle definiert ist.

### <a name="creating-projected-types"></a>Erstellen von projizierten Typen

Im folgenden Beispiel wird eine anonyme LINQ-Abfrage verwendet, die die adressenbezogenen Eigenschaften des `Customers`-Typs in einen neuen `CustomerAddress`-Typ projiziert, der auf dem Client definiert und als Entitätstyp deklariert wurde:

[!code-csharp[Astoria Northwind Client#SelectCustomerAddressSpecific](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressspecific)]
[!code-vb[Astoria Northwind Client#SelectCustomerAddressSpecific](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressspecific)]

In diesem Beispiel wird das Objektinitialisierermuster statt eines Konstruktoraufrufs verwendet, um eine neue Instanz des `CustomerAddress`-Typs zu erstellen. Beim Projizieren in Entitätstypen werden Konstruktoren nicht unterstützt, beim Projizieren in Nicht-Entitätstypen und anonyme Typen können sie jedoch verwendet werden. Da `CustomerAddress` ein Entitätstyp ist, können Änderungen vorgenommen werden und an den Datendienst zurückgesendet werden.

Auch werden die Daten vom `Customer`-Typ in eine Instanz des `CustomerAddress`-Entitätstyps statt eines anonymen Typs projiziert. Die Projektion auf anonyme Typen wird unterstützt, die Daten sind jedoch schreibgeschützt, weil anonyme Typen wie Nicht-Entitätstypen behandelt werden.

Die <xref:System.Data.Services.Client.MergeOption>-Einstellungen des <xref:System.Data.Services.Client.DataServiceContext>-Kontexts werden während der Abfrageprojektion zur Identitätsauflösung verwendet. Wenn eine Instanz des `Customer`-Typs bereits im <xref:System.Data.Services.Client.DataServiceContext>-Kontext vorhanden ist, dann folgt eine Instanz von `CustomerAddress` mit der gleichen Identität dem Identitätsauflösungsregelsatz vom <xref:System.Data.Services.Client.MergeOption>.

Im folgenden wird die Verhalten beim Projizieren von Ergebnissen in Entitäts- und nicht entitätsbezogenen Typen beschrieben:

**Erstellen einer neuen projizierten Instanz mit Initialisierern**

- Beispiel:

   [!code-csharp[Astoria Northwind Client#ProjectWithInitializer](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithinitializer)]
   [!code-vb[Astoria Northwind Client#ProjectWithInitializer](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithinitializer)]

- Der Entitätstyp: Unterstützt

- Nicht-Entitätstyp: Unterstützt

**Erstellen einer neuen projizierten Instanz mit Konstruktoren**

- Beispiel:

   [!code-csharp[Astoria Northwind Client#ProjectWithConstructor](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithconstructor)]
   [!code-vb[Astoria Northwind Client#ProjectWithConstructor](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithconstructor)]

- Der Entitätstyp: Es wird eine Ausnahme vom Typ <xref:System.NotSupportedException> ausgelöst.

- Nicht-Entitätstyp: Unterstützt

**Projektion verwenden, um einen Eigenschaftswert zu transformieren.**

- Beispiel:

   [!code-csharp[Astoria Northwind Client#ProjectWithTransform](~/samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#projectwithtransform)]
   [!code-vb[Astoria Northwind Client#ProjectWithTransform](~/samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#projectwithtransform)]

- Der Entitätstyp: Diese Transformation wird für Entitätstypen nicht unterstützt, da sie zu Verwirrung und potenziell zum Überschreiben von Daten in der Datenquelle führen kann, die zu einer anderen Entität gehören. Es wird eine Ausnahme vom Typ <xref:System.NotSupportedException> ausgelöst.

- Nicht-Entitätstyp: Unterstützt

<a name="considerations"></a>

## <a name="projection-considerations"></a>Überlegungen zur Projektion

Beim Definieren einer Abfrageprojektion sind außerdem die folgenden Punkte zu berücksichtigen.

- Wenn Sie benutzerdefinierte Feeds für das Atom-Format definieren, müssen Sie sicherstellen, dass alle Entitätseigenschaften, für die benutzerdefinierte Zuordnungen definiert wurden, in der Projektion enthalten sind. Wenn eine zugeordnete Entitätseigenschaft nicht in der Projektion enthalten ist, könnten Datenverluste auftreten. Weitere Informationen finden Sie unter [Feed Anpassung](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).

- Wenn Entitäten in einen projizierten Typ eingefügt werden, der nicht alle Eigenschaften der Entität im Datenmodell des Datendiensts umfasst, werden die in der Projektion in den Client nicht enthaltenen Eigenschaften auf ihre Standardwerte festgelegt.

- Wenn Aktualisierungen an einem projizierten Typ vorgenommen werden, der nicht alle Eigenschaften der Entität im Datenmodell des Datendiensts umfasst, werden vorhandene Werte, die in der Projektion auf dem Client nicht enthalten sind, mit den nicht initialisierten Standardwerten überschrieben.

- Wenn eine Projektion eine komplexe Eigenschaft beinhaltet, muss das gesamte komplexe Objekt zurückgegeben werden.

- Wenn eine Projektion eine Navigationseigenschaft umfasst, werden die verknüpften Objekte implizit geladen, ohne dass die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode aufgerufen werden muss. Die <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A>-Methode kann in projizierten Abfragen nicht verwendet werden.

- Abfragen mit Abfrageprojektionen für den Client werden übersetzt, sodass die `$select`-Abfrageoption im Anforderungs-URI verwendet wird. Wenn eine Abfrage mit Projektion für eine frühere Version von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ausgeführt wird, welche die `$select`-Abfrageoption nicht unterstützt, wird ein Fehler zurückgegeben. Dies kann auch geschehen, wenn die <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A>-Eigenschaft des <xref:System.Data.Services.DataServiceBehavior>-Objekts für den Datendienst auf den Wert <xref:System.Data.Services.Common.DataServiceProtocolVersion.V1> festgelegt wird. Weitere Informationen finden Sie unter [Datendienst-Versionskontrolle](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).

Weitere Informationen finden Sie unter [Vorgehensweise: Projizieren von Abfrageergebnissen](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md).

## <a name="see-also"></a>Siehe auch

- [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)
