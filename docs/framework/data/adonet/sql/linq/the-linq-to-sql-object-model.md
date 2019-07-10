---
title: Das LINQ to SQL-Objektmodell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
ms.openlocfilehash: de3fc8b23bd132179fc7fb67d29010552138e3ab
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742825"
---
# <a name="the-linq-to-sql-object-model"></a>Das LINQ to SQL-Objektmodell
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], ein in der Programmiersprache des Entwicklers ausgedrücktes Objektmodell dem Datenmodell einer relationalen Datenbank zugeordnet ist. Operationen mit den Daten werden dann nach dem Objektmodell durchgeführt.  
  
 In diesem Szenario übergeben Sie keine Datenbankbefehle (z. B. `INSERT`) an die Datenbank. Stattdessen ändern Sie Werte und führen Methoden innerhalb des Objektmodells aus. Wenn Sie die Datenbank abfragen oder Änderungen übergeben möchten, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Anforderungen in die richtigen SQL-Befehle und sendet diese an die Datenbank.  
  
 ![Screenshot mit der Linq-Objektmodell.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 Die grundlegenden Elemente in der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Objektmodell und deren Beziehungen zu Elementen im relationalen Datenmodell werden in der folgenden Tabelle zusammengefasst:  
  
|LINQ to SQL-Objektmodell|Relationales Datenmodell|  
|------------------------------|---------------------------|  
|Entitätsklasse|Tabelle|  
|Klassenmember|Spalte|  
|Zuordnung|Fremdschlüsselbeziehung|  
|Methode|Gespeicherte Prozedur oder Funktion|  
  
> [!NOTE]
>  Die folgenden Beschreibungen gehen davon aus, dass Sie über Grundkenntnisse des relationalen Datenmodells und der Regeln verfügen.  
  
## <a name="linq-to-sql-entity-classes-and-database-tables"></a>LINQ to SQL-Entitätsklassen und Datenbanktabellen  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], eine Datenbanktabelle wird dargestellt, indem ein *Entitätsklasse*. Eine Entitätsklasse entspricht jeder anderen Klasse, die Sie erstellen können. Allerdings fügen Sie der Klasse Anmerkungen mit speziellen Informationen hinzu, die diese Klasse einer Datenbanktabelle zuweisen. Sie fügen diese Anmerkungen hinzu, indem Sie Ihrer Klassendeklaration ein benutzerdefiniertes Attribut (<xref:System.Data.Linq.Mapping.TableAttribute>) hinzufügen. Siehe hierzu das folgende Beispiel:  
  
### <a name="example"></a>Beispiel  
 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 Nur als Tabelle deklarierte Klasseninstanzen (Entitätsklassen) können in der Datenbank gespeichert werden.  
  
 Weitere Informationen finden Sie im Abschnitt Tabellenattributen [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-class-members-and-database-columns"></a>LINQ to SQL-Klassenmember und Datenbankspalten  
 Neben der Zuordnung von Klassen zu Tabellen legen Sie Felder oder Eigenschaften fest, um Datenbankspalten darzustellen. Zu diesem Zweck definiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut wie im folgenden Beispiel:  
  
### <a name="example"></a>Beispiel  
 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 Nur Felder und Eigenschaften, die Spalten zugeordnet werden, bleiben in der Datenbank erhalten oder werden aus dieser abgerufen. Alle übrigen Elemente gelten als Übergangsteile Ihrer Anwendungslogik.  
  
 Das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut weist eine Reihe von Eigenschaften auf, mit denen Sie die Member, die Spalten darstellen, anpassen können (sie können z. B. ein Member für die Darstellung einer Primärschlüsselspalte festlegen). Weitere Informationen finden Sie im Abschnitt Spaltenattribut [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-associations-and-database-foreign-key-relationships"></a>LINQ to SQL-Zuordnungen und Datenbank-Fremdschlüsselbeziehungen  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], Sie darstellen datenbankzuordnungen (z. B. Fremdschlüssel zu primärschlüsselbeziehungen) durch Anwenden der <xref:System.Data.Linq.Mapping.AssociationAttribute> Attribut. Im folgenden Codesegment von Code der `Order` -Klasse enthält eine `Customer` Eigenschaft mit einer <xref:System.Data.Linq.Mapping.AssociationAttribute> Attribut. Diese Eigenschaft und ihr Attribut stellen die `Order`-Klasse mit einer Beziehung zur `Customer`-Klasse bereit.  
  
 Im folgenden Codebeispiel wird die `Customer`-Eigenschaft der `Order`-Klasse gezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 Weitere Informationen finden Sie im Abschnitt Association-Attribut [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-methods-and-database-stored-procedures"></a>LINQ to SQL-Methoden und in der Datenbank gespeicherte Prozeduren  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt gespeicherte Prozeduren und benutzerdefinierte Funktionen. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], Sie diese Datenbank definierten Abstraktionen den Client-Objekten zuordnen, damit Sie in einem strikter Typzuordnung aus Clientcode darauf zugreifen können. Die Methodensignaturen entsprechen so weit wie möglich den Signaturen der Prozeduren und Funktionen in der Datenbank. Sie können IntelliSense verwenden, um diese Methoden zu ermitteln.  
  
 Ein von einem Aufruf einer zugeordneten Prozedur zurückgegebener Ergebnissatz ist eine Auflistung mit strikter Typzuordnung.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ordnet gespeicherte Prozeduren und Funktionen den Methoden durch Verwendung des <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut und des <xref:System.Data.Linq.Mapping.ParameterAttribute>-Attribut zu. Methoden, die gespeicherte Prozeduren darstellen, werden von jenen unterschieden, die benutzerdefinierte Funktionen durch die <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>-Eigenschaft darstellen. Wenn diese Eigenschaft auf `false` (Standard) festgelegt wird, stellt die Methode eine gespeicherte Prozedur dar. Wenn sie auf `true` festgelegt wird, stellt die Methode eine Datenbankfunktion dar.  
  
> [!NOTE]
>  Wenn Sie Visual Studio verwenden, können Sie den Object Relational Designer verwenden, zum Erstellen von Methoden, die die gespeicherten Prozeduren und benutzerdefinierten Funktionen zugeordnet.  
  
### <a name="example"></a>Beispiel  
 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 Weitere Informationen finden Sie in den Abschnitten zu Funktionsattributen, gespeicherten Prozeduren und Parameter-Attribut [attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) und [gespeicherte Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>Siehe auch

- [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
