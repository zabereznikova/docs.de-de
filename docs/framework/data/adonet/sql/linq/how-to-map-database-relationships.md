---
title: 'Vorgehensweise: Zuordnen von Datenbankbeziehungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: 40e376f2c2584490273ec27b78fe5315cbb0315e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033721"
---
# <a name="how-to-map-database-relationships"></a>Vorgehensweise: Zuordnen von Datenbankbeziehungen
Sie können in Ihrer Entitätsklasse alle Datenbeziehungen als Eigenschaftenverweise codieren, die stets gleich bleiben. Da Kunden in der Beispieldatenbank Northwind typischerweise Bestellungen übermitteln, besteht im Modell stets eine Beziehung zwischen Kunden und deren Bestellungen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definiert eine <xref:System.Data.Linq.Mapping.AssociationAttribute> -Attribut zur Unterstützung der Darstellung solcher Beziehungen. Dieses Attribut wird zusammen mit dem <xref:System.Data.Linq.EntitySet%601>-Typ und dem <xref:System.Data.Linq.EntityRef%601>-Typ verwendet, um eine Fremdschlüsselbeziehung in einer Datenbank darzustellen. Weitere Informationen finden Sie im Abschnitt Association-Attribut [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
> [!NOTE]
>  Bei den "Storage"-Eigenschaftswerten "AssociationAttribute" und "ColumnAttribute" wird die Groß- und Kleinschreibung beachtet. Stellen Sie beispielsweise sicher, dass die im Attribut für die "AssociationAttribute.Storage"-Eigenschaft verwendeten Werte in der Schreibung mit den entsprechenden Eigenschaftsnamen an anderer Stelle im Code übereinstimmen. Dies gilt für alle .NET Programmiersprachen, auch solche, die nicht in der Regel Groß-/Kleinschreibung beachtet, z. B. Visual Basic sind. Weitere Informationen über die "Storage"-Eigenschaft finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 Die meisten Beziehungen sind 1:n, wie im Beispiel weiter unten in diesem Abschnitt. Sie können auch 1:1- und n:n-Beziehungen wie folgt darstellen:  
  
- 1: 1: Diese Art von Beziehung darstellen, indem Sie einschließlich <xref:System.Data.Linq.EntitySet%601> auf beiden Seiten.  
  
     Betrachten Sie beispielsweise eine `Customer` - `SecurityCode` Beziehung erstellt, sodass in Sicherheitscode des Kunden nicht gefunden werden, wird die `Customer` -Tabelle und kann nur von autorisierten Personen zugegriffen werden.  
  
- M: n: In den primären Schlüssel des der Verknüpfungstabelle m: n Beziehungen (auch mit dem Namen der *Junction* Tabelle) wird häufig durch eine Kombination der Fremdschlüssel aus den beiden anderen Tabellen gebildet.  
  
     Betrachten Sie beispielsweise eine `Employee` - `Project` m: n Beziehung aus, die mit der Verknüpfungstabelle `EmployeeProject`. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfordert, dass eine solche Beziehung unter Verwendung von drei Klassen modelliert wird: `Employee`, `Project` und `EmployeeProject`. In diesem Fall kann beim Ändern der Beziehung zwischen einem `Employee` und einem `Project` das Update des Primärschlüssels `EmployeeProject` erfordern. Diese Situation lässt sich jedoch durch Löschen eines vorhandenen `EmployeeProject` und Erstellen eines neuen `EmployeeProject` am besten modellieren.  
  
    > [!NOTE]
    >  Beziehungen in relationalen Datenbanken werden typischerweise als Fremdschlüsselwerte modelliert, die sich auf Fremdschlüssel in anderen Dateien beziehen. Navigation zwischen ihnen Sie explizit die beiden Tabellen mit einer relationalen zuordnen *Join* Vorgang.  
    >   
    >  Objekte im [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], auf der anderen hand, verweisen Sie untereinander, indem Sie Eigenschaftenverweise oder verweisauflistungen verwenden, die Sie durch Navigieren *Punkt* Notation.  
  
## <a name="example"></a>Beispiel  
 Im folgenden 1:n-Beispiel verfügt die `Customer`-Klasse über eine Eigenschaft, die die Beziehung zwischen Kunden und deren Bestellungen deklariert.  Die `Orders`-Eigenschaft ist vom Typ <xref:System.Data.Linq.EntitySet%601>. Dieser Typ bedeutet, dass diese Beziehung 1:n (ein Kunde zu vielen Bestellungen) ist. Die <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>-Eigenschaft wird zur Beschreibung der Zuweisung verwendet, d. h. durch Angeben des Namens der Eigenschaft in der zugehörigen Klasse, die mit dieser verglichen werden soll. In diesem Beispiel die `CustomerID` -Eigenschaft so verglichen, wie ein *Join* Spaltenwert vergleicht.  
  
> [!NOTE]
>  Wenn Sie Visual Studio verwenden, können Sie die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] zum Erstellen einer Zuordnung zwischen Klassen.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Sie können die Situation auch umkehren. Anstelle der Verwendung der `Customer`-Klasse zur Beschreibung der Zuordnung von Kunden und Bestellungen können Sie die `Order`-Klasse verwenden. Die `Order`-Klasse verwendet den <xref:System.Data.Linq.EntityRef%601>-Typ, um die Beziehung zurück zum Kunden zu beschreiben. Siehe hierzu das folgende Codebeispiel.  
  
> [!NOTE]
>  Die <xref:System.Data.Linq.EntityRef%601> -Klasse unterstützt *verzögertes Laden*. Weitere Informationen *finden Sie unter* [verzögertes im Vergleich zu den sofortigen Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
