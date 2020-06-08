---
title: XML-Integration mit relationalen Daten und ADO.NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: f6ebb1a1-f2ca-49b9-92c9-0150940cf6e6
ms.openlocfilehash: f54c7a890ada01f2cffdd54c024cfbc98777200d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289017"
---
# <a name="xml-integration-with-relational-data-and-adonet"></a>XML-Integration mit relationalen Daten und ADO.NET
Die **XmlDataDocument**-Klasse ist eine von der **XmlDocument**-Klasse abgeleitete Klasse und enthält XML-Daten. Der Vorteil der **XmlDataDocument**-Klasse liegt im Herstellen einer Brücke zwischen relationalen und hierarchischen Daten. Ein **XmlDocument** kann an ein **DataSet** gebunden werden, und Änderungen, die an den Dateien in den beiden Klassen vorgenommen wurden, können in beiden Klassen synchronisiert werden. Ein an ein **DataSet** gebundenes **XmlDocument** ermöglicht die Integration von XML in relationale Daten, und die Daten müssen nicht als XML oder in einem relationalen Format dargestellt werden. Sie können beide Möglichkeiten nutzen und sind somit nicht auf eine einzige Darstellung der Daten festgelegt.  
  
 Wenn die Daten in zwei Ansichten zur Verfügung stehen, ergeben sich folgende Vorteile:  
  
- Der strukturierte Teil eines XML-Dokuments kann einem Dataset zugeordnet und effizient gespeichert, indiziert und durchsucht werden.  
  
- Transformationen, Validierungen und die Navigationen können mit einem Cursormodell in den relational gespeicherten XML-Daten effizient ausgeführt werden. Manchmal kann dies mit relationalen Strukturen effektiver ausgeführt werden als anhand von XML-Code, der in einem **XmlDocument**-Modell gespeichert ist.  
  
- Im **DataSet** kann ein Teil des XML-Codes gespeichert werden. Das heißt, dass Sie mithilfe von **XPath** oder **XslTransform** nur die für Sie relevanten Elemente und Attribute in einem **DataSet** speichern können. Dort können Änderungen an der kleineren gefilterten Teilmenge der Daten vorgenommen werden, und diese Änderungen werden anschließend in den umfangreicheren Daten von **XmlDataDocument** verbreitet.  
  
 Sie können auch eine Transformation von Daten vornehmen, die aus SQL Server in das **DataSet** geladen wurden. Eine andere Möglichkeit besteht darin, nach Klasse und Stil verwaltete WinForm- und WebForm-Steuerelemente aus .NET Framework an ein **DataSet** zu binden, das aus einem XML-Eingabestream aufgefüllt wurde.  
  
 Neben der Unterstützung von **XslTransform** macht ein **XmlDataDocument** relationale Daten für **XPath**-Abfragen und Validierungen verfügbar.  Grundsätzlich sind alle XML-Dienste für relationale Daten verfügbar, und relationale Funktionen wie Steuerelementbindung, CODEGEN usw. sind für eine strukturierte Projektion von XML verfügbar, ohne die XML-Integrität zu beeinträchtigen.  
  
 Da **XmlDataDocument** aus einem **XmlDocument** geerbt wird, enthält es eine Implementierung des W3C-Dokumentobjektmodells (DOM). Durch die Tatsache, dass das **XmlDataDocument** einem **DataSet** zugeordnet ist und eine Teilmenge seiner Daten darin speichert, wird dessen Verwendung als **XmlDocument** in keiner Weise eingeschränkt oder verändert. Code, der zur Verarbeitung von **XmlDocument** geschrieben wurde, funktioniert unverändert mit **XmlDataDocument**. Das **DataSet** bietet eine relationale Ansicht derselben Daten durch die Definition von Tabellen, Spalten, Beziehungen und Einschränkungen. Es ist ein eigenständiger, in den Arbeitsspeicher geladener Benutzerdatenspeicher.  
  
 In der folgenden Abbildung werden die verschiedenen Beziehungen zwischen XML-Daten und dem **DataSet** sowie dem **XmlDataDocument** dargestellt:
  
 ![Abbildung zu verschiedenen Zuordnungen mit dem XML-DataSet.](./media/xml-integration-with-relational-data-and-adonet/xml-integration-relational-data-adodotnet.gif)  
  
 Aus der Abbildung geht hervor, dass XML-Daten direkt in ein **DataSet** geladen werden können. Dadurch kann XML direkt in relationaler Weise bearbeitet werden. XML kann auch in eine abgeleitete Klasse des Dokumentobjektmodells (DOM) geladen werden, d.h. in ein **XmlDataDocument**, und anschließend erfolgt das Laden in das **DataSet** sowie die Synchronisierung. Da das **DataSet** und das **XmlDataDocument** anhand einer einzigen Datengruppe synchronisiert werden, werden Änderungen an den Daten eines Speichers im anderen Speicher widergespiegelt.  
  
 Das **XmlDataDocument** erbt vom **XmlDocument** alle Funktionen zum Bearbeiten und Navigieren. In bestimmten Situationen ist es sinnvoller, das **XmlDataDocument** und dessen geerbte Funktionen zu verwenden und eine Synchronisierung mit dem **DataSet** auszuführen, anstatt XML-Daten direkt in das **DataSet** zu laden. In der folgenden Tabelle sind die Punkte aufgeführt, die bei der Auswahl der geeigneten Methode zum Laden des **DataSet** zu berücksichtigen sind.  
  
|Direktes Laden von XML in ein DataSet|Synchronisieren von „XmlDataDocument“ mit einem „DataSet“|  
|----------------------------------------------|-----------------------------------------------------------|  
|Datenabfragen im **DataSet** können mit SQL einfacher ausgeführt werden als mit XPath.|Für Daten im **DataSet** sind XPath-Abfragen erforderlich.|  
|Das Beibehalten der Elementreihenfolge in der Quell-XML ist nicht funktionsentscheidend.|Das Beibehalten der Elementreihenfolge in der Quell-XML ist funktionsentscheidend.|  
|Leerraum zwischen Elementen und Formatierung muss in der Quell-XML nicht beibehalten werden.|Die Beibehaltung von Leerraum und Formatierung in der Quell-XML ist funktionsentscheidend.|  
  
 Wenn das direkte Laden und Schreiben von XML in ein **DataSet** und aus einem solchen Ihren Anforderungen entspricht, können Sie unter [Laden eines DataSets aus XML](../../../framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md) und [Schreiben eines DataSets als XML-Daten](../../../framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md) weitere Informationen finden.  
  
 Wenn das Laden des **DataSet** aus einem **XmlDataDocument** Ihren Anforderungen entspricht, finden Sie unter [Synchronisieren eines DataSets mit einem XML-Dokument](../../../framework/data/adonet/dataset-datatable-dataview/dataset-and-xmldatadocument-synchronization.md) weitere Informationen.  
  
## <a name="see-also"></a>Siehe auch

- [Using XML in a DataSet (Verwenden von XML in einem DataSet)](../../../framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
