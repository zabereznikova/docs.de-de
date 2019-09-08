---
title: Verwenden von Befehlen zum Ändern von Daten
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: 34c73549f18cd4bebb8caf842b252828b7f0a185
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780558"
---
# <a name="using-commands-to-modify-data"></a>Verwenden von Befehlen zum Ändern von Daten
Mit einem .NET Framework-Datenanbieter können gespeicherte Prozeduren oder Datendefinitionssprachen-Anweisungen (z. B. CREATE TABLE und ALTER COLUMN) ausgeführt werden, um eine Schemabearbeitung an einer Datenbank oder einem Katalog vorzunehmen. Diese Befehle geben keine Zeilen als Abfrage zurück, sodass das **Command** -Objekt eine **ExecuteNonQuery** zur Verarbeitung bereitstellt.  
  
 Zusätzlich zur Verwendung von **ExecuteNonQuery** zum Ändern des Schemas können Sie diese Methode auch verwenden, um SQL-Anweisungen zu verarbeiten, die Daten ändern, aber keine Zeilen zurückgeben, wie z. b. Insert, Update und DELETE.  
  
 Obwohl Zeilen von der **ExecuteNonQuery** -Methode nicht zurückgegeben werden, können Eingabe-und Ausgabeparameter und Rückgabewerte über die **Parameters** -Auflistung des **Command** -Objekts übermittelt und zurückgegeben werden.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Aktualisieren von Daten in einer Datenquelle](updating-data-in-a-data-source.md)  
 Beschreibt das Ausführen von Befehlen oder gespeicherten Prozeduren, mit denen Daten in einer Datenbank geändert werden.  
  
 [Ausführen von Katalogoperationen](performing-catalog-operations.md)  
 Beschreibt das Ausführen von Befehlen, mit denen ein Datenbankschema geändert wird.  
  
## <a name="see-also"></a>Siehe auch

- [Abrufen und Ändern von Daten in ADO.NET](retrieving-and-modifying-data.md)
- [Befehle und Parameter](commands-and-parameters.md)
- [Übersicht über ADO.NET](ado-net-overview.md)
