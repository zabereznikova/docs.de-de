---
title: "Das LINQ to SQL-Objektmodell | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Das LINQ to SQL-Objektmodell
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird ein in der Programmiersprache des Entwicklers ausgedrücktes Objektmodell dem Datenmodell einer relationalen Datenbank zugeordnet.  Operationen mit den Daten werden dann nach dem Objektmodell durchgeführt.  
  
 In diesem Szenario übergeben Sie keine Datenbankbefehle \(z. B. `INSERT`\) an die Datenbank.  Stattdessen ändern Sie Werte und führen Methoden innerhalb des Objektmodells aus.  Wenn Sie die Datenbank abfragen oder Änderungen übergeben möchten, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Anforderungen in die richtigen SQL\-Befehle und sendet diese an die Datenbank.  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 In der nachfolgenden Tabelle werden die grundlegenden Elemente im [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Objektmodell und deren Beziehungen zu Elementen im relationalen Datenmodell aufgeführt:  
  
|LINQ to SQL\-Objektmodell|Relationales Datenmodell|  
|-------------------------------|------------------------------|  
|Entitätsklasse|Tabelle|  
|Klassenmember|Spalte|  
|Zuordnung|Fremdschlüsselbeziehung|  
|Methode|Gespeicherte Prozedur oder Funktion|  
  
> [!NOTE]
>  Die folgenden Beschreibungen gehen davon aus, dass Sie über Grundkenntnisse des relationalen Datenmodells und der Regeln verfügen.  
  
## LINQ to SQL\-Entitätsklassen und Datenbanktabellen  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird eine Datenbanktabelle durch eine *Entitätsklasse* dargestellt.  Eine Entitätsklasse entspricht jeder anderen Klasse, die Sie erstellen können. Allerdings fügen Sie der Klasse Anmerkungen mit speziellen Informationen hinzu, die diese Klasse einer Datenbanktabelle zuweisen.  Sie fügen diese Anmerkungen hinzu, indem Sie Ihrer Klassendeklaration ein benutzerdefiniertes Attribut \(<xref:System.Data.Linq.Mapping.TableAttribute>\) hinzufügen. Siehe hierzu das folgende Beispiel:  
  
### Beispiel  
 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 Nur als Tabelle deklarierte Klasseninstanzen \(Entitätsklassen\) können in der Datenbank gespeichert werden.  
  
 Weitere Informationen finden Sie im Abschnitt zu Tabellenattributen unter [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## LINQ to SQL\-Klassenmember und Datenbankspalten  
 Neben der Zuordnung von Klassen zu Tabellen legen Sie Felder oder Eigenschaften fest, um Datenbankspalten darzustellen.  Zu diesem Zweck definiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] das <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut wie im folgenden Beispiel:  
  
### Beispiel  
 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 Nur Felder und Eigenschaften, die Spalten zugeordnet werden, bleiben in der Datenbank erhalten oder werden aus dieser abgerufen.  Alle übrigen Elemente gelten als Übergangsteile Ihrer Anwendungslogik.  
  
 Das <xref:System.Data.Linq.Mapping.ColumnAttribute>\-Attribut weist eine Reihe von Eigenschaften auf, mit denen Sie die Member, die Spalten darstellen, anpassen können \(sie können z. B. ein Member für die Darstellung einer Primärschlüsselspalte festlegen\).  Weitere Informationen finden Sie im Abschnitt zu Spaltenattributen unter [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## LINQ to SQL\-Zuordnungen und Datenbank\-Fremdschlüsselbeziehungen  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] werden Datenbankzuordnungen \(z. B. Fremdschlüssel zu Primärschlüsselbeziehungen\) durch Anwenden des <xref:System.Data.Linq.Mapping.AssociationAttribute>\-Attributs dargestellt.  Im folgenden Codesegment enthält die `Order`\-Klasse eine `Customer`\-Eigenschaft mit einem <xref:System.Data.Linq.Mapping.AssociationAttribute>\-Attribut.  Diese Eigenschaft und ihr Attribut stellen die `Order`\-Klasse mit einer Beziehung zur `Customer`\-Klasse bereit.  
  
 Im folgenden Codebeispiel wird die `Customer`\-Eigenschaft der `Order`\-Klasse gezeigt.  
  
### Beispiel  
 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 Weitere Informationen finden Sie im Abschnitt zu Zuordnungsattributen unter [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## LINQ to SQL\-Methoden und in der Datenbank gespeicherte Prozeduren  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt gespeicherte Prozeduren und benutzerdefinierte Funktionen.  In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] weisen Sie diese in der Datenbank definierten Abstraktionen den Client\-Objekten zu, sodass Sie diese vom Client\-Code aus mit strikter Typzuordnung nutzen können.  Die Methodensignaturen entsprechen so weit wie möglich den Signaturen der Prozeduren und Funktionen in der Datenbank.  Sie können IntelliSense verwenden, um diese Methoden zu ermitteln.  
  
 Ein von einem Aufruf einer zugeordneten Prozedur zurückgegebener Ergebnissatz ist eine Auflistung mit strikter Typzuordnung.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ordnet gespeicherte Prozeduren und Funktionen den Methoden durch Verwendung des <xref:System.Data.Linq.Mapping.FunctionAttribute>\-Attribut und des <xref:System.Data.Linq.Mapping.ParameterAttribute>\-Attribut zu.  Methoden, die gespeicherte Prozeduren darstellen, werden von jenen unterschieden, die benutzerdefinierte Funktionen durch die <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>\-Eigenschaft darstellen.  Wenn diese Eigenschaft auf `false` \(Standard\) festgelegt wird, stellt die Methode eine gespeicherte Prozedur dar.  Wenn sie auf `true` festgelegt wird, stellt die Methode eine Datenbankfunktion dar.  
  
> [!NOTE]
>  Wenn Sie [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] verwenden, können Sie mit [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] Methoden erstellen, die gespeicherten Prozeduren und benutzerdefinierten Funktionen zugeordnet werden.  
  
### Beispiel  
 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 Weitere Informationen finden Sie in den Abschnitten zu Funktionsattributen, Attributen von gespeicherten Prozeduren und Parameterattributen unter [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) und [Gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## Siehe auch  
 [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)   
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)