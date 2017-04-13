---
title: "Vorgehensweise: Zuordnen von Datenbankbeziehungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Vorgehensweise: Zuordnen von Datenbankbeziehungen
Sie können in Ihrer Entitätsklasse alle Datenbeziehungen als Eigenschaftenverweise codieren, die stets gleich bleiben.  Da Kunden in der Beispieldatenbank Northwind typischerweise Bestellungen übermitteln, besteht im Modell stets eine Beziehung zwischen Kunden und deren Bestellungen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definiert ein <xref:System.Data.Linq.Mapping.AssociationAttribute>\-Attribut zur Unterstützung der Darstellung solcher Beziehungen.  Dieses Attribut wird zusammen mit dem <xref:System.Data.Linq.EntitySet%601>\-Typ und dem <xref:System.Data.Linq.EntityRef%601>\-Typ verwendet, um eine Fremdschlüsselbeziehung in einer Datenbank darzustellen. Weitere Informationen finden Sie im Abschnitt zu Zuordnungsattributen unter [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
> [!NOTE]
>  Bei den "Storage"\-Eigenschaftswerten "AssociationAttribute" und "ColumnAttribute" wird die Groß\- und Kleinschreibung beachtet.  Stellen Sie beispielsweise sicher, dass die im Attribut für die "AssociationAttribute.Storage"\-Eigenschaft verwendeten Werte in der Schreibung mit den entsprechenden Eigenschaftsnamen an anderer Stelle im Code übereinstimmen.  Dies gilt für alle .NET\-Programmiersprachen, auch für diejenigen, bei denen die Groß\- und Kleinschreibung nicht beachtet wird, darunter [!INCLUDE[vb_current_short](../../../../../../includes/vb-current-short-md.md)].  Weitere Informationen über die "Storage"\-Eigenschaft finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=fullName>.  
  
 Die meisten Beziehungen sind 1:n, wie im Beispiel weiter unten in diesem Abschnitt.  Sie können auch 1:1\- und n:n\-Beziehungen wie folgt darstellen:  
  
-   1:1\-Beziehung: Stellen Sie diese Art von Beziehung dar, indem Sie <xref:System.Data.Linq.EntitySet%601> auf beiden Seiten einschließen.  
  
     Stellen Sie sich beispielsweise eine `Customer`\-`SecurityCode`\-Beziehung vor, die so erstellt wurde, dass der Sicherheitscode des Kunden nicht in der `Customer`\-Tabelle gefunden wird, und die nur von autorisierten Personen genutzt werden kann.  
  
-   n:n\-Beziehung: Bei Beziehungen dieser Art wird der Primärschlüssel der Verbindungstabelle \(wird auch als *Verknüpfungstabelle* bezeichnet\) häufig durch eine Kombination der Fremdschlüssel aus den beiden anderen Tabellen gebildet.  
  
     Gehen Sie zum Beispiel von einer `Employee`\-`Project`\-m:n\-Beziehung aus, die mit der Verknüpfungstabelle `EmployeeProject` erstellt wurde.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erfordert, dass eine solche Beziehung unter Verwendung von drei Klassen modelliert wird: `Employee`, `Project` und `EmployeeProject`.  In diesem Fall kann beim Ändern der Beziehung zwischen einem `Employee` und einem `Project` das Update des Primärschlüssels `EmployeeProject` erfordern.  Diese Situation lässt sich jedoch durch Löschen eines vorhandenen `EmployeeProject` und Erstellen eines neuen `EmployeeProject` am besten modellieren.  
  
    > [!NOTE]
    >  Beziehungen in relationalen Datenbanken werden typischerweise als Fremdschlüsselwerte modelliert, die sich auf Fremdschlüssel in anderen Dateien beziehen.  Um zwischen ihnen zu navigieren, ordnen Sie die beiden Tabellen explizit zu, indem Sie eine relationale *Joinoperation* verwenden.  
    >   
    >  Objekte in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verweisen andererseits aufeinander, indem sie Eigenschaftenverweise oder Verweisauflistungen verwenden, in denen Sie mithilfe der *dot*\-Schreibweise navigieren.  
  
## Beispiel  
 Im folgenden 1:n\-Beispiel verfügt die `Customer`\-Klasse über eine Eigenschaft, die die Beziehung zwischen Kunden und deren Bestellungen deklariert.  Die `Orders`\-Eigenschaft ist vom Typ <xref:System.Data.Linq.EntitySet%601>.  Dieser Typ bedeutet, dass diese Beziehung 1:n \(ein Kunde zu vielen Bestellungen\) ist.  Die <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>\-Eigenschaft wird zur Beschreibung der Zuweisung verwendet, d. h. durch Angeben des Namens der Eigenschaft in der zugehörigen Klasse, die mit dieser verglichen werden soll.  In diesem Beispiel wird die `CustomerID`\-Eigenschaft so verglichen, wie ein *Datenbankjoin* den Spaltenwert vergleicht.  
  
> [!NOTE]
>  Wenn Sie [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, können Sie mit [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] eine Zuordnung zwischen den Klassen herstellen.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## Beispiel  
 Sie können die Situation auch umkehren.  Anstelle der Verwendung der `Customer`\-Klasse zur Beschreibung der Zuordnung von Kunden und Bestellungen können Sie die `Order`\-Klasse verwenden.  Die `Order`\-Klasse verwendet den <xref:System.Data.Linq.EntityRef%601>\-Typ, um die Beziehung zurück zum Kunden zu beschreiben. Siehe hierzu das folgende Codebeispiel.  
  
> [!NOTE]
>  Die <xref:System.Data.Linq.EntityRef%601>\-Klasse unterstützt *verzögertes Laden*.  Weitere Informationen *finden Sie unter* [Verzögertes und unmittelbares Laden](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## Siehe auch  
 [Vorgehensweise: Anpassen von Entitätsklassen mithilfe des Code\-Editors](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)   
 [Das LINQ to SQL\-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)