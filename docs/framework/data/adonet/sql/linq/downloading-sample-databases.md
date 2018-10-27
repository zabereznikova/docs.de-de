---
title: Rufen Sie die Beispieldatenbanken für ADO.NET-Codebeispiele
description: Laden Sie die Beispieldatenbanken, die in den Codebeispielen in der Dokumentation zu ADO.NET sowie SQL Server und Verwaltungstools verwendet
ms.date: 10/18/2018
ms.assetid: ef9d69a1-9461-43fe-94bb-7c836754bcb5
ms.openlocfilehash: 9779300288135cb9332a028d547ce55a07e89471
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188390"
---
# <a name="get-the-sample-databases-for-adonet-code-samples"></a>Rufen Sie die Beispieldatenbanken für ADO.NET-Codebeispiele

Eine Reihe von Beispielen und exemplarischen Vorgehensweisen in der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation zu verwenden, Beispieldatenbanken und SQL Server Express. Sie können diese Produkte kostenlos von Microsoft herunterladen.

## <a name="get-the-northwind-sample-database"></a>Abrufen der Northwind-Beispieldatenbank

Laden Sie die Beispieldatenbank Northwind aus der folgenden Seite im Microsoft Download Center herunter:

[Northwind und Pubs-Beispieldatenbanken](https://go.microsoft.com/fwlink?linkid=64296)

Nachdem die Datei heruntergeladen wurde, doppelklicken Sie auf die Datei, um die Datenbanken und die Skripts extrahieren. Standardmäßig werden die Dateien im Ordner installiert `<drive>:\SQL Server 2000 Sample Databases`.

Bevor Sie die Northwind-Datenbank verwenden können, Sie müssen die Datenbank auf einer Instanz von SQL Server mithilfe von neu erstellen [SQL Server Management Studio](#get_ssms) oder ein ähnliches Tool zum Ausführen der `instnwnd.sql` Skriptdatei im Installationsordner.

## <a name="get-the-adventureworks-sample-database"></a>Abrufen der AdventureWorks-Beispieldatenbank

Laden Sie die AdventureWorks-Beispieldatenbank aus den folgenden GitHub-Repository herunter:

[AdventureWorks-Beispieldatenbanken](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)

Nachdem Sie eine der Sicherungskopie der Datenbank herunterladen (\*. bak) Dateien wiederherstellen die Sicherung mit einer Instanz von SQL Server mithilfe von SQL Server Management Studio (SSMS). Finden Sie unter [erhalten SQL Server Management Studio](#get_ssms).

## <a name="get_sql"></a> Erwerben von SQLServer Express

SQL Server Express ist eine kostenlose, professionelles Edition von SQL Server, die Sie mit Anwendungen verteilen können. SQL Server Express auf der folgenden Seite herunterladen:
  
[SQL Server Express-Editionen](https://www.microsoft.com/sql-server/sql-server-editions-express)

Bei Verwendung von [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), SQL Server Express LocalDB ist in der kostenlosen communityedition als auch für die Editionen Professional und höheren enthalten.  

## <a name="get_ssms"></a> Abrufen von SQL Server Management Studio
Wenn Sie möchten anzeigen oder Ändern einer Datenbank, die Sie heruntergeladen haben, können Sie SQL Server Management Studio (SSMS). Herunterladen von SSMS auf der folgenden Seite:

[SQL Server Management Studio (SSMS) herunterladen](/sql/ssms/download-sql-server-management-studio-ssms) 

Sie können auch anzeigen und Verwalten von Datenbanken in der integrierten Entwicklungsumgebung (IDE) von Visual Studio. In [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017), Verbinden mit der Datenbank aus **Objekt-Explorer von SQL Server**, oder erstellen Sie eine Datenverbindung mit der Datenbank in **Server-Explorer**. Öffnen Sie diese Explorer-Bereiche aus der **Ansicht** Menü.
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)
