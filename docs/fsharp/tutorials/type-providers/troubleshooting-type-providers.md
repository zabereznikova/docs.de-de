---
title: Problembehandlung bei Typanbietern
description: Ermitteln Sie potenzielle Lösungen für die Probleme, die am wahrscheinlichsten auftreten, wenn Sie in F#-Typanbieter verwenden.
ms.date: 05/16/2016
ms.openlocfilehash: 6dcae0e510d27fb0b07799b4edfe2d5bb9aeb2d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563518"
---
# <a name="troubleshooting-type-providers"></a>Problembehandlung bei Typanbietern

Dieses Thema beschreibt, sowie mögliche Lösungen für die Probleme, die am wahrscheinlichsten auftreten, wenn Sie Typanbieter verwenden.


## <a name="possible-problems-with-type-providers"></a>Mögliche Probleme mit Typanbietern
Wenn Sie ein Problem auftritt, wenn Sie mit typanbietern arbeiten, können Sie die folgende Tabelle werden die am häufigsten verwendeten Lösungen überprüfen.



|Problem|Empfohlene Aktionen|
|-------|-----------------|
|**Schemaänderungen**. Geben Sie Anbieter Arbeit am besten, wenn das Schema der Datenquellensicht stabil ist. Wenn Sie eine Datentabelle oder eine Spalte hinzufügen oder eine andere an diesem Schema Änderungen, erkannt nicht der Typanbieter diese Änderungen automatisch.|Bereinigen oder das Projekt neu. Um das Projekt zu bereinigen, wählen Sie **erstellen**, **Bereinigen** *Projektname* in der Menüleiste. Um das Projekt neu zu erstellen, wählen Sie **erstellen**, **Rebuild** *Projektname* in der Menüleiste. Diese Aktionen alle Typ anbieterzustand zurückgesetzt werden, und den Anbieter das erneute Verbinden mit der Datenquelle und Abrufen von aktualisierten Schemainformationen zu erzwingen.|
|**Verbindungsfehler**. Die Zeichenfolge URL oder die Verbindungszeichenfolge ist falsch, das Netzwerk ist ausgefallen oder die Datenquelle oder den Dienst ist nicht verfügbar.|Für einen Webdienst oder ein OData-Dienst können Sie versuchen, die URL in Internet Explorer zu überprüfen, ob die URL richtig ist und der Dienst verfügbar ist. Für eine Datenbank-Verbindungszeichenfolge können Sie die Verbindung Datentools in **Server-Explorer** zu überprüfen, ob die Verbindungszeichenfolge ungültig ist, und die Datenbank verfügbar ist. Nachdem Sie die Verbindung wiederhergestellt haben, sollten Sie dann bereinigen oder das Projekt neu erstellen, damit Sie der Typanbieter mit dem Netzwerk verbunden wird.|
|**Keine gültige Anmeldeinformationen**. Sie müssen gültige Berechtigungen für den Datendienst Quell- oder Web verfügen.|Für eine SQL-Verbindung müssen den Benutzernamen und das Kennwort, die in der Verbindung Zeichenfolge oder der Konfigurationsdatei angegeben sind für die Datenbank gültig sein. Wenn Sie Windows-Authentifizierung verwenden, benötigen Sie Zugriff auf die Datenbank. Der Datenbankadministrator erkennen, welche erforderlichen Berechtigungen für jede Datenbank und jedes Element innerhalb einer Datenbank zugreifen.<br /><br />Für einen Webdienst oder einen Datendienst müssen Sie die entsprechende Anmeldeinformationen verfügen. Die meisten Typanbieter bieten eine DataContext-Objekt, das eine Anmeldeinformationen-Eigenschaft enthält, die Sie mit dem entsprechenden Benutzernamen und den Zugriffsschlüssel festlegen können.|
|**Ungültiger Pfad**. Ein Pfad zu einer Datei war ungültig.|Überprüfen Sie, ob der Pfad richtig ist und die Datei vorhanden ist. Darüber hinaus müssen Sie entweder alle Backlashes im Pfad entsprechend Angebot oder eine wörtliche Zeichenfolge oder eine Zeichenfolge in dreifachen Anführungszeichen.|

## <a name="see-also"></a>Siehe auch
[Typanbieter](index.md)
