---
title: Holen Sie sich die Beispiel SQL Server Datenbanken für ADO.NET-Codebeispiele.
description: Herunterladen der Beispiel SQL Server-Datenbanken, die in den Codebeispielen in der ADO.NET-Dokumentation verwendet werden, sowie SQL Server und Verwaltungs Tools
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: f7c0d1eb0089a6bfabc92e1deecf563c3e59cc6a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156055"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Holen Sie sich die Beispiel Datenbanken für ADO.NET-Codebeispiele.

In einer Reihe von Beispielen und exemplarischen Vorgehensweisen in der- [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation werden Beispiel SQL Server Datenbanken und SQL Server Express verwendet. Sie können diese Produkte kostenlos von Microsoft herunterladen.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Holen Sie sich die Beispieldatenbank Northwind für SQL Server

Laden Sie das Skript `instnwnd.sql` aus dem folgenden GitHub-Repository herunter, um die Beispieldatenbank Northwind für SQL Server zu erstellen und zu laden:

[Beispiel Datenbanken Northwind und Pubs für Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Bevor Sie die Northwind-Datenbank verwenden können, müssen Sie die heruntergeladene `instnwnd.sql` Skriptdatei ausführen, um die Datenbank auf einer Instanz von SQL Server mit [SQL Server Management Studio](#get_ssms) oder einem ähnlichen Tool neu zu erstellen. Befolgen Sie die Anweisungen in der Infodatei im Repository.

> [!TIP]
> Wenn Sie die Northwind-Datenbank für Microsoft Access suchen, finden Sie weitere Informationen unter [Installieren der Beispieldatenbank Northwind für Microsoft Access](#northwind_access).

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a> Abrufen der Beispieldatenbank Northwind für Microsoft Access

Die Beispieldatenbank Northwind für Microsoft Access ist im Microsoft Download Center nicht verfügbar. Gehen Sie folgendermaßen vor, um Northwind direkt innerhalb des Zugriffs zu installieren:

1. Öffnen Sie den Zugriff.

1. Geben Sie **Northwind** in das Feld **nach Online Vorlagen suchen** ein, und **drücken**Sie dann die EINGABETASTE.

1. Wählen Sie auf dem Bildschirm Ergebnisse die Option **Northwind**aus. Ein neues Fenster mit einer Beschreibung der Northwind-Datenbank wird geöffnet.

1. Geben Sie im neuen Fenster im Textfeld **Dateiname** einen Dateinamen für die Kopie der Northwind-Datenbank an.

1. Klicken Sie auf **Erstellen**. Access lädt die Northwind-Datenbank herunter und bereitet die Datei vor.

1. Wenn dieser Vorgang vollständig ist, wird die Datenbank mit einem Willkommensbildschirm geöffnet.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Holen Sie sich die AdventureWorks-Beispieldatenbank für SQL Server

Laden Sie die AdventureWorks-Beispieldatenbank für SQL Server aus dem folgenden GitHub-Repository herunter:

[AdventureWorks-Beispieldatenbanken](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Nachdem Sie eine der Daten Bank Sicherungsdateien ( \* BAK-Dateien) heruntergeladen haben, stellen Sie die Sicherung in einer Instanz von SQL Server mithilfe von SQL Server Management Studio (SSMS) wieder her. Siehe [Get SQL Server Management Studio](#get_ssms).

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a> Get-SQL Server Management Studio

Wenn Sie eine Datenbank anzeigen oder ändern möchten, die Sie heruntergeladen haben, können Sie SQL Server Management Studio (SSMS) verwenden. Laden Sie SSMS von der folgenden Seite herunter:

[Herunterladen von SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)

Sie können auch Datenbanken in der integrierten Entwicklungsumgebung (IDE) von Visual Studio anzeigen und verwalten. Stellen Sie in [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)von **SQL Server-Objekt-Explorer**aus eine Verbindung mit der-Datenbank her, oder erstellen Sie eine Datenverbindung mit der-Datenbank in **Server-Explorer**. Öffnen Sie diese Explorer-Bereiche über das Menü **Ansicht** .

## <a name="get-sql-server-express"></a><a name="get_sql"></a> Get-SQL Server Express

SQL Server Express ist eine kostenlose Edition von SQL Server auf Einstiegsebene, die Sie mit Anwendungen neu verteilen können. Laden Sie SQL Server Express von der folgenden Seite herunter:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Wenn Sie [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)verwenden, ist SQL Server Express localdb in der kostenlosen Community Edition von Visual Studio sowie in den Editionen Professional und höher enthalten.  

## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte](getting-started.md)
