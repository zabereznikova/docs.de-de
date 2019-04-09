---
title: Attributbasiertes Zuordnen
ms.date: 03/30/2017
ms.assetid: 6dd89999-f415-4d61-b8c8-237d23d7924e
ms.openlocfilehash: d7d7c14ca12e40af643d164069cf7b0f3165fa20
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223562"
---
# <a name="attribute-based-mapping"></a>Attributbasiertes Zuordnen
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ordnet eine SQL Server-Datenbank eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Objektmodell mithilfe von Attributen oder mit einer externen Zuordnungsdatei. Dieser Abschnitt befasst sich mit dem attributbasierten Ansatz.  
  
 In der einfachsten Form weist [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine Datenbank einem <xref:System.Data.Linq.DataContext>, eine Tabelle einer Klasse und Spalten/Beziehungen den Eigenschaften dieser Klassen zu. Sie können auch Attribute verwenden, um im Objektmodell eine Vererbungshierarchie zuzuordnen. Weitere Informationen finden Sie unter [Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C# ](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md).  
  
 Entwickler, die in der Regel mithilfe von Visual Studio führen attributbasiertes Mapping mithilfe der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]. Sie können auch das Befehlszeilentool SQLMetal verwenden, oder Sie können den Code für die Attribute selbst schreiben. Weitere Informationen finden Sie unter [Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C# ](../../../../../../docs/framework/data/adonet/sql/linq/how-to-generate-the-object-model-in-visual-basic-or-csharp.md).  
  
> [!NOTE]
>  Sie können die Zuordnung auch mit einer externen XML-Datei vornehmen. Weitere Informationen finden Sie unter [externe Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md).  
  
 In den folgenden Abschnitten wird die attributbasierte Zuordnung ausführlich beschrieben. Weitere Informationen finden Sie unter den Ausführungen zum <xref:System.Data.Linq.Mapping>-Namespace.  
  
## <a name="databaseattribute-attribute"></a>DatabaseAttribute-Attribut  
 Verwenden Sie dieses Attribut, um den Standardnamen der Datenbank anzugeben, wenn dieser nicht von der Verbindung bereitgestellt wird. Dieses Attribut ist optional. Wenn Sie es jedoch verwenden, müssen Sie die <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>-Eigenschaft gemäß der folgenden Tabelle anwenden.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>|Zeichenfolge|Siehe <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>|Gibt in Verbindung mit seiner <xref:System.Data.Linq.Mapping.DatabaseAttribute.Name%2A>-Eigenschaft den Namen der Datenbank an.|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.DatabaseAttribute>.  
  
## <a name="tableattribute-attribute"></a>TableAttribute-Attribut  
 Verwenden Sie dieses Attribut, um eine Klasse als Entität zu kennzeichnen, die einer Datenbanktabelle oder einer Ansicht zugeordnet ist. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] behandelt Klassen, die dieses Attribut als permanente Klassen verfügen. In der folgenden Tabelle wird die <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>-Eigenschaft beschrieben.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.TableAttribute.Name%2A>|Zeichenfolge|Gleiche Zeichenfolge wie Klassenname|Legt eine Klasse als Entitätsklasse fest, die einer Datenbanktabelle zugeordnet ist.|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.TableAttribute>.  
  
## <a name="columnattribute-attribute"></a>ColumnAttribute-Attribut  
 Mit diesem Attribut können Sie einen Member einer Entitätsklasse für die Darstellung einer Spalte in einer Datenbanktabelle festlegen. Dieses Attribut kann auf Felder oder Eigenschaften angewendet werden.  
  
 Nur die von Ihnen als Spalten angegebenen Member werden abgerufen und erhalten, wenn [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Änderungen in der Datenbank speichert. Member ohne dieses Attribut gelten als nicht permanent und werden nicht für Einfügungen oder Updates übermittelt.  
  
 In der folgenden Tabelle werden Eigenschaften dieses Attributs beschrieben.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.AutoSync%2A>|AutoSync|Nie|Weist die Common Language Runtime (CLR) an, nach einer Einfügung oder einem Updatevorgang den Wert abzurufen.<br /><br /> Optionen: Always, Never, OnUpdate, OnInsert.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.CanBeNull%2A>|Boolesch|`true`|Gibt an, dass eine Spalte NULL-Werte enthalten kann.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.DbType%2A>|Zeichenfolge|Abgeleiteter Datenbankspaltentyp|Verwendet Datenbanktypen und Modifizierer, um den Typ der Datenbankspalte anzugeben.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>|Zeichenfolge|Empty|Definiert eine berechnete Spalte in einer Datenbank.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDbGenerated%2A>|Boolesch|`false`|Gibt an, dass eine Spalte Werte enthält, die die Datenbank automatisch generiert.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsDiscriminator%2A>|Boolesch|`false`|Gibt an, dass die Spalte einen Diskriminatorwert für eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Vererbungshierarchie enthält.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsPrimaryKey%2A>|Boolesch|`false`|Legt fest, dass dieser Klassenmember eine Spalte darstellt, die zu den Primärschlüsseln der Tabelle zählt oder ein Teil davon ist.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A>|Boolesch|`false`|Identifiziert den Spaltentyp des Members als Datenbank-Timestamp oder Versionsnummer.|  
|<xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>|UpdateCheck|`Always`, es sei denn, <xref:System.Data.Linq.Mapping.ColumnAttribute.IsVersion%2A> ist `true` für ein Element|Gibt an, wie [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] der Erkennung von Konflikten bei der vollständigen Parallelität handhabt.|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ColumnAttribute>.  
  
> [!NOTE]
>  Bei den "Storage"-Eigenschaftswerten "AssociationAttribute" und "ColumnAttribute" wird die Groß- und Kleinschreibung beachtet. Stellen Sie beispielsweise sicher, dass die im Attribut für die "AssociationAttribute.Storage"-Eigenschaft verwendeten Werte in der Schreibung mit den entsprechenden Eigenschaftsnamen an anderer Stelle im Code übereinstimmen. Dies gilt für alle .NET Programmiersprachen, auch solche, die nicht in der Regel Groß-/Kleinschreibung beachtet, z. B. Visual Basic sind. Weitere Informationen über die "Storage"-Eigenschaft finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
## <a name="associationattribute-attribute"></a>AssociationAttribute-Attribut  
 Mit diesem Attribut legen Sie eine Eigenschaft für die Darstellung der Zuordnung in einer Datenbank dar, z. B. die Beziehung zwischen einem Fremdschlüssel und einem Primärschlüssel. Weitere Informationen zu Beziehungen finden Sie unter [Vorgehensweise: Zuordnen von Datenbankbeziehungen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-map-database-relationships.md).  
  
 In der folgenden Tabelle werden Eigenschaften dieses Attributs beschrieben.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.DeleteOnNull%2A>|Boolesch|`false`|Bei Platzierung in einer Zuordnung, für deren Fremdschlüsselmember keine NULL-Werte zulässig sind, wird das Objekt gelöscht, wenn die Zuordnung auf NULL festgelegt wird.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.DeleteRule%2A>|Zeichenfolge|Keiner|Fügt einer Zuordnung ein Löschverhalten hinzu.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.IsForeignKey%2A>|Boolesch|`false`|Wenn true, legt den Member als Fremdschlüssel in einer Zuordnung fest, die eine Datenbankbeziehung darstellt.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.IsUnique%2A>|Boolesch|`false`|Wenn true, gibt eine Eindeutigkeitseinschränkung des Fremdschlüssels an.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A>|Zeichenfolge|ID der verbundenen Klasse|Kennzeichnet einen oder mehrere Member der Zielentitätsklasse als Schlüsselwerte auf der anderen Seite der Zuordnung.|  
|<xref:System.Data.Linq.Mapping.AssociationAttribute.ThisKey%2A>|Zeichenfolge|ID der enthaltenden Klasse|Legt Member dieser Entitätsklasse fest, um die Schlüsselwerte diesseits der Zuordnung darzustellen.|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.AssociationAttribute>.  
  
> [!NOTE]
>  Bei den "Storage"-Eigenschaftswerten "AssociationAttribute" und "ColumnAttribute" wird die Groß- und Kleinschreibung beachtet. Stellen Sie beispielsweise sicher, dass die im Attribut für die "AssociationAttribute.Storage"-Eigenschaft verwendeten Werte in der Schreibung mit den entsprechenden Eigenschaftsnamen an anderer Stelle im Code übereinstimmen. Dies gilt für alle .NET Programmiersprachen, auch solche, die nicht in der Regel Groß-/Kleinschreibung beachtet, z. B. Visual Basic sind. Weitere Informationen über die "Storage"-Eigenschaft finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
## <a name="inheritancemappingattribute-attribute"></a>InheritanceMappingAttribute-Attribut  
 Verwenden Sie dieses Attribut, um eine Vererbungshierarchie zuzuordnen.  
  
 In der folgenden Tabelle werden Eigenschaften dieses Attributs beschrieben.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Code%2A>|Zeichenfolge|Keine Wert muss angegeben werden.|Gibt den Codewert des Diskriminators an.|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.IsDefault%2A>|Boolesch|`false`|Wenn true, erstellt eine Objektinstanz dieses Typs, wenn kein Diskriminatorwert im Store mit einem der angegebenen Werte übereinstimmt.|  
|<xref:System.Data.Linq.Mapping.InheritanceMappingAttribute.Type%2A>|Typ|Keine Wert muss angegeben werden.|Gibt den Typ der Klasse in der Hierarchie an.|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.InheritanceMappingAttribute>.  
  
## <a name="functionattribute-attribute"></a>FunctionAttribute-Attribut  
 Verwenden Sie dieses Attribut, um eine Methode für die Darstellung einer gespeicherten Prozedur oder einer benutzerdefinierten Funktion in der Datenbank festzulegen.  
  
 In der folgenden Tabelle werden Eigenschaften dieses Attributs beschrieben.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>|Boolesch|`false`|Wenn false, gibt Zuordnungen zu einer gespeicherten Prozedur an. Wenn true, gibt Zuordnungen zu einer benutzerdefinierten Funktion an.|  
|<xref:System.Data.Linq.Mapping.FunctionAttribute.Name%2A>|Zeichenfolge|Gleiche Zeichenfolge wie der Name in der Datenbank|Gibt den Namen der gespeicherten Prozedur oder der benutzerdefinierter Funktion an.|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.FunctionAttribute>.  
  
## <a name="parameterattribute-attribute"></a>ParameterAttribute-Attribut  
 Verwenden Sie dieses Attribut, um Eingabeparameter für gespeicherte Prozedurmethoden zuzuordnen.  
  
 In der folgenden Tabelle werden Eigenschaften dieses Attributs beschrieben.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ParameterAttribute.DbType%2A>|Zeichenfolge|Keiner|Gibt den Datenbanktyp an.|  
|<xref:System.Data.Linq.Mapping.ParameterAttribute.Name%2A>|Zeichenfolge|Gleiche Zeichenfolge wie der Parametername in der Datenbank|Gibt einen Namen für den Parameter an.|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ParameterAttribute>.  
  
## <a name="resulttypeattribute-attribute"></a>ResultTypeAttribute-Attribut  
 Verwenden Sie dieses Attribut, um einen Ergebnistyp anzugeben.  
  
 In der folgenden Tabelle werden Eigenschaften dieses Attributs beschrieben.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.ResultTypeAttribute.Type%2A>|Typ|(Keine)|Verwendet für Methoden, die gespeicherten Prozeduren zugeordnet werden, die <xref:System.Data.Linq.IMultipleResults> zurückgeben. Deklariert die gültigen oder erwarteten Typzuordnungen für die gespeicherte Prozedur.|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.ResultTypeAttribute>.  
  
## <a name="dataattribute-attribute"></a>DataAttribute-Attribut  
 Verwenden Sie dieses Attribut, um Namen und private Speicherfelder anzugeben.  
  
 In der folgenden Tabelle werden Eigenschaften dieses Attributs beschrieben.  
  
|Eigenschaft|Typ|Standard|Beschreibung|  
|--------------|----------|-------------|-----------------|  
|<xref:System.Data.Linq.Mapping.DataAttribute.Name%2A>|Zeichenfolge|Wie der Name in der Datenbank|Gibt den Namen der Tabelle, Spalte usw. an.|  
|<xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>|Zeichenfolge|Öffentliche Zugriffsmethoden|Definiert den Namen eines zugrunde liegenden Speicherfelds an|  
  
 Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.DataAttribute>.  
  
## <a name="see-also"></a>Siehe auch

- [Referenz](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
