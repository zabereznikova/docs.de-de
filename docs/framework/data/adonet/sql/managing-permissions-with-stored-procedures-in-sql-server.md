---
title: Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08fa34e8-2ffa-470d-ba62-e511a5f8558e
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 58129cf690d4d46cda1e59671ae1423b8a64163f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="managing-permissions-with-stored-procedures-in-sql-server"></a>Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server
Eine Möglichkeit, eine Bastion aus mehreren Verteidigungslinien um Ihre Datenbank aufzubauen, besteht darin, den Zugriff auf Daten so zu implementieren, dass er nur über gespeicherte Prozeduren oder benutzerdefinierten Funktionen läuft. Sie können alle Berechtigungen für die zugrunde liegenden Objekte, z. B. Tabellen, widerrufen oder verweigern, und Sie können EXECUTE-Berechtigungen für gespeicherte Prozeduren gewähren. Auf diese Weise wird um Ihre Daten und Datenbankobjekte herum ein wirksamer Sicherheitszaun aufgebaut.  
  
## <a name="stored-procedure-benefits"></a>Vorteile gespeicherter Prozeduren  
 Gespeicherte Prozeduren bieten die folgenden Vorteile:  
  
-   Datenlogik und Geschäftsregeln können gekapselt werden, sodass die Benutzer so auf die Daten und Objekte zugreifen, wie das von den Entwicklern und Datenbankadministratoren beabsichtigt ist.  
  
-   Zur Abwehr von Angriffen durch Einschleusung von SQL-Befehlen (SQL Injection-Angriffe) können parametrisierte gespeicherte Prozeduren verwendet werden, die alle Benutzereingaben validieren. Bei Verwendung von dynamischem SQL sollten Sie Ihre Befehle unbedingt parametrisieren und auf keinen Fall Parameterwerte direkt in eine Abfragezeichenfolge aufnehmen.  
  
-   Es ist möglich, Ad-hoc-Abfragen und Datenänderungen nicht zuzulassen. So werden die Benutzer daran gehindert, vorsätzlich oder unbeabsichtigt Daten zu zerstören oder Abfragen auszuführen, die die Leistung auf dem Server oder im Netzwerk negativ beeinflussen.  
  
-   Fehler können in prozeduralem Code und ohne direkte Weitergabe an Clientanwendungen behandelt werden. So wird verhindert, dass Fehlermeldungen zurückgegeben werden, die von Angreifern ausgewertet werden könnten. Protokollieren Sie Fehler, und lassen Sie sie auf dem Server behandeln.  
  
-   Einmal geschriebene gespeicherte Prozeduren stehen für viele Anwendungen zur Verfügung.  
  
-   Clientanwendungen müssen nichts über die zugrunde liegenden Datenstrukturen wissen. Code in gespeicherten Prozeduren kann geändert werden, ohne dass Änderungen in den Clientanwendungen erforderlich sind, so lange die Änderungen sich nicht auf Parameterlisten oder zurückgegebene Datentypen auswirken.  
  
-   Gespeicherte Prozeduren können Netzwerkverkehr reduzieren, da sie in einem Prozeduraufruf mehrere Vorgänge kombinieren.  
  
## <a name="stored-procedure-execution"></a>Ausführung gespeicherter Prozeduren  
 Gespeicherte Prozeduren profitieren beim Datenzugriff von der Besitzverkettung, sodass die Benutzer keine explizite Zugriffsberechtigung für die Datenbankobjekte benötigen. Eine Besitzkette ist vorhanden, wenn Objekte, die sequenziell aufeinander zugreifen, demselben Benutzer gehören. So kann eine gespeicherte Prozedur z. B. andere gespeicherte Prozeduren aufrufen oder auf mehrere Tabellen zugreifen. Wenn alle Objekte in einer Ausführungskette demselben Besitzer gehören, prüft SQL Server nur die EXECUTE-Berechtigungen für den Aufrufer, nicht aber die Berechtigungen des Aufrufers für die anderen Objekte. Sie müssen daher bei gespeicherten Prozeduren nur die EXECUTE-Berechtigungen gewähren. Sämtliche Berechtigungen für die zugrunde liegenden Tabellen können Sie widerrufen oder verweigern.  
  
## <a name="best-practices"></a>Bewährte Methoden  
 Für eine hinreichende Absicherung Ihrer Anwendung reicht es nicht aus, einfach nur gespeicherte Prozeduren zu schreiben. Sie sollten darüber hinaus auch auf die folgenden potenziellen Sicherheitslücken eingehen.  
  
-   Erteilen Sie EXECUTE-Berechtigungen für die gespeicherten Prozeduren für die Datenbankrollen, die auf die Daten zugreifen können sollen.  
  
-   Widerrufen oder verweigern Sie alle Berechtigungen für die zugrunde liegenden Tabellen, und zwar für alle Rollen und Benutzer in der Datenbank, darunter auch für die `public`-Rolle. Alle Benutzer erben die Berechtigungen der <legacyBold>public</legacyBold>-Rolle. Wenn Sie also die Berechtigungen für `public` verweigern, erhalten nur die Besitzer und die `sysadmin`-Member Zugriff. Alle anderen Benutzer können aus ihrer Zugehörigkeit zu anderen Rollen keine Berechtigungen erben.  
  
-   Fügen Sie den Rollen `sysadmin` und `db_owner` keine Benutzer oder Rollen hinzu. Systemadministratoren und Datenbankbesitzer können auf alle Datenbankobjekte zugreifen.  
  
-   Deaktivieren Sie das `guest`-Konto. So wird verhindert, dass anonyme Benutzer eine Verbindung mit der Datenbank herstellen können. Das Gastkonto ist in neuen Datenbanken standardmäßig deaktiviert.  
  
-   Implementieren Sie Fehlerbehandlungsmechanismen, und protokollieren Sie Fehler.  
  
-   Erstellen Sie parametrisierte gespeicherte Prozeduren, die alle Benutzereingaben validieren. Behandeln Sie alle Benutzereingaben als nicht vertrauenswürdig.  
  
-   Verwenden Sie dynamisches SQL nur, wenn das unbedingt notwendig ist. Verwenden Sie die Transact-SQL-QUOTENAME()-Funktion, um Zeichenfolgenwerte zu begrenzen, und maskieren Sie sämtliche Vorkommen des Trennzeichens in der Eingabezeichenfolge.  
  
## <a name="external-resources"></a>Externe Ressourcen  
 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|--------------|-----------------|  
|[Gespeicherte Prozeduren](http://msdn.microsoft.com/library/ms190782.aspx) und [SQL Injection](http://go.microsoft.com/fwlink/?LinkId=98234) in SQL Server-Onlinedokumentation|In den Themen wird beschrieben, wie Sie gespeicherte Prozeduren erstellen und wie die Einschleusung von SQL-Befehlen bei SQL Injection-Angriffen funktioniert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Sichern von ADO.NET-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [Übersicht über die SQL Server-Sicherheit](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [Schreiben von sicherem dynamischen SQL in SQL Server](../../../../../docs/framework/data/adonet/sql/writing-secure-dynamic-sql-in-sql-server.md)  
 [Signieren von gespeicherten Prozeduren in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md)  
 [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md)  
 [Ändern von Daten mit gespeicherten Prozeduren](../../../../../docs/framework/data/adonet/modifying-data-with-stored-procedures.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](http://go.microsoft.com/fwlink/?LinkId=217917)
