---
title: Abrufen der SQL Server-Beispieldatenbanken für ADO.NET Codebeispiele
description: Laden Sie die SQL Server-Beispieldatenbanken herunter, die in den Codebeispielen in der ADO.NET-Dokumentation sowie sql Server- und Verwaltungstools verwendet werden.
ms.date: 01/11/2019
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 19d659cbe8f39d27b71dc59c738355f12fce92a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148386"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Abrufen der Beispieldatenbanken für ADO.NET Codebeispiele

Eine Reihe von Beispielen und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] exemplarischen Vorgehensweisen in der Dokumentation verwenden Beispielsql Server-Datenbanken und SQL Server Express. Sie können diese Produkte kostenlos von Microsoft herunterladen.

## <a name="get-the-northwind-sample-database-for-sql-server"></a>Abrufen der Northwind-Beispieldatenbank für SQL Server

Laden Sie `instnwnd.sql` das Skript aus dem folgenden GitHub-Repository herunter, um die Northwind-Beispieldatenbank für SQL Server zu erstellen und zu laden:

[Northwind- und Pubs-Beispieldatenbanken für Microsoft SQL Server](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs)

Bevor Sie die Northwind-Datenbank verwenden können, `instnwnd.sql` müssen Sie die heruntergeladene Skriptdatei ausführen, um die Datenbank auf einer Instanz von SQL Server mithilfe von [SQL Server Management Studio](#get_ssms) oder einem ähnlichen Tool neu zu erstellen. Folgen Sie den Anweisungen in der Readme-Datei im Repository.

> [!TIP]
> Informationen zur Northwind-Datenbank für Microsoft Access finden Sie unter [Installieren der Northwind-Beispieldatenbank für Microsoft Access](#northwind_access).

## <a name="get-the-northwind-sample-database-for-microsoft-access"></a><a name="northwind_access"></a>Abrufen der Northwind-Beispieldatenbank für Microsoft Access

Die Northwind-Beispieldatenbank für Microsoft Access ist im Microsoft Download Center nicht verfügbar. Gehen Sie folgendzulande vor, um Northwind direkt in Access zu installieren:

1. Open Access.

1. Geben Sie **Northwind** in das Feld **Suchen nach Onlinevorlagen** ein, und wählen Sie dann **Eingeben**aus.

1. Wählen Sie auf dem Ergebnisbildschirm **Northwind**aus. Ein neues Fenster wird mit einer Beschreibung der Northwind-Datenbank geöffnet.

1. Geben Sie im neuen Fenster im Textfeld **Dateiname** einen Dateinamen für Ihre Kopie der Northwind-Datenbank an.

1. Wählen Sie **Erstellen** aus. Access lädt die Northwind-Datenbank herunter und bereitet die Datei vor.

1. Wenn dieser Vorgang abgeschlossen ist, wird die Datenbank mit einem Begrüßungsbildschirm geöffnet.

## <a name="get-the-adventureworks-sample-database-for-sql-server"></a>Abrufen der AdventureWorks-Beispieldatenbank für SQL Server

Laden Sie die AdventureWorks-Beispieldatenbank für SQL Server aus dem folgenden GitHub-Repository herunter:

[AdventureWorks-Beispieldatenbanken](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Nachdem Sie eine der Datenbanksicherungsdateien (.bak)\*heruntergeladen haben, stellen Sie die Sicherung mithilfe von SQL Server Management Studio (SSMS) auf einer Instanz von SQL Server wieder her. Weitere Informationen finden Sie unter Abrufen von [SQL Server Management Studio](#get_ssms).

## <a name="get-sql-server-management-studio"></a><a name="get_ssms"></a>SQL Server Management Studio abrufen
Wenn Sie eine heruntergeladene Datenbank anzeigen oder ändern möchten, können Sie SQL Server Management Studio (SSMS) verwenden. Laden Sie SSMS von der folgenden Seite herunter:

[Herunterladen von SQL Server Management Studio (SSMS)](/sql/ssms/download-sql-server-management-studio-ssms)

Sie können Datenbanken auch in der integrierten Visual Studio-Entwicklungsumgebung (IDE) anzeigen und verwalten. Stellen Sie in [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)eine Verbindung mit der Datenbank über den **SQL Server-Objekt-Explorer**her, oder erstellen Sie eine Datenverbindung zur Datenbank im **Server-Explorer**. Öffnen Sie diese Explorer-Bereiche im Menü **Ansicht.**

## <a name="get-sql-server-express"></a><a name="get_sql"></a>SQL Server Express abrufen

SQL Server Express ist eine kostenlose Einstiegsedition von SQL Server, die Sie mit Anwendungen weiterverteilen können. Laden Sie SQL Server Express von der folgenden Seite herunter:
  
[SQL Server Express Edition](https://www.microsoft.com/sql-server/sql-server-editions-express)

Wenn Sie [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)verwenden, ist SQL Server Express LocalDB in der kostenlosen Community-Edition von Visual Studio sowie in den Professional- und höheren Editionen enthalten.  

## <a name="see-also"></a>Weitere Informationen

- [Erste Schritte](getting-started.md)
