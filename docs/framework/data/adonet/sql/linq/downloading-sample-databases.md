---
title: Rufen Sie die SQL Server-Beispieldatenbanken für ADO.NET-Codebeispiele
description: Laden Sie die SQL Server-Beispieldatenbanken, die in den Codebeispielen in der Dokumentation zu ADO.NET sowie SQL Server und Verwaltungstools verwendet
ms.date: 10/18/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 8ab65f992c9cf2b65271a237fa06eb96e358ae6a
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153487"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Rufen Sie die Beispieldatenbanken für ADO.NET-Codebeispiele

Eine Reihe von Beispielen und exemplarischen Vorgehensweisen in der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation Beispieldatenbanken für SQL Server und SQL Server Express zu verwenden. Sie können diese Produkte kostenlos von Microsoft herunterladen.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Abrufen der Northwind-Beispieldatenbank für SQL Server

Das Skript herunterladen `instnwnd.sql` aus den folgenden GitHub-Repository zum Erstellen und laden die Beispieldatenbank Northwind für SQL Server:

[Northwind und Pubs-Beispieldatenbanken für Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Bevor Sie die Northwind-Datenbank verwenden können, müssen Sie führen Sie die heruntergeladene `instnwnd.sql` Skriptdatei, mit die Datenbank auf einer Instanz von SQL Server neu zu erstellen [SQL Server Management Studio](#get_ssms) oder ein ähnliches Tool. Folgen Sie den Anweisungen der Readme-Datei im Repository aus.

> [!TIP]
> Wenn Sie für die Datenbank Northwind für Microsoft Access suchen, finden Sie unter [installieren die Beispieldatenbank Northwind für Microsoft Access](#northwind_access).

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Abrufen der AdventureWorks-Beispieldatenbank für SQL Server

Laden Sie die AdventureWorks-Beispieldatenbank für SQL Server aus dem folgenden GitHub-Repository herunter:

[AdventureWorks-Beispieldatenbanken](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Nachdem Sie eine der Sicherungskopie der Datenbank herunterladen (\*. bak) Dateien wiederherstellen die Sicherung mit einer Instanz von SQL Server mithilfe von SQL Server Management Studio (SSMS). Finden Sie unter [erhalten SQL Server Management Studio](#get_ssms).

## <a name="get_sql"></a> Erwerben von SQLServer Express

SQL Server Express ist eine kostenlose, professionelles Edition von SQL Server, die Sie mit Anwendungen verteilen können. SQL Server Express auf der folgenden Seite herunterladen:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Bei Verwendung von [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB ist in der kostenlosen communityedition von Visual Studio als auch die Editionen Professional und höheren enthalten.  

## <a name="get_ssms"></a> Abrufen von SQL Server Management Studio
Wenn Sie möchten anzeigen oder Ändern einer Datenbank, die Sie heruntergeladen haben, können Sie SQL Server Management Studio (SSMS). Herunterladen von SSMS auf der folgenden Seite:

[SQL Server Management Studio (SSMS) herunterladen](/sql/ssms/download-sql-server-management-studio-ssms) 

Sie können auch anzeigen und Verwalten von Datenbanken in der integrierten Entwicklungsumgebung (IDE) von Visual Studio. In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), Verbinden mit der Datenbank aus **Objekt-Explorer von SQL Server**, oder erstellen Sie eine Datenverbindung mit der Datenbank in **Server-Explorer**. Öffnen Sie diese Explorer-Bereiche aus der **Ansicht** Menü.

## <a name="northwind_access"></a> Installieren der Beispieldatenbank Northwind für Microsoft Access

Die Northwind-Beispieldatenbank für Microsoft Access ist nicht im Microsoft Download Center verfügbar. Um Northwind direkt von innerhalb von Access zu installieren, gehen Sie folgendermaßen vor:

1. Öffnen Sie den Zugriff.

1. Geben Sie **Northwind** in die **Onlinevorlagen suchen** Feld, und wählen Sie dann **EINGABETASTE**.

1. Wählen Sie auf dem Bildschirm "Ergebnisse" **Northwind**. Es wird ein neues Fenster mit einer Beschreibung der Northwind-Datenbank.

1. Im neuen Fenster in der **Dateiname** Text geben einen Dateinamen für Ihre Kopie der Northwind-Datenbank.

1. Wählen Sie **Erstellen** aus. Der Zugriff die Northwind-Datenbank-downloads und bereitet Sie vor.

1. Wenn dieser Prozess abgeschlossen ist, öffnet sich die Datenbank mit der eine Willkommensseite angezeigt.

## <a name="see-also"></a>Siehe auch

- [Erste Schritte](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
