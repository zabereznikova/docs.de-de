---
title: 'Vorgehensweise: Zuordnen von Datenbankbeziehungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: 42e7a715c8137574bff617715c1f174314080131
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943615"
---
# <a name="how-to-map-database-relationships"></a>Vorgehensweise: Zuordnen von Datenbankbeziehungen
Sie können in Ihrer Entitätsklasse alle Datenbeziehungen als Eigenschaftenverweise codieren, die stets gleich bleiben. Da Kunden in der Beispieldatenbank Northwind typischerweise Bestellungen übermitteln, besteht im Modell stets eine Beziehung zwischen Kunden und deren Bestellungen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]definiert ein <xref:System.Data.Linq.Mapping.AssociationAttribute> Attribut, das die Darstellung solcher Beziehungen unterstützt. Dieses Attribut wird zusammen mit dem <xref:System.Data.Linq.EntitySet%601>-Typ und dem <xref:System.Data.Linq.EntityRef%601>-Typ verwendet, um eine Fremdschlüsselbeziehung in einer Datenbank darzustellen. Weitere Informationen finden Sie im Abschnitt Association Attribute ( [Attribut basierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)).  
  
> [!NOTE]
> Bei den "Storage"-Eigenschaftswerten "AssociationAttribute" und "ColumnAttribute" wird die Groß- und Kleinschreibung beachtet. Stellen Sie beispielsweise sicher, dass die im Attribut für die "AssociationAttribute.Storage"-Eigenschaft verwendeten Werte in der Schreibung mit den entsprechenden Eigenschaftsnamen an anderer Stelle im Code übereinstimmen. Dies gilt für alle .NET-Programmiersprachen, auch für solche, bei denen die Groß-/Kleinschreibung nicht beachtet wird, einschließlich Visual Basic. Weitere Informationen über die "Storage"-Eigenschaft finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 Die meisten Beziehungen sind 1:n, wie im Beispiel weiter unten in diesem Abschnitt. Sie können auch 1:1- und n:n-Beziehungen wie folgt darstellen:  
  
- Eins zu eins: Stellen Sie diese Art von Beziehung dar <xref:System.Data.Linq.EntitySet%601> , indem Sie auf beiden Seiten einschließen.  
  
     Angenommen `Customer` , eine - `Customer` Beziehung wird erstellt, sodass der Sicherheitscode des Kunden nicht in der Tabelle gefunden wird und nur autorisierte Personen darauf zugreifen können. `SecurityCode`  
  
- M:n-Zahl: Bei m:n-Beziehungen wird der Primärschlüssel der Verknüpfungs Tabelle (auch als Verknüpfungs Tabelle bezeichnet) häufig durch eine zusammengesetzte der Fremdschlüssel aus den beiden anderen Tabellen gebildet.  
  
     Stellen Sie sich z. `Employee` b. eine m:n-Beziehung vor, die `EmployeeProject` - `Project` mit Link Table erstellt wurde. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfordert, dass eine solche Beziehung unter Verwendung von drei Klassen modelliert wird: `Employee`, `Project` und `EmployeeProject`. In diesem Fall kann beim Ändern der Beziehung zwischen einem `Employee` und einem `Project` das Update des Primärschlüssels `EmployeeProject` erfordern. Diese Situation lässt sich jedoch durch Löschen eines vorhandenen `EmployeeProject` und Erstellen eines neuen `EmployeeProject` am besten modellieren.  
  
    > [!NOTE]
    > Beziehungen in relationalen Datenbanken werden typischerweise als Fremdschlüsselwerte modelliert, die sich auf Fremdschlüssel in anderen Dateien beziehen. Um zwischen Ihnen zu navigieren, ordnen Sie die beiden Tabellen explizit zu, indem Sie einen relationalen Joinvorgang verwenden.  
    >   
    >  Objekte in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]hingegen verweisen einander mithilfe von Eigenschafts verweisen oder Auflistungen von verweisen, die Sie mithilfe der *Punkt* Notation navigieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden 1:n-Beispiel verfügt die `Customer`-Klasse über eine Eigenschaft, die die Beziehung zwischen Kunden und deren Bestellungen deklariert.  Die `Orders`-Eigenschaft ist vom Typ <xref:System.Data.Linq.EntitySet%601>. Dieser Typ bedeutet, dass diese Beziehung 1:n (ein Kunde zu vielen Bestellungen) ist. Die <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>-Eigenschaft wird zur Beschreibung der Zuweisung verwendet, d. h. durch Angeben des Namens der Eigenschaft in der zugehörigen Klasse, die mit dieser verglichen werden soll. In diesem Beispiel wird die `CustomerID` -Eigenschaft verglichen, ebenso wie ein Daten *bankjoin* diesen Spaltenwert vergleicht.  
  
> [!NOTE]
> Wenn Sie Visual Studio verwenden, können Sie die objektrelationaler Designer verwenden, um eine Zuordnung zwischen Klassen zu erstellen.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Sie können die Situation auch umkehren. Anstelle der Verwendung der `Customer`-Klasse zur Beschreibung der Zuordnung von Kunden und Bestellungen können Sie die `Order`-Klasse verwenden. Die `Order`-Klasse verwendet den <xref:System.Data.Linq.EntityRef%601>-Typ, um die Beziehung zurück zum Kunden zu beschreiben. Siehe hierzu das folgende Codebeispiel.  
  
> [!NOTE]
> Die <xref:System.Data.Linq.EntityRef%601> -Klasse unterstützt verzögertes *Laden*. Weitere Informationen *finden* Sie unter Verzögertes im [Vergleich zu unmittelbarem laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anpassen von Entitäts Klassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
