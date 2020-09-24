---
title: Ableiten von Beziehungen
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177565"
---
# <a name="inferring-relationships"></a>Ableiten von Beziehungen

Wenn ein als Tabelle hergeleitetes Element ein ebenfalls als Tabelle hergeleitetes untergeordnetes Element aufweist, wird zwischen den beiden Tabellen eine <xref:System.Data.DataRelation> erstellt. Eine neue Spalte mit dem Namen **ParentTableName_Id** wird sowohl der für das übergeordnete Element erstellten Tabelle als auch der Tabelle hinzugefügt, die für das untergeordnete Element erstellt wurde. Die **ColumnMapping** -Eigenschaft dieser Identitäts Spalte wird auf **MappingType. Hidden**festgelegt. Bei der Spalte handelt es sich um einen automatisch inkrementierenden Primärschlüssel für die übergeordnete Tabelle, der für die **DataRelations** -Beziehung zwischen den beiden Tabellen verwendet wird. Der Datentyp der hinzugefügten Identitäts Spalte ist **System. Int32**, anders als beim Datentyp aller anderen abgelegten Spalten, d. h. **System. String**. <xref:System.Data.ForeignKeyConstraint> **DeleteRule**  =  Mithilfe der neuen Spalte in der übergeordneten und der untergeordneten Tabelle wird auch ein mit DeleteRule**Cascade** erstellt.  
  
 Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Der Rückschluss Prozess erzeugt zwei Tabellen: **Element1** und **ChildElement1**.  
  
 Die **Element1** -Tabelle enthält zwei Spalten: **Element1_Id** und **ChildElement2**. Die **ColumnMapping** -Eigenschaft der **Element1_Id** -Spalte wird auf **MappingType. Hidden**festgelegt. Die **ColumnMapping** -Eigenschaft der **ChildElement2** -Spalte wird auf **MappingType. Element**festgelegt. Die **Element1_Id** Spalte wird als Primärschlüssel der **Element1** -Tabelle festgelegt.  
  
 Die **ChildElement1** -Tabelle enthält drei Spalten: **attr1**, **attr2** und **Element1_Id**. Die **ColumnMapping** -Eigenschaft für die Spalten **attr1** und **attr2** wird auf **MappingType. Attribute**festgelegt. Die **ColumnMapping** -Eigenschaft der **Element1_Id** -Spalte wird auf **MappingType. Hidden**festgelegt.  
  
 Eine **DataRelations** -und eine fremd **Schlüssel Einschränkung** werden mithilfe der **Element1_Id** Spalten aus beiden Tabellen erstellt.  
  
 **DataSet:** DocumentElement  
  
 **Tabelle:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Tabelle:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelations:** Element1_ChildElement1  
  
 **Parametritable:** Element1  
  
 Element **Column:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 In der folgenden Liste **:** Fall  
  
 Fremd **Schlüssel Einschränkung:** Element1_ChildElement1  
  
 **Spalte:** Element1_Id  
  
 **Parametritable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Mix  
  
 **Akzeptrejectrule:** Gar  
  
## <a name="see-also"></a>Weitere Informationen

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines "DataSets" aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [Verschachteln von "DataRelations"](nesting-datarelations.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- ["DataSets", "DataTables" und "DataViews"](index.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
