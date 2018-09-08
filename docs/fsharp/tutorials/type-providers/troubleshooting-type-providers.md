---
title: Problembehandlung bei Typanbietern
description: Ermitteln Sie potenzielle Lösungen für Probleme, die Sie häufig auftreten, wenn Sie Typanbieter in f# verwenden.
ms.date: 05/16/2016
ms.openlocfilehash: f3b8ffdaf615563305b7b84b45a9ed1e066d0dcc
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44192924"
---
# <a name="troubleshooting-type-providers"></a>Problembehandlung bei Typanbietern

In diesem Thema wird beschrieben, sowie mögliche Lösungen für die Probleme, die Sie häufig auftreten, bei der Verwendung von typanbietern.

## <a name="possible-problems-with-type-providers"></a>Mögliche Probleme mit Typanbietern

Wenn ein Problem bei der Arbeit mit typanbietern auftreten, können Sie die folgende Tabelle enthält die gängigsten Lösungen überprüfen.

|Problem|Vorgeschlagene Aktionen|
|-------|-----------------|
|**Änderungen am Datenbankschema**. Geben Sie Anbieter-Arbeit am besten, wenn das Schema der Datenquellensicht stabil ist. Wenn Sie eine Datentabelle oder Spalten hinzufügen oder eine andere an diesem Schema Änderungen, erkennt der Typanbieter nicht automatisch diese Änderungen.|Bereinigen, oder das Projekt neu erstellen. Um das Projekt zu bereinigen, wählen Sie **erstellen**, **Bereinigen** *ProjectName* in der Menüleiste. Um das Projekt neu zu erstellen, wählen Sie **erstellen**, **Rebuild** *ProjectName* in der Menüleiste. Diese Aktionen alle Typ anbieterzustand zurückgesetzt werden, und erzwingen, dass den Anbieter mit der Datenquelle und Abrufen von Informationen von aktualisierten Schema.|
|**Verbindungsfehler**. Die URL oder der angegebenen Verbindungszeichenfolge ist falsch, das Netzwerk ist ausgefallen oder die Datenquelle oder den Dienst ist nicht verfügbar.|Für einen Webdienst oder eine OData-Dienst können Sie versuchen, die URL in Internet Explorer, um zu überprüfen, ob die URL korrekt ist und der Dienst verfügbar ist. Für eine Datenbank-Verbindungszeichenfolge, können Sie die Verbindung Datentools in **Server-Explorer** zu überprüfen, ob die Verbindungszeichenfolge gültig ist und die Datenbank verfügbar ist. Nachdem Sie die Verbindung wiederhergestellt haben, sollten dann bereinigen oder das Projekt neu erstellen, damit der Typanbieter neu verbunden wird, mit dem Netzwerk.|
|**Keine gültige Anmeldeinformationen**. Sie müssen gültige Berechtigungen für den Data Source "oder" Web Service verfügen.|Für eine SQL-Verbindung müssen den Benutzernamen und das Kennwort, die in der Verbindung Zeichenfolge oder der Konfigurationsdatei angegeben sind für die Datenbank gültig sein. Wenn Sie Windows-Authentifizierung verwenden, benötigen Sie Zugriff auf die Datenbank. Der Datenbankadministrator erkennen, welche Berechtigungen an, die, denen Sie für benötigen, jede Datenbank, und jedes Element in einer Datenbank zugreifen.<br /><br />Für einen Webdienst oder einem Datendienst müssen Sie die entsprechende Anmeldeinformationen verfügen. Die meisten Typanbieter bieten ein DataContext-Objekt, das Credentials-Eigenschaft enthält, die Sie mit den entsprechenden Benutzernamen und den Schlüssel für den Zugriff festlegen können.|
|**Ungültiger Pfad**. Ein Pfad zu einer Datei war ungültig.|Überprüfen Sie, ob der Pfad korrekt ist und die Datei vorhanden ist. Darüber hinaus müssen Sie entweder alle Backlashes im Pfad entsprechend Zitat oder eine wörtliche Zeichenfolge oder Zeichenfolge in dreifachen Anführungszeichen.|

## <a name="see-also"></a>Siehe auch

- [Typanbieter](index.md)
