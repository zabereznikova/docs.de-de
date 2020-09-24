---
title: Benutzerdefinierte SQL-CLR-Typenzuordnungen
ms.date: 03/30/2017
ms.assetid: d916c7fb-4b56-4214-acbe-5e23365047b2
ms.openlocfilehash: 14d7f8409f93a5414a37a8b1c8e172f53478e817
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155704"
---
# <a name="sql-clr-custom-type-mappings"></a>Benutzerdefinierte SQL-CLR-Typenzuordnungen

Das Typmapping zwischen SQL Server und der Common Language Runtime (CLR) wird bei der Verwendung des SQLMetal-Befehlszeilentools oder des Object Relational Designer (O/R-Designer) automatisch festgelegt.  
  
 Wenn keine angepasste Zuordnung durchgeführt wird, weisen diese Tools standardmäßige Typzuordnungen zu, wie in [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md)beschrieben. Wenn Sie von den Standardeinstellungen abweichende Typmappings benötigen, müssen die Typmappings angepasst werden.  
  
 Beim Anpassen der Typmappings wird empfohlen, die Änderungen in einer vorübergehend verwendeten DBML-Datei vorzunehmen. Anschließend sollte die benutzerdefinierte DBML-Datei beim Erstellen des Codes und der Mappingdateien mit SQLMetal oder O/R-Designer verwendet werden.  
  
 Beim Instanziieren des <xref:System.Data.Linq.DataContext>-Objekts in Code- und Mappingdateien erstellt die <xref:System.Data.Linq.DataContext.CreateDatabase%2A?displayProperty=nameWithType>-Methode anhand der festgelegten Typmappings eine Datenbank. Wenn in den Mappings keine CLR-`type`-Attribute bestimmt wurden, wird das Standardtypmapping verwendet.  
  
## <a name="customization-with-sqlmetal-or-or-designer"></a>Anpassung mit SQLMetal oder O/R-Designer  

 Mit SQLMetal und O/R-Designer kann automatisch ein Objektmodell erstellt werden, das die Typmappinginformationen innerhalb oder außerhalb der Codedatei enthält. Da diese Dateien von SQLMetal oder O/R-Designer überschrieben werden, wird beim erneuten Erstellen der Mappings für das Festlegen benutzerdefinierter Typmappings empfohlen, eine DBML-Datei anzupassen.  
  
 Um Typmappings mit SQLMetal oder O/R-Designer anzupassen, muss zunächst eine DBML-Datei erstellt werden. Anschließend (und noch vor dem Erstellen der Code- oder Mappingdatei) muss die DBML-Datei bearbeitet werden, um die gewünschten Typmappings festzulegen. In SQLMetal müssen die Attribute `Type` und `DbType` in der DBML-Datei manuell geändert werden, um die Anpassungen am Typmapping vorzunehmen. In O/R-Designer können Sie die Änderungen im Designer vornehmen. Weitere Informationen zur Verwendung des O/R-Designers finden Sie unter [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).  
  
> [!NOTE]
> Einige Typmappings können bei der Übertragung in die Datenbank oder aus der Datenbank einen Überlauf oder Datenverlust verursachen. Überprüfen Sie sorgfältig die Lauf Zeit Verhaltens-Matrix für die Typzuordnung in der [SQL-CLR-Typzuordnung](sql-clr-type-mapping.md) , bevor Sie Anpassungen vornehmen.  
  
 Damit Ihre Anpassungen der Typmappings in SQLMetal oder O/R-Designer erkannt werden, muss sichergestellt werden, dass diese Tools über den Pfad zu Ihrer benutzerdefinierten DBML-Datei verfügen, wenn Sie Ihre Code- oder externe Mappingdatei erstellen. Obwohl dies für die Anpassung des Typmappings nicht erforderlich ist, wird empfohlen, die Typmappinginformationen stets von der Codedatei zu trennen und eine zusätzliche externe Typmappingdatei zu erstellen. Dadurch erhalten Sie eine gewisse Flexibilität, da die Codedatei nicht erneut kompiliert werden muss.  
  
## <a name="incorporating-database-changes"></a>Integrieren von Datenbankänderungen  

 Wenn Änderungen an der Datenbank auftreten, muss die DBML-Datei entsprechend aktualisiert werden. Eine Möglichkeit hierfür besteht im automatischen Erstellen einer neuen DBML-Datei und dem erneuten Anpassen des Typmappings. Sie können jedoch auch die Unterschiede zwischen der neuen DBML-Datei und der benutzerdefinierten DBML-Datei abgleichen und die benutzerdefinierte DBML-Datei manuell aktualisieren, damit diese den Datenbankänderungen entspricht.  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL-CLR-Typenzuordnung](sql-clr-type-mapping.md)
- [Codegenerierung in LINQ to SQL](code-generation-in-linq-to-sql.md)
