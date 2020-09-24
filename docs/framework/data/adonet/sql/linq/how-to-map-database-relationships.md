---
title: 'Vorgehensweise: Zuordnen von Datenbankbeziehungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: 2f612877f5e7da6442c242aa0d56d811c0aa7cf8
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166455"
---
# <a name="how-to-map-database-relationships"></a>Vorgehensweise: Zuordnen von Datenbankbeziehungen

Sie können in Ihrer Entitätsklasse alle Datenbeziehungen als Eigenschaftenverweise codieren, die stets gleich bleiben. Da Kunden in der Beispieldatenbank Northwind typischerweise Bestellungen übermitteln, besteht im Modell stets eine Beziehung zwischen Kunden und deren Bestellungen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definiert ein <xref:System.Data.Linq.Mapping.AssociationAttribute> Attribut, das die Darstellung solcher Beziehungen unterstützt. Dieses Attribut wird zusammen mit dem <xref:System.Data.Linq.EntitySet%601>-Typ und dem <xref:System.Data.Linq.EntityRef%601>-Typ verwendet, um eine Fremdschlüsselbeziehung in einer Datenbank darzustellen. Weitere Informationen finden Sie im Abschnitt Association Attribute ( [Attribut basierte Zuordnung](attribute-based-mapping.md)).  
  
> [!NOTE]
> Bei den "Storage"-Eigenschaftswerten "AssociationAttribute" und "ColumnAttribute" wird die Groß- und Kleinschreibung beachtet. Stellen Sie beispielsweise sicher, dass die im Attribut für die "AssociationAttribute.Storage"-Eigenschaft verwendeten Werte in der Schreibung mit den entsprechenden Eigenschaftsnamen an anderer Stelle im Code übereinstimmen. Dies gilt für alle .NET-Programmiersprachen, auch für solche, bei denen die Groß-/Kleinschreibung nicht beachtet wird, einschließlich Visual Basic. Weitere Informationen über die "Storage"-Eigenschaft finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 Die meisten Beziehungen sind 1:n, wie im Beispiel weiter unten in diesem Abschnitt. Sie können auch 1:1- und n:n-Beziehungen wie folgt darstellen:  
  
- 1:1-Beziehung: Stellen Sie diese Art von Beziehung dar, indem Sie <xref:System.Data.Linq.EntitySet%601> auf beiden Seiten einschließen.  
  
     Angenommen, eine Beziehung wird `Customer` - `SecurityCode` erstellt, sodass der Sicherheitscode des Kunden nicht in der Tabelle gefunden wird `Customer` und nur autorisierte Personen darauf zugreifen können.  
  
- M:n-Beziehungen: der Primärschlüssel der Verknüpfungs Tabelle (auch als Verknüpfungs *Tabelle bezeichnet* ) wird häufig von einem zusammengesetzten der Fremdschlüssel aus den beiden anderen Tabellen gebildet.  
  
     Stellen Sie sich z. b. eine m:n-Beziehung vor, die mit `Employee` - `Project` Link Table erstellt wurde `EmployeeProject` . [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfordert, dass eine solche Beziehung unter Verwendung von drei Klassen modelliert wird: `Employee`, `Project` und `EmployeeProject`. In diesem Fall kann beim Ändern der Beziehung zwischen einem `Employee` und einem `Project` das Update des Primärschlüssels `EmployeeProject` erfordern. Diese Situation lässt sich jedoch durch Löschen eines vorhandenen `EmployeeProject` und Erstellen eines neuen `EmployeeProject` am besten modellieren.  
  
    > [!NOTE]
    > Beziehungen in relationalen Datenbanken werden typischerweise als Fremdschlüsselwerte modelliert, die sich auf Fremdschlüssel in anderen Dateien beziehen. Um zwischen Ihnen zu navigieren, ordnen Sie die beiden Tabellen explizit zu, indem Sie *einen relationalen* Joinvorgang verwenden.  
    >
    >  Objekte in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] hingegen verweisen einander mithilfe von Eigenschafts verweisen oder Auflistungen von verweisen, die Sie mithilfe der *Punkt* Notation navigieren.  
  
## <a name="example"></a>Beispiel  

 Im folgenden 1:n-Beispiel verfügt die `Customer`-Klasse über eine Eigenschaft, die die Beziehung zwischen Kunden und deren Bestellungen deklariert.  Die `Orders`-Eigenschaft ist vom Typ <xref:System.Data.Linq.EntitySet%601>. Dieser Typ bedeutet, dass diese Beziehung 1:n (ein Kunde zu vielen Bestellungen) ist. Die <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>-Eigenschaft wird zur Beschreibung der Zuweisung verwendet, d. h. durch Angeben des Namens der Eigenschaft in der zugehörigen Klasse, die mit dieser verglichen werden soll. In diesem Beispiel wird die- `CustomerID` Eigenschaft verglichen, ebenso wie ein Daten *bankjoin* diesen Spaltenwert vergleicht.  
  
> [!NOTE]
> Wenn Sie Visual Studio verwenden, können Sie die objektrelationaler Designer verwenden, um eine Zuordnung zwischen Klassen zu erstellen.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Beispiel  

 Sie können die Situation auch umkehren. Anstelle der Verwendung der `Customer`-Klasse zur Beschreibung der Zuordnung von Kunden und Bestellungen können Sie die `Order`-Klasse verwenden. Die `Order`-Klasse verwendet den <xref:System.Data.Linq.EntityRef%601>-Typ, um die Beziehung zurück zum Kunden zu beschreiben. Siehe hierzu das folgende Codebeispiel.  
  
> [!NOTE]
> Die- <xref:System.Data.Linq.EntityRef%601> Klasse unterstützt *Verzögertes Laden*. Weitere Informationen *finden* Sie unter [Verzögertes im Vergleich zu unmittelbarem laden](deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
