---
title: Das LINQ to SQL-Objektmodell
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
ms.openlocfilehash: b17e1b6f4a6f849e3b42d69e9b9c2d5f906218e1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155509"
---
# <a name="the-linq-to-sql-object-model"></a>Das LINQ to SQL-Objektmodell

In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird ein Objektmodell, das in der Programmiersprache des Entwicklers ausgedrückt wird, dem Datenmodell einer relationalen Datenbank zugeordnet. Operationen mit den Daten werden dann nach dem Objektmodell durchgeführt.  
  
 In diesem Szenario übergeben Sie keine Datenbankbefehle (z. B. `INSERT`) an die Datenbank. Stattdessen ändern Sie Werte und führen Methoden innerhalb des Objektmodells aus. Wenn Sie die Datenbank abfragen oder Änderungen übergeben möchten, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Anforderungen in die richtigen SQL-Befehle und sendet diese an die Datenbank.  
  
 ![Screenshot, der das LINQ-Objektmodell zeigt.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]In der folgenden Tabelle sind die grundlegendsten Elemente im-Objektmodell und deren Beziehung zu Elementen im relationalen Datenmodell zusammengefasst:  
  
|LINQ to SQL-Objektmodell|Relationales Datenmodell|  
|------------------------------|---------------------------|  
|Entitätsklasse|Tabelle|  
|Klassenmember|Column|  
|Zuordnung|Fremdschlüsselbeziehung|  
|Methode|Gespeicherte Prozedur oder Funktion|  
  
> [!NOTE]
> Die folgenden Beschreibungen gehen davon aus, dass Sie über Grundkenntnisse des relationalen Datenmodells und der Regeln verfügen.  
  
## <a name="linq-to-sql-entity-classes-and-database-tables"></a>LINQ to SQL-Entitätsklassen und Datenbanktabellen  

 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird eine Datenbanktabelle durch eine *Entitäts Klasse*dargestellt. Eine Entitätsklasse entspricht jeder anderen Klasse, die Sie erstellen können. Allerdings fügen Sie der Klasse Anmerkungen mit speziellen Informationen hinzu, die diese Klasse einer Datenbanktabelle zuweisen. Sie fügen diese Anmerkungen hinzu, indem Sie Ihrer Klassendeklaration ein benutzerdefiniertes Attribut (<xref:System.Data.Linq.Mapping.TableAttribute>) hinzufügen. Siehe hierzu das folgende Beispiel:  
  
### <a name="example"></a>Beispiel  

 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 Nur als Tabelle deklarierte Klasseninstanzen (Entitätsklassen) können in der Datenbank gespeichert werden.  
  
 Weitere Informationen finden Sie im Abschnitt Tabellen Attribut der [Attribut basierten Zuordnung](attribute-based-mapping.md).  
  
## <a name="linq-to-sql-class-members-and-database-columns"></a>LINQ to SQL-Klassenmember und Datenbankspalten  

 Neben der Zuordnung von Klassen zu Tabellen legen Sie Felder oder Eigenschaften fest, um Datenbankspalten darzustellen. Zu diesem Zweck definiert [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut wie im folgenden Beispiel:  
  
### <a name="example"></a>Beispiel  

 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 Nur Felder und Eigenschaften, die Spalten zugeordnet werden, bleiben in der Datenbank erhalten oder werden aus dieser abgerufen. Alle übrigen Elemente gelten als Übergangsteile Ihrer Anwendungslogik.  
  
 Das <xref:System.Data.Linq.Mapping.ColumnAttribute>-Attribut weist eine Reihe von Eigenschaften auf, mit denen Sie die Member, die Spalten darstellen, anpassen können (sie können z. B. ein Member für die Darstellung einer Primärschlüsselspalte festlegen). Weitere Informationen finden Sie im Abschnitt Column Attribute der [Attribut basierten Zuordnung](attribute-based-mapping.md).  
  
## <a name="linq-to-sql-associations-and-database-foreign-key-relationships"></a>LINQ to SQL-Zuordnungen und Datenbank-Fremdschlüsselbeziehungen  

 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Stellen Sie Daten Bank Zuordnungen (z. b. Fremdschlüssel zu Primärschlüssel Beziehungen) durch Anwenden des- <xref:System.Data.Linq.Mapping.AssociationAttribute> Attributs dar. Im folgenden Codesegment enthält die- `Order` Klasse eine- `Customer` Eigenschaft, die über ein- <xref:System.Data.Linq.Mapping.AssociationAttribute> Attribut verfügt. Diese Eigenschaft und ihr Attribut stellen die `Order`-Klasse mit einer Beziehung zur `Customer`-Klasse bereit.  
  
 Im folgenden Codebeispiel wird die `Customer`-Eigenschaft der `Order`-Klasse gezeigt.  
  
### <a name="example"></a>Beispiel  

 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 Weitere Informationen finden Sie im Abschnitt Association Attribute ( [Attribut basierte Zuordnung](attribute-based-mapping.md)).  
  
## <a name="linq-to-sql-methods-and-database-stored-procedures"></a>LINQ to SQL-Methoden und in der Datenbank gespeicherte Prozeduren  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt gespeicherte Prozeduren und benutzerdefinierte Funktionen. In ordnen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Sie diese Daten Bank definierten Abstraktionen Client Objekten zu, sodass Sie auf eine stark typisierte Weise aus dem Client Code darauf zugreifen können. Die Methodensignaturen entsprechen so weit wie möglich den Signaturen der Prozeduren und Funktionen in der Datenbank. Sie können IntelliSense verwenden, um diese Methoden zu ermitteln.  
  
 Ein von einem Aufruf einer zugeordneten Prozedur zurückgegebener Ergebnissatz ist eine Auflistung mit strikter Typzuordnung.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ordnet gespeicherte Prozeduren und Funktionen den Methoden durch Verwendung des <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut und des <xref:System.Data.Linq.Mapping.ParameterAttribute>-Attribut zu. Methoden, die gespeicherte Prozeduren darstellen, werden von jenen unterschieden, die benutzerdefinierte Funktionen durch die <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>-Eigenschaft darstellen. Wenn diese Eigenschaft auf `false` (Standard) festgelegt wird, stellt die Methode eine gespeicherte Prozedur dar. Wenn sie auf `true` festgelegt wird, stellt die Methode eine Datenbankfunktion dar.  
  
> [!NOTE]
> Wenn Sie Visual Studio verwenden, können Sie den objektrelationaler Designer verwenden, um Methoden zu erstellen, die gespeicherten Prozeduren und benutzerdefinierten Funktionen zugeordnet sind.  
  
### <a name="example"></a>Beispiel  

 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 Weitere Informationen finden Sie in den Abschnitten Funktions Attribut, Attribut für gespeicherte Prozeduren und Parameter Attribute der [Attribut basierten Zuordnung](attribute-based-mapping.md) und [gespeicherter Prozeduren](stored-procedures.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Attributbasiertes Zuordnen](attribute-based-mapping.md)
- [Hintergrundinformationen](background-information.md)
