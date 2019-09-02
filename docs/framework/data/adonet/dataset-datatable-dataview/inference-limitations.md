---
title: Rückschlusseinschränkungen
ms.date: 03/30/2017
ms.assetid: 78517994-5d57-44f8-9d20-38812977de09
ms.openlocfilehash: 4e0f63776162b60c9333ba47be58ea78a9b6805d
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204835"
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
  
 Bei "Document1" erzeugt der Rückschluss Prozess ein **DataSet** mit dem Namen "DocumentElement" und eine Tabelle mit dem Namen "Element1", da "Element1" ein sich wiederholendes Element ist.  
  
 **DataSet** DocumentElement  
  
 **Glaub** Element1  
  
|Element1_Text|  
|--------------------|  
|Text1|  
|Text2|  
  
 Bei "Document2" erzeugt der Rückschluss Prozess jedoch ein **DataSet** mit dem Namen "NewDataSet" und eine Tabelle mit dem Namen "DocumentElement". "Element1" wird als Spalte hergeleitet, da es keine Attribute und keine untergeordneten Elemente hat.  
  
 **DataSet** NewDataSet  
  
 **Glaub** DocumentElement  
  
|Element1|  
|--------------|  
|Text1|  
  
 Es war möglicherweise beabsichtigt, dass sich für beide XML-Dokumente dasselbe XML-Schema ergibt, aber die Herleitung führt aufgrund der in den Dokumenten enthaltenen Elemente zu sehr verschiedenen Ergebnissen.  
  
 Um Abweichungen zu vermeiden, die beim Erstellen eines Schemas aus einem XML-Dokument auftreten können, empfiehlt es sich, beim Laden eines **DataSets** aus XML explizit ein Schema mit XSD (XML Schema Definition Language) oder XDR (XML-Data Reduced) anzugeben. Weitere Informationen zum expliziten Angeben eines **Datasetschemas** mit XML-Schema finden Sie unter [ableiten von relationalen DataSet-Strukturen aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).  
  
## <a name="see-also"></a>Siehe auch

- [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema](inferring-dataset-relational-structure-from-xml.md)
- [Laden eines DataSet aus XML](loading-a-dataset-from-xml.md)
- [Laden von DataSet-Schemainformationen aus XML](loading-dataset-schema-information-from-xml.md)
- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](using-xml-in-a-dataset.md)
- [DataSets, DataTables und DataViews](index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
