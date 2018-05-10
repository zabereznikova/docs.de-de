---
title: LINQ to SQL-Beispiel
ms.date: 03/30/2017
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
ms.openlocfilehash: 3cfcaf3de1a22b8bb5505083f127a9888b99dbd8
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="linq-to-sql-sample"></a>LINQ to SQL-Beispiel
Dieses Beispiel veranschaulicht, wie eine Aktivität so erstellt wird, dass LINQ to SQL verwendet wird, um Entitäten aus Tabellen in SQL Server-Datenbanken abzufragen.  
  
> [!IMPORTANT]
>  Die WCF-Beispiele möglicherweise bereits auf dem Computer installiert werden. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, klicken Sie auf den Link zum Herunterladen von Beispielen oben auf dieser Seite. Beachten Sie, dass dieser Link heruntergeladen und alle von installiert der [!INCLUDE[wf1](../../../../includes/wf1-md.md)], WCF und [!INCLUDE[infocard](../../../../includes/infocard-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a>Aktivitätsdetails für FindInSqlTable  
 Diese Aktivität ermöglicht es Benutzern, Entitäten aus Tabellen in einer Datenbank mit LINQ to SQL abzufragen. Benutzer der Aktivität können auch in Form eines Lambda-Ausdrucks ein LINQ-Prädikat bereitstellen, um die Ergebnisse zu filtern. Wenn kein Prädikat angegeben wird, wird die ganze Tabelle zurückgegeben. In der folgenden Tabelle werden die Eigenschaft und die Rückgabewerte für die Aktivität aufgelistet.  
  
|Eigenschaft oder Rückgabewert|Beschreibung|  
|------------------------------|-----------------|  
|`Collection`-Eigenschaft|Eine erforderliche Eigenschaft, die die Quellauflistung angibt.|  
|`Predicate`-Eigenschaft|Eine erforderliche Eigenschaft, die den Filter für die Auflistung in Form eines Lambda-Ausdrucks angibt.|  
|Rückgabewert|Die gefilterte Auflistung.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>Codebeispiel, in dem die benutzerdefinierte Aktivität verwendet wird  
 Im folgenden Codebeispiel wird die benutzerdefinierte `FindInSqlTable`-Aktivität verwendet, um alle Zeilen in einer SQL Server-Tabelle mit dem Namen `Employee` zu finden, bei denen die Spalte `Role` gleich `SDE` ist.  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Navigieren Sie zum Ordner, der dieses Beispiel enthält.  
  
3.  Führen Sie die Befehlsdatei "Setup.cmd" aus.  
  
    > [!NOTE]
    >  Das Skript "Setup.cmd" versucht, die Beispieldatenbank in SQL Server Express auf dem lokalen Computer zu installieren. Wenn Sie es in einer anderen SQL Server-Instanz installieren möchten, bearbeiten Sie "Setup.cmd".  
  
     Das Skript "Setup.cmd" führt die folgenden Aktionen aus:  
  
    -   Erstellt eine Datenbank mit dem Namen "LinqToSqlSample".  
  
    -   Erstellt eine Tabelle "Roles".  
  
    -   Erstellt eine Tabelle "Employees"  
  
    -   Fügt 3 Datensätze in die Tabelle "Roles" ein.  
  
    -   Fügt 12 Datensätze in die Tabelle "Employees" ein.  
  
4.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "LinqToSQL.sln".  
  
5.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
6.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a>So deinstallieren Sie die Beispieldatenbank "LinqToSql"  
  
1.  Öffnen Sie eine Eingabeaufforderung.  
  
2.  Navigieren Sie zum Ordner, der dieses Beispiel enthält.  
  
3.  Führen Sie die Befehlsdatei "Cleanup.cmd" aus.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to SQL](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [Erste Schritte (LINQ to SQL)](http://go.microsoft.com/fwlink/?LinkId=150377)
