---
title: Ableiten von Beziehungen
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 7dc3fb0c6098d636e640aaf52b72a404c1486492
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47080038"
---
# <a name="inferring-relationships"></a>Ableiten von Beziehungen
Wenn ein als Tabelle hergeleitetes Element ein ebenfalls als Tabelle hergeleitetes untergeordnetes Element aufweist, wird zwischen den beiden Tabellen eine <xref:System.Data.DataRelation> erstellt. Eine neue Spalte mit dem Namen **ParentTableName_Id** wird sowohl für das übergeordnete Element erstellten Tabelle als auch für das untergeordnete Element erstellten Tabelle hinzugefügt werden. Die **ColumnMapping** -Eigenschaft dieser Identitätsspalte wird festgelegt **MappingType.Hidden**. Die Spalte wird ein automatisch erhöhenden Primärschlüssel für die übergeordnete Tabelle und verwendet werden, für die **DataRelation** zwischen den beiden Tabellen. Der Datentyp der hinzugefügten Identitätsspalte **System. Int32**, im Gegensatz zu dem Datentyp der aller anderen hergeleiteten Spalten, d.h. **System.String**. Ein <xref:System.Data.ForeignKeyConstraint> mit **DeleteRule** = **Cascade** wird auch unter Verwendung der neuen Spalte in der über- und untergeordneten Tabellen erstellt werden.  
  
 Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Die Herleitung wird zwei Tabellen: **Element1** und **ChildElement1**.  
  
 Die **Element1** Tabelle weist zwei Spalten: **Element1_Id** und **ChildElement2**. Die **ColumnMapping** Eigenschaft der **Element1_Id** Spalte festgelegt **MappingType.Hidden**. Die **ColumnMapping** Eigenschaft der **ChildElement2** Spalte festgelegt **MappingType.Element**. Die **Element1_Id** Spaltensatz wird als den primären Schlüssel für die **Element1** Tabelle.  
  
 Die **ChildElement1** Tabelle weist drei Spalten: **attr1**, **attr2** und **Element1_Id**. Die **ColumnMapping** -Eigenschaft für die **attr1** und **attr2** Spalten festgelegt **MappingType.Attribute**. Die **ColumnMapping** Eigenschaft der **Element1_Id** Spalte festgelegt **MappingType.Hidden**.  
  
 Ein **DataRelation** und **ForeignKeyConstraint** erstellt mithilfe der **Element1_Id** Spalten beider Tabellen.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabelle:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **ParentTable:** Element1  
  
 **Von der übergeordneten Spalte:** Element1_Id  
  
 **UntergeordneteTabelle:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Geschachtelte:** "true"  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **Spalte:** Element1_Id  
  
 **ParentTable:** Element1  
  
 **UntergeordneteTabelle:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** keine  
  
## <a name="see-also"></a>Siehe auch  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Schachteln von DataRelations](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
