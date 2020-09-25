---
title: Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server
description: Erfahren Sie, wie Sie den Zugriff auf Ihre Daten und Datenbankobjekte einschränken, indem Sie den Zugriff mithilfe von gespeicherten Prozeduren oder benutzerdefinierten Funktionen implementieren.
ms.date: 03/30/2017
ms.assetid: 08fa34e8-2ffa-470d-ba62-e511a5f8558e
ms.openlocfilehash: 44f6a0c3ca6b913c8998c4e5ddb60eab2b64e71b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172722"
---
# <a name="managing-permissions-with-stored-procedures-in-sql-server"></a>Verwalten von Berechtigungen mit gespeicherten Prozeduren in SQL Server

Eine Möglichkeit, eine Bastion aus mehreren Verteidigungslinien um Ihre Datenbank aufzubauen, besteht darin, den Zugriff auf Daten so zu implementieren, dass er nur über gespeicherte Prozeduren oder benutzerdefinierten Funktionen läuft. Sie können alle Berechtigungen für die zugrunde liegenden Objekte, z. B. Tabellen, widerrufen oder verweigern, und Sie können EXECUTE-Berechtigungen für gespeicherte Prozeduren gewähren. Auf diese Weise wird um Ihre Daten und Datenbankobjekte herum ein wirksamer Sicherheitszaun aufgebaut.  
  
## <a name="stored-procedure-benefits"></a>Vorteile gespeicherter Prozeduren  

 Gespeicherte Prozeduren bieten die folgenden Vorteile:  
  
- Datenlogik und Geschäftsregeln können gekapselt werden, sodass die Benutzer so auf die Daten und Objekte zugreifen, wie das von den Entwicklern und Datenbankadministratoren beabsichtigt ist.  
  
- Zur Abwehr von Angriffen durch Einschleusung von SQL-Befehlen (SQL Injection-Angriffe) können parametrisierte gespeicherte Prozeduren verwendet werden, die alle Benutzereingaben validieren. Bei Verwendung von dynamischem SQL sollten Sie Ihre Befehle unbedingt parametrisieren und auf keinen Fall Parameterwerte direkt in eine Abfragezeichenfolge aufnehmen.  
  
- Es ist möglich, Ad-hoc-Abfragen und Datenänderungen nicht zuzulassen. So werden die Benutzer daran gehindert, vorsätzlich oder unbeabsichtigt Daten zu zerstören oder Abfragen auszuführen, die die Leistung auf dem Server oder im Netzwerk negativ beeinflussen.  
  
- Fehler können in prozeduralem Code und ohne direkte Weitergabe an Clientanwendungen behandelt werden. So wird verhindert, dass Fehlermeldungen zurückgegeben werden, die von Angreifern ausgewertet werden könnten. Protokollieren Sie Fehler, und lassen Sie sie auf dem Server behandeln.  
  
- Einmal geschriebene gespeicherte Prozeduren stehen für viele Anwendungen zur Verfügung.  
  
- Clientanwendungen müssen nichts über die zugrunde liegenden Datenstrukturen wissen. Code in gespeicherten Prozeduren kann geändert werden, ohne dass Änderungen in den Clientanwendungen erforderlich sind, so lange die Änderungen sich nicht auf Parameterlisten oder zurückgegebene Datentypen auswirken.  
  
- Gespeicherte Prozeduren können Netzwerkverkehr reduzieren, da sie in einem Prozeduraufruf mehrere Vorgänge kombinieren.  
  
## <a name="stored-procedure-execution"></a>Ausführung gespeicherter Prozeduren  

 Gespeicherte Prozeduren profitieren beim Datenzugriff von der Besitzverkettung, sodass die Benutzer keine explizite Zugriffsberechtigung für die Datenbankobjekte benötigen. Eine Besitzkette ist vorhanden, wenn Objekte, die sequenziell aufeinander zugreifen, demselben Benutzer gehören. So kann eine gespeicherte Prozedur z. B. andere gespeicherte Prozeduren aufrufen oder auf mehrere Tabellen zugreifen. Wenn alle Objekte in einer Ausführungskette demselben Besitzer gehören, prüft SQL Server nur die EXECUTE-Berechtigungen für den Aufrufer, nicht aber die Berechtigungen des Aufrufers für die anderen Objekte. Sie müssen daher bei gespeicherten Prozeduren nur die EXECUTE-Berechtigungen gewähren. Sämtliche Berechtigungen für die zugrunde liegenden Tabellen können Sie widerrufen oder verweigern.  
  
## <a name="best-practices"></a>Bewährte Methoden  

 Für eine hinreichende Absicherung Ihrer Anwendung reicht es nicht aus, einfach nur gespeicherte Prozeduren zu schreiben. Sie sollten darüber hinaus auch auf die folgenden potenziellen Sicherheitslücken eingehen.  
  
- Erteilen Sie EXECUTE-Berechtigungen für die gespeicherten Prozeduren für die Datenbankrollen, die auf die Daten zugreifen können sollen.  
  
- Widerrufen oder verweigern Sie alle Berechtigungen für die zugrunde liegenden Tabellen, und zwar für alle Rollen und Benutzer in der Datenbank, darunter auch für die `public`-Rolle. Alle Benutzer erben die Berechtigungen der public-Rolle. Wenn Sie also die Berechtigungen für `public` verweigern, erhalten nur die Besitzer und die `sysadmin`-Member Zugriff. Alle anderen Benutzer können aus ihrer Zugehörigkeit zu anderen Rollen keine Berechtigungen erben.  
  
- Fügen Sie den Rollen `sysadmin` und `db_owner` keine Benutzer oder Rollen hinzu. Systemadministratoren und Datenbankbesitzer können auf alle Datenbankobjekte zugreifen.  
  
- Deaktivieren Sie das `guest`-Konto. So wird verhindert, dass anonyme Benutzer eine Verbindung mit der Datenbank herstellen können. Das Gastkonto ist in neuen Datenbanken standardmäßig deaktiviert.  
  
- Implementieren Sie Fehlerbehandlungsmechanismen, und protokollieren Sie Fehler.  
  
- Erstellen Sie parametrisierte gespeicherte Prozeduren, die alle Benutzereingaben validieren. Behandeln Sie alle Benutzereingaben als nicht vertrauenswürdig.  
  
- Verwenden Sie dynamisches SQL nur, wenn das unbedingt notwendig ist. Verwenden Sie die Transact-SQL-QUOTENAME()-Funktion, um Zeichenfolgenwerte zu begrenzen, und maskieren Sie sämtliche Vorkommen des Trennzeichens in der Eingabezeichenfolge.  
  
## <a name="external-resources"></a>Externe Ressourcen  

 Weitere Informationen finden Sie in den folgenden Ressourcen.  
  
|Resource|Beschreibung|  
|--------------|-----------------|  
|[Gespeicherte Prozeduren](/sql/relational-databases/stored-procedures/stored-procedures-database-engine) und [SQL Injection](/sql/relational-databases/security/sql-injection)|In den Artikeln wird beschrieben, wie gespeicherte Prozeduren erstellt werden und wie SQL Injection funktioniert.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Sichern von ADO.NET-Anwendungen](../securing-ado-net-applications.md)
- [Übersicht über die SQL Server-Sicherheit](overview-of-sql-server-security.md)
- [Anwendungssicherheitsszenarios in SQL Server](application-security-scenarios-in-sql-server.md)
- [Schreiben von sicherem dynamischem SQL in SQL Server](writing-secure-dynamic-sql-in-sql-server.md)
- [Signieren von gespeicherten Prozeduren in SQL Server](signing-stored-procedures-in-sql-server.md)
- [Anpassen von Berechtigungen durch Identitätswechsel in SQL Server](customizing-permissions-with-impersonation-in-sql-server.md)
- [Ändern von Daten mit gespeicherten Prozeduren](../modifying-data-with-stored-procedures.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
