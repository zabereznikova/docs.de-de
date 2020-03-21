---
title: 'Gewusst wie: Zuordnen von Datenbankbeziehungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: c89fb3e11ae8e0f8ea37727446cdf65db9499a1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148373"
---
# <a name="how-to-map-database-relationships"></a>Gewusst wie: Zuordnen von Datenbankbeziehungen
Sie können in Ihrer Entitätsklasse alle Datenbeziehungen als Eigenschaftenverweise codieren, die stets gleich bleiben. Da Kunden in der Beispieldatenbank Northwind typischerweise Bestellungen übermitteln, besteht im Modell stets eine Beziehung zwischen Kunden und deren Bestellungen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]definiert ein <xref:System.Data.Linq.Mapping.AssociationAttribute> Attribut, um solche Beziehungen darzustellen. Dieses Attribut wird zusammen mit dem <xref:System.Data.Linq.EntitySet%601>-Typ und dem <xref:System.Data.Linq.EntityRef%601>-Typ verwendet, um eine Fremdschlüsselbeziehung in einer Datenbank darzustellen. Weitere Informationen finden Sie im Abschnitt Zuordnungsattribut [der attributbasierten Zuordnung](attribute-based-mapping.md).  
  
> [!NOTE]
> Bei den "Storage"-Eigenschaftswerten "AssociationAttribute" und "ColumnAttribute" wird die Groß- und Kleinschreibung beachtet. Stellen Sie beispielsweise sicher, dass die im Attribut für die "AssociationAttribute.Storage"-Eigenschaft verwendeten Werte in der Schreibung mit den entsprechenden Eigenschaftsnamen an anderer Stelle im Code übereinstimmen. Dies gilt für alle .NET-Programmiersprachen, auch für Programmiersprachen, die in der Regel nicht von Groß-/Kleinschreibung beachtet werden, einschließlich Visual Basic. Weitere Informationen über die "Storage"-Eigenschaft finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 Die meisten Beziehungen sind 1:n, wie im Beispiel weiter unten in diesem Abschnitt. Sie können auch 1:1- und n:n-Beziehungen wie folgt darstellen:  
  
- 1:1-Beziehung: Stellen Sie diese Art von Beziehung dar, indem Sie <xref:System.Data.Linq.EntitySet%601> auf beiden Seiten einschließen.  
  
     Betrachten Sie beispielsweise `Customer` - `SecurityCode` eine Beziehung, die erstellt wurde, damit der `Customer` Sicherheitscode des Debitors nicht in der Tabelle gefunden wird und nur autorisierte Personen darauf zugreifen können.  
  
- Viele:Viele: In vielen Beziehungen wird der Primärschlüssel der Verknüpfungstabelle (auch *Als Verknüpfungstabelle* bezeichnet) häufig durch einen Verbund der Fremdschlüssel aus den anderen beiden Tabellen gebildet.  
  
     Betrachten Sie z. B. `Employee` - `Project` eine n:n-Beziehung, die mithilfe der Linktabelle `EmployeeProject`gebildet wird. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfordert, dass eine solche Beziehung unter Verwendung von drei Klassen modelliert wird: `Employee`, `Project` und `EmployeeProject`. In diesem Fall kann beim Ändern der Beziehung zwischen einem `Employee` und einem `Project` das Update des Primärschlüssels `EmployeeProject` erfordern. Diese Situation lässt sich jedoch durch Löschen eines vorhandenen `EmployeeProject` und Erstellen eines neuen `EmployeeProject` am besten modellieren.  
  
    > [!NOTE]
    > Beziehungen in relationalen Datenbanken werden typischerweise als Fremdschlüsselwerte modelliert, die sich auf Fremdschlüssel in anderen Dateien beziehen. Um zwischen ihnen zu navigieren, verknüpfen Sie die beiden Tabellen explizit mithilfe eines relationalen *Verknüpfungsvorgangs.*  
    >
    >  Objekte [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]in hingegen verweisen aufeinander, indem Sie Eigenschaftenverweise oder Sammlungen von Verweisen verwenden, die Sie mithilfe der *Punktnotation* navigieren.  
  
## <a name="example"></a>Beispiel  
 Im folgenden 1:n-Beispiel verfügt die `Customer`-Klasse über eine Eigenschaft, die die Beziehung zwischen Kunden und deren Bestellungen deklariert.  Die `Orders`-Eigenschaft ist vom Typ <xref:System.Data.Linq.EntitySet%601>. Dieser Typ bedeutet, dass diese Beziehung 1:n (ein Kunde zu vielen Bestellungen) ist. Die <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>-Eigenschaft wird zur Beschreibung der Zuweisung verwendet, d. h. durch Angeben des Namens der Eigenschaft in der zugehörigen Klasse, die mit dieser verglichen werden soll. In diesem Beispiel `CustomerID` wird die Eigenschaft verglichen, genau wie eine *Datenbankverknüpfung* diesen Spaltenwert vergleichen würde.  
  
> [!NOTE]
> Wenn Sie Visual Studio verwenden, können Sie den Objektrelational-Designer verwenden, um eine Zuordnung zwischen Klassen zu erstellen.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Sie können die Situation auch umkehren. Anstelle der Verwendung der `Customer`-Klasse zur Beschreibung der Zuordnung von Kunden und Bestellungen können Sie die `Order`-Klasse verwenden. Die `Order`-Klasse verwendet den <xref:System.Data.Linq.EntityRef%601>-Typ, um die Beziehung zurück zum Kunden zu beschreiben. Siehe hierzu das folgende Codebeispiel.  
  
> [!NOTE]
> Die <xref:System.Data.Linq.EntityRef%601> Klasse unterstützt *das verzögerte Laden*. Weitere Informationen finden Sie *unter* [Verzögertes und sofortiges Laden](deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Das LINQ to SQL-Objektmodell](the-linq-to-sql-object-model.md)
