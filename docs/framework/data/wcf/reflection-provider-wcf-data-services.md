---
title: Reflektionsanbieter (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: ef5ba300-6d7c-455e-a7bd-d0cc6d211ad4
ms.openlocfilehash: e36f9124ec9979dac69b596c6d87491581ae9ec6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59159522"
---
# <a name="reflection-provider-wcf-data-services"></a>Reflektionsanbieter (WCF Data Services)
Zusätzlich zu Daten aus einem Datenmodell über das Entity Framework kann [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Daten verfügbar machen, die in einem entitätsbasierten Modell nicht streng definiert sind. Der Reflexionsanbieter macht Daten in Klassen verfügbar, die Typen zurückgeben, die die <xref:System.Linq.IQueryable%601>-Schnittstelle implementieren. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verwendet Reflexion, um ein Datenmodell für diese Klassen abzuleiten, und kann adressenbasierte Abfragen nach Ressourcen in LINQ (Language Integrated Query)-basierte Abfragen nach den verfügbar gemachten <xref:System.Linq.IQueryable%601>-Typen übersetzen.  
  
> [!NOTE]
>  Sie können eine <xref:System.Linq.Queryable.AsQueryable%2A>-Schnittstelle mithilfe der <xref:System.Linq.IQueryable%601>-Methode aus einer Klasse zurückgeben, die die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert. Dies ermöglicht die Verwendung der meisten generischen Auflistungstypen als Datenquelle für den Datendienst.  
  
 Der Reflektionsanbieter unterstützt Typhierarchien. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Datendiensts mit dem Reflektionsanbieter](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).  
  
## <a name="inferring-the-data-model"></a>Herleiten des Datenmodells  
 Wenn Sie den Datendienst erstellen, leitet der Anbieter das Datenmodell mithilfe der Reflektion her. In der folgenden Liste wird gezeigt, wie der Reflektionsanbieter das Datenmodell herleitet:  
  
-   Entitätscontainer - die Klasse, die die Daten als Eigenschaften verfügbar macht, die eine <xref:System.Linq.IQueryable%601>-Instanz zurückgeben. Wenn Sie ein reflektionsbasiertes Datenmodell adressieren, stellt der Entitätscontainer den Stamm des Diensts dar. Es wird nur eine Entitätscontainerklasse für einen angegebenen Namespace unterstützt.  
  
-   Entitätenmengen - Eigenschaften, die <xref:System.Linq.IQueryable%601>-Instanzen zurückgeben, werden als Entitätenmengen behandelt. Entitätenmengen werden in der Abfrage direkt als Ressourcen adressiert. Nur eine Eigenschaft im Entitätscontainer kann eine <xref:System.Linq.IQueryable%601>-Instanz eines angegebenen Typs zurückgeben.  
  
-   Entitätstypen - der Typ `T` der <xref:System.Linq.IQueryable%601>, den die Entitätenmenge zurückgibt. Klassen, die Teil einer Vererbungshierarchie sind, werden vom Reflektionsanbieter in eine entsprechende Entitätstyphierarchie übersetzt.  
  
-   Entitätsschlüssel - jede Datenklasse, die ein Entitätstyp ist, muss über eine Schlüsseleigenschaft verfügen. Dieser Eigenschaft wird das <xref:System.Data.Services.Common.DataServiceKeyAttribute>-Attribut (`[DataServiceKeyAttribute]`) zugewiesen.  
  
    > [!NOTE]
    >  Sie sollten das <xref:System.Data.Services.Common.DataServiceKeyAttribute>-Attribut nur auf eine Eigenschaft anwenden, mit der eine Instanz des Entitätstyps eindeutig identifiziert werden kann. Dieses Attribut wird ignoriert, wenn es auf eine Navigationseigenschaft angewendet wird.  
  
-   Entitätstypeigenschaften - im Gegensatz zum Entitätsschlüssel behandelt der Reflektionsanbieter die zugänglichen, nicht indizierten Eigenschaften einer Klasse, die ein Entitätstyp ist, wie folgt:  
  
    -   Wenn die Eigenschaft einen primitiven Typ zurückgibt, dann wird davon ausgegangen, dass die Eigenschaft eine Eigenschaft eines Entitätstyps ist.  
  
    -   Wenn die Eigenschaft einen Typ zurückgibt, der auch ein Entitätstyp ist, dann wird davon ausgegangen, dass die Eigenschaft eine Navigationseigenschaft ist, die das "1"-Ende einer n:1- oder 1:1-Beziehung darstellt.  
  
    -   Wenn die Eigenschaft einen <xref:System.Collections.Generic.IEnumerable%601> eines Entitätstyps zurückgibt, dann wird davon ausgegangen, dass die Eigenschaft eine Navigationseigenschaft ist, die das "n"-Ende einer 1:n- oder m:n-Beziehung darstellt.  
  
    -   Wenn es sich beim Rückgabetyp der Eigenschaft um einen Werttyp handelt, stellt die Eigenschaft einen komplexen Typ dar.  
  
> [!NOTE]
>  Im Gegensatz zu einem Datenmodell, das auf dem Entitätsbeziehungsmodell basiert, verstehen auf dem Reflektionsanbieter basierende Modelle keine relationalen Daten. Verwenden Sie das Entity Framework, um relationale Daten über [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verfügbar zu machen.  
  
## <a name="data-type-mapping"></a>Datentypzuordnung  
 Wenn ein Datenmodell aus .NET Framework-Klassen abgeleitet wird, werden die primitiven Typen im Datenmodell .NET Framework-Datentypen wie folgt zugeordnet:  
  
|.NET Framework-Datentyp|Datenmodelltyp|  
|------------------------------|---------------------|  
|<xref:System.Byte> `[]`|`Edm.Binary`|  
|<xref:System.Boolean>|`Edm.Boolean`|  
|<xref:System.Byte>|`Edm.Byte`|  
|<xref:System.DateTime>|`Edm.DateTime`|  
|<xref:System.Decimal>|`Edm.Decimal`|  
|<xref:System.Double>|`Edm.Double`|  
|<xref:System.Guid>|`Edm.Guid`|  
|<xref:System.Int16>|`Edm.Int16`|  
|<xref:System.Int32>|`Edm.Int32`|  
|<xref:System.Int64>|`Edm.Int64`|  
|<xref:System.SByte>|`Edm.SByte`|  
|<xref:System.Single>|`Edm.Single`|  
|<xref:System.String>|`Edm.String`|  
  
> [!NOTE]
>  .NET Framework-Werttypen, denen ein NULL-Wert zugewiesen werden kann, werden den gleichen Datenmodelltypen zugeordnet wie den entsprechenden Werttypen, denen kein NULL-Wert zugewiesen werden kann.  
  
## <a name="enabling-updates-in-the-data-model"></a>Aktivieren von Updates im Datenmodell  
 Der Reflektionsanbieter definiert eine <xref:System.Data.Services.IUpdatable>-Schnittstelle, um Updates für Daten zu ermöglichen, die durch diese Art von Datenmodell verfügbar gemacht werden. Diese Schnittstelle weist den Datendienst an, wie Updates für die verfügbar gemachten Typen beibehalten werden. Die Entitätscontainerklasse muss die <xref:System.Data.Services.IUpdatable>-Schnittstelle implementieren, um Updates für vom Datenmodell definierte Ressourcen zu aktivieren. Ein Beispiel für die Implementierung von der <xref:System.Data.Services.IUpdatable> Benutzeroberfläche, siehe [Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).  
  
 Die <xref:System.Data.Services.IUpdatable>-Schnittstelle erfordert, dass die folgenden Member implementiert werden, damit Updates mit dem Reflektionsanbieter zur Datenquelle weitergegeben werden können:  
  
|Member|Beschreibung|  
|------------|-----------------|  
|<xref:System.Data.Services.IUpdatable.AddReferenceToCollection%2A>|Stellt die Funktionen bereit, um ein Objekt einer Auflistung von verknüpften Objekten hinzuzufügen, auf die von einer Navigationseigenschaft aus zugegriffen wird.|  
|<xref:System.Data.Services.IUpdatable.ClearChanges%2A>|Stellt die Funktionen bereit, die ausstehende Änderungen der Daten abbrechen.|  
|<xref:System.Data.Services.IUpdatable.CreateResource%2A>|Stellt die Funktionen bereit, um im angegebenen Container eine neue Ressource zu erstellen.|  
|<xref:System.Data.Services.IUpdatable.DeleteResource%2A>|Stellt die Funktionen zum Löschen einer Ressource bereit.|  
|<xref:System.Data.Services.IUpdatable.GetResource%2A>|Stellt die Funktionen zum Abrufen einer Ressource bereit, die durch eine bestimmte Abfrage und einen Typnamen identifiziert wird.|  
|<xref:System.Data.Services.IUpdatable.GetValue%2A>|Stellt die Funktionen bereit, um den Wert einer Eigenschaft einer Ressource zurückzugeben.|  
|<xref:System.Data.Services.IUpdatable.RemoveReferenceFromCollection%2A>|Stellt die Funktionen bereit, um ein Objekt aus einer Auflistung von verknüpften Objekten zu entfernen, auf die von einer Navigationseigenschaft aus zugegriffen wird.|  
|<xref:System.Data.Services.IUpdatable.ResetResource%2A>|Stellt die Funktionen bereit, um eine angegebene Ressource zu aktualisieren.|  
|<xref:System.Data.Services.IUpdatable.ResolveResource%2A>|Stellt die Funktionen bereit, um die Ressource zurückzugeben, die durch eine bestimmte Objektinstanz dargestellt wird.|  
|<xref:System.Data.Services.IUpdatable.SaveChanges%2A>|Stellt die Funktionen bereit, um alle ausstehenden Änderungen zu speichern.|  
|<xref:System.Data.Services.IUpdatable.SetReference%2A>|Stellt die Funktionen bereit, um mit einer Navigationseigenschaft einen verknüpften Objektverweis festzulegen.|  
|<xref:System.Data.Services.IUpdatable.SetValue%2A>|Stellt die Funktionen bereit, um den Wert der Eigenschaft einer Ressource festzulegen.|  
  
## <a name="handling-concurrency"></a>Behandeln von Parallelität  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt ein Modell vollständiger Parallelität, indem es Ihnen das Definieren eines Parallelitätstokens für eine Entität ermöglicht. Dieses Parallelitätstoken, das eine oder mehrere Eigenschaften der Entität beinhaltet, wird vom Datendienst verwendet, um zu bestimmen, ob eine Änderung in den angeforderten, aktualisierten oder gelöschten Daten aufgetreten ist. Wenn Tokenwerte die vom eTag in der Anforderung abgerufen wurden, sich von den aktuellen Werten der Entität unterscheiden, löst der Datendienst eine Ausnahme aus. Das <xref:System.Data.Services.ETagAttribute> wird auf einen Entitätstyp angewendet, um im Reflektionsanbieter ein Parallelitätstoken zu definieren. Im Parallelitätstoken darf keine Schlüsseleigenschaft oder Navigationseigenschaft enthalten sein. Weitere Informationen finden Sie unter [Aktualisieren des Datendiensts](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
## <a name="using-linq-to-sql-with-the-reflection-provider"></a>Verwenden von LINQ to SQL mit dem Reflektionsanbieter  
 Da das Entity Framework standardmäßig systemintern unterstützt wird, ist es der empfohlene Datenanbieter zum Verwenden von relationalen Daten mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. Sie können allerdings LINQ to SQL-Klassen mithilfe des Reflektionsanbieters mit einem Datendienst verwenden. Die <xref:System.Data.Linq.Table%601> Resultsets, die von Methoden zurückgegeben werden, auf die <xref:System.Data.Linq.DataContext> generiert, die vom LINQ to SQL Object Relational Designer (O/R Designer) implementieren die <xref:System.Linq.IQueryable%601> Schnittstelle. Dies ermöglicht dem Reflektionsanbieter, auf diese Methoden zuzugreifen und mit den generierten LINQ to SQL-Klassen Entitätsdaten aus SQL Server zurückzugeben. Da LINQ to SQL die <xref:System.Data.Services.IUpdatable>-Schnittstelle nicht implementiert, müssen Sie jedoch eine partielle Klasse hinzufügen, die die vorhandene partielle <xref:System.Data.Linq.DataContext>-Klasse erweitert, um die <xref:System.Data.Services.IUpdatable>-Implementierung hinzuzufügen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
