---
title: 'Vorgehensweise: Generieren des Objektmodells als externe Datei'
ms.date: 03/30/2017
ms.assetid: 2496fa06-3df4-4ecb-86c4-70a49ea08565
ms.openlocfilehash: 2442caec5400759ae2bfeca35f99ebd2ff52d011
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91180763"
---
# <a name="how-to-generate-the-object-model-as-an-external-file"></a>Vorgehensweise: Generieren des Objektmodells als externe Datei

Alternativ zur attributbasierten Zuordnung können Sie Ihr Objektmodell als externe XML-Datei generieren, indem Sie das Befehlszeilentool SQLMetal verwenden. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../tools/sqlmetal-exe-code-generation-tool.md). Mit einer externen XML-Zuordnungsdatei verbessern Sie die Übersichtlichkeit des Codes. Sie können auch das Verhalten anpassen, indem Sie die externe Datei ändern, ohne die Binärdateien der Anwendung neu zu kompilieren. Weitere Informationen finden Sie unter [externe Zuordnung](external-mapping.md).  
  
> [!NOTE]
> Das objektrelationaler Designer unterstützt nicht die Generierung einer externen Datei.  
  
## <a name="example"></a>Beispiel  

 Mit dem folgenden Befehl wird eine externe Zuordnungsdatei für die Beispieldatenbank Northwind erstellt.  
  
```console  
sqlmetal /server:myserver /database:northwind /map:externalfile.xml  
```  
  
## <a name="example"></a>Beispiel  

 Im folgenden Auszug aus einer externen Zuordnungsdatei ist die Zuordnung für die Tabelle Customers in der Beispieldatenbank Northwind zu sehen. Dieser Auszug wurde durch Ausführen von SQLMetal mit der **/map** -Option generiert.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Database xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" Name="northwnd">  
  <Table Name="Customers">  
    <Type Name=".Customer">  
      <Column Name="CustomerID" Member="CustomerID" Storage="_CustomerID" DbType="NChar(5) NOT NULL" CanBeNull="False" IsPrimaryKey="True" />  
      <Column Name="CompanyName" Member="CompanyName" Storage="_CompanyName" DbType="NVarChar(40) NOT NULL" CanBeNull="False" />  
      <Column Name="ContactName" Member="ContactName" Storage="_ContactName" DbType="NVarChar(30)" />  
      <Column Name="ContactTitle" Member="ContactTitle" Storage="_ContactTitle" DbType="NVarChar(30)" />  
      <Column Name="Address" Member="Address" Storage="_Address" DbType="NVarChar(60)" />  
      <Column Name="City" Member="City" Storage="_City" DbType="NVarChar(15)" />  
      <Column Name="Region" Member="Region" Storage="_Region" DbType="NVarChar(15)" />  
      <Column Name="PostalCode" Member="PostalCode" Storage="_PostalCode" DbType="NVarChar(10)" />  
      <Column Name="Country" Member="Country" Storage="_Country" DbType="NVarChar(15)" />  
      <Column Name="Phone" Member="Phone" Storage="_Phone" DbType="NVarChar(24)" />  
      <Column Name="Fax" Member="Fax" Storage="_Fax" DbType="NVarChar(24)" />  
      <Association Name="FK_CustomerCustomerDemo_Customers" Member="CustomerCustomerDemos" Storage="_CustomerCustomerDemos" ThisKey="CustomerID" OtherTable="CustomerCustomerDemo" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
      <Association Name="FK_Orders_Customers" Member="Orders" Storage="_Orders" ThisKey="CustomerID" OtherTable="Orders" OtherKey="CustomerID" DeleteRule="NO ACTION" />  
    </Type>  
  </Table>  
</Database>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen des Objektmodells](creating-the-object-model.md)
- [External Mapping (Externe Zuordnung)](external-mapping.md)
- [How to: (Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C#)](how-to-generate-the-object-model-in-visual-basic-or-csharp.md)
