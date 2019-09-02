---
title: Ableiten von Beziehungen
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 92a4953dc7f5119ffbf171ff2a7bf5b58e896638
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204771"
---
# <a name="inferring-relationships"></a>Ableiten von Beziehungen
Wenn ein als Tabelle hergeleitetes Element ein ebenfalls als Tabelle hergeleitetes untergeordnetes Element aufweist, wird zwischen den beiden Tabellen eine <xref:System.Data.DataRelation> erstellt. Eine neue Spalte mit dem Namen **ParentTableName_Id** wird sowohl der für das übergeordnete Element erstellten Tabelle als auch der Tabelle hinzugefügt, die für das untergeordnete Element erstellt wurde. Die **ColumnMapping** -Eigenschaft dieser Identitäts Spalte wird auf **MappingType. Hidden**festgelegt. Bei der Spalte handelt es sich um einen automatisch inkrementierenden Primärschlüssel für die übergeordnete Tabelle, der für die **DataRelations** -Beziehung zwischen den beiden Tabellen verwendet wird. Der Datentyp der hinzugefügten Identitäts Spalte ist **System. Int32**, anders als beim Datentyp aller anderen abgelegten Spalten, d. h. **System. String**. Mithilfe <xref:System.Data.ForeignKeyConstraint> der neuen Spalte in der übergeordneten und der untergeordneten Tabelle wird auch ein mit **DeleteRule** = **Cascade** erstellt.  
  
 Betrachten Sie beispielsweise den folgenden XML-Code:  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 Der Herleitungsprozess erstellt die folgenden zwei Tabellen: **Element1** und **ChildElement1**.  
  
 Die **Element1** -Tabelle hat zwei Spalten: **Element1_Id** und **ChildElement2**. Die **ColumnMapping** -Eigenschaft der **Element1_Id** -Spalte wird auf **MappingType. Hidden**festgelegt. Die **ColumnMapping** -Eigenschaft der **ChildElement2** -Spalte wird auf **MappingType. Element**festgelegt. Die **Element1_Id** -Spalte wird als Primärschlüssel der **Element1** -Tabelle festgelegt.  
  
 Die **ChildElement1** -Tabelle enthält drei Spalten: **attr1**, **attr2** und **Element1_Id**. Die **ColumnMapping** -Eigenschaft für die Spalten **attr1** und **attr2** wird auf **MappingType. Attribute**festgelegt. Die **ColumnMapping** -Eigenschaft der **Element1_Id** -Spalte wird auf **MappingType. Hidden**festgelegt.  
  
 Eine **DataRelations** -und eine fremd **Schlüssel Einschränkung** werden mithilfe der **Element1_Id** -Spalten aus beiden Tabellen erstellt.  
  
 **DataSet** DocumentElement  
  
 **Glaub** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **Glaub** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation** Element1_ChildElement1  
  
 **ÜbergeordneteTabelle** Element1  
  
 **Element column:** Element1_Id  
  
 **ChildTable** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **Geschachtelte** True  
  
 **ForeignKeyConstraint** Element1_ChildElement1  
  
 **Kolumne** Element1_Id  
  
 **ÜbergeordneteTabelle** Element1  
  
 **ChildTable** ChildElement1  
  
 **DeleteRule** Cascade  
  
 **AcceptRejectRule** None  
  
## <a name="see-also"></a>Siehe auch

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines DataSet aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [Schachteln von DataRelations](nesting-datarelations.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [DataSets, DataTables und DataViews](index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
