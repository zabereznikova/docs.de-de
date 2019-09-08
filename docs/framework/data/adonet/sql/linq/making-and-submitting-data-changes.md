---
title: Vornehmen und Übergeben von Datenänderungen
ms.date: 03/30/2017
ms.assetid: d68c2dc3-99b3-49ab-b547-2ca5b386429a
ms.openlocfilehash: 18468c9a2018a28e85d87155d98b0853854013fd
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792964"
---
# <a name="making-and-submitting-data-changes"></a>Vornehmen und Übergeben von Datenänderungen

Die Themen in diesem Abschnitt erläutern das Vornehmen und Übergeben von Änderungen an die Datenbank sowie den Umgang mit Konflikten bei der vollständigen Parallelität.

> [!NOTE]
> Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update-und DELETE-Vorgängen](customizing-insert-update-and-delete-operations.md).
>
> Entwickler, die Visual Studio verwenden, können den objektrelationaler Designer verwenden, um gespeicherte Prozeduren für denselben Zweck zu entwickeln.

## <a name="in-this-section"></a>In diesem Abschnitt

[Vorgehensweise: Einfügen von Zeilen in die Datenbank](how-to-insert-rows-into-the-database.md) \
Erläutert das Einfügen von Zeilen in die Datenbank durch Hinzufügen von Objekten in das Objektmodell.

[Vorgehensweise: Aktualisieren von Zeilen in der Datenbank](how-to-update-rows-in-the-database.md) \
Erläutert das Aktualisieren von Zeilen in der Datenbank durch Aktualisieren von Objekten im Objektmodell.

[Vorgehensweise: Zeilen aus der Datenbank löschen](how-to-delete-rows-from-the-database.md) \
Erläutert das Löschen von Zeilen in der Datenbank durch Löschen von Objekten aus dem Objektmodell.

[Vorgehensweise: Übermitteln von Änderungen an die Datenbank](how-to-submit-changes-to-the-database.md) \
Beschreibt das Übergeben von Objektmodelländerungen an die Datenbank.

[Vorgehensweise: Übermittlungen von Daten mithilfe von Transaktionen](how-to-bracket-data-submissions-by-using-transactions.md) \
Beschreibt das Einschließen von Operationen in eine Transaktion.

[Vorgehensweise: Dynamisches Erstellen einer Datenbank](how-to-dynamically-create-a-database.md) \
Beschreibt das dynamische Erzeugen von Datenbanken und typische Szenarien für diesen Ansatz.

[Vorgehensweise: Verwalten von Änderungs Konflikten](how-to-manage-change-conflicts.md) \
Beschreibt Techniken für den Umgang mit Problemen mit der vollständigen Parallelität.
