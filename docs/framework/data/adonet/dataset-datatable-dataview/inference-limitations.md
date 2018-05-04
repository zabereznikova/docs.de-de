---
title: Rückschlusseinschränkungen
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: b3ad1e66a6a1a4cb2a2aab7b2f86f38e5c784876
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="inference-limitations"></a>Rückschlusseinschränkungen
Beim Herleiten eines <xref:System.Data.DataSet>-Schemas aus XML können sich in Abhängigkeit von den XML-Elementen jedes Dokuments verschiedene Schemata ergeben. Betrachten Sie beispielsweise den folgenden XML-Code:  
  
 Document1:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 Document2:  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
</DocumentElement>  
```  
  
 Für "Document1" die Herleitung ein **DataSet** mit dem Namen "DocumentElement" und eine Tabelle mit dem Namen "Element1", da "Element1" ein sich wiederholendes Element ist.  
  
 **DataSet:** DocumentElement  
  
 **Table:** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Allerdings für "" document2"," die Herleitung ein **DataSet** mit dem Namen "NewDataSet" und eine Tabelle mit dem Namen "DocumentElement". "Element1" wird als Spalte hergeleitet, da es keine Attribute und keine untergeordneten Elemente hat.  
  
 **DataSet:** NewDataSet  
  
 **Table:** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Es war möglicherweise beabsichtigt, dass sich für beide XML-Dokumente dasselbe XML-Schema ergibt, aber die Herleitung führt aufgrund der in den Dokumenten enthaltenen Elemente zu sehr verschiedenen Ergebnissen.  
  
 Zur Vermeidung von abweichungen, die auftreten können, wenn das Schema aus einem XML-Dokument generieren, wird empfohlen, dass Sie explizit ein Schema, das beim Laden von XML-Schemadefinitionssprache (XSD) oder XML-Data Reduced (XDR) verwenden eine **DataSet** aus XML-DATEI. Weitere Informationen zum expliziten Angeben einer **DataSet** Schemas mit XML-Schema finden Sie unter [ableiten relationalen DataSet-Struktur von XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [Laden eines DataSet aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [Laden von DataSet-Schemainformationen aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
